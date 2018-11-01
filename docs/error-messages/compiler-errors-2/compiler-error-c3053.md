---
title: Compilerfehler C3053
ms.date: 11/04/2016
f1_keywords:
- C3053
helpviewer_keywords:
- C3053
ms.assetid: ab9a25f3-e341-4f6e-8e69-069b4a963a64
ms.openlocfilehash: cb01207be15a628fb0c6206df3e6a673067f568a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441368"
---
# <a name="compiler-error-c3053"></a>Compilerfehler C3053

'symbol': 'threadprivate' ist nur für globale oder statische Datenelemente gültig.

An [threadprivate](../../parallel/openmp/reference/threadprivate.md) übergebene Symbole müssen global oder statisch sein.

Das folgende Beispiel generiert C3053:

```
// C3053.cpp
// compile with: /openmp
void Test() {
   int x, y;
   #pragma omp threadprivate(x, y)   // C3053
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

Mögliche Lösung:

```
// C3053b.cpp
// compile with: /openmp /LD
int x, y;
#pragma omp threadprivate(x, y)

void Test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```