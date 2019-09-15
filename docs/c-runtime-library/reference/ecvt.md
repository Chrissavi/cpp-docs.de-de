---
title: _ecvt
ms.date: 04/05/2018
api_name:
- _ecvt
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ecvt
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
ms.openlocfilehash: 9f91733c566c1782d5ccfc9a7c01e490a5915a85
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942047"
---
# <a name="_ecvt"></a>_ecvt

Konvertiert eine **doppelte** Zahl in eine Zeichenfolge. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [_ecvt_s](ecvt-s.md).

## <a name="syntax"></a>Syntax

```C
char *_ecvt(
   double value,
   int count,
   int *dec,
   int *sign
);
```

### <a name="parameters"></a>Parameter

*value*<br/>
Zu konvertierende Zahl.

*count*<br/>
Anzahl der gespeicherten Ziffern.

*dec*<br/>
Gespeicherte Position der Dezimalstelle.

*sign*<br/>
Vorzeichen der konvertierten Zahl.

## <a name="return-value"></a>Rückgabewert

**_ecvt** gibt einen Zeiger auf die Zeichenfolge der Ziffern zurück. **Null** , wenn ein Fehler aufgetreten ist.

## <a name="remarks"></a>Hinweise

Die **_ecvt** -Funktion konvertiert eine Gleit Komma Zahl in eine Zeichenfolge. Der *value* -Parameter ist die zu konvertierende Gleit Komma Zahl. Diese Funktion speichert bis zum *zählen* der Ziffern des *Werts* als Zeichenfolge und fügt ein NULL-Zeichen (' \ 0 ') an. Wenn die Anzahl der Ziffern im *Wert* die *Anzahl überschreitet,* wird die nieder wertige Ziffer gerundet. Wenn weniger als *Zähl* Ziffern vorhanden sind, wird die Zeichenfolge mit Nullen aufgefüllt.

Die Gesamtanzahl von Ziffern, die von **_ecvt** zurückgegeben werden, überschreitet **_CVTBUFSIZE**nicht.

In der Zeichenfolge werden nur Ziffern gespeichert. Die Position des Dezimal Trennzeichens und das Vorzeichen des *Werts* können aus *Dec* abgerufen und nach dem-Befehl *signiert* werden. Der *Dec* -Parameter verweist auf einen ganzzahligen Wert, der die Position des Dezimal Trennzeichens in Bezug auf den Anfang der Zeichenfolge gibt. Der Wert 0 oder ein negativer Integer-Wert geben an, dass sich die Dezimalstelle links neben der ersten Ziffer befindet. Der *Sign* -Parameter verweist auf eine Ganzzahl, die das Vorzeichen der konvertierten Zahl angibt. Wenn der Integer-Wert 0 ist, ist die Zahl positiv. Andernfalls ist die Zahl negativ.

Der Unterschied zwischen **_ecvt** und **_fcvt** ist die Interpretation des *count* -Parameters. **_ecvt** interpretiert *count* als die Gesamtanzahl der Ziffern in der Ausgabe Zeichenfolge, wohingegen **_fcvt** die Anzahl als Anzahl der Ziffern nach dem Dezimaltrennzeichen *interpretiert.*

**_ecvt** und **_fcvt** verwenden einen einzelnen statisch zugeordneten Puffer für die Konvertierung. Bei jedem Aufruf dieser Routinen wird das Ergebnis des vorherigen Aufrufs zerstört.

Diese Funktion überprüft ihre Parameter. Wenn *Dec* oder *Sign* **null**ist oder *count* 0 ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird **errno** auf **EINVAL** festgelegt, und es wird **null** zurückgegeben.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_ecvt**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_ecvt.c
// compile with: /W3
// This program uses _ecvt to convert a
// floating-point number to a character string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int     decimal,   sign;
   char    *buffer;
   int     precision = 10;
   double  source = 3.1415926535;

   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996
   // Note: _ecvt is deprecated; consider using _ecvt_s instead
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",
           source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
