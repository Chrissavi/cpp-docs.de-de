---
title: scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l
ms.date: 03/26/2019
apiname:
- wscanf_s
- _wscanf_s_l
- scanf_s
- _scanf_s_l
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
apitype: DLLExport
f1_keywords:
- wscanf_s
- _tscanf_s_l
- _wscanf_s_l
- scanf_s
- _tscanf_s
- _scanf_s_l
helpviewer_keywords:
- reading data [C++], from input streams
- buffers [C++], buffer overruns
- _scanf_s_l function
- _wscanf_s_l function
- tscanf_s_l function
- tscanf_s function
- scanf_s function
- data [C++], reading from input stream
- wscanf_s function
- _tscanf_s_l function
- _tscanf_s function
- scanf_s_l function
- formatted data [C++], from input streams
- wscanf_s_l function
- buffers [C++], avoiding overruns
ms.assetid: 42cafcf7-52d6-404a-80e4-b056a7faf2e5
ms.openlocfilehash: 28697cac20181c3dda0581c7486ebb673aec1241
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357082"
---
# <a name="scanfs-scanfsl-wscanfs-wscanfsl"></a>scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l

Liest formatierte Daten aus dem Standardeingabestream. Diese Versionen von [scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md) enthalten Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
int scanf_s(
   const char *format [,
   argument]...
);
int _scanf_s_l(
   const char *format,
   locale_t locale [,
   argument]...
);
int wscanf_s(
   const wchar_t *format [,
   argument]...
);
int _wscanf_s_l(
   const wchar_t *format,
   locale_t locale [,
   argument]...
);
```

### <a name="parameters"></a>Parameter

*format*<br/>
Formatsteuerzeichenfolge.

*argument*<br/>
Optionale Argumente.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Gibt die Anzahl von Feldern, die erfolgreich konvertiert und zugewiesen. Der Rückgabewert enthalten nicht Felder, die gelesen, aber nicht zugewiesen wurden. Der Rückgabewert 0 gibt an, dass keine Felder zugewiesen wurden. Der Rückgabewert ist **EOF** ein Fehler, oder wenn das EOF Zeichen oder das Ende der Zeichenfolge Zeichen, beim ersten Versuch gefunden wird, ein Zeichen zu lesen. Wenn *Format* ist eine **NULL** -Zeiger ist, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Scanf_s** und **Wscanf_s** zurückgeben **EOF** und **Errno** zu **EINVAL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (errno, _doserrno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Scanf_s** -Funktion liest Daten aus dem Standardeingabestream **Stdin**, und schreibt es in *Argument*. Jede *Argument* muss ein Zeiger auf einen Variablentyp, die der Typspezifizierer in entspricht *Format*. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.

**Wscanf_s** ist eine Breitzeichen-Version von **Scanf_s**; die *Format* Argument **Wscanf_s** ist eine Breitzeichen-Zeichenfolge. **Wscanf_s** und **Scanf_s** Verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **Scanf_s** unterstützt derzeit keine Eingabe aus einem unicodestream.

Die Versionen dieser Funktionen, die **_l** -Suffix sind nahezu identisch, außer sie verwenden die *Gebietsschema* Parameter anstelle des aktuellen threadgebietsschemas.

Im Gegensatz zu **Scanf** und **Wscanf**, **Scanf_s** und **Wscanf_s** müssen Puffergrößen für einige Parameter angeben. Geben Sie die Größe für alle **c**, **C**, **s**, **S**, oder einen Zeichenfolgentyp-Steuerelementsatz **[]** Parameter. Die Größe des Puffers in Zeichen wird als zusätzlicher Parameter übergeben. Es folgt unmittelbar auf den Zeiger auf den Puffer oder Variable. Wenn Sie eine Zeichenfolge lesen, wird die Puffergröße für diese Zeichenfolge z. B. wie folgt übergeben:

```C
char s[10];
scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9
```

Die Puffergröße enthält das terminal Null-Zeichen. Sie können ein Feld für die Breitenangabe verwenden, um sicherzustellen, dass das Token, das am besten entspricht, in den Puffer gelesen wird. Wenn ein Token zu groß ist, wird nichts in den Puffer geschrieben, es sei denn, es eine Spezifikation für die Breite ist.

> [!NOTE]
> Size-Parameter ist vom Typ **ohne Vorzeichen**, nicht **"size_t"**. Verwenden Sie eine statische Umwandlung zum Konvertieren einer **"size_t"** Wert **ohne Vorzeichen** für 64-Bit-Buildkonfigurationen.

Der puffergrößenparameter wird beschrieben, die maximale Anzahl von Zeichen, nicht Bytes. In diesem Beispiel passt die Breite des Puffertyps die Breite des Formatbezeichners nicht.

```C
wchar_t ws[10];
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));
```

Die **S** Formatbezeichner bedeutet, dass die Zeichenbreite verwenden, die "die Standardbreite einen Gegensatz" von der Funktion unterstützt wird. Die Zeichenbreite ist einzelne Byte, aber die Funktion unterstützt Doppelbytezeichen. In diesem Beispiel liest eine Zeichenfolge mit bis zu neun einzelne Bytes bestehendes Zeichen und schreibt sie in einen Double-Byte-Breitzeichen-Puffer. Die Zeichen werden als Einzelbytewerte behandelt; die ersten zwei Zeichen werden in `ws[0]` gespeichert, die zweiten zwei Zeichen in `ws[1]` usw.

In diesem Beispiel liest ein einzelnes Zeichen an:

```C
char c;
scanf_s("%c", &c, 1);
```

Wenn mehrere Zeichen für nicht-Null-terminierte Zeichenfolgen gelesen werden, werden ganze Zahlen für die Breitenangabe und die Größe des Puffers verwendet.

```C
char c[4];
scanf_s("%4c", c, (unsigned)_countof(c)); // not null terminated
```

Weitere Informationen finden Sie unter [scanf Width Specification (scanf-Breitenangabe)](../../c-runtime-library/scanf-width-specification.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tscanf_s**|**scanf_s**|**scanf_s**|**wscanf_s**|
|**_tscanf_s_l**|**_scanf_s_l**|**_scanf_s_l**|**_wscanf_s_l**|

Weitere Informationen finden Sie unter [Format Specification Fields: scanf and wscanf Functions (Formatspezifikationsfelder: Funktionen scanf und wscanf)](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**scanf_s**, **_scanf_s_l**|\<stdio.h>|
|**wscanf_s**, **_wscanf_s_l**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in den apps der universellen Windows-Plattform (UWP) nicht unterstützt. Standardstreamhandles **Stdin**, **"stdout"**, und **"stderr"** müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in UWP-apps verwenden können. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_scanf_s.c
// This program uses the scanf_s and wscanf_s functions
// to read formatted input.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int      i,
            result;
   float    fp;
   char     c,
            s[80];
   wchar_t  wc,
            ws[80];

   result = scanf_s( "%d %f %c %C %s %S", &i, &fp, &c, 1,
                     &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );
   printf( "The number of fields input is %d\n", result );
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c,
           wc, s, ws);
   result = wscanf_s( L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,
                      &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );
   wprintf( L"The number of fields input is %d\n", result );
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp,
            c, wc, s, ws);
}
```

Dieses Programm generiert bei dieser Eingabe die folgende Ausgabe:

```Input
71 98.6 h z Byte characters
36 92.3 y n Wide characters
```

```Output
The number of fields input is 6
The contents are: 71 98.599998 h z Byte characters
The number of fields input is 6
The contents are: 36 92.300003 y n Wide characters
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
