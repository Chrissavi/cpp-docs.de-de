---
title: Compilerwarnung (Stufe 1) C4518
ms.date: 11/04/2016
f1_keywords:
- C4518
helpviewer_keywords:
- C4518
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
ms.openlocfilehash: 85e0d87094fc355bf63d79bf2eb5b1d06f233542
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466806"
---
# <a name="compiler-warning-level-1-c4518"></a>Compilerwarnung (Stufe 1) C4518

"Spezifizierer": Speicher-Klasse, oder geben Sie unerwartete(r). ignoriert

Im folgende Beispiel wird die C4518 generiert:

```
// C4518.cpp
// compile with: /c /W1
_declspec(dllexport) extern "C" void MyFunction();   // C4518

extern "C" void MyFunction();   // OK
```