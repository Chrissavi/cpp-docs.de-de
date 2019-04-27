---
title: _lfind_s
ms.date: 11/04/2016
apiname:
- _lfind_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- lfind_s
- _lfind_s
helpviewer_keywords:
- linear searching
- keys, finding in arrays
- lfind_s function
- arrays [CRT], searching
- searching, linear
- _lfind_s function
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
ms.openlocfilehash: 08c04d9d1ca69998d54304c96468298013907179
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286426"
---
# <a name="lfinds"></a>_lfind_s

Führt eine lineare Suche für den angegebenen Schlüssel aus. Dies ist eine Version von [_lfind](lfind.md) mit Sicherheitserweiterungen, wie in den [Sicherheitsfunktionen in CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
void *_lfind_s(
   const void *key,
   const void *base,
   unsigned int *num,
   size_t size,
   int (__cdecl *compare)(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>Parameter

*key*<br/>
Das Objekt, nach dem gesucht werden soll.

*base*<br/>
Zeiger auf die Basis der Suchdaten.

*Anzahl*<br/>
Die Anzahl der Arrayelemente.

*size*<br/>
Die Größe der Arrayelemente in Bytes.

*compare*<br/>
Zeiger auf die Vergleichsroutine. Der erste Parameter ist der *Kontext* Zeiger. Der zweite Parameter ist ein Zeiger auf den Schlüssel für die Suche. Der dritte Parameter ist ein Zeiger auf das Arrayelement, das mit dem Schlüssel verglichen werden soll.

*context*<br/>
Ein Zeiger auf ein Objekt, auf das in der Vergleichsfunktion zugegriffen werden kann.

## <a name="return-value"></a>Rückgabewert

Wenn der Schlüssel gefunden wird, **_lfind_s** gibt einen Zeiger auf das Element des Arrays, an *Basis* entspricht *Schlüssel*. Wenn der Schlüssel nicht gefunden wird, **_lfind_s** gibt **NULL**.

Wenn ungültige Parameter an die Funktion übergeben werden, ruft sie den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parametervalidierung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktion gibt **NULL**.

### <a name="error-conditions"></a>Fehlerbedingungen

|Key|Basis|compare|num|size|errno|
|---------|----------|-------------|---------|----------|-----------|
|**NULL**|any|any|any|any|**EINVAL**|
|any|**NULL**|any|!= 0|any|**EINVAL**|
|any|any|any|any|Null|**EINVAL**|
|any|any|**NULL**|ein|any|**EINVAL**|

## <a name="remarks"></a>Hinweise

Die **_lfind_s** Funktion führt eine lineare Suche für den Wert *Schlüssel* in ein Array von *Anzahl* Elementen, die jeweils von *Breite* Bytes. Im Gegensatz zu **Bsearch_s**, **_lfind_s** erfordert keine Arrays, das sortiert werden. Die *Basis* Argument ist ein Zeiger auf die Basis des Arrays, das gesucht werden soll. Die *vergleichen* Argument ist ein Zeiger auf eine benutzerdefinierte Routine, die zwei Elemente des Arrays vergleicht und dann gibt einen Wert, der ihre Beziehung angibt. **_lfind_s** Aufrufe der *vergleichen* -Routine einmal oder mehrere Male während der Suche, und übergeben die *Kontext* Zeiger und Verweise auf zwei Arrayelemente bei jedem Aufruf. Die *vergleichen* Routine muss die Elemente vergleichen und Zurückgeben von ungleich Null (d. h., dass die Elemente unterscheiden) oder 0 (d.h. die Elemente sind identisch).

**_lfind_s** ähnelt **_lfind** mit Ausnahme der Hinzufügung von der *Kontext* Zeiger auf den Argumenten der Vergleichsfunktion und der Parameterliste der Funktion. Die *Kontext* Zeiger ist nützlich, wenn die durchsuchte Datenstruktur Teil eines Objekts ist und die *vergleichen* Funktion, die auf Member des Objekts zugreifen muss. Die *vergleichen* Funktion kann den void-Zeiger umgewandelt, in das entsprechende Objekt und auf Member des Objekts. Das Hinzufügen der *Kontext* -Parameters macht **_lfind_s** sicherer, da weiterer Kontext verwendet werden kann, um Wiedereintreten mit der Verwendung statischer Variablen zur Daten zur Verfügung stellen zu vermeiden. die *vergleichen* Funktion.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_lfind_s**|\<search.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```cpp
// crt_lfind_s.cpp
// This program uses _lfind_s to search a string array,
// passing a locale as the context.
// compile with: /EHsc
#include <stdlib.h>
#include <stdio.h>
#include <search.h>
#include <process.h>
#include <locale.h>
#include <locale>
#include <windows.h>
using namespace std;

// The sort order is dependent on the code page.  Use 'chcp' at the
// command line to change the codepage.  When executing this application,
// the command prompt codepage must match the codepage used here:

#define CODEPAGE_850

#ifdef CODEPAGE_850
// Codepage 850 is the OEM codepage used by the command line,
// so \x00e1 is the German Sharp S

char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };

#define GERMAN_LOCALE "German_Germany.850"

#endif

#ifdef CODEPAGE_1252
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df
   // for the German Sharp S
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };

#define GERMAN_LOCALE "German_Germany.1252"

#endif

// The context parameter lets you create a more generic compare.
// Without this parameter, you would have stored the locale in a
// static variable, thus making it vulnerable to thread conflicts
// (if this were a multithreaded program).

int compare( void *pvlocale, const void *str1, const void *str2)
{
    char *s1 = *(char**)str1;
    char *s2 = *(char**)str2;

    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));

    return use_facet< collate<char> >(loc).compare(
       s1, s1+strlen(s1),
       s2, s2+strlen(s2) );
}

void find_it( char *key, char *array[], unsigned int num, locale &loc )
{
   char **result = (char **)_lfind_s( &key, array,
                      &num, sizeof(char *), compare, &loc );
   if( result )
      printf( "%s found\n", *result );
   else
      printf( "%s not found\n", key );
}

int main( )
{
   find_it( "weit", array1, sizeof(array1)/sizeof(char*), locale(GERMAN_LOCALE) );
}
```

```Output
weit found
```

## <a name="see-also"></a>Siehe auch

[Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort_s](qsort-s.md)<br/>
[_lfind](lfind.md)<br/>
