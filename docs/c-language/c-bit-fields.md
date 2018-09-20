---
title: C-Bitfelder | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- bitfields
- bit fields
ms.assetid: 9faf74c4-7fd5-4b44-ad18-04485193d06e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b3e828af6232dec6ebfb4558fdb8501c7f90abb
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757486"
---
# <a name="c-bit-fields"></a>C-Bitfelder
Neben Deklaratoren für Member einer Struktur oder Union kann ein Strukturdeklarator auch eine angegebene Anzahl von Bits sein, die als "Bitfeld" bezeichnet wird. Seine Länge wird vom Deklarator für den Feldnamen durch einen Doppelpunkt abgegrenzt. Ein Bitfeld wird als Ganzzahltyp interpretiert.  
  
## <a name="syntax"></a>Syntax

*struct-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-specifier* *declarator*<sub>opt</sub> **:** *constant-expression*
  
*constant-expression* gibt die Breite des Felds in Bits an. *type-specifier* für `declarator` muss `unsigned int`, **signed int** oder `int` sein, und *constant-expression* muss ein nicht negativer Ganzzahlwert sein. Falls der Wert 0 (null) ist, weist die Deklaration keinen `declarator` auf. Arrays aus Bitfeldern, Zeiger auf Bitfelder und Funktionen, die Bitfelder zurückgeben, sind nicht zulässig. Der optionale `declarator` benennt das Bitfeld. Bitfelder können nur als Teil einer Struktur deklariert werden. Der address-of-Operator (**&**) kann nicht auf Bitfeldkomponenten angewendet werden.  
  
Auf unbenannte Bitfelder kann nicht verwiesen werden, und deren Inhalt zur Laufzeit ist unvorhersehbar. Sie können als "Dummy"-Felder zu Ausrichtungszwecken verwendet werden. Ein unbenanntes Bitfeld, dessen Breite auf 0 festgelegt ist, garantiert, dass der Speicher für das in *struct-declaration-list* nachfolgende Element an einer `int`-Grenze beginnt.  
  
Bitfelder müssen lang genug sein, um das Bitmuster zu enthalten. Beispielsweise sind die folgenden beiden Anweisungen nicht gültig:  
  
```  
short a:17;        /* Illegal! */  
int long y:33;     /* Illegal! */  
```  
  
In diesem Beispiel wird ein zweidimensionales Array von Strukturen mit dem Namen `screen` definiert.  
  
```  
struct   
{  
    unsigned short icon : 8;  
    unsigned short color : 4;  
    unsigned short underline : 1;  
    unsigned short blink : 1;  
} screen[25][80];  
```  
  
Das Array enthält 2.000 Elemente. Jedes Element ist eine einzelne Struktur, die vier Bitfeldmember enthält: `icon`, `color`, `underline` und `blink`. Die Größe der einzelnen Strukturen beträgt zwei Bytes.  
  
Bitfelder weisen die gleiche Semantik wie der Ganzzahltyp auf. Dies bedeutet, dass ein Bitfeld in Ausdrücken auf genau die gleiche Weise verwendet wird, wie eine Variable des gleichen Basistyps, unabhängig davon, wie viele Bits das Bitfeld aufweist.  
  
**Microsoft-spezifisch**  
  
Bitfelder, die als `int` definiert sind, werden als signiert behandelt. Eine Microsoft-Erweiterung für den ANSI C-Standard ermöglicht die Typen `char` und **long** (sowohl **signed** als auch `unsigned`) in Bitfeldern. Unbenannte Bitfelder mit Basistyp **long**, **short** oder `char` (**signed** oder `unsigned`) erzwingen eine Ausrichtung an einer Grenze, die dem Basistyp entspricht.  
  
Bitfelder werden innerhalb einer Ganzzahl vom niedrigstwertigen hin zum höchstwertigen Bit angeordnet. Im folgenden Code etwa  
  
```  
struct mybitfields  
{  
    unsigned short a : 4;  
    unsigned short b : 5;  
    unsigned short c : 7;  
} test;  
  
int main( void );  
{  
    test.a = 2;  
    test.b = 31;  
    test.c = 0;  
}  
```  
  
wären die Bits folgendermaßen angeordnet:  
  
```  
00000001 11110010  
cccccccb bbbbaaaa  
```  
  
Da die Familie der 8086-Prozessoren das niedrige Byte ganzzahliger Werte vor dem hohen Byte speichert, wird die oben stehende Ganzzahl `0x01F2` im physischen Speicher als `0xF2` gefolgt von `0x01` gespeichert.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
[Strukturdeklarationen](../c-language/structure-declarations.md)