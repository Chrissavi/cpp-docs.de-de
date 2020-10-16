---
title: 'Address-of Operator: &amp;'
description: Der Address-of-Operator in der Programmiersprache C++.
ms.date: 10/02/2020
f1_keywords:
- '&'
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
ms.openlocfilehash: 8ef7ad065281e4de58ddbdebea25950f8eb9dd06
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765283"
---
# <a name="address-of-operator-amp"></a>Address-of-Operator: &amp;

## <a name="syntax"></a>Syntax

> **`&`** *`cast-expression`*

## <a name="remarks"></a>Bemerkungen

Der unäre address-of Operator ( **`&`** ) übernimmt die Adresse seines Operanden. Der Operand des address-of Operators kann entweder ein Funktionskennzeichner oder ein L-Wert sein, der ein Objekt angibt, das kein Bitfeld ist.

Der address-of Operator kann nur auf Variablen von grundlegenden, Struktur-, Klassen-oder Union-Typen angewendet werden, die auf der Datei Gültigkeits-Ebene deklariert sind, oder auf Index Verweise. In diesen Ausdrücken kann ein konstanter Ausdruck, der nicht den Address-of Operator einschließt, dem address-of Ausdruck hinzugefügt oder von diesem subtrahiert werden.

Bei Anwendung auf Funktionen oder L-Werte ist das Ergebnis des Ausdrucks ein Zeigertyp (ein R-Wert), der vom Typ des Operanden abgeleitet wird. Wenn z. B. der Operand vom Typ **`char`** ist, ist das Ergebnis des Ausdrucks vom Typ Zeiger auf **`char`** . Der address-of Operator, der auf **`const`** oder **`volatile`** -Objekte angewendet wird, wird zu `const type *` oder `volatile type *` ausgewertet, wobei `type` der Typ des ursprünglichen Objekts ist.

Die Adresse einer überladenen Funktion kann nur verwendet werden, wenn klar ist, auf welche Version der Funktion verwiesen wird. Weitere Informationen zum Abrufen der Adresse einer bestimmten überladenen Funktion finden Sie unter [Funktions Überladung](function-overloading.md) .

Wenn der address-of Operator auf einen qualifizierten Namen angewendet wird, hängt das Ergebnis davon ab, ob der *qualifizierte Name* ein statisches Element angibt. Wenn dies der Fall ist, ist das Ergebnis ein Zeiger auf den Typ, der in der Deklaration des Members angegeben wird. Bei einem Member, der nicht statisch ist, ist das Ergebnis ein Zeiger auf den Element *Namen* der Klasse, die durch *qualified-class-Name* angegeben wird. Weitere Informationen zu *qualified-class-Name* finden Sie unter [Primary Expressions](../cpp/primary-expressions.md).

## <a name="example-address-of-static-member"></a>Beispiel: Adresse des statischen Members

Das folgende Code Fragment zeigt, wie sich das Ergebnis der address-of Operatoren unterscheidet, je nachdem, ob ein Klassenmember statisch ist:

```cpp
// expre_Address_Of_Operator.cpp
// C2440 expected
class PTM {
public:
    int iValue;
    static float fValue;
};

int main() {
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static
   float *spfValue     = &PTM::fValue;  // OK
}
```

In diesem Beispiel ergibt der Ausdruck `&PTM::fValue` den Typ `float *` anstelle von Typ `float PTM::*`, da `fValue` ein statischer Member ist.

## <a name="example-address-of-a-reference-type"></a>Beispiel: Adresse eines Referenz Typs

Die Anwendung des address-of Operators auf einen Referenztyp führt zum gleichen Ergebnis wie die Anwendung des Operators auf das Objekt, an das der Verweis gebunden ist. Zum Beispiel:

```cpp
// expre_Address_Of_Operator2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
int main() {
   double d;        // Define an object of type double.
   double& rd = d;  // Define a reference to the object.

   // Obtain and compare their addresses
   if( &d == &rd )
      cout << "&d equals &rd" << endl;
}
```

```Output
&d equals &rd
```

## <a name="example-function-address-as-parameter"></a>Beispiel: Funktions Adresse als Parameter

Im folgenden Beispiel wird der address-of Operator benutzt, um ein Zeigerargument an eine Funktion zu übergeben:

```cpp
// expre_Address_Of_Operator3.cpp
// compile with: /EHsc
// Demonstrate address-of operator &

#include <iostream>
using namespace std;

// Function argument is pointer to type int
int square( int *n ) {
   return (*n) * (*n);
}

int main() {
   int mynum = 5;
   cout << square( &mynum ) << endl;   // pass address of int
}
```

```Output
25
```

## <a name="see-also"></a>Siehe auch

[Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)<br/>
[C++ integrierte Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Lvalue-Verweisdeklarator: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[Dereferenzierungs- und Address-of-Operatoren](../c-language/indirection-and-address-of-operators.md)
