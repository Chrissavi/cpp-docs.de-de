---
title: OMP_NUM_THREADS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_NUM_THREADS
dev_langs:
- C++
helpviewer_keywords:
- OMP_NUM_THREADS OpenMP environment variable
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e25369f18f542198638e324110ba14d10b8ddc69
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691767"
---
# <a name="ompnumthreads"></a>OMP_NUM_THREADS
Legt die maximale Anzahl von Threads in den parallelen Bereich, es sei denn, durch Überschreiben [Omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) oder [Num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `num`  
 Die maximale Anzahl von Threads ab, die in den parallelen Bereich, bis zu 64 in der Visual C++-Implementierung werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Die **OMP_NUM_THREADS** -Umgebungsvariable kann überschrieben werden, indem die [Omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) Funktion oder durch [Num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
 Der Standardwert von `num` in der Visual C++-Implementierung des OpenMP-Standards ist die Anzahl virtueller Prozessoren, einschließlich der Hyperthreading-CPUs.  
  
 Weitere Informationen finden Sie unter [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl legt die **OMP_NUM_THREADS** -Umgebungsvariable um 16:  
  
```  
set OMP_NUM_THREADS=16  
```  
  
 Der folgende Befehl zeigt die aktuelle Einstellung der **OMP_NUM_THREADS** -Umgebungsvariablen angegeben:  
  
```  
set OMP_NUM_THREADS  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Umgebungsvariablen](../../../parallel/openmp/reference/openmp-environment-variables.md)