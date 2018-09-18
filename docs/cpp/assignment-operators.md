---
title: Zuweisungsoperatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/05/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- =
- '*='
- /=
- '%='
- +=
- -=
- <<=
- '>>='
- '&='
- ^=
- '|='
- '&&='
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], C++
- '&= operator'
- '&&= operator'
- ^= operator
- += operator
- '>>= operator'
- '|= operator'
- operator>>=
- '*= operator'
- '%= operator'
- ^= operator
- operator >>=
- = operator
- -= operator
- /= operator
- <<= operator
ms.assetid: b028cf35-2ff1-4f14-9027-fd53ebec8aa0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 15c9efaf8dc5b9f0886a697ad2b872e24264820f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017897"
---
# <a name="assignment-operators"></a>Zuweisungsoperatoren

## <a name="syntax"></a>Syntax

```
expression assignment-operator expression 
assignment-operator : one of
   =   *=   /=   %=   +=   -=   <<=   >>=   &=   ^=   |=  &&=
```

## <a name="remarks"></a>Hinweise

Zuweisungsoperatoren speichern einen Wert in dem Objekt, das durch den linken Operanden festgelegt ist. Es gibt drei Arten von Zuweisungsvorgängen:

1. einfache Zuweisung, in dem der Wert des zweiten Operanden in dem Objekt durch den ersten Operanden angegeben gespeichert wird. 1. verbundzuweisung, in dem ein Arithmetik-, UMSCHALT oder bitweise Operation erfolgt vor dem Speichern der Ergebnisse.
1. Verschieben Sie Zuweisung (für Klassentypen), in welche Ressourcen, ohne zu kopieren übertragen werden.


Alle Zuweisungsoperatoren in der folgenden Tabelle außer der = und & & = Operatoren sind Verbundzuweisungsoperatoren.

### <a name="assignment-operators"></a>Zuweisungsoperatoren

|Operator|Bedeutung|
|--------------|-------------|
|**=**|Speichern Sie den Wert des zweiten Operanden in dem Objekt, das durch den ersten Operanden angegeben wird (einfache Zuweisung).|
|**\*=**|Multiplizieren Sie den Wert des ersten Operanden mit dem Wert des zweiten Operanden. Speichern Sie das Ergebnis in dem Objekt, das durch den ersten Operanden angegeben wird.|
|**/=**|Dividieren Sie den Wert des ersten Operanden durch den Wert des zweiten Operanden. Speichern Sie das Ergebnis in dem Objekt, das durch den ersten Operanden angegeben wird.|
|**%=**|Errechnen Sie den Modul des ersten Operanden, der vom Wert des zweiten Operanden angegeben wird. Speichern Sie das Ergebnis in dem Objekt, das durch den ersten Operanden angegeben wird.|
|**+=**|Addieren Sie den Wert des zweiten Operanden zu dem Wert des ersten Operanden. Speichern Sie das Ergebnis in dem Objekt, das durch den ersten Operanden angegeben wird.|
|**-=**|Subtrahieren Sie den Wert des zweiten Operanden von dem Wert des ersten Operanden. Speichern Sie das Ergebnis in dem Objekt, das durch den ersten Operanden angegeben wird.|
|**<\<=**|Verschieben Sie den Wert des ersten Operanden links der Anzahl von Bits, die durch den Wert des zweiten Operanden angegeben werden. Speichern Sie das Ergebnis in dem Objekt, das durch den ersten Operanden angegeben wird.|
|**>>=**|Verschieben Sie den Wert des ersten Operanden rechts der Anzahl von Bits, die durch den Wert des zweiten Operanden angegeben werden. Speichern Sie das Ergebnis in dem Objekt, das durch den ersten Operanden angegeben wird.|
|**&=**|Rufen Sie den bitweisen AND-Operator des ersten und zweiten Operanden auf. Speichern Sie das Ergebnis in dem Objekt, das durch den ersten Operanden angegeben wird.|
|**^=**|Rufen Sie den bitweisen exklusiven OR-Operator des ersten und zweiten Operanden auf. Speichern Sie das Ergebnis in dem Objekt, das durch den ersten Operanden angegeben wird.|
|**\|=**|Rufen Sie den bitweisen inklusiven OR-Operator des ersten und zweiten Operanden auf. Speichern Sie das Ergebnis in dem Objekt, das durch den ersten Operanden angegeben wird.|
|**&&=**| Move-Zuweisungsoperator (für nur Klassentypen). Ist der zweite Operand ein Rvalue-Wert, verschieben Sie die Ressourcen auf den ersten Operanden (ohne sie zu kopieren). Finden Sie unter [Bewegungskonstruktoren und bewegungszuweisungsoperatoren](move-constructors-and-move-assignment-operators-cpp.md) für Weitere Informationen.|

**Operatorschlüsselwörter**

Drei der Verbundzuweisungsoperatoren weisen Textentsprechungen auf. Dies sind:

|Operator|Entsprechung|
|--------------|----------------|
|**&=**|`and_eq`|
|**\|=**|`or_eq`|
|**^=**|`xor_eq`|

Es gibt zwei Möglichkeiten, um auf diese Operatorschlüsselwörter in Ihren Programmen zuzugreifen: Einschließen der Headerdatei `iso646.h`, oder Kompilieren Sie mit der [/Za](../build/reference/za-ze-disable-language-extensions.md) -Compileroption (spracherweiterungen deaktivieren).

## <a name="example"></a>Beispiel

```cpp
// expre_Assignment_Operators.cpp
// compile with: /EHsc
// Demonstrate assignment operators
#include <iostream>
using namespace std;
int main() {
   int a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555;

   a += b;      // a is 9
   b %= a;      // b is 6
   c >>= 1;      // c is 5
   d |= e;      // Bitwise--d is 0xFFFF

   cout  << "a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555" << endl
         << "a += b yields " << a << endl
         << "b %= a yields " << b << endl
         << "c >>= 1 yields " << c << endl
         << "d |= e yields " << hex << d << endl;
}
```

## <a name="simple-assignment"></a>Einfache Zuweisung

Der einfache Zuweisungsoperator (=) bewirkt, dass der Wert des zweiten Operanden in dem durch den ersten Operanden angegebenen Objekt gespeichert wird. Wenn beide Objekte arithmetische Typen sind, wird der rechte Operand in den Typ des linken Operanden konvertiert, bevor der Wert gespeichert wird.

Objekte vom Typ "const" und "volatile" können L-Werten von Typen zugewiesen werden, die nur "volatile" oder die weder "const" noch "volatile" sind.

Die Zuweisung zu Objekten des Klassentyps (Struktur-, Union- und Klassentypen) wird durch eine Funktion mit dem Namen "operator=" ausgeführt. Das Standardverhalten dieser Operatorfunktion besteht darin, eine bitweise Kopie auszuführen. Allerdings kann dieses Verhalten mithilfe von überladenen Operatoren geändert werden. (Finden Sie unter [überladene Operatoren](../cpp/operator-overloading.md) für Weitere Informationen.)

Ein Objekt einer eindeutig abgeleiteten Klasse von einer angegebenen Basisklasse kann einem Objekt der Basisklasse zugewiesen werden. Umgekehrt gilt dies nicht, da eine implizite Konvertierung von einer abgeleiteten Klasse in eine Basisklasse vorliegt, jedoch nicht von der Basisklasse in die abgeleitete Klasse. Zum Beispiel:

```cpp
// expre_SimpleAssignment.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
class ABase
{
public:
    ABase() { cout << "constructing ABase\n"; }
};

class ADerived : public ABase
{
public:
    ADerived() { cout << "constructing ADerived\n"; }
};

int main()
{
    ABase aBase;
    ADerived aDerived;

    aBase = aDerived; // OK
    aDerived = aBase; // C2679
}
```

Zuweisungen zu Verweistypen verhalten sich so, als ob die Zuweisung zu dem Objekt ausgeführt würde, auf das der Verweis zeigt.

Für Klassentypobjekte unterscheidet sich die Zuweisung von der Initialisierung. Um zu sehen, wie unterschiedlich Zuweisung und Initialisierung sein können, betrachten Sie diesen Code:

```cpp
UserType1 A;
UserType2 B = A;
```

Der vorhergehende Code zeigt einen Initialisierer; er ruft den Konstruktor für `UserType2` auf, der ein Argument vom Typ `UserType1` akzeptiert. Mit dem Code

```cpp
UserType1 A;
UserType2 B;

B = A;
```

kann die Zuweisungsanweisung

```cpp
B = A;
```

eine der folgenden Auswirkungen haben:

- Aufruf der Funktion "operator=" für `UserType2`, vorausgesetzt "operator=" wird mit einem `UserType1`-Argument bereitgestellt.

- Aufruf der expliziten Konvertierungsfunktion `UserType1::operator UserType2`, wenn eine solche Funktion vorhanden ist.

- Aufruf eines Konstruktors `UserType2::UserType2`, sofern ein solcher Konstruktor vorhanden ist, der ein `UserType1`-Argument akzeptiert und das Ergebnis kopiert.

## <a name="compound-assignment"></a>Verbundzuweisung

Die Verbundzuweisungsoperatoren, in der Tabelle gezeigt [Zuweisungsoperatoren](../cpp/assignment-operators.md), sind im Formular angegeben habe *e1* `op` =  *e2*, wobei *e1* ist ein änderbarer l-Wert nicht vom const-Typ und *e2* ist eine der folgenden:

- Ein arithmetischer Typ

- Ein Zeiger ist, wenn `op` ist + oder –

Die *e1* `op` =  *e2* Formular verhält sich wie *e1* *= e1* `op` *e2*, aber *e1* wird nur einmal ausgewertet.

Eine Verbundzuweisung für einen enumerierten Typ generiert eine Fehlermeldung. Wenn der linke Operand ein Zeigertyp ist, muss der rechte Operand ein Zeigertyp oder ein konstanter Ausdruck sein, der 0 (null) ergibt. Wenn der linke Operand ein ganzzahliger Typ ist, darf der rechte Operand kein Zeigertyp sein.

## <a name="result-of-assignment-operators"></a>Ergebnis von Zuweisungsoperatoren

Die Zuweisungsoperatoren geben den Wert des Objekts zurück, das vom linken Operanden nach der Zuweisung angegeben wird. Das Typergebnis ist der Typ des linken Operanden. Das Ergebnis eines Zuweisungsausdrucks ist immer ein l-value. Diese Operatoren weisen eine Assoziativität von rechts nach links auf. Der linke Operand muss ein veränderbarer l-value sein.

In ANSI C ist das Ergebnis eines Zuweisungsausdrucks kein l-value. Daher ist der gültige C++-Ausdruck `(a += b) += c` in C ungültig.

## <a name="see-also"></a>Siehe auch

[Ausdrücke mit binären Operatoren](../cpp/expressions-with-binary-operators.md)<br/>
[C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C-Zuweisungsoperatoren](../c-language/c-assignment-operators.md)