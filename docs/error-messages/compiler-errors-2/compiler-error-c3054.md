---
title: Compilerfehler C3054 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3054
dev_langs:
- C++
helpviewer_keywords:
- C3054
ms.assetid: 6f4b7ac5-0d12-474b-b611-76ff26ee41ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13a25b731c602d4b684b1cfcea65aba651ddbac0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029402"
---
# <a name="compiler-error-c3054"></a>Compilerfehler C3054

"#pragma omp parallel" wird in einer generischen Klasse oder Funktion derzeit nicht unterstützt.

Weitere Informationen finden Sie unter [Generika](../../windows/generics-cpp-component-extensions.md) und [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3054 generiert.

```
// C3054.cpp
// compile with: /openmp /clr /c
#include <omp.h>

ref struct MyBaseClass {
   // Delete the following 7 lines to resolve.
   generic <class ItemType>
   void Test(ItemType i) {   // C3054
      #pragma omp parallel num_threads(4)
      {
         int i = omp_get_thread_num();
      }
   }

   // OK
   void Test2() {
      #pragma omp parallel num_threads(4)
      {
         int i = omp_get_thread_num();
      }
   }
};
```