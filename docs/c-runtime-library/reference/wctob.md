---
title: wctob
ms.date: 11/04/2016
apiname:
- wctob
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wctob
helpviewer_keywords:
- wide characters, converting
- wctob function
- characters, converting
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
ms.openlocfilehash: 9c977bc204f4c9428a4aae09300269b1ed82d53e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498955"
---
# <a name="wctob"></a>wctob

Bestimmt, ob ein Breitzeichen einem Multibytezeichen entspricht und gibt dessen Multibytezeichen-Darstellung zurück.

## <a name="syntax"></a>Syntax

```C
int wctob(
   wint_t wchar
);
```

### <a name="parameters"></a>Parameter

*wchar*<br/>
Zu übersetzender Wert.

## <a name="return-value"></a>Rückgabewert

Wenn **wcdeb** ein breit Zeichen erfolgreich konvertiert, wird dessen multibytezeichendarstellung nur dann zurückgegeben, wenn das Multibytezeichen genau ein Byte lang ist. Wenn **wcesb** ein breit Zeichen erkennt, das nicht in ein Multibytezeichen konvertiert werden kann, oder wenn das Multibytezeichen nicht genau ein Byte lang ist, wird "-1" zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **wcdeb** -Funktion konvertiert ein in *WCHAR* enthaltenes breit Zeichen in das entsprechende Multibytezeichen, das vom Return **int** -Wert übergeben wird, wenn das Multibytezeichen genau ein Byte lang ist.

Wenn **wcdeb** nicht erfolgreich war und kein entsprechendes Multibytezeichen gefunden wurde, legt die Funktion **errno** auf **EILSEQ** fest und gibt-1 zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**wctob**|\<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Dieses Programm veranschaulicht das Verhalten der **wcstomsb** -Funktion.

```C
// crt_wctob.c
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    int     bChar = 0;
    wint_t  wChar = 0;

    // Set the corresponding wide character to exactly one byte.
    wChar = (wint_t)'A';

    bChar = wctob( wChar );
    if (bChar == WEOF)
    {
        printf( "No corresponding multibyte character was found.\n");
    }
    else
    {
        printf( "Determined the corresponding multibyte character to"
                " be \"%c\".\n", bChar);
    }
}
```

```Output
Determined the corresponding multibyte character to be "A".
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
