---
title: Vorrang und Auswertungsreihenfolge | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- associativity of operators [C++]
- precedence [C++], operators
- data binding [C++], operator precedence
- operators [C++], precedence
ms.assetid: 201f7864-0c51-4c55-9d6f-39c5d013bcb0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84c3ec69c936605729f6813f28450ee1194951c7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392184"
---
# <a name="precedence-and-order-of-evaluation"></a>Vorrang und Auswertungsreihenfolge
Die Rangfolge und Assoziativität von C-Operatoren beeinflussen das Gruppieren und die Auswertung von Operanden in Ausdrücken. Eine Operatorrangfolge ist nur sinnvoll, wenn andere Operatoren mit einer höheren oder niedrigerer Rangfolge vorhanden sind. Ausdrücke mit vorrangigen Operatoren werden zuerst ausgewertet. Rangfolge kann auch mit dem Wort "Bindung" beschrieben werden. Es wird davon ausgegangen, dass Operatoren mit einer höheren Priorität eine festere Bindung haben.  
  
 In der folgenden Tabelle werden die Rangfolge und Assoziativität (die Reihenfolge, in der Operanden überprüft werden) von C-Operatoren zusammengefasst, wobei sie nach Priorität von der höchsten bis zur niedrigsten aufgeführt werden. Wenn mehrere Operatoren zusammengefasst werden, weisen sie einen gleichen Rang auf, und sie werden gemäß ihrer Assoziativität ausgewertet. Die Operatoren in der Tabelle werden in den Abschnitten beschrieben, die mit [Postfix-Operatoren](../c-language/postfix-operators.md) beginnen. Im Rest dieses Abschnitts sind allgemeine Informationen über die Rangfolge und Assoziativität aufgeführt.  
  
## <a name="precedence-and-associativity-of-c-operators"></a>Rangfolge und Assoziativität von C-Operatoren  
  
|Symbol <sup>1</sup>|Vorgangstyp|Assoziativität|  
|-------------|-----------------------|-------------------|  
|**\[ ] ( ) . ->**<br /><br />**++** **--** (Postfix)|Ausdruck|Von links nach rechts|  
**sizeof & \* + - ~ !**<br /><br />**++ --** (Präfix)|Unär|Von rechts nach links|  
|*Typumwandlungen*|Unär|Von rechts nach links|  
|**\* / %**|Multiplikativ|Von links nach rechts|  
|**+ -**|Additiv|Von links nach rechts|  
|**\<\< >>**|Bitweise Verschiebung|Von links nach rechts|  
|**\< > \<= >=**|Relational|Von links nach rechts|  
|**== !=**|Gleichheit|Von links nach rechts|  
|**&**|Bitweises AND|Von links nach rechts|  
|**^**|Bitweises exklusives OR|Von links nach rechts|  
|**&#124;**|Bitweises inklusives OR|Von links nach rechts|  
|**&&**|Logisches AND|Von links nach rechts|  
|**&#124;&#124;**|Logisches OR|Von links nach rechts|  
|**? :**|Bedingter Ausdruck|Von rechts nach links|  
|**= \*= /= %=**<br /><br /> **+= -= \<\<= >>= &=**<br /><br /> **^= &#124;=**|Einfache und Verbundzuweisung <sup>2</sup>|Von rechts nach links|  
|**,**|Sequenzielle Auswertung|Von links nach rechts|  
  
 1. Operatoren werden in absteigender Prioritätsreihenfolge aufgeführt. Wenn mehrere Operatoren in der gleichen Zeile oder in einer Gruppe stehen, haben sie denselben Rang.  
  
 2. Alle einfachen und zusammengesetzten Zuweisungsoperatoren haben denselben Rang.  
  
 Ein Ausdruck kann mehrere Operatoren mit gleichem Rang enthalten. Wenn mehrere solcher Operatoren auf der gleichen Ebene in einem Ausdruck vorkommen, wird die Auswertung entsprechend der Assoziativität des Operators entweder von rechts nach links oder von links nach rechts fortgesetzt. Die Richtung der Überprüfung wirkt sich nicht auf die Ergebnisse der Ausdrücke aus, die mehr als einen Multiplikations- (**\***), Additions- (**+**) oder binären bitweisen (**& &#124; ^**) Operator auf der gleichen Ebene umfassen. Die Reihenfolge der Vorgänge wird von der Sprache nicht definiert. Der Compiler kann solche Ausdrücke in beliebiger Reihenfolge auswerten, wenn der Compiler ein einheitliches Ergebnis garantieren kann.  
  
 Nur der Operator für sequenzielle Auswertung (**,**), der logische AND-Operator (**&&**), der logische OR-Operator (`||`), der bedingten Ausdrucksoperator (**? :**) und der Funktionsaufrufoperator konstituieren Sequenzpunkte und stellen daher eine bestimmte Auswertungsreihenfolge für ihre Operanden sicher. Die Funktionsaufrufoperator ist der Klammersatz, welcher dem Funktionsbezeichner folgt. Der Operator für sequenzielle Auswertung (**,**) wertet seine Operanden von links nach rechts aus. (Beachten Sie, dass der Kommaoperator in einem Funktionsaufruf nicht derselbe ist wie der Operator für sequenzielle Auswertung und keine derartige Garantie bereitstellt.) Weitere Informationen finden Sie unter [Sequenzpunkte](../c-language/c-sequence-points.md).  
  
 Logische Operatoren gewährleisten auch die Auswertung ihrer Operanden von links nach rechts. Allerdings werten Sie die kleinste Anzahl von Operanden aus, die erforderlich sind, um das Ergebnis des Ausdrucks zu bestimmen. Dies wird als "Kurzschlussauswertung" bezeichnet. Somit werden einige Operanden des Ausdrucks möglicherweise nicht ausgewertet. Beispielsweise wird im Ausdruck  
  
`x && y++`  
  
 der zweite Operand, `y++`, nur ausgewertet, wenn `x` zutrifft (Wert ungleich Null). Folglich wird `y` nicht inkrementiert, wenn `x` false (0) ist.  
  
## <a name="examples"></a>Beispiele
  
 Die folgende Liste zeigt, wie der Compiler automatisch mehrere Musterausdrücke bindet:  

|Ausdruck|Automatische Bindung|  
|----------------|-----------------------|  
|a & b || c|(a & b) || c|  
|a = b || c|a = (b || c)|  
|q && r || s--|(q && r) || s--|  

 Im ersten Ausdruck hat der bitweise AND-Operator (`&`) Vorrang vor dem logischen OR-Operator (`||`), deshalb bildet `a & b` den ersten Operanden der logischen OR-Operation.  
  
 Im zweiten Ausdruck hat der logische Operator OR (`||`) Vorrang vor dem SIMPLE-Zuweisungsoperator (`=`), sodass `b || c` als rechter Operand in der Zuweisung gruppiert wird. Beachten Sie, dass der Wert, der `a` zugewiesen wird, entweder 0 oder 1 ist.  
  
 Der dritte Ausdruck zeigt einen ordnungsgemäß gebildeten Ausdruck an, der möglicherweise ein unerwartetes Ergebnis bereitstellt. Der logische AND-Operator (`&&`) hat Vorrang vor dem logischen OR-Operator (`||`), sodass `q && r` als Operand gruppiert wird. Da die logischen Operatoren eine Auswertung von Operanden von links nach rechts garantieren, wird `q && r` vor `s--` ausgewertet. Wenn jedoch `q && r` einen Wert ungleich 0 (null) ergibt, wird `s--` nicht ausgewertet, und `s` wird nicht verringert. Wenn dadurch, dass `s` nicht dekrementiert wird, im Programm ein Problem auftritt, sollte `s--` als erster Operand im Ausdruck stehen oder `s` in einem separaten Vorgang dekrementiert werden.  
  
 Der folgende Ausdruck ist nicht zulässig und erzeugt eine Diagnosemeldung zur Kompilierzeit:  
  
|Ungültiger Ausdruck|Standardmäßiges Gruppieren|  
|------------------------|----------------------|  
|p == 0 ? p += 1: p += 2|( p == 0 ? p += 1 : p ) += 2|  
  
 In diesem Ausdruck hat der Gleichheitsoperator (`==`) den höchsten Rang, sodass `p == 0` als Operand gruppiert wird. Der bedingte Ausdrucksoperator (`? :`) hat die nächsthöhere Priorität. Sein erster Operand ist `p == 0`, und sein zweiter Operand ist `p += 1`. Allerdings wird der letzte Operand des bedingten Ausdrucksoperators als `p` und nicht als `p += 2` betrachtet, da dieses Vorkommen von `p` genauer an den bedingten Ausdrucksoperator bindet als an den kombinierten Zuweisungsoperator. Ein Syntaxfehler tritt auf, weil `+= 2` keinen linken Operanden besitzt. Sie sollten Klammern verwenden, um Fehler dieser Art zu vermeiden und den Code verständlicher zu erzeugen. Beispielsweise können Sie Klammern verwenden, wie weiter unten dargestellt, um das vorherige Beispiel zu korrigieren und zu verdeutlichen:  
  
`( p == 0 ) ? ( p += 1 ) : ( p += 2 )`  
  
## <a name="see-also"></a>Siehe auch  
 [C-Operatoren](../c-language/c-operators.md)
