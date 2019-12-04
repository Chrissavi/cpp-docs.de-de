---
title: Compilerfehler C3085
ms.date: 11/04/2016
f1_keywords:
- C3085
helpviewer_keywords:
- C3085
ms.assetid: 1ac40bf2-f63e-439e-8921-47e6dadc8354
ms.openlocfilehash: 4ebb4d52316c7143e63074f81f9950f92340a004
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751429"
---
# <a name="compiler-error-c3085"></a>Compilerfehler C3085

"Konstruktor": Ein Konstruktor kann nicht "Schlüsselwort" sein.

Ein Konstruktor wurde falsch deklariert. Weitere Informationen finden Sie unter [Override Specifiers](../../extensions/override-specifiers-cpp-component-extensions.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3085 generiert.

```cpp
// C3085.cpp
// compile with: /c /clr
ref struct S {
   S() abstract;   // C3085
   S(S%) abstract;   // C3085
};

ref struct T {
   T() sealed {}   // C3085
   T(T%) sealed {}   // C3085
};
```
