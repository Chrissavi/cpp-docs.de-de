---
title: Compilerfehler C2052
ms.date: 11/04/2016
f1_keywords:
- C2052
helpviewer_keywords:
- C2052
ms.assetid: 922ca43b-b64b-4ef7-9611-c7313be3fd79
ms.openlocfilehash: a9e891ad60d5eea31a2554320a8c2c584234c435
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739115"
---
# <a name="compiler-error-c2052"></a>Compilerfehler C2052

' Typ ': Unzulässiger Typ für Case-Ausdruck

Case-Ausdrücke müssen eine ganzzahlige Konstante sein.

Im folgenden Beispiel wird C2052 generiert:

```cpp
// C2052.cpp
int main() {
   int index = 0;
   switch (index) {
      case 1:
         return 24;
      case 1.0:   // C2052
      // try the following line instead
      // case 2:
         return 23;
   }
}
```
