---
title: Compilerfehler C2206
ms.date: 11/04/2016
f1_keywords:
- C2206
helpviewer_keywords:
- C2206
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
ms.openlocfilehash: f1dd1d0706018a2a3f7d5b483a8dcdb2227e05be
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221288"
---
# <a name="compiler-error-c2206"></a>Compilerfehler C2206

„function“: typedef kann nicht für die Definition einer Funktion verwendet werden.

Ein- **`typedef`** Typ wird verwendet, um einen Funktionstyp zu definieren.

Das folgende Beispiel generiert C2206:

```cpp
// C2206.cpp
typedef int functyp();
typedef int MyInt;
functyp func1 {};   // C2206
int main() {
   MyInt i = 0;   // OK
}
```
