---
title: Compilerfehler C3155
ms.date: 11/04/2016
f1_keywords:
- C3155
helpviewer_keywords:
- C3155
ms.assetid: b04a42e1-64e7-40f8-81fe-c7945348b2cf
ms.openlocfilehash: ccbe96075a22ef67d7ebd1f2998b42820bbc79f9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745901"
---
# <a name="compiler-error-c3155"></a>Compilerfehler C3155

Attribute sind in einem eigenschaftenindexer nicht zulässig.

Eine indizierte Eigenschaft wurde falsch deklariert. Weitere Informationen finden Sie unter Gewusst [wie: Verwenden von Eigenschaften C++in/CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3155 generiert.

```cpp
// C3155.cpp
// compile with: /clr /c
using namespace System;
ref struct R {
   property int F[[ParamArray] int] {   // C3155
   // try the following line instead
   // property int F[ int] {   // OK
      int get(int i) {
         return 0;
      }
   }
};
```
