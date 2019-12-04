---
title: Compilerfehler C2436
ms.date: 11/04/2016
f1_keywords:
- C2436
helpviewer_keywords:
- C2436
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
ms.openlocfilehash: 2fd910f18e8d863c6894a7fe99449d5ba213bf61
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744380"
---
# <a name="compiler-error-c2436"></a>Compilerfehler C2436

' Identifier ': Element Funktion oder eine in der Konstruktorinitialisiererliste angehosterte Klasse

Element Funktionen oder lokale Klassen in der Konstruktorinitialisiererliste können nicht initialisiert werden.

Im folgenden Beispiel wird C2436 generiert:

```cpp
// C2436.cpp
struct S{
   int f();
   struct Inner{
      int i;
   };
   S():f(10), Inner(0){}   // C2436
};
```
