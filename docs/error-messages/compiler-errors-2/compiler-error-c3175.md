---
title: Compilerfehler C3175 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3175
dev_langs:
- C++
helpviewer_keywords:
- C3175
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b4ba372dd542bfb2c38435b6084b55d95b1bdf2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043273"
---
# <a name="compiler-error-c3175"></a>Compilerfehler C3175

"Funktion1": eine Methode eines verwalteten Typs kann nicht aufgerufen werden, von nicht verwalteten Funktion "Funktion2"

Nicht verwaltete Funktionen können keine Memberfunktionen von verwalteten Klassen aufrufen.

Im folgende Beispiel wird die C3175 generiert:

```
// C3175_2.cpp
// compile with: /clr

ref struct A {
   static void func() {
   }
};

#pragma unmanaged   // remove this line to resolve

void func2() {
   A::func();   // C3175
}

#pragma managed

int main() {
   A ^a = gcnew A;
   func2();
}
```
