---
title: 'Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation: ++ und --'
ms.date: 11/04/2016
f1_keywords:
- --
- ++
helpviewer_keywords:
- increment operators [C++], syntax
- member-selection operators [C++]
- -- operator [C++], postfix decrement operators
- postfix operators [C++]
- ++ operator [C++], postfix increment operators
- decrement operators [C++], syntax
- operators [C++], postfix
- decrement operators [C++]
ms.assetid: 0204d5c8-51b0-4108-b8a1-074c5754d89c
ms.openlocfilehash: 8c3eeb47ec81f4073452c17f40eb2fec4911989f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213280"
---
# <a name="postfix-increment-and-decrement-operators--and---"></a>Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation: ++ und --

## <a name="syntax"></a>Syntax

```
postfix-expression ++
postfix-expression --
```

## <a name="remarks"></a>Bemerkungen

C++ bietet Präfix- und Postfixinkrement- und Dekrementoperatoren. Dieser Abschnitt beschreibt nur die Postfixinkrement- und Dekrementoperatoren. (Weitere Informationen finden Sie unter [Präfix Inkrement-und Dekrementoperatoren](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md).) Der Unterschied zwischen den beiden besteht darin, dass in der Postfix-Notation der Operator nach *Postfix-Expression*angezeigt wird, wohingegen in der Präfix-Notation der Operator vor Expression angezeigt wird *.* Das folgende Beispiel zeigt einen Postfixinkrement-Operator:

```cpp
i++;
```

Der Effekt der Anwendung des Postfix Inkrement-Operators ( **++** ) besteht darin, dass der Wert des Operanden um eine Einheit des entsprechenden Typs erhöht wird. Ebenso besteht die Auswirkung der Anwendung des Postfix-Dekrementoperators ( **--** ) darin, dass der Wert des Operanden um eine Einheit des entsprechenden Typs verringert wird.

Beachten Sie, dass ein postfix-Inkrement-oder dekrementausdruck zu dem Wert des Ausdrucks *vor* der Anwendung des jeweiligen Operators ausgewertet wird. Der Inkrement-oder Dekrement-Vorgang tritt auf, *nachdem* der Operand ausgewertet wurde. Dieses Problem tritt nur auf, wenn der Postfix-Inkrement- oder Postfix-Dekrementvorgang im Kontext eines umfassenderen Ausdrucks stattfindet.

Wenn ein Postfix-Operator auf ein Funktionsargument angewendet wird, ist für den Wert des Arguments nicht gewährleistet, dass er vor der Übergabe an die Funktion inkrementiert oder dekrementiert wird.  Weitere Informationen finden Sie in Abschnitt 1.9.17 im C++-Standard.

Durch Anwenden des Postfix-Inkrementoperators auf einen Zeiger auf ein Array von Objekten vom Typ werden der **`long`** internen Darstellung des Zeigers tatsächlich vier hinzugefügt. Dieses Verhalten bewirkt, dass der Zeiger, der zuvor auf das *n*-te Element des Arrays verwiesen hat, auf das (*n*+ 1) th-Element verweist.

Die Operanden für postfix Inkrement-und postfix-Dekrementoperatoren müssen änderbar (not **`const`** ) l-Werte des arithmetischen Typs oder Zeiger Typs sein. Der Ergebnistyp entspricht dem des *Postfix-Expression*, aber es handelt sich nicht mehr um einen l-Wert.

**Visual Studio 2017 Version 15,3 und** höher (verfügbar mit [/Std: c++ 17](../build/reference/std-specify-language-standard-version.md)): der Operand eines Postfix Inkrement-oder Dekrementoperators ist möglicherweise nicht vom Typ **`bool`** .

Der folgende Code veranschaulicht den Postfixinkrement-Operator:

```cpp
// expre_Postfix_Increment_and_Decrement_Operators.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main() {
   int i = 10;
   cout << i++ << endl;
   cout << i << endl;
}
```

Postinkrement- und Postdekrementvorgänge für Enumerationstypen werden nicht unterstützt:

```cpp
enum Compass { North, South, East, West );
Compass myCompass;
for( myCompass = North; myCompass != West; myCompass++ ) // Error
```

## <a name="see-also"></a>Weitere Informationen

[Postfix Ausdrücke](../cpp/postfix-expressions.md)<br/>
[Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C postfix Inkrement-und Dekrementoperatoren](../c-language/c-postfix-increment-and-decrement-operators.md)
