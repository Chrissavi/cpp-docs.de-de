---
title: _ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l
ms.date: 4/2/2020
api_name:
- _ismbcalpha
- _ismbcalnum
- _ismbcdigit
- _ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha_l
- _o__ismbcalnum
- _o__ismbcalnum_l
- _o__ismbcalpha
- _o__ismbcalpha_l
- _o__ismbcdigit
- _o__ismbcdigit_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbcdigit
- ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha
- ismbcalnum
- ismbcdigit
- ismbcalpha
- _ismbcalnum_l
- _ismbcalnum
- ismbcdigit_l
helpviewer_keywords:
- ismbcalpha function
- _ismbcalnum function
- ismbcdigit_l function
- _ismbcalnum_l function
- _ismbcdigit function
- ismbcalnum function
- _ismbcalpha_l function
- ismbcdigit function
- _ismbcalpha function
- _ismbcdigit_l function
- ismbcalnum_l function
- ismbcalpha_l function
ms.assetid: 12d57925-aebe-46e0-80b0-82b84c4c31ec
ms.openlocfilehash: 6e650c15ca2b7d3b448d5480a6b1f09769100171
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918555"
---
# <a name="_ismbcalnum-_ismbcalnum_l-_ismbcalpha-_ismbcalpha_l-_ismbcdigit-_ismbcdigit_l"></a>_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l

Überprüft, ob ein Multibytezeichen ein alphanumerisches Zeichen ist oder aus einem Buchstaben oder einer Ziffer besteht.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _ismbcalnum
(
   unsigned int c
);
int _ismbcalnum_l
(
   unsigned int c,
   _locale_t locale
);
int _ismbcalpha
(
   unsigned int c
);
int _ismbcalpha_l
(
   unsigned int c,
   _locale_t locale
);
int _ismbcdigit
(
   unsigned int c
);
int _ismbcdigit_l
(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*scher*<br/>
Zu testende Zeichen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen gibt einen Wert ungleich 0 zurück, wenn das Zeichen die Testbedingung erfüllt, bzw. 0, wenn es sie nicht erfüllt. Wenn *c*<= 255 und es eine entsprechende **_ismbb** Routine gibt (z. b. **_ismbcalnum** entspricht **_ismbbalnum**), ist das Ergebnis der Rückgabewert der entsprechenden **_ismbb** -Routine.

## <a name="remarks"></a>Hinweise

Jede dieser Routinen testet ein angegebenes Multibytezeichen auf eine angegebene Bedingung.

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch das übergebene Gebiets Schema anstelle des aktuellen Gebiets Schemas für Ihr vom Gebiets Schema abhängiges Verhalten. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

|Routine|Testbedingung|Beispiel für Codepage 932|
|-------------|--------------------|---------------------------|
|**_ismbcalnum** **_ismbcalnum_l**|Alphanumerisch|Gibt nur dann einen Wert ungleich 0 (null) zurück, wenn *c* eine Einzel Byte Darstellung eines englischen ASCII-Buchstabens ist: siehe Beispiele für **_ismbcdigit** und **_ismbcalpha**.|
|**_ismbcalpha** **_ismbcalpha_l**|Alphabetisch|Gibt nur dann einen Wert ungleich 0 (null) zurück, wenn *c* eine Einzel Byte Darstellung eines englischen ASCII-Buchstabens ist: 0x41<=*c*<= 0x5A oder 0x61<=*c*<= 0x7a; oder ein Katakana-Buchstabe: 0xA6<=*c*<= 0xDF.|
|**_ismbcdigit** **_ismbcdigit**|Ziffer|Gibt nur dann einen Wert ungleich 0 (null) zurück, wenn *c* eine Einzel Byte Darstellung einer ASCII-Ziffer ist: 0x30<=*c*<= 0x39.|

Standardmäßig ist der globale Status dieser Funktion auf die Anwendung beschränkt. Informationen hierzu finden Sie unter [globaler Status in der CRT](../global-state.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_ismbcalnum** **_ismbcalnum_l**|\<mbstring.h>|
|**_ismbcalpha** **_ismbcalpha_l**|\<mbstring.h>|
|**_ismbcdigit** **_ismbcdigit_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Weitere Informationen

[Zeichen Klassifizierung](../../c-runtime-library/character-classification.md)<br/>
[_ismbc-Routinen](../../c-runtime-library/ismbc-routines.md)<br/>
[is-, ISW-Routinen](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Routinen](../../c-runtime-library/ismbb-routines.md)<br/>
