---
title: Compilerfehler C2199
ms.date: 11/04/2016
f1_keywords:
- C2199
helpviewer_keywords:
- C2199
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
ms.openlocfilehash: 8bd6d587d28b8e7c190f7d3d58448fda501796cf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758982"
---
# <a name="compiler-error-c2199"></a>Compilerfehler C2199

Syntax Fehler: "Bezeichner (" im globalen Gültigkeitsbereich gefunden (war eine Deklaration beabsichtigt?)

Der angegebene Kontext hat einen Syntax Fehler verursacht. Möglicherweise gibt es eine falsche Deklarations Syntax.

Im folgenden Beispiel wird C2199 generiert:

```cpp
// C2199.cpp
// compile with: /c
int j = int(1) int(1);   // C2199
int j = 1;   // OK
```
