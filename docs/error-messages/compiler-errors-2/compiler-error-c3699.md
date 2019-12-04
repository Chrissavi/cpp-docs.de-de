---
title: Compilerfehler C3699
ms.date: 11/04/2016
f1_keywords:
- C3699
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
ms.openlocfilehash: ec902266550e591623894823e6336bd2436bfbd5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758033"
---
# <a name="compiler-error-c3699"></a>Compilerfehler C3699

"Operator": Diese Dereferenzierung kann nicht für den Typ "Typ" verwendet werden.

Es wurde versucht, eine Dereferenzierung zu verwenden, die auf `type`nicht zulässig ist.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3699 generiert.

```cpp
// C3699.cpp
// compile with: /clr /c
using namespace System;
int main() {
   String * s;   // C3699
   // try the following line instead
   // String ^ s2;
}
```

## <a name="example"></a>Beispiel

Eine triviale Eigenschaft kann keinen Verweistyp aufweisen. Weitere Informationen finden Sie unter [property](../../extensions/property-cpp-component-extensions.md) . Im folgenden Beispiel wird C3699 generiert.

```cpp
// C3699_b.cpp
// compile with: /clr /c
ref struct C {
   property System::String % x;   // C3699
   property System::String ^ y;   // OK
};
```

## <a name="example"></a>Beispiel

Das Äquivalent eines "Zeiger auf eine Zeiger"-Syntax ist ein Handle für einen nach Verfolgungs Verweis. Im folgenden Beispiel wird C3699 generiert.

```cpp
// C3699_c.cpp
// compile with: /clr /c
using namespace System;
void Test(String ^^ i);   // C3699
void Test2(String ^% i);
```
