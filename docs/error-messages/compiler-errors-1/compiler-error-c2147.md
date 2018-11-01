---
title: Compilerfehler C2147
ms.date: 11/04/2016
f1_keywords:
- C2147
helpviewer_keywords:
- C2147
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
ms.openlocfilehash: 0a093bbbaf9cf9f72625226f949a27b681005c35
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614486"
---
# <a name="compiler-error-c2147"></a>Compilerfehler C2147

Syntaxfehler: 'Bezeichner' ist ein neues Schlüsselwort

Ein Bezeichner wurde verwendet, die nun ein reserviertes Schlüsselwort in der Sprache ist.

Im folgende Beispiel wird die C2147 generiert:

```
// C2147.cpp
// compile with: /clr
int main() {
   int gcnew = 0;   // C2147
   int i = 0;   // OK
}
```