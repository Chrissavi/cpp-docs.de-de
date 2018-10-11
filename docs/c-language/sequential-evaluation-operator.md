---
title: Operator für sequenzielle Auswertungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], sequential-evaluation
- sequential-evaluation operator
- comma operator
ms.assetid: 587514f4-c8e2-44e9-81a8-7a553ce1453a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a285cc87ec4182586663afcb3559101167ae7261
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095572"
---
# <a name="sequential-evaluation-operator"></a>Operator für sequenzielle Auswertungen

Der Operator für sequenzielle Auswertung wird auch als „Komma-Operator“ bezeichnet. Er wertet seine beiden Operanden der Reihe nach von links nach rechts aus.

## <a name="syntax"></a>Syntax

*Ausdruck*: *assignment-expression*

*expression*  **,**  *assignment-expression*

Der linke Operand des Operators für die sequenzielle Auswertung wird als `void`-Ausdruck ausgewertet. Das Ergebnis der Operation hat den gleichen Wert und Typ wie der rechte Operand. Jeder Operand kann einen beliebigen Typ aufweisen. Der Operator für sequenzielle Auswertung führt keine Typkonvertierungen zwischen seinen Operanden durch, und er erreicht keinen l-Wert. Es gibt einen Sequenzpunkt nach dem ersten Operanden. Dies bedeutet, dass alle Nebeneffekte bei der Auswertung des linken Operanden abgeschlossen werden, bevor die Auswertung des rechten Operanden beginnt. Weitere Informationen finden Sie unter [Sequenzpunkte](../c-language/c-sequence-points.md).

Der Operator für sequenzielle Auswertung wird normalerweise verwendet, um mindestens zwei Ausdrücke in Kontexten auszuwerten, in denen nur ein Ausdruck zulässig ist.

Kommas können in einigen Kontexten als Trennzeichen verwendet werden. Allerdings müssen Sie darauf achten, die Funktion des Kommas als Trennzeichen nicht mit der Funktion als Operator zu verwechseln, da beide Verwendungsmöglichkeiten vollkommen unterschiedlich sind.

## <a name="example"></a>Beispiel

In diesem Beispiel wird der Operator für die sequenzielle Auswertung veranschaulicht:

```
for ( i = j = 1; i + j < 20; i += i, j-- );
```

In diesem Beispiel wird jeder Operand des dritten Ausdrucks der **for**-Anweisung unabhängig ausgewertet. Der linke Operand `i += i` wird zuerst ausgewertet; anschließend wird der rechte Operand `j--` ausgewertet.

```
func_one( x, y + 2, z );
func_two( (x--, y + 2), z );
```

Im Funktionsaufruf an `func_one` werden drei Argumente durch Trennzeichen getrennt übergeben: `x`, `y + 2` und `z`. Im Funktionsaufruf an `func_two` zwingen Klammern den Compiler, das erste Komma als Operator für sequenzielle Auswertung zu interpretieren. Dieser Funktionsaufruf übergibt zwei Argumente an `func_two`. Das erste Argument ist das Ergebnis der Sequentialauswertungsoperation `(x--, y + 2)`, welche den Wert und den Typ des Ausdrucks `y + 2` hat; das zweite Argument ist `z`.

## <a name="see-also"></a>Siehe auch

[Kommaoperator: ,](../cpp/comma-operator.md)