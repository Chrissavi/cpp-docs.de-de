---
title: Multibyte- und Breitzeichen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- character data types [C]
- Unicode [C++], wide character set
- types [C], character
- characters [C++], wide
- international applications [C++], character display
- multibyte characters [C++]
- wide characters [C++]
- characters [C++], codes
- character codes [C++], wide
- character codes [C++], multibyte
ms.assetid: 1943c469-200d-4724-b18f-781d70520f9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc259a75ab12352a7d0029241496aea22803152a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384199"
---
# <a name="multibyte-and-wide-characters"></a>Mehrbyte- und Breitzeichen
Ein Mehrbytezeichen ist ein Zeichen, das aus einem oder mehreren Bytesequenzen besteht. Jede Bytesequenz stellt ein einzelnes Zeichen im erweiterten Zeichensatz dar. Mehrbytezeichen werden in Zeichensätzen wie Kanji verwendet.  
  
 Breitzeichen sind mehrsprachige Zeichencodes, deren Breite immer 16 Bit beträgt. Der Typ für Zeichenkonstanten ist `char`. Der Typ ist für Breitzeichen ist `wchar_t`. Da Breitzeichen stets eine feste Größe aufweisen, vereinfachen diese das Programmieren mit internationalen Zeichensätzen.  
  
 Das Breitzeichen-Zeichenfolgenliteral `L"hello"` wird zu einem Array mit sechs Ganzzahlen vom Typ `wchar_t`.  
  
```  
{L'h', L'e', L'l', L'l', L'o', 0}  
```  
  
 Die Unicode-Spezifikation entspricht der Spezifikation für Breitzeichen. Die Laufzeitbibliotheksroutinen für Übersetzungen zwischen Multibyte- und Breitzeichen enthalten `mbstowcs`, `mbtowc`, `wcstombs` und `wctomb`.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Bezeichner](../c-language/c-identifiers.md)