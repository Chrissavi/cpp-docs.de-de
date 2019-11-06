---
title: Compilerwarnung (Stufe 1) C4052
ms.date: 11/04/2016
f1_keywords:
- C4052
helpviewer_keywords:
- C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
ms.openlocfilehash: 848db5df19908150d9f869bf2995ed69c24a1ec0
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626969"
---
# <a name="compiler-warning-level-1-c4052"></a>Compilerwarnung (Stufe 1) C4052

Unterschiedliche Funktionsdeklarationen; eine enthält variable Argumente

Eine Deklaration der Funktion enthält keine variablen Argumente. Wird ignoriert.

Im folgenden Beispiel wird C4052 generiert:

```c
// C4052.c
// compile with: /W4 /c
int f();
int f(int i, ...);   // C4052
```