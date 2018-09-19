---
title: Compilerwarnung (Stufe 1) C4730 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4730
dev_langs:
- C++
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d740e1574d4cc538a27471c07795b7c95dd17565
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070455"
---
# <a name="compiler-warning-level-1-c4730"></a>Compilerwarnung (Stufe 1) C4730

"main": Kombinieren von _m64 und Gleitkommaausdrücken kann zu fehlerhaftem Code

Eine Funktion verwendet [__m64](../../cpp/m64.md) und **"float"**/**doppelte** Typen. Da der MMX- und Gleitkommaregister denselben physischen registerraum (kann nicht gleichzeitig verwendet werden), mit `__m64` und **"float"**/**doppelte** Typen im gleichen Funktion kann dazu führen, dass Daten beschädigt, möglicherweise eine Ausnahme verursacht.

Für eine sichere Verwendung `__m64` Typen und Gleitkommatypen in derselben Funktion, sollte jede Anweisung, einer der Typen verwendet, getrennt werden, durch die **_m_empty()** (für MMX) oder **_m_femms()** (für 3DNow!) systeminterne.

Im folgende Beispiel wird die C4730 generiert:

```
// C4730.cpp
// compile with: /W1
// processor: x86
#include "mmintrin.h"

void func(double)
{
}

int main(__m64 a, __m64 b)
{
   __m64 m;
   double f;
   f = 1.0;
   m = _m_paddb(a, b);
   // uncomment the next line to resolve C4730
   // _m_empty();
   func(f * 3.0);   // C4730
}
```