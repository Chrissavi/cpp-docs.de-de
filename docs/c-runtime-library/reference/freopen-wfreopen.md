---
title: freopen, _wfreopen
ms.date: 11/04/2016
api_name:
- freopen
- _wfreopen
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wfreopen
- _tfreopen
- freopen
helpviewer_keywords:
- _wfreopen function
- file pointers [C++], reassigning
- _tfreopen function
- freopen function
- tfreopen function
- wfreopen function
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
ms.openlocfilehash: 9f6d4343db3cb507e43e409361059e83fad63148
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956858"
---
# <a name="freopen-_wfreopen"></a>freopen, _wfreopen

Weist einen Dateizeiger neu zu. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md).

## <a name="syntax"></a>Syntax

```C
FILE *freopen(
   const char *path,
   const char *mode,
   FILE *stream
);
FILE *_wfreopen(
   const wchar_t *path,
   const wchar_t *mode,
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*path*<br/>
Pfad der neuen Datei.

*mode*<br/>
Zugriffstyp zulässig.

*stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Zeiger an die gerade geöffnete Datei zurück. Wenn ein Fehler auftritt, wird die ursprüngliche Datei geschlossen und die Funktion gibt einen **null** -Zeiger Wert zurück. Wenn *path*, *Mode*oder *Stream* ein NULL-Zeiger ist, oder wenn *filename* eine leere Zeichenfolge ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, legen diese Funktionen **errno** auf **EINVAL** fest und geben **null**zurück.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md).

Die **freopen** -Funktion schließt die Datei, die derzeit mit *Stream* verknüpft ist, und weist den *Stream* der durch *path*angegebenen Datei neu zu. **_wfreopen** ist eine breit Zeichen Version von **_freopen**. die *path* -und *Mode* -Argumente für **_wfreopen** sind Zeichen folgen mit breit Zeichen. **_wfreopen** und **_freopen** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen**|**freopen**|**freopen**|**_wfreopen**|

**freopen** wird normalerweise verwendet, um die vorab geöffneten Dateien **stdin**, **stdout**und **stderr** in Dateien umzuleiten, die vom Benutzer angegeben werden. Die neue Datei, die dem *Stream* zugeordnet ist, wird mit dem- *Modus*geöffnet. dabei handelt es sich um eine Zeichenfolge, die den für die Datei angeforderten Zugriffstyp wie folgt angibt:

|*mode*|Zugriff|
|-|-|
| **"r"** | Öffnet zum Lesen. Wenn die Datei nicht vorhanden ist oder nicht gefunden werden kann, schlägt der **freopen** -Befehl fehl. |
| **"w"** | Öffnet eine leere Datei zum Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört. |
| **„a“** | Wird vor dem Schreiben neuer Daten in die Datei zum Schreiben am Ende der Datei (Anfügen) geöffnet, ohne die EOF-Markierung (end-of-file, Dateiende) zu entfernen. Erstellt die Datei, wenn sie nicht vorhanden ist. |
| **„r+“** | Öffnet sowohl zum Lesen als auch zum Schreiben. Die Datei muss vorhanden sein. |
| **„w+“** | Öffnet eine leere Datei zum Lesen und Schreiben. Wenn die Datei vorhanden ist, wird ihr Inhalt zerstört. |
| **„a+“** | Öffnet sich zum Lesen und Anfügen. Der Anfügevorgang umfasst das Entfernen der EOF-Markierung, bevor neue Daten in die Datei geschrieben werden. Die EOF-Markierung wird nach Abschluss des Schreibvorgangs nicht wiederhergestellt. Erstellt die Datei, wenn sie nicht vorhanden ist. |

Verwenden Sie die Typen **"w"** und **"w +"** mit Sorgfalt, da Sie vorhandene Dateien zerstören können.

Wenn eine Datei mit dem Zugriffstyp **"a"** oder **"a +"** geöffnet wird, erfolgen alle Schreibvorgänge am Ende der Datei. Obwohl der Dateizeiger mithilfe von [fseek](fseek-fseeki64.md) oder [Rewind](rewind.md)neu positioniert werden kann, wird der Dateizeiger immer wieder an das Ende der Datei verschoben, bevor ein Schreibvorgang durchgeführt wird. Folglich können vorhandene Daten nicht überschrieben werden.

Der **"a"** -Modus entfernt die EOF-Markierung nicht, bevor Sie an die Datei angehängt wird. Nach dem Anfügen werden durch den MS-DOS-Befehl TYPE nur Daten bis zur ursprünglichen EOF-Markierung angezeigt, aber keine Daten, die an die Datei angefügt wurden. Der **"+"** -Modus entfernt die EOF-Markierung, bevor Sie an die Datei angehängt wird. Nach dem Anhängen werden mit dem Befehl MS-DOS TYPE alle Daten in der Datei angezeigt. Der Modus **"a +"** ist zum Anfügen an eine streamdatei erforderlich, die mit der EOF-Markierung STRG + Z beendet wird.

Wenn der Zugriffstyp **"r +"** , **"w +"** oder **"a +** " angegeben wird, sind sowohl Lese-als auch Schreibvorgänge zulässig (die Datei ist zum Aktualisieren geöffnet). Wenn Sie jedoch zwischen Lese- und Schreibvorgängen wechseln, muss ein sich dazwischen befindender Vorgang wie [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md) oder [rewind](rewind.md) vorhanden sein. Wenn gewünscht, kann die aktuelle Position für den Vorgang " [f](fsetpos.md) " oder " [f](fseek-fseeki64.md) " angegeben werden. Zusätzlich zu den oben aufgeführten Werten kann eines der folgenden Zeichen in der *Mode* -Zeichenfolge enthalten sein, um den Übersetzungsmodus für neue Zeilen anzugeben.

|modusmodifizierer|Übersetzungsmodus|
|-|-|
| **t** | Öffnen im Textmodus (übersetzt). |
| **b** | Im binären (nicht übersetzten) Modus öffnen; Übersetzungen mit Wagen Rücklauf-und Zeilenvorschub Zeichen werden unterdrückt. |

Im Text Modus (übersetzt) werden die Kombinationen aus Wagen Rücklauf-und Zeilenvorschub (CR-LF) bei der Eingabe in Einzel Zeilenvorschub Zeichen (LF) übersetzt. LF-Zeichen werden bei der Ausgabe in CR-LF-Kombinationen übersetzt. Außerdem wird STRG+Z bei der Eingabe als EOF-Zeichen interpretiert. In Dateien, die zum Lesen oder schreiben und lesen mit **"a +"** geöffnet sind, prüft die Lauf Zeit Bibliothek, ob am Ende der Datei STRG + Z angezeigt wird, und entfernt Sie nach Möglichkeit. Dies geschieht, da die Verwendung von [fseek](fseek-fseeki64.md) und [ftell](ftell-ftelli64.md) zum Verschieben innerhalb einer Datei dazu führen kann, dass sich [fseek](fseek-fseeki64.md) in der Nähe des Datei Endes nicht ordnungsgemäß verhält. Die **t** -Option ist eine Microsoft-Erweiterung, die nicht verwendet werden sollte, wenn ANSI-Portabilität gewünscht wird.

Wenn " **t** " oder " **b** " im *Modus*nicht angegeben wird, wird der Standard Übersetzungsmodus durch die globale Variable " [_fmode](../../c-runtime-library/fmode.md)" definiert. Wenn **t** oder **b** dem Argument vorangestellt wird, schlägt die Funktion fehl und gibt **null**zurück.

Eine Erörterung von Text- und Binärmodi finden Sie unter [Text- und Binärmodus-Datei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**freopen**|\<stdio.h>|
|**_wfreopen**|\<stdio.h> oder \<wchar.h>|

Die-Konsole wird in universelle Windows-Plattform-Apps (UWP) nicht unterstützt. Die Standarddaten Strom Handles, die der Konsole, **stdin**, **stdout**und **stderr**zugeordnet sind, müssen umgeleitet werden, bevor Sie von C-Lauf Zeitfunktionen in UWP-Apps verwendet werden können. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_freopen.c
// compile with: /W3
// This program reassigns stderr to the file
// named FREOPEN.OUT and writes a line to that file.
#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   // Reassign "stderr" to "freopen.out":
   stream = freopen( "freopen.out", "w", stderr ); // C4996
   // Note: freopen is deprecated; consider using freopen_s instead

   if( stream == NULL )
      fprintf( stdout, "error on freopen\n" );
   else
   {
      fprintf( stdout, "successfully reassigned\n" ); fflush( stdout );
      fprintf( stream, "This will go to the file 'freopen.out'\n" );
      fclose( stream );
   }
   system( "type freopen.out" );
}
```

```Output
successfully reassigned
This will go to the file 'freopen.out'
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
