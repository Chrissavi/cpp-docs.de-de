---
title: isalpha, iswalpha, _isalpha_l, _iswalpha_l
ms.date: 11/04/2016
apiname:
- iswalpha
- _iswalpha_l
- isalpha
- _isalpha_l
apilocation:
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _istalpha
- _ismbcalpha_l
- isalpha
- _isalpha_l
- iswalpha
- _istalpha_l
- _iswalpha_l
helpviewer_keywords:
- _iswalpha_l function
- _isalpha_l function
- _ismbcalpha_l function
- _istalpha_l function
- _ismbcalpha function
- isalpha function
- iswalpha function
- istalpha function
- _istalpha function
ms.assetid: ed6cc2be-c4b0-4475-87ac-bc06d8c23064
ms.openlocfilehash: 47b7e43172884524e50e332dcb421e84a99b9806
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591749"
---
# <a name="isalpha-iswalpha-isalphal-iswalphal"></a>isalpha, iswalpha, _isalpha_l, _iswalpha_l

Bestimmt, ob eine ganze Zahl ein alphabetisches Zeichen darstellt.

## <a name="syntax"></a>Syntax

```C
int isalpha(
   int c
);
int iswalpha(
   wint_t c
);
int _isalpha_l(
   int c,
   _locale_t locale
);
int _iswalpha_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu testende ganze Zahl.

*locale*<br/>
Das statt des aktuellen Gebietsschemas zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen gibt ungleich NULL, wenn *c* eine bestimmte Darstellung eines alphabetischen Zeichens ist. **Isalpha** gibt einen Wert ungleich NULL zurück, wenn *c* innerhalb der Bereiche A - Z oder a - Z. **iswalpha_l** gibt einen Wert ungleich NULL nur für Breitzeichen zurück, für die [Iswupper](isupper-isupper-l-iswupper-iswupper-l.md) oder **Iswlower** ungleich NULL ist, d. h. für jedes Breitzeichen Zeichen, das ein von der Implementierung definierten für den **Iswcntrl**, **Iswdigit**, **Iswpunct**, oder **Iswspace** ungleich NULL ist. Jede dieser Routinen gibt 0 zurück, wenn *c* die testbedingung nicht erfüllt.

Die Versionen dieser Funktionen, die **_l** -Suffix verwenden den Gebietsschemaparameter, der übergeben wird, anstelle des aktuellen Gebietsschemas. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Das Verhalten der **Isalpha** und **_isalpha_l** ist undefiniert, wenn *c* nicht EOF-Markierung ist oder im Bereich von 0 bis 0xFF liegt. Wenn eine CRT-Debugbibliothek verwendet wird und *c* ist keine dieser Werte, lösen die Funktionen eine Assertion.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istalpha**|**isalpha**|**_ismbcalpha**|**iswalpha**|
|**_istalpha_l**|**_isalpha_l**|**_ismbcalpha_l**|**_iswalpha_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**isalpha**|\<ctype.h>|
|**iswalpha**|\<ctype.h> oder \<wchar.h>|
|**_isalpha_l**|\<ctype.h>|
|**_iswalpha_l**|\<ctype.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
