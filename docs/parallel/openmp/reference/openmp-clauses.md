---
title: OpenMP-Klauseln | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7abe5a637a2a32c696f19f5ab9988f1be361f647
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692837"
---
# <a name="openmp-clauses"></a>OpenMP-Klauseln
Enthält Links zu Klauseln in der OpenMP-API verwendet.  
  
 Visual C++ unterstützt die folgenden OpenMP-Klauseln:  
  
|Klausel|Beschreibung|  
|------------|-----------------|  
|[copyin](../../../parallel/openmp/reference/copyin.md)|Können Threads für die master-Thread-Wert, den Zugriff auf eine [Threadprivate](../../../parallel/openmp/reference/threadprivate.md) Variable.|  
|[copyprivate](../../../parallel/openmp/reference/copyprivate.md)|Gibt an, dass eine oder mehrere Variablen auf allen Threads freigegeben werden soll.|  
|[default](../../../parallel/openmp/reference/default-openmp.md)|Gibt das Verhalten des ohne bereichseinschränkung Variablen in einem parallelen Bereich an.|  
|[firstprivate](../../../parallel/openmp/reference/firstprivate.md)|Gibt an, dass jeder Thread eine eigene Instanz einer Variablen zugewiesen werden soll, und die Variable mit dem Wert der Variablen, initialisiert werden soll, da sie bevor Sie das parallele Konstrukt vorhanden ist.|  
|[if](../../../parallel/openmp/reference/if-openmp.md)|Gibt an, ob eine Schleife parallel oder seriell ausgeführt werden soll.|  
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|Gibt an, dass der umschließenden Kontext Version der Variablen festgelegt, wird die private Version der Thread ausgeführt, der letzten Iteration (for-Schleife-Konstrukt) oder der letzte Abschnitt (#pragma Abschnitte wird) gleich.|  
|[nowait](../../../parallel/openmp/reference/nowait.md)|Überschreibt die Grenze, die in einer Anweisung implizit.|  
|[num_threads](../../../parallel/openmp/reference/num-threads.md)|Legt die Anzahl der Threads in einem Team Thread fest.|  
|[sortiert](../../../parallel/openmp/reference/ordered-openmp-clauses.md)|Erforderlich für eine parallele [für](../../../parallel/openmp/reference/for-openmp.md) Anweisung Wenn ein [sortiert](../../../parallel/openmp/reference/ordered-openmp-directives.md) Richtlinie ist in der Schleife verwendet werden.|  
|[private](../../../parallel/openmp/reference/private-openmp.md)|Gibt an, dass jeder Thread eine eigene Instanz einer Variablen zugewiesen werden soll.|  
|[reduction](../../../parallel/openmp/reference/reduction.md)|Gibt an, dass eine oder mehrere Variablen, die für jeden Thread privat sind am Ende des parallelen Bereichs ein Reduzierungsvorgang werden.|  
|[schedule](../../../parallel/openmp/reference/schedule.md)|Gilt für die [für](../../../parallel/openmp/reference/for-openmp.md) Richtlinie.|  
|[Freigegebene](../../../parallel/openmp/reference/shared-openmp.md)|Gibt an, dass eine oder mehrere Variablen auf allen Threads freigegeben werden soll.|  
  
## <a name="see-also"></a>Siehe auch  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Anweisungen](../../../parallel/openmp/reference/openmp-directives.md)