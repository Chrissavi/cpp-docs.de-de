---
title: Compilerfehler Fehler C2653 | Microsoft Docs
ms.custom: ''
ms.date: 11/30/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2653
dev_langs:
- C++
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8e1df7dd6337b1a3e363a5744181b12d94c879b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234966"
---
# <a name="compiler-error-c2653"></a>Compilerfehler Fehler C2653

> "*Bezeichner*": ist kein Name für eine Klasse oder Namespace

Die Sprachsyntax ist erforderlich, eine Klasse, Struktur, Union oder Namespace an dieser Stelle.

Dieser Fehler kann auftreten, wenn Sie einen Namen verwenden, der nicht als eine Klasse, Struktur, Union oder Namespace vor einen Bereichsoperator deklariert wurde. Um dieses Problem zu beheben, deklarieren Sie den Namen oder den Header, der den Namen deklariert, bevor sie verwendet wird.

C2653 ist auch möglich, wenn Sie versuchen, Sie definieren eine *zusammengesetzten Namespace*, einen Namespace, eine oder mehrere Bereich geschachtelten Namespace-Namen enthält. Zusammengesetzte Namespace Definitionen in C++ vor C ++ 17 sind nicht zulässig. Zusammengesetzte Namespaces sind in Visual Studio 2015 Update 3 gestartet wird, wenn Sie angeben, unterstützt die [/std:c ++ neueste](../../build/reference/std-specify-language-standard-version.md) -Compileroption. Ab Visual C++ 2017 Version 15.5, unterstützt der Compiler zusammengesetzten Namespacedefinitionen bei der [/std:c ++ 17](../../build/reference/std-specify-language-standard-version.md) angegeben wird.

## <a name="examples"></a>Beispiele

In diesem Beispiel wird C2653 generiert, da ein Bereichsnamen verwendet wird, aber nicht deklariert. Der Compiler erwartet, dass eine Klasse, Struktur, Union oder Namespacenamen, bevor Sie einen Bereichsoperator (:).

```cpp
// C2653.cpp
// compile with: /c
class yy {
   void func1(int i);
};

void xx::func1(int m) {}   // C2653, xx is not declared
void yy::func1(int m) {}   // OK
```

In Code, der nicht für C ++ 17 oder höher Standards kompiliert wird, müssen geschachtelte Namespaces eine expliziten Namespace-Deklaration auf jede Schachtelungsebene verwenden:

```cpp
// C2653b.cpp
namespace a::b {int i;}   // C2653 prior to Visual C++ 2015 Update 3,
                          // C2429 thereafter. Use /std:c++17 or /std:c++latest to fix.

namespace a {             // Use this form for compliant code under /std:c++14 (the default)
   namespace b {          // or when using compilers before Visual Studio 2015 update 3.
      int i;
   }
}

int main() {
   a::b::i = 2;
}
```
