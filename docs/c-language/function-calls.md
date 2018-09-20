---
title: Funktionsaufrufe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls, about function calls
- function calls
ms.assetid: 2cfa897d-3874-4820-933c-e624f75d1712
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8849cd932bd44b5dd7094d05470a4a97f58b08cb
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755490"
---
# <a name="function-calls"></a>Funktionsaufrufe
Ein *Funktionsaufruf* ist ein Ausdruck, der Steuerung und Argumente (falls vorhanden) an eine Funktion übergibt und folgende Form annimmt:  
  
*expression* (*expression-list*<sub>opt</sub>)  
  
wobei *expression* ein Funktionsname oder zu einer Funktionsadresse ausgewertet ist und *expression-list* eine Liste von Ausdrücken (durch Trennzeichen getrennt) ist. Die Werte dieser letzten Ausdrücke sind die Argumente, die an die Funktion übergeben werden. Wenn die Funktion keinen Wert zurückgibt, deklarieren Sie ihn zu einer Funktion, die `void` zurückgibt.  
  
Wenn eine Deklaration vor dem Funktionsaufruf vorhanden ist, jedoch keine Informationen zu dem Parameter angegeben werden, durchlaufen alle nicht deklarierten Argumente einfach die üblichen arithmetischen Konvertierungen.  
  
> [!NOTE]
>  Die Ausdrücke in der Funktionsargumentliste können in jeder Reihenfolge bewertet werden, Argumente, deren Werte sich über Nebeneffekte eines anderen Arguments ändern können, können also undefinierte Werte haben. Der Sequenzpunkt, der vom Funktionsaufrufoperator definiert ist, gewährleistet lediglich, dass alle Nebeneffekte in der Argumentliste ausgewertet werden, bevor die Steuerung an die aufgerufene Funktion übergeben wird. (Beachten Sie, dass die Reihenfolge, in der Argumente auf dem Stapel abgelegt werden, eine andere Angelegenheit ist.) Weitere Informationen finden Sie unter [Sequenzpunkte](../c-language/c-sequence-points.md).  
  
Die einzige Anforderung in einem beliebigen Funktionsaufruf ist, dass der Ausdruck vor den Klammern mit einer Funktionsadresse ausgewertet werden muss. Dies bedeutet, dass eine Funktion von jedem Funktionszeigerausdruck aufgerufen werden kann.  
  
## <a name="example"></a>Beispiel  
Dieses Beispiel veranschaulicht die Funktionsaufrufe, die von einer `switch`-Anweisung aufgerufen werden:  
  
```  
int main()  
{  
    /* Function prototypes */  
  
    long lift( int ), step( int ), drop( int );  
    void work( int number, long (*function)(int i) );  
  
    int select, count;  
    .  
    .  
    .  
    select = 1;  
    switch( select )   
    {  
        case 1: work( count, lift );  
                break;  
  
        case 2: work( count, step );  
                break;  
  
        case 3: work( count, drop );  
                /* Fall through to next case */  
        default:  
                break;  
    }  
}  
  
/* Function definition */  
  
void work( int number, long (*function)(int i) )  
{  
    int i;  
    long j;  
  
    for ( i = j = 0; i < number; i++ )  
            j += ( *function )( i );  
}  
```  
  
In diesem Beispiel übergibt der Funktionsaufruf in `main`  
  
```  
work( count, lift );  
```  
  
eine ganzzahlige Variable, `count`, und die Adresse der Funktion `lift` an die `work`-Funktion. Beachten Sie, dass die Funktionsadresse einfach durch den Funktionsbezeichner übergeben wird, da ein Funktionsbezeichner zu einem Zeigerausdruck ausgewertet wird. Um einen Funktionsbezeichner auf diese Weise zu verwenden, muss die Funktion deklariert oder definiert werden, bevor der Bezeichner verwendet wird; andernfalls wird der Bezeichner nicht erkannt. In diesem Fall ist ein Prototyp `work` am Anfang der `main`-Funktion gegeben.  
  
Der Parameter `function` in `work` wird deklariert, um einen Zeiger auf eine Funktion zu ergeben, die ein `int`-Argument akzeptiert und einen **long**-Wert zurückgibt. Die Klammern um den Parameternamen sind erforderlich, denn ohne sie würde die Deklaration eine Funktion angeben, die einen Zeiger auf einen **long**-Wert zurückgibt.  
  
Die Funktion `work` ruft die ausgewählte Funktion aus der **for**-Schleife heraus auf, indem sie den folgenden Funktionsaufruf verwendet:  
  
```  
( *function )( i );  
```  
  
Ein Argument, `i`, wird an die aufgerufene Funktion übergeben.  
  
## <a name="see-also"></a>Siehe auch  
[Funktionen](../c-language/functions-c.md)