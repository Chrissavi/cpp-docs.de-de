---
title: _mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l
ms.date: 11/04/2016
apiname:
- _mbsnbicoll_l
- _mbsnbcoll_l
- _mbsnbcoll
- _mbsnbicoll
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
apitype: DLLExport
f1_keywords:
- mbsnbicoll
- mbsnbcoll
- mbsnbicoll_l
- _mbsnbcoll
- _mbsnbicoll
- _ftcsnicoll
- _ftcsncoll
- mbsnbcoll_l
helpviewer_keywords:
- _mbsnbcoll_l function
- mbsnbcoll_l function
- _mbsnbcoll function
- _tcsnicoll function
- mbsnbcoll function
- mbsnbicoll_l function
- mbsnbicoll function
- _tcsncoll function
- _mbsnbicoll function
- _mbsnbicoll_l function
- tcsncoll function
- tcsnicoll function
ms.assetid: d139ed63-ccba-4458-baa2-61cbcef03e94
ms.openlocfilehash: c18faa3c93969a683b3ee3ef58dd02e1c1ae61f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665197"
---
# <a name="mbsnbcoll-mbsnbcolll-mbsnbicoll-mbsnbicolll"></a>_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l

Vergleicht *n* Bytes von zwei Multibyte-Zeichenfolgen mithilfe von multibyte-Codepage-Informationen.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _mbsnbcoll(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbcoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
int _mbsnbicoll(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbicoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*Zeichenfolge1*, *Zeichenfolge2*<br/>
Zu vergleichende Zeichenfolgen.

*count*<br/>
Anzahl der zu vergleichenden Bytes.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert gibt an, die Beziehung der Teilzeichenfolgen von *string1* und *Zeichenfolge2*.

|Rückgabewert|Beschreibung|
|------------------|-----------------|
|< 0|*Zeichenfolge1* Teilzeichenfolge höchstens *Zeichenfolge2* Teilzeichenfolge.|
|0|*Zeichenfolge1* identisch *Zeichenfolge2* Teilzeichenfolge.|
|> 0|*Zeichenfolge1* größer als *Zeichenfolge2* Teilzeichenfolge.|

Wenn *string1* oder *Zeichenfolge2* ist **NULL** oder *Anzahl* ist größer als **INT_MAX**, die ungültig parameterhandler wird aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **_NLSCMPERROR** und **Errno** zu **EINVAL**. Verwendung von **_NLSCMPERROR**, fügen Sie String.h oder MBSTRING.h ein.

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen sortiert höchstens die ersten *Anzahl* Bytes *string1* und *Zeichenfolge2* und gibt einen Wert, der angibt, der die Beziehung zwischen der resultierenden der Teilzeichenfolgen *string1* und *Zeichenfolge2*. Wenn das letzte Byte der Teilzeichenfolge von *string1* oder *Zeichenfolge2* ein führendes Byte, es ist nicht im Vergleich enthalten; diese Funktionen vergleichen nur vollständige Zeichen der Teilzeichenfolgen. **_mbsnbicoll** ist eine Groß-/Kleinschreibung Version **_mbsnbcoll**. Wie [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) und [_mbsnbicmp](mbsnbicmp-mbsnbicmp-l.md), **_mbsnbcoll** und **_mbsnbicoll** sortieren Sie die beiden Multibyte-Zeichenfolgen gemäß der lexikografische Reihenfolge gemäß der Mehrbyte [Codepage](../../c-runtime-library/code-pages.md) aktuell.

Bei manchen Codepages und entsprechenden Zeichensätzen kann die Reihenfolge der Zeichen im Zeichensatz möglicherweise von der lexikografischen Reihenfolge abweichen. Im "C "-Gebietsschema ist dies nicht der Fall: Die Reihenfolge der Zeichen im ASCII-Zeichensatz entspricht der lexikografischen Reihenfolge der Zeichen. In bestimmten europäischen Codepages beispielsweise steht im Zeichensatz das Zeichen "a" (Wert 0x61) vor dem Zeichen "ä" (Wert 0xE4), das Zeichen "ä" steht lexikografisch gesehen jedoch vor dem Zeichen "a". Um einen lexikografischen Vergleich von Zeichenfolgen nach Bytes in einem solchen auszuführen, verwenden **_mbsnbcoll** statt **_mbsnbcmp**; verwenden Sie zum Überprüfen, die nur die zeichenfolgengleichheit **_mbsnbcmp**.

Da die **Coll** Funktionen Zeichenfolgen für Vergleiche, lexikografisch sortieren, während die **Cmp** Funktionen einfach Gleichheit Zeichenfolge, die **Coll** Funktionen sind sehr viel langsamer als die entsprechenden **Cmp** Versionen. Aus diesem Grund die **Coll** Funktionen sollten verwendet werden, nur, wenn es in der aktuellen Codepage ein Unterschied zwischen der Reihenfolge des Zeichensatzes und der lexikografischen Reihenfolge gibt, und dieser Unterschied für den Zeichenfolgenvergleich relevant ist.

Der Ausgabewert ist von der Kategorieeinstellung **LC_CTYPE** des Gebietsschemas betroffen. Weitere Informationen finden Sie unter [setlocale](setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das **_l**-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem **_l**-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncoll**|[_strncoll](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|**_mbsnbcoll**|[_wcsncoll](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|
|**_tcsncoll_l**|[_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|**_mbsnbcoll_l**|[_wcsncoll_l](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|
|**_tcsnicoll**|[_strnicoll](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|**_mbsnbicoll**|[_wcsnicoll](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|
|**_tcsnicoll_l**|[_strnicoll_l](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|**_mbsnbicoll_l**|[_wcsnicoll_l](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_mbsnbcoll**|\<mbstring.h>|
|**_mbsnbcoll_l**|\<mbstring.h>|
|**_mbsnbicoll**|\<mbstring.h>|
|**_mbsnbicoll_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
