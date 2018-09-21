---
title: Bedingter Ausdrucksoperator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- conditional operators
- operators [C++], conditional
- expressions [C++], conditional
ms.assetid: c4f1a5ca-0844-44a7-a384-eca584d4e3dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2037d64aba025b9acf8279a3da9073611d11ce8e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107909"
---
# <a name="conditional-expression-operator"></a>Bedingter Ausdrucksoperator

C hat einen ternären Operator: den bedingten Ausdrucksoperator (**? :**).

## <a name="syntax"></a>Syntax

*conditional-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*logical-OR-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*logical-OR expression*  **?**  *expression* **:** *conditional-expression*

Der Ausdruck für *logical-OR-expression* muss über Ganzzahl-, Gleitkomma- oder Zeigertypen verfügen. Er wird hinsichtlich seiner Übereinstimmung mit 0 ausgewertet. Ein Sequenzpunkt folgt dem Ausdruck für *logical-OR-expression*. Die Auswertung der Operanden wird wie folgt ausgeführt:

- Wenn der Ausdruck für *logical-OR-expression* ungleich 0 ist, wird *expression* ausgewertet. Das Ergebnis der Auswertung des Ausdrucks wird durch den Nichtterminal *expression* angegeben. (Dies bedeutet, dass *expression* nur ausgewertet wird, wenn der Ausdruck für *logical-OR-expression* „true“ ist.)

- Wenn der Ausdruck für *logical-OR-expression* gleich 0 ist, wird *conditional-expression* ausgewertet. Das Ergebnis des Ausdrucks ist der Wert von *conditional-expression*. (Dies bedeutet, dass *conditional-expression* nur ausgewertet wird, wenn der Ausdruck für *logical-OR-expression* „false“ ist.)

Es wird entweder nur *expression* oder *conditional-expression* ausgewertet, jedoch nicht beide.

Der Typ des Ergebnisses einer bedingten Operation hängt wie folgt vom Typ des Operands *expression* oder *conditional-expression* ab:

- Wenn *expression* oder *conditional-expression* über einen Ganzzahl- oder Gleitkommatyp verfügt (ihre Typen können unterschiedlich sein), führt der Operator die üblichen arithmetischen Konvertierungen aus. Der Ergebnistyp ist der Typ der Operanden nach der Konvertierung.

- Wenn sowohl *expression* als auch *conditional-expression* denselben Struktur-, Union- oder Zeigertyp aufweisen, ist der Typ des Ergebnisses derselbe Struktur-, Union- oder Zeigertyp.

- Wenn beide Operanden den Typ `void` haben, hat das Ergebnis den Typ `void`.

- Wenn einer der Operanden ein Zeiger auf ein Objekt eines beliebigen Typs und der andere Operand ein Zeiger auf `void` ist, wird der Zeiger auf das Objekt in einen Zeiger auf einen `void` konvertiert, und das Ergebnis ist ein Zeiger auf `void`.

- Wenn *expression* oder *conditional-expression* ein Zeiger und der andere Operand ein konstanter Ausdruck mit dem Wert 0 ist, ist der Typ des Ergebnisses der Zeigertyp.

Im Typvergleich für Zeiger sind alle Typqualifizierer (**const** oder `volatile`) in dem Typ, auf den der Zeiger weist, nicht signifikant. Der Ergebnistyp erbt jedoch die Qualifizierer von beiden Komponenten des bedingten Operators.

## <a name="examples"></a>Beispiele

In den folgenden Beispielen werden verschiedene Verwendungen des bedingten Operators veranschaulicht:

```
j = ( i < 0 ) ? ( -i ) : ( i );
```

In diesem Beispiel wird der absolute Wert von `i` dem Wert `j` zugewiesen. Wenn `i` kleiner als 0 ist, wird `-i` dem Wert `j` zugewiesen. Wenn `i` größer oder gleich 0 ist, wird `i` dem Wert `j` zugewiesen.

```
void f1( void );
void f2( void );
int x;
int y;
    .
    .
    .
( x == y ) ? ( f1() ) : ( f2() );
```

In diesem Beispiel werden die zwei Funktionen `f1` und `f2` sowie die zwei Variablen `x` und `y` deklariert. Wenn die zwei Variablen später im Programm den gleichen Wert haben, wird die `f1`-Funktion aufgerufen. Andernfalls wird `f2` aufgerufen.

## <a name="see-also"></a>Siehe auch

[Bedingter Operator: ? :](../cpp/conditional-operator-q.md)