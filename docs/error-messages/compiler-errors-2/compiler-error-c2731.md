---
title: Compilerfehler C2731
ms.date: 11/04/2016
f1_keywords:
- C2731
helpviewer_keywords:
- C2731
ms.assetid: 9b563999-febd-4582-9147-f355083c091e
ms.openlocfilehash: 4b73ee4ad205bfc2203423b5f413011ce090852f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755810"
---
# <a name="compiler-error-c2731"></a>Compilerfehler C2731

"Bezeichner": Funktion kann nicht überladen werden.

Die Funktionen `main`, `WinMain`, `DllMain`und `LibMain` können nicht überladen werden.

Im folgenden Beispiel wird C2731 generiert:

```cpp
// C2731.cpp
extern "C" void WinMain(int, char *, char *);
void WinMain(int, short, char *, char*);   // C2731
```
