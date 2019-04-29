---
title: qsort_s
ms.date: 11/04/2016
apiname:
- qsort_s
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- qsort_s
helpviewer_keywords:
- arrays [C++], sorting
- quick-sort algorithm
- qsort_s function
- sorting arrays
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
ms.openlocfilehash: f3b8bbfeb8079322a174233f3d8048a6d1b51804
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358111"
---
# <a name="qsorts"></a>qsort_s

Führt eine schnelle Sortierung aus. Dies ist eine Version von [qsort](qsort.md) mit Sicherheitserweiterungen wie in den [Sicherheitsfunktionen in CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
void qsort_s(
   void *base,
   size_t num,
   size_t width,
   int (__cdecl *compare )(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>Parameter

*base*<br/>
Start des Zielarrays.

*Anzahl*<br/>
Arraygröße in Elementen.

*width*<br/>
Elementgröße in Bytes.

*compare*<br/>
Vergleichsfunktion. Das erste Argument ist der *Kontext* Zeiger. Das zweite Argument ist ein Zeiger auf die *Schlüssel* für die Suche. Das dritte Argument ist ein Zeiger auf das Arrayelement mit verglichen werden soll *Schlüssel*.

*context*<br/>
Ein Zeiger auf einen Kontext, d.h. alle möglichen-Objekt, das *vergleichen* -Routine zugreifen muss.

## <a name="remarks"></a>Hinweise

Die **Qsort_s** -Funktion implementiert einen Schnellsortierungsalgorithmus, um ein Array von sortieren *Anzahl* Elementen, die jeweils von *Breite* Bytes. Das Argument *Basis* ist ein Zeiger auf die Basis des Arrays, das sortiert werden. **Qsort_s** überschreibt dieses Array mit den sortierten Elementen. Das Argument *vergleichen* ist ein Zeiger auf eine benutzerdefinierte Routine, die zwei Elemente des Arrays vergleicht und gibt einen Wert, der ihre Beziehung angibt. **Qsort_s** Aufrufe der *vergleichen* -Routine einmal oder mehrere Male während der Sortierung, die Übergabe von Zeigern auf zwei Arrayelemente bei jedem Aufruf:

```C
compare( context, (void *) & elem1, (void *) & elem2 );
```

Die Routine muss die Elemente vergleichen und einen der folgenden Werte zurückgeben:

|Rückgabewert|Beschreibung|
|------------------|-----------------|
|< 0|**elem1** kleiner als **elem2**|
|0|**elem1** entspricht **elem2**|
|> 0|**elem1** größer als **elem2**|

Das Array wird in aufsteigender Reihenfolge sortiert, wie von der Vergleichsfunktion definiert. Kehren Sie die Richtung „größer als“ und „kleiner als“ in der Vergleichsfunktion um, um ein Array in absteigender Reihenfolge zu sortieren.

Wenn ungültige Parameter an die Funktion übergeben werden, ruft sie den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parametervalidierung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, und klicken Sie dann die Funktion zurückgibt und **Errno** nastaven NA hodnotu **EINVAL**. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Fehlerbedingungen

|Key|Basis|compare|num|Breite|errno|
|---------|----------|-------------|---------|-----------|-----------|
|**NULL**|any|any|any|any|**EINVAL**|
|any|**NULL**|any|!= 0|any|**EINVAL**|
|any|any|any|any|<= 0|**EINVAL**|
|any|any|**NULL**|any|any|**EINVAL**|

**Qsort_s** hat das gleiche Verhalten wie **Qsort** hat jedoch die *Kontext* Parameter und legt **Errno**. Durch Übergeben einer *Kontext* Parameter Vergleichsfunktionen können einen Objektzeiger auf objektfunktionalitäten oder andere Informationen, die nicht zugegriffen werden kann über einen Elementzeiger zugreifen. Das Hinzufügen der *Kontext* -Parameters macht **Qsort_s** sicherer, da *Kontext* kann verwendet werden, um Wiedereintreten durch die Verwendung statischer Variablen zur stellen zu vermeiden. Informationen zur freigegebenen der *vergleichen* Funktion.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**qsort_s**|\<stdlib.h> und \<search.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken:** Alle Versionen der [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die *Kontext* Parameter in der **Qsort_s** Funktion. Die *Kontext* -Parameter erleichtert das Ausführen von threadsicheren Sortiervorgängen. Anstelle von statischen Variablen, die synchronisiert werden müssen, um Threadsicherheit zu gewährleisten, übergeben Sie einen anderen *Kontext* Parameter in jeder Sortierung. In diesem Beispiel wird ein Gebietsschemaobjekt als verwendet die *Kontext* Parameter.

```cpp
// crt_qsort_s.cpp
// compile with: /EHsc /MT
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
// so \x00e1 is the German Sharp S in that codepage and \x00a4
// is the n tilde.

char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };
char *array2[] = { "Espa\x00a4ol", "Espa\x00a4" "a", "espantado" };
char *array3[] = { "table", "tableux", "tablet" };

#define GERMAN_LOCALE "German_Germany.850"
#define SPANISH_LOCALE "Spanish_Spain.850"
#define ENGLISH_LOCALE "English_US.850"

#endif

#ifdef CODEPAGE_1252
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df
   // for the German Sharp S and \x001f for the n tilde.
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };
char *array2[] = { "Espa\x00f1ol", "Espa\x00f1" "a", "espantado" };
char *array3[] = { "table", "tableux", "tablet" };

#define GERMAN_LOCALE "German_Germany.1252"
#define SPANISH_LOCALE "Spanish_Spain.1252"
#define ENGLISH_LOCALE "English_US.1252"

#endif

// The context parameter lets you create a more generic compare.
// Without this parameter, you would have stored the locale in a
// static variable, thus making sort_array vulnerable to thread
// conflicts.

int compare( void *pvlocale, const void *str1, const void *str2)
{
    char s1[256];
    char s2[256];
    strcpy_s(s1, 256, *(char**)str1);
    strcpy_s(s2, 256, *(char**)str2);
    _strlwr_s( s1, sizeof(s1) );
    _strlwr_s( s2, sizeof(s2) );

    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));

    return use_facet< collate<char> >(loc).compare(s1,
       &s1[strlen(s1)], s2, &s2[strlen(s2)]);

}

void sort_array(char *array[], int num, locale &loc)
{
    qsort_s(array, num, sizeof(char*), compare, &loc);
}

void print_array(char *a[], int c)
{
   for (int i = 0; i < c; i++)
      printf("%s ", a[i]);
   printf("\n");

}

void sort_german(void * Dummy)
{
   sort_array(array1, 6, locale(GERMAN_LOCALE));
}

void sort_spanish(void * Dummy)
{
   sort_array(array2, 3, locale(SPANISH_LOCALE));
}

void sort_english(void * Dummy)
{
   sort_array(array3, 3, locale(ENGLISH_LOCALE));
}

int main( )
{
   int i;
   HANDLE threads[3];

   printf("Unsorted input:\n");
   print_array(array1, 6);
   print_array(array2, 3);
   print_array(array3, 3);

   // Create several threads that perform sorts in different
   // languages at the same time.

   threads[0] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_german , 0, NULL));
   threads[1] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_spanish, 0, NULL));
   threads[2] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_english, 0, NULL));

   for (i = 0; i < 3; i++)
   {
      if (threads[i] == reinterpret_cast<HANDLE>(-1))
      {
         printf("Error creating threads.\n");
         exit(1);
      }
   }

   // Wait until all threads have terminated.
   WaitForMultipleObjects(3, threads, true, INFINITE);

   printf("Sorted output: \n");

   print_array(array1, 6);
   print_array(array2, 3);
   print_array(array3, 3);
}
```

### <a name="sample-output"></a>Beispielausgabe

```Output
Unsorted input:
weiß weis annehmen weizen Zeit weit
Español España espantado
table tableux tablet
Sorted output:
annehmen weiß weis weit weizen Zeit
España Español espantado
table tablet tableux
```

## <a name="see-also"></a>Siehe auch

[Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort](qsort.md)<br/>
