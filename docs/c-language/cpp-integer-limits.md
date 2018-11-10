---
title: Ganzzahlige Grenzen in C++
ms.date: 01/29/2018
helpviewer_keywords:
- limits, integer
- limits, integer constants
- integer limits
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
ms.openlocfilehash: 057da1ac8e4549a05d10a01cc3aead678045d9c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548290"
---
# <a name="c-integer-limits"></a>Ganzzahlige Grenzen in C++

**Microsoft-spezifisch**

Die Grenzwerte für ganzzahlige Typen sind in der folgenden Tabelle aufgeführt. Diese Grenzwerte werden in der Standardheaderdatei LIMITS.H definiert. Microsoft C ermöglicht zudem die Deklaration von Ganzzahlvariablen mit angegebener Größe, die ganzzahlige Typen der Größe 8-, 16-, oder 32-Bit sind. Weitere Informationen über ganze Zahlen mit angepasster Größe finden Sie unter [Angepasste Ganzzahltypen](../c-language/c-sized-integer-types.md).

## <a name="limits-on-integer-constants"></a>Grenzwerte für ganzzahlige Konstanten

|**Konstante**|Bedeutung|Wert|
|------------------|-------------|-----------|
|**CHAR_BIT**|Anzahl von Bits in der kleinsten Variable, die kein Bitfeld ist.|8|
|**SCHAR_MIN**|Minimalwert für eine Variable vom Typ **signed char**.|-128|
|**SCHAR_MAX**|Maximalwert für eine Variable vom Typ **signed char**.|127|
|**UCHAR_MAX**|Maximalwert für eine Variable vom Typ **unsigned char**.|255 (0xff)|
|**CHAR_MIN**|Minimalwert für eine Variable vom Typ **char**.|-128; 0 wenn /J-Option verwendet|
|**CHAR_MAX**|Maximalwert für eine Variable vom Typ **char**.|127; 255 wenn /J-Option verwendet|
|**MB_LEN_MAX**|Maximale Anzahl von Bytes in einer Konstante mit mehreren Zeichen.|5|
|**SHRT_MIN**|Minimalwert für eine Variable vom Typ **short**.|-32768|
|**SHRT_MAX**|Maximalwert für eine Variable vom Typ **short**.|32767|
|**USHRT_MAX**|Maximalwert für eine Variable vom Typ **unsigned short**.|65535 (0xffff)|
|**INT_MIN**|Minimalwert für eine Variable vom Typ **int**.|-2147483647 - 1|
|**INT_MAX**|Maximalwert für eine Variable vom Typ **int**.|2147483647|
|**UINT_MAX**|Maximalwert für eine Variable vom Typ **unsigned int**.|4294967295 (0xffffffff)|
|**LONG_MIN**|Minimalwert für eine Variable vom Typ **long**.|-2147483647 - 1|
|**LONG_MAX**|Maximalwert für eine Variable vom Typ **long**.|2147483647|
|**ULONG_MAX**|Maximalwert für eine Variable vom Typ **unsigned long**.|4294967295 (0xffffffff)|

Wenn ein Wert die größte Ganzzahldarstellung übersteigt, generiert der Microsoft-Compiler einen Fehler.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[C-Ganzzahlkonstanten](../c-language/c-integer-constants.md)
