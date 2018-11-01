---
title: Compilerwarnung (Stufe 1) C4572
ms.date: 11/04/2016
f1_keywords:
- C4572
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
ms.openlocfilehash: b4d3356522faacfc343c33908b64597387fbe51c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521072"
---
# <a name="compiler-warning-level-1-c4572"></a>Compilerwarnung (Stufe 1) C4572

/ CLR [ParamArray]-Attribut ist veraltet, verwenden Sie '...' stattdessen

Es wurde ein veraltetes Format zum Angeben einer Liste variabler Argumente verwendet. Verwenden Sie beim Kompilieren für die CLR auslassungszeichensyntax anstelle von <xref:System.ParamArrayAttribute>. Weitere Informationen finden Sie unter [Variablenargumentlisten (...) (C++ / CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4572 generiert.

```
// C4572.cpp
// compile with: /clr /W1
void Func([System::ParamArray] array<int> ^);   // C4572
void Func2(... array<int> ^){}   // OK

int main() {
   Func2(1, 2, 3);
}
```