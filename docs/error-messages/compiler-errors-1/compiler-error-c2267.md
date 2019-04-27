---
title: Compilerfehler C2267
ms.date: 11/04/2016
f1_keywords:
- C2267
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
ms.openlocfilehash: 5ff8b0bee1f79d9534841e4368fd5a5249cbb413
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153397"
---
# <a name="compiler-error-c2267"></a>Compilerfehler C2267

'Funktion': statische Funktionen mit blockgültigkeit sind unzulässig

Deklariert eine lokale Funktion `static`. Statische Funktionen müssen globalen Gültigkeitsbereich.

Im folgende Beispiel wird die C2267 generiert:

```
// C2267.cpp
static int func2();   // OK
int main() {
    static int func1();   // C2267
}
```