---
title: A.25 Beispiele für die Copyprivate-Klausel Data-Attribut | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7b1cb6a5-5691-4b95-b3ac-d7543ede6405
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c92d9ce6f22c2d53a2e65d7b67c22e4f080f162c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691689"
---
# <a name="a25---examples-of-the-copyprivate-data-attribute-clause"></a>A.25   Beispiele der copyprivate-Datenattributklausel
**Beispiel 1:** der `copyprivate` -Klausel ([Abschnitt 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) auf der Seite "32") kann verwendet werden, um Werte über einen einzelnen Thread direkt für alle Instanzen der in anderen Threads privaten Variablen abgerufen.  
  
```  
float x, y;  
#pragma omp threadprivate(x, y)  
  
void init( )   
{  
    float a;  
    float b;  
  
    #pragma omp single copyprivate(a,b,x,y)  
    {  
        get_values(a,b,x,y);  
    }  
  
    use_values(a, b, x, y);  
}  
```  
  
 Wenn Sie routinemäßige *Init* wird aufgerufen, aus einer seriellen Region wird das Verhalten nicht durch das Vorhandensein der Direktiven für die beeinflusst. Nach dem Aufruf der *Get_values* Routine wurde von einem Thread ausgeführt, der kein Thread das Konstrukt verlässt, bis die privaten Objekte, die vom angegebenen *eine*, *b*, *x*, und *y* in allen Threads haben mit den Werten lesen definiert werden.  
  
 **Beispiel 2:** im Gegensatz zum vorherigen Beispiel nehmen Sie an der Lesevorgang muss von einem bestimmten Thread, z. B. das master-Thread ausgeführt werden. In diesem Fall die `copyprivate` Klausel kann nicht verwendet werden, um die Übertragung direkt zu tun, aber es kann für den Zugriff auf ein freigegebenes temporäre Objekt verwendet werden.  
  
```  
float read_next( )   
{  
    float * tmp;  
    float return_val;  
  
    #pragma omp single copyprivate(tmp)  
    {  
        tmp = (float *) malloc(sizeof(float));  
    }  
  
    #pragma omp master  
    {  
        get_float( tmp );  
    }  
  
    #pragma omp barrier  
    return_val = *tmp;  
    #pragma omp barrier  
  
    #pragma omp single  
    {  
       free(tmp);  
    }  
  
    return return_val;  
}  
```  
  
 **Beispiel 3:** nehmen wir an, dass die Anzahl der Sperrobjekte, die erforderlich sind, innerhalb eines parallelen Bereichs problemlos bestimmt werden kann, bevor sie die Eingabe. Die `copyprivate` -Klausel kann verwendet werden, um den Zugriff auf freigegebene Sperrobjekte bereitzustellen, die innerhalb dieser parallelen Bereichs zugeordnet werden.  
  
```  
#include <omp.h>  
  
omp_lock_t *new_lock()  
{  
    omp_lock_t *lock_ptr;  
  
    #pragma omp single copyprivate(lock_ptr)  
    {  
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));  
        omp_init_lock( lock_ptr );  
    }  
  
    return lock_ptr;  
}  
```