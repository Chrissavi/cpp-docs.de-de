---
title: _mbclen, mblen, _mblen_l
ms.date: 11/04/2016
apiname:
- _mbclen
- mblen
- _mblen_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mblen
- ftclen
- _mbclen
- tclen
- _ftclen
- _tclen
- mbclen
helpviewer_keywords:
- tclen function
- _mblen_l function
- _tclen function
- mblen_l function
- _mbclen function
- mbclen function
- mblen function
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
ms.openlocfilehash: dddf7d3a1705460d2c8d42cc1b36230d7bdaf942
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434385"
---
# <a name="mbclen-mblen-mblenl"></a>_mbclen, mblen, _mblen_l

Ruft die Länge ab und bestimmt die Gültigkeit eines Multibytezeichens.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
size_t _mbclen(
   const unsigned char *c
);
int mblen(
   const char *mbstr,
   size_t count
);
int _mblen_l(
   const char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Multibytezeichen.

*mbstr*<br/>
Adresse einer Multibytezeichen-Bytesequenz.

*count*<br/>
Anzahl zu überprüfender Bytes.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**_mbclen** gibt 1 oder 2, je nachdem, ob das Multibytezeichen *c* 1 oder 2 Bytes lang ist. Es gibt keine Fehlerrückgabe für **_mbclen**. Wenn *Mbstr* nicht **NULL**, **Mblen** gibt die Länge in Byte des multibytezeichens zurück. Wenn *Mbstr* ist **NULL** oder das Objekt zeigt auf das Breitzeichen Null-Zeichen, **Mblen** gibt 0 zurück. Wenn das Objekt, *Mbstr* verweist auf ein gültiges Multibytezeichen innerhalb der ersten nicht bildet *Anzahl* Zeichen **Mblen** gibt-1 zurück.

## <a name="remarks"></a>Hinweise

Die **_mbclen** Funktion gibt die Länge in Byte des multibytezeichens zurück *c*. Wenn *c* verweist nicht auf das führende Byte eines multibytezeichens laut eines impliziten Aufrufs von **_ismbblead**, das Ergebnis des **_mbclen** ist unvorhersehbar.

**Mblen** gibt die Länge in Bytes zurück *Mbstr* , wenn sie ein gültiges Multibytezeichen ist und die Gültigkeit der Multibytezeichen der Codepage zugeordnet bestimmt. **Mblen** untersucht *Anzahl* oder weniger Bytes, die in enthaltenen *Mbstr*, aber nicht länger als **MB_CUR_MAX** Bytes.

Der Ausgabewert ist von der Kategorieeinstellung **LC_CTYPE** des Gebietsschemas betroffen. Weitere Informationen finden Sie unter [setlocale](setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das **_l**-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem **_l**-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tclen**|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus|**_mbclen**|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_mbclen**|\<mbstring.h>|
|**mblen**|\<stdlib.h>|
|**_mblen_l**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_mblen.c
/* illustrates the behavior of the mblen function
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    int      i;
    char    *pmbc = (char *)malloc( sizeof( char ) );
    wchar_t  wc   = L'a';

    printf( "Convert wide character to multibyte character:\n" );
    wctomb_s( &i, pmbc, sizeof(char), wc );
    printf( "   Characters converted: %u\n", i );
    printf( "   Multibyte character: %x\n\n", *pmbc );

    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );

    pmbc = NULL;
    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );
}
```

```Output
Convert wide character to multibyte character:
   Characters converted: 1
   Multibyte character: 61

Length in bytes of multibyte character 61: 1
Length in bytes of NULL multibyte character 0: 0
```

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
