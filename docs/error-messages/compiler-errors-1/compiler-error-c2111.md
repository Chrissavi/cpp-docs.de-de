---
title: Compilerfehler C2111
ms.date: 11/04/2016
f1_keywords:
- C2111
helpviewer_keywords:
- C2111
ms.assetid: 38fd42ec-1480-4a44-aaca-ae4593ed5f50
ms.openlocfilehash: 9545e44518a7a377378929d684bf08573a214b18
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437136"
---
# <a name="compiler-error-c2111"></a>Compilerfehler C2111

"+": Zeigeraddition erfordert einen Ganzzahloperanden

Es wurde versucht, einem Zeiger einen nicht ganzzahligen Wert mit dem Plus-Operator ( `+` ) hinzuzufügen.

Im folgenden Beispiel wird C2111 generiert:

```
// C2111.cpp
int main() {
   int *a = 0, *pa = 0, b = 0;
   double d = 0.00;

   a = pa + d;   // C2111
   a = pa + b;   // OK
}
```