---
title: Compilerwarnung (Stufe 4) C4212
ms.date: 11/04/2016
f1_keywords:
- C4212
helpviewer_keywords:
- C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
ms.openlocfilehash: 8eca942de1d2f78f5e42d4aac7e2441789a01862
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401162"
---
# <a name="compiler-warning-level-4-c4212"></a>Compilerwarnung (Stufe 4) C4212

nicht dem Standard entsprechende Erweiterung: Funktionsdeklaration verwendet Ellipse

Der Funktionsprototyp verfügt über eine Variable Anzahl von Argumenten. Definition der Funktion nicht.

Im folgende Beispiel wird die C4212 generiert:

```
// C4212.c
// compile with: /W4 /Ze /c
void f(int , ...);
void f(int i, int j) {}
```