---
title: C-Sequenzpunkte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- sequence points
ms.assetid: c84885a5-4336-4eba-a643-058df4249903
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9cf0b72314103587ddf64021db2a265044c469e3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384306"
---
# <a name="c-sequence-points"></a>C-Sequenzpunkte
Zwischen aufeinanderfolgenden "Sequenzpunkten" kann der Wert eines Objekts nur einmal durch einen Ausdruck geändert werden. Die C-Programmiersprache definiert die folgenden Sequenzpunkte:  
  
-   Linker Operand des logischen AND-Operators (**&&**). Der linke Operand des logischen AND-Operators wird vollständig ausgewertet, und alle Nebeneffekte werden vor dem Fortsetzen abgeschlossen. Wenn der linke Operand als "False (0)" ausgewertet wird, wird der andere Operand nicht ausgewertet.  
  
-   Linker Operand des logischen OR-Operators (`||`) Der linke Operand des logischen OR-Operators wird vollständig ausgewertet, und alle Nebeneffekte werden vor dem Fortsetzen abgeschlossen. Wenn der linke Operand als "True" (ein Wert ungleich 0) ausgewertet wird, wird der andere Operand nicht ausgewertet.  
  
-   Linker Operand des Komma-Operators. Der linke Operand des Komma-Operators wird vollständig ausgewertet, und alle Nebeneffekte werden vor dem Fortsetzen abgeschlossen. Beide Operanden des Komma-Operators werden immer ausgewertet. Der Komma-Operator in einem Funktionsaufruf gewährleistet keine Auswertungsreihenfolge.  
  
-   Funktionsaufrufoperator. Alle Argumente für eine Funktion werden ausgewertet, und alle Nebeneffekte werden vor dem Eintrag in die Funktion abgeschlossen. Es wird keine Auswertungsreihenfolge zwischen den Argumenten angegeben.  
  
-   Der erste Operand des bedingten Operators. Der erste Operand des bedingten Operators wird vollständig ausgewertet, und alle Nebeneffekte werden vor dem Fortsetzen abgeschlossen.  
  
-   Das Ende eines vollständigen Initialisierungsausdrucks (das heißt, der Ausdruck, der nicht Teil eines anderen Ausdrucks ist, wie am Ende einer Initialisierung in einer Deklarationsanweisung).  
  
-   Der Ausdruck in einer Ausdrucksanweisung. Ausdrucksanweisungen bestehen aus einem optionalen Ausdruck, dem ein Semikolon (**;**) folgt. Der Ausdruck wird auf seine Nebeneffekte hin ausgewertet, und es gibt einen Sequenzpunkt, der dieser Auswertung folgt.  
  
-   Der steuernde Ausdruck in einer Auswahlanweisung (**if** oder `switch`). Der Ausdruck wird vollständig ausgewertet, und alle Nebeneffekte werden abgeschlossen, bevor der von der Auswahl abhängige Code ausgeführt wird.  
  
-   Der steuernde Ausdruck einer `while`- oder **do**-Anweisung. Der Ausdruck wird vollständig ausgewertet, und alle Nebeneffekte werden abgeschlossen, bevor eine beliebige Anweisung in der nächsten Iteration der `while`- oder **do**-Schleife ausgeführt wird.  
  
-   Jede der drei Ausdrücke einer **for**-Anweisung. Die Ausdrücke werden vollständig ausgewertet und alle Nebeneffekte abgeschlossen, bevor beliebige Anweisungen in der nächsten Iteration der **for**-Schleife ausgeführt werden.  
  
-   Der Ausdruck in einer `return`-Anweisung. Der Ausdruck wird vollständig ausgewertet, und alle Nebeneffekte werden abgeschlossen, bevor die Steuerung an die aufrufende Funktion zurückgegeben wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrucksauswertung](../c-language/expression-evaluation-c.md)