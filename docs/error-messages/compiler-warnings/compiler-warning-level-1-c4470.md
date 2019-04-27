---
title: Compilerwarnung (Stufe 1) C4470
ms.date: 11/04/2016
f1_keywords:
- C4470
helpviewer_keywords:
- C4470
ms.assetid: f52a3eaa-a235-4747-a47d-9ec4ad4cb0ea
ms.openlocfilehash: 7fd4644ab39e350c0c0badb527875b427a2c6987
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160899"
---
# <a name="compiler-warning-level-1-c4470"></a>Compilerwarnung (Stufe 1) C4470

zur gleitkommasteuerung ignoriert unter/CLR

Die "float"-Control-Pragmas:

- [fenv_access](../../preprocessor/fenv-access.md)

- [float_control](../../preprocessor/float-control.md)

- [fp_contract](../../preprocessor/fp-contract.md)

wirken sich nicht unter ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md).

Im folgende Beispiel wird die C4470 generiert:

```
// C4470.cpp
// compile with: /clr /W1 /LD
#pragma float_control(except, on)   // C4470
```