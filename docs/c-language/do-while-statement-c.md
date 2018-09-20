---
title: do-while-Anweisung (C) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- do
- while
dev_langs:
- C++
helpviewer_keywords:
- do-while keyword [C]
ms.assetid: f2ac20a6-10c7-4a08-b5e3-c3b3639dbeaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5254adbf533a30da65349f2f8aadd100b8776d7
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755550"
---
# <a name="do-while-statement-c"></a>do-while-Anweisung (C)

Mit der *do-while*-Anweisung wird eine Anweisung oder ein Anweisungsblock wiederholt ausgeführt, bis ein bestimmter Ausdruck den Wert „false“ liefert.

## <a name="syntax"></a>Syntax

*iteration-statement*:  
&nbsp;&nbsp;&nbsp;&nbsp;**do**  *statement*  **while (**  *Ausdruck*  **) ;**

Der *Ausdruck* in einer *do-while*-Anweisung wird ausgewertet, nachdem der Text der Schleife ausgeführt wird. Daher wird der Text der Schleife immer mindestens einmal ausgeführt.

Der *Ausdruck* muss einen arithmetischen Typ oder einen Zeigertyp aufweisen. Die Ausführung erfolgt folgendermaßen:

1. Der Anweisungstext wird ausgeführt.

2. Danach wird *expression*, der Ausdruck, ausgewertet. Wenn der *Ausdruck* „false“ ist, wird die *do-while*-Anweisung beendet und die Steuerung an die nächste Anweisung im Programm weitergegeben. Wenn *expression* „true“ (ungleich 0 [null]) ist, wird der Prozess wiederholt, beginnend mit Schritt 1.

Die *do-while*-Anweisung kann auch beendet werden, wenn eine **break**-, **goto**- oder **return**-Anweisung innerhalb des Anweisungstexts ausgeführt wird.

In diesem Beispiel wird die *do-while*-Anweisung veranschaulicht:

```C
do
{  
    y = f( x );  
    x--;  
} while ( x > 0 );  
```

In dieser *do-while*-Anweisung werden die beiden Anweisungen `y = f( x );` und `x--;` unabhängig vom Anfangswert von `x` ausgeführt. Anschließend wird `x > 0` ausgewertet. Wenn `x` größer als 0 ist, wird der Anweisungstext noch einmal ausgeführt und `x > 0` erneut ausgewertet. Der Anweisungstext wird wiederholt ausgeführt, solange `x` größer als 0 ist. Die Ausführung der *do-while*-Anweisung wird beendet, wenn `x` 0 oder negativ ist. Der Text der Schleife wird mindestens einmal ausgeführt.

## <a name="see-also"></a>Siehe auch

[do-while-Anweisung (C++)](../cpp/do-while-statement-cpp.md)