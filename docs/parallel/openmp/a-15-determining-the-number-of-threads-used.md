---
title: Bestimmen der Anzahl der verwendeten Threads A.15 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b50858a3384fa5f8d867f13a699e1fc271c101ef
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686385"
---
# <a name="a15---determining-the-number-of-threads-used"></a>A.15   Ermitteln der Anzahl von verwendeten Threads
Betrachten Sie das folgende Beispiel falsche (für [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37):  
  
```  
np = omp_get_num_threads(); // misplaced   
#pragma omp parallel for schedule(static)  
    for (i=0; i<np; i++)  
        work(i);  
```  
  
 Die `omp_get_num_threads()` Aufrufen gibt 1 zurück in den seriellen Abschnitt des Codes, daher *Np* wird immer im vorherigen Beispiel gleich 1 sein. Um die Anzahl der Threads zu bestimmen, die für den parallelen Bereich bereitgestellt wird, sollte der Aufruf innerhalb des parallelen Bereichs.  
  
 Das folgende Beispiel zeigt, wie Sie dieses Programm zu schreiben, ohne eine Abfrage für die Anzahl der Threads:  
  
```  
#pragma omp parallel private(i)  
{  
    i = omp_get_thread_num();  
    work(i);  
}  
```