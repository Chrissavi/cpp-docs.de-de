---
title: Speicherklassenspezifizierer für Deklarationen der externen Ebene | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- external definitions
- linkage [C++], external
- external linkage, variable declarations
- declaring variables, external variables
- declarations [C++], external
- declarations [C++], specifiers
- external declarations
- static variables, external declarations
- variables, visibility
- external linkage, storage-class specifiers
- referencing declarations
- visibility, variables
- static storage class specifiers
ms.assetid: b76b623a-80ec-4d5d-859b-6cef422657ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cfdae4791b89ffd78661a983fdc8c1beec77edea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392116"
---
# <a name="storage-class-specifiers-for-external-level-declarations"></a>Speicherklassenspezifizierer für Deklarationen der externen Ebene
Externe Variablen sind Variablen im Dateigültigkeitsbereich. Sie sind außerhalb einer Funktion definiert und sind potenziell für viele Funktionen verfügbar. Funktionen können nur auf der externen Ebene definiert werden und deshalb nicht geschachtelt werden. Standardmäßig sind alle Verweise auf externe Variablen und Funktionen desselben Namens Verweise auf dasselbe Objekt. Das bedeutet, dass sie "externe Bindung" besitzen. (Sie können das **static**-Schlüsselwort verwenden, um dies zu überschreiben. Weitere Informationen über **static** finden Sie weiter unten in diesem Abschnitt.)  
  
 Variablendeklarationen auf externer Ebene sind entweder Definitionen von Variablen ("definierende Deklarationen") oder Verweise auf Variablen, die an anderer Stelle definiert werden ("verweisende Deklarationen").  
  
 Eine externe Variablendeklaration, die auch die Variable initialisiert (implizit oder explizit), ist eine definierende Deklaration der Variable. Eine Definition der externen Ebene kann verschiedene Formen aufweisen:  
  
-   Eine Variable, die Sie mit dem Speicherklassenspezifizierer **static** deklarieren. Sie können die Variable **static** mit einem konstanten Ausdruck explizit initialisieren, wie in [Initialisierung](../c-language/initialization.md) beschrieben. Wenn Sie den Initialisierer weglassen, wird die Variable standardmäßig auf 0 initialisiert. Beispielsweise gelten diese beiden Anweisungen als Definitionen der Variable `k`.  
  
    ```  
    static int k = 16;  
    static int k;  
    ```  
  
-   Eine Variable, die Sie explizit für die externe Ebene initialisieren. Beispielsweise ist `int j = 3;` eine Definition für die Variable `j`.  
  
 In den Variablendeklarationen auf der externen Ebene (d.h. außerhalb aller Funktionen) können Sie den Speicherklassenspezifizierer **static** oder `extern` verwenden oder diesen vollständig auslassen. Sie können die **auto**- und **register**-*storage-class-specifier*-Terminals nicht auf der externen Ebene verwenden.  
  
 Sobald eine Variable auf der externen Ebene definiert wird, ist sie für den Rest der Übersetzungseinheit sichtbar. Die Variable ist vor ihrer Deklaration in derselben Quelldatei nicht sichtbar. Außerdem ist sie nicht in anderen Quelldateien des Programms sichtbar, es sei denn, eine verweisende Deklaration macht sie sichtbar, wie im Folgenden beschrieben.  
  
 Die Regeln bezüglich **static** umfassen:  
  
-   Variablen, die außerhalb aller Blöcke ohne das Schlüsselwort **static** deklariert werden, behalten ihre Werte immer während des gesamten Programmablaufs bei. Um den Zugriff auf eine bestimmte Übersetzungseinheit einzuschränken, müssen Sie das **static**-Schlüsselwort verwenden. Dadurch erhalten sie eine "interne Bindung". Um sie als global für ein gesamtes Programm festzulegen, lassen Sie die explizite Speicherklasse aus, oder verwenden Sie das Schlüsselwort `extern` (siehe die Regeln in der folgenden Liste.) Dadurch erhalten sie eine "externe Bindung". Interne und externe Verknüpfungen werden auch in [Verknüpfung](../c-language/linkage.md) erläutert.  
  
-   Sie können eine Variable auf der externen Ebene nur einmal innerhalb eines Programms definieren. Sie können eine andere Variable mit dem gleichen Namen und dem **static**-Speicherklassenspezifizierer in einer anderen Übersetzungseinheit definieren. Da jede **static**-Definition nur innerhalb der eigenen Übersetzungseinheit sichtbar ist, tritt kein Konflikt auf. Dies ist eine gute Möglichkeit, Bezeichnernamen auszublenden, die von Funktionen einer einzelnen Übersetzungseinheit gemeinsam verwendet werden müssen, jedoch nicht für andere Übersetzungseinheiten sichtbar sein dürfen.  
  
-   Der **static**-Speicherklassenspezifizierer kann auch für Funktionen gelten. Wenn Sie eine Funktion als **static** deklarieren, ist ihr Name nicht sichtbar außerhalb der Datei, in der sie deklariert wurde.  
  
 Die Regeln für die Verwendung von `extern` sind:  
  
-   Der Speicherklassenbezeichner `extern` deklariert einen Verweis auf eine Variable, die an anderer Stelle definiert ist. Sie können eine `extern`-Deklaration verwenden, um eine Definition in einer anderen Quelldatei sichtbar zu machen oder um eine Variable vor ihrer Definition in der gleichen Quelldatei sichtbar zu machen. Sobald Sie einen Verweis auf die Variable auf der externen Ebene deklariert haben, ist die Variable für den Rest der Übersetzungseinheit sichtbar, in der der deklarierte Verweis erfolgt.  
  
-   Damit ein `extern` Verweis gültig ist, muss die Variable, auf die verwiesen wird, einmal und nur einmal auf der externen Ebene definiert sein. Diese Definition (ohne die `extern`-Speicherklasse) kann sich in einer der Übersetzungseinheiten befinden, aus denen das Programm besteht.  
  
## <a name="example"></a>Beispiel  
 Das unten gezeigte Beispiel veranschaulicht externe Deklarationen:  
  
```  
/******************************************************************  
                      SOURCE FILE ONE   
*******************************************************************/  
#include <stdio.h>  
  
extern int i;                // Reference to i, defined below   
void next( void );           // Function prototype              
  
int main()  
{  
    i++;  
    printf_s( "%d\n", i );   // i equals 4   
    next();  
}  
  
int i = 3;                  // Definition of i  
  
void next( void )  
{  
    i++;  
    printf_s( "%d\n", i );  // i equals 5  
    other();  
}  
  
/******************************************************************  
                      SOURCE FILE TWO   
*******************************************************************/  
#include <stdio.h>  
  
extern int i;              // Reference to i in   
                           // first source file   
void other( void )  
{  
    i++;  
    printf_s( "%d\n", i ); // i equals 6   
}  
```  
  
 Die zwei Quelldateien in diesem Beispiel enthalten insgesamt drei externe Deklarationen von `i`. Nur eine Deklaration ist eine "definierende Deklaration". Diese Deklaration  
  
```  
int i = 3;  
```  
  
 definiert die globale Variable `i` und initialisiert sie mit dem Anfangswert 3. Die "verweisende" Deklaration von `i` am Anfang der ersten Quelldatei, die `extern` verwendet, macht die globale Variable vor der definierenden Deklaration in der Datei sichtbar. Die verweisende Deklaration von `i` in der zweiten Quelldatei macht außerdem die Variable in der Quelldatei sichtbar. Wenn eine definierende Instanz für eine Variable nicht in der Übersetzungseinheit bereitgestellt wird, geht der Compiler davon aus, dass eine verweisende Deklaration  
  
```  
extern int x;  
```  
  
 vorhanden ist und dass sich eine definierende Verweisdeklaration  
  
```  
int x = 0;  
```  
  
 in einer anderen Übersetzungseinheit des Programms befindet.  
  
 Alle drei Funktionen, `main`, `next` und `other`, führen die gleiche Aufgabe aus: `i` wird erweitert und gedruckt. Die Werte 4, 5 und 6 werden gedruckt.  
  
 Wenn die Variable `i` nicht initialisiert war, würde sie automatisch auf 0 festgelegt. In diesem Fall wären die Werte 1, 2 und 3 gedruckt worden. Weitere Informationen zur Variableninitialisierung erhalten Sie unter [Initialisierung](../c-language/initialization.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C-Speicherklassen](../c-language/c-storage-classes.md)