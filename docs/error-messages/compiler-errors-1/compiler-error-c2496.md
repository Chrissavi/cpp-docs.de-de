---
title: Compilerfehler C2496
ms.date: 11/04/2016
f1_keywords:
- C2496
helpviewer_keywords:
- C2496
ms.assetid: 9a25237d-5bbb-4112-98f3-29cd99d3f89f
ms.openlocfilehash: 258012fdefed877558f122790954d830095d5026
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578697"
---
# <a name="compiler-error-c2496"></a>Compilerfehler C2496

'Bezeichner': "Selectany" kann nur auf Daten mit externer Bindung angewendet werden

Die [Selectany](../../cpp/selectany.md) Attribut kann nur auf extern sichtbar und globaler Datenelemente angewendet werden.

Im folgende Beispiel wird die C2496 generiert:

```
// C2496.cpp
// compile with: /c
__declspec(selectany) int x1 = 1;
const __declspec(selectany) int x2 = 2;   // C2496
static __declspec(selectany) int x6 = 6;   // C2496

extern const __declspec(selectany) int x3 = 3;

__declspec(selectany) int x4;

// dynamic initialization of x5
int f();
__declspec(selectany) int x5 = f();

extern const int x7;
// OK - redeclaration of x7 that is extern
const __declspec(selectany) int x7 = 7;
```