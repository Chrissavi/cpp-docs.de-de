---
title: Atomic | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- atomic
dev_langs:
- C++
helpviewer_keywords:
- atomic OpenMP directive
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c845f6147280e7248db7899a182eed8d71fc34f5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442694"
---
# <a name="atomic"></a>atomisch

Gibt an, dass eine Speicheradresse, die automatisch aktualisiert werden.

## <a name="syntax"></a>Syntax

```
#pragma omp atomic
   expression
```

#### <a name="parameters"></a>Parameter

*Ausdruck*<br/>
Die Anweisung, enthält die l-Wert, dessen Speicherort, die Sie für mehrere Schreibvorgänge schützen möchten. Weitere Informationen zu rechtlichen Ausdruck Formen finden Sie in der OpenMP-Spezifikation.

## <a name="remarks"></a>Hinweise

Die `atomic` -Anweisung unterstützt keine OpenMP-Klauseln.

Weitere Informationen finden Sie unter [2.6.4 atomic erstellen](../../../parallel/openmp/2-6-4-atomic-construct.md).

## <a name="example"></a>Beispiel

```
// omp_atomic.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define MAX 10

int main() {
   int count = 0;
   #pragma omp parallel num_threads(MAX)
   {
      #pragma omp atomic
      count++;
   }
   printf_s("Number of threads: %d\n", count);
}
```

```Output
Number of threads: 10
```

## <a name="see-also"></a>Siehe auch

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)