---
title: Compilerwarnung (Stufe 1) C4572
ms.date: 11/04/2016
f1_keywords:
- C4572
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
ms.openlocfilehash: 52285f391af0a8028307cbbc320af33f9cb1fca5
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965948"
---
# <a name="compiler-warning-level-1-c4572"></a>Compilerwarnung (Stufe 1) C4572

[ParamArray] das Attribut ist unter/CLR veraltet, verwenden Sie "...". Stattdessen

Es wurde ein veralteter Stil zum Angeben einer Variablen Argumentliste verwendet. Wenn Sie für die CLR kompilieren, verwenden Sie die Ellipsen Syntax anstelle <xref:System.ParamArrayAttribute>. Weitere Informationen finden Sie unter [Variablen Argument Listen (...) (C++/CLI)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4572 generiert.

```cpp
// C4572.cpp
// compile with: /clr /W1
void Func([System::ParamArray] array<int> ^);   // C4572
void Func2(... array<int> ^){}   // OK

int main() {
   Func2(1, 2, 3);
}
```