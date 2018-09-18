---
title: Compilerfehler C2563 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2563
dev_langs:
- C++
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eec8526df1c5ff69899dd0a2d103cb5f28d4c00c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067401"
---
# <a name="compiler-error-c2563"></a>Compilerfehler C2563

nicht übereinstimmende in der Liste formaler parameter

Die Liste der formalen Parameter einer Funktion (oder ein Zeiger auf eine Funktion) entspricht nicht den von einer anderen Funktion (oder Zeiger auf eine Memberfunktion). Daher kann die Zuweisung von Funktionen oder Zeiger vorgenommen werden.

Im folgende Beispiel wird die C2563 generiert:

```
// C2563.cpp
void func( int );
void func( int, int );
int main() {
   void *fp();
   fp = func;   // C2563
}
```