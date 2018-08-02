---
title: Einzelne Vererbung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- single inheritance
- base classes [C++], indirect
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- derived classes [C++], single base class
- inheritance, single
ms.assetid: 1cb946ed-8b1b-4cf1-bde0-d9cecbfdc622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4f0f2a82c02bcb58f89d604978d31eb01ebd1fd
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465686"
---
# <a name="single-inheritance"></a>Einfache Vererbung
In der einfachen Vererbung, eine häufige Art der Vererbung, haben Klassen nur eine Basisklasse. Betrachten Sie die Beziehung, wie in der folgenden Abbildung veranschaulicht.  
  
 ![Grundlegende einzelne&#45;Vererbungsdiagramm](../cpp/media/vc38xj1.gif "vc38XJ1")  
Einfaches Diagramm für einzelne Vererbung  
  
 Beachten Sie den Ablauf von allgemein zu spezifisch in der Abbildung. Ein anderes häufiges Attribut, das im Entwurf der meisten Klassenhierarchien zu finden ist, ist, dass die abgeleitete Klasse "eine Art" Beziehung mit der Basisklasse hat. In der Abbildung ist `Book` eine Art `PrintedDocument` und `PaperbackBook` eine Art `book`.  
  
 Ein weiteres relevantes Element in der Abbildung: `Book` ist eine abgeleitete Klasse (von `PrintedDocument`) und eine Basisklasse (`PaperbackBook` ist von `Book` abgeleitet). Eine Skeletal-Deklaration einer solchen Klassenhierarchie wird im folgenden Beispiel gezeigt:  
  
```cpp 
// deriv_SingleInheritance.cpp  
// compile with: /LD  
class PrintedDocument {};  
  
// Book is derived from PrintedDocument.  
class Book : public PrintedDocument {};  
  
// PaperbackBook is derived from Book.  
class PaperbackBook : public Book {};  
```  
  
 `PrintedDocument` gilt als "direkte Basisklasse" für `Book`. Es ist eine "indirekte Basisklasse" für `PaperbackBook`. Der Unterschied liegt darin, dass eine direkte Basisklasse in der Basisliste einer Klassendeklaration angezeigt wird und eine indirekte Basisklasse nicht.  
  
 Die Basisklasse, von der jeder Klasse abgeleitet ist, wird vor der Deklaration der abgeleiteten Klasse deklariert. Es genügt nicht, eine Vorwärtsverweis-Deklaration für eine Basisklasse bereitzustellen, es muss eine vollständige Deklaration sein.  
  
 Im vorherigen Beispiel, dem Zugriffsspezifizierer **öffentliche** verwendet wird. Die Bedeutung von öffentlichen, geschützten und privater Vererbung wird im beschrieben [Memberzugriffssteuerung.](../cpp/member-access-control-cpp.md)  
  
 Eine Klasse kann als Basisklasse für viele bestimmte Klassen dienen, wie in der folgenden Abbildung veranschaulicht.  
  
 ![Gerichtetes azyklisches Diagramm](../cpp/media/vc38xj2.gif "vc38XJ2")  
Beispiel für gerichtetes azyklisches Diagramm  
  
 Im oben gezeigten Diagramm, das "gerichtetes azyklisches Diagramm" (oder "DAG") genannt wird, sind einige der Klassen Basisklassen für mehrere abgeleitete Klassen. Umgekehrt ist dies jedoch nicht wahr: Es gibt nur eine direkte Basisklasse für jede abgeleitete Klasse. Das Diagramm in der Abbildung stellt eine Struktur mit einfacher Vererbung dar.  
  
> [!NOTE]
>  Gerichtete azyklische Diagramme sind nicht eindeutig für die einfache Vererbung. Sie werden auch verwendet, um Mehrfachvererbungsdiagramme darzustellen. In diesem Thema finden Sie im [Mehrfachvererbung](http://msdn.microsoft.com/3b74185e-2beb-4e29-8684-441e51d2a2ca).  
  
 Bei der Vererbung enthält die abgeleitete Klasse die Member der Basisklasse plus alle neuen Member, die Sie hinzufügen. Daher kann eine abgeleitete Klasse auf Member der Basisklasse verweisen (es sei denn, diese Member werden in der abgeleiteten Klasse neu definiert). Der Bereichsauflösungsoperator (`::`) kann verwendet werden, um auf Member von direkten oder indirekten Basisklassen zu verweisen, wenn diese Member in der abgeleiteten Klasse neu definiert wurden. Betrachten Sie das folgende Beispiel:  
  
```cpp 
// deriv_SingleInheritance2.cpp  
// compile with: /EHsc /c  
#include <iostream>  
using namespace std;  
class Document {  
public:  
   char *Name;   // Document name.  
   void PrintNameOf();   // Print name.  
};  
  
// Implementation of PrintNameOf function from class Document.  
void Document::PrintNameOf() {  
   cout << Name << endl;  
}  
  
class Book : public Document {  
public:  
   Book( char *name, long pagecount );  
private:  
   long  PageCount;  
};  
  
// Constructor from class Book.  
Book::Book( char *name, long pagecount ) {  
   Name = new char[ strlen( name ) + 1 ];  
   strcpy_s( Name, strlen(Name), name );  
   PageCount = pagecount;  
};  
```  
  
 Beachten Sie, dass der Konstruktor für `Book`, (`Book::Book`), Zugriff auf Datenmember, `Name` hat. In einem Programm kann ein Objekt vom Typ `Book` erstellt und wie folgt verwendet werden:  
  
```cpp 
//  Create a new object of type Book. This invokes the  
//   constructor Book::Book.  
Book LibraryBook( "Programming Windows, 2nd Ed", 944 );  
  
...  
  
//  Use PrintNameOf function inherited from class Document.  
LibraryBook.PrintNameOf();  
```  
  
 Wie das obige Beispiel zeigt, werden Klassenmember und geerbte Daten und Funktionen identisch verwendet. Wenn die Implementierung für die Klasse `Book` eine Neuimplementierung der Funktion `PrintNameOf` aufruft, kann die Funktion, die der `Document`-Klasse angehört, nur durch den Bereichsauflösungsoperator (`::`) aufgerufen werden:  
  
```cpp 
// deriv_SingleInheritance3.cpp  
// compile with: /EHsc /LD  
#include <iostream>  
using namespace std;  
  
class Document {  
public:  
   char *Name;          // Document name.  
   void  PrintNameOf() {}  // Print name.  
};  
  
class Book : public Document {  
   Book( char *name, long pagecount );  
   void PrintNameOf();  
   long  PageCount;  
};  
  
void Book::PrintNameOf() {  
   cout << "Name of book: ";  
   Document::PrintNameOf();  
}  
```  
  
 Zeiger und Verweise auf abgeleitete Klassen können implizit in Zeiger und Verweise auf ihre Basisklassen konvertiert werden, wenn es eine erreichbare, eindeutige Basisklasse gibt. Der folgende Code veranschaulicht dieses Konzept unter Verwendung von Zeigern (das gleiche Prinzip gilt für Verweise):  
  
```cpp 
// deriv_SingleInheritance4.cpp  
// compile with: /W3  
struct Document {  
   char *Name;  
   void PrintNameOf() {}  
};  
  
class PaperbackBook : public Document {};  
  
int main() {  
   Document * DocLib[10];   // Library of ten documents.  
   for (int i = 0 ; i < 5 ; i++)  
      DocLib[i] = new Document;  
   for (int i = 5 ; i < 10 ; i++)  
      DocLib[i] = new PaperbackBook;  
}  
```  
  
 Im vorherigen Beispiel werden verschiedene Typen erstellt. Da diese Typen aber alle von der `Document`-Klasse abgeleitet werden, gibt es eine implizite Konvertierung zu `Document *`. Folglich ist `DocLib` eine "heterogene Liste" (eine Liste, in der nicht alle Objekte vom gleichen Typ sind) mit verschiedene Arten von Objekten.  
  
 Da die `Document`-Klasse eine `PrintNameOf`-Funktion aufweist, kann sie den Namen jedes Buch in der Bibliothek drucken. Möglicherweise lässt sie jedoch einen Teil der spezifische Informationen zum Typ des Dokuments weg (Seitenanzahl für `Book`, Anzahl von Bytes für `HelpFile` usw.).  
  
> [!NOTE]
>  Die Basisklasse zu zwingen, eine Funktion wie `PrintNameOf` zu implementieren, führt häufig nicht zum optimalen Entwurf. [Virtuelle Funktionen](../cpp/virtual-functions.md) bieten andere Entwurfsalternativen.  