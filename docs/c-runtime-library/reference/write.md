---
title: _write | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _write
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _write
dev_langs:
- C++
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 917309717d72048650d2b3975fefd74a1db50949
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2018
ms.locfileid: "42571774"
---
# <a name="write"></a>_write

Schreibt Daten in eine Datei.

## <a name="syntax"></a>Syntax

```C
int _write(
   int fd,
   const void *buffer,
   unsigned int count
);
```

### <a name="parameters"></a>Parameter

*fd*<br/>
Dateideskriptor der Datei, in die die Daten geschrieben werden.

*buffer*<br/>
Zu schreibende Daten.

*count*<br/>
Anzahl der Bytes.

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall **_write** gibt die Anzahl der tatsächlich geschriebenen Bytes zurück. Wenn die auf dem Datenträger verbleibende Speicherplatz kleiner als die Größe des Puffers die Funktion versucht ist, auf dem Datenträger schreiben **_write** schlägt fehl, und keiner der Inhalte des Puffers auf den Datenträger zu leeren. Ein Rückgabewert 1 gibt einen Fehler. Wenn ungültige Parameter übergeben werden, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, gibt die Funktion-1 zurück und **Errno** auf einen der drei folgenden Werte festgelegt: **EBADF**, was bedeutet, dass den Dateideskriptor ungültig ist oder die Datei ist nicht geöffnet zum Schreiben. **ENOSPC**, d. h., es nicht ist, genügend Speicherplatz auf dem Gerät für den Vorgang oder **EINVAL**, was bedeutet, dass *Puffer* wurde ein null-Zeiger ist oder dass eine ungerade *Anzahl* Bytes wurde übergeben, um in eine Datei im Unicode-Modus geschrieben werden.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Wenn die Datei im Textmodus geöffnet wird, wird jedes Zeilenvorschubzeichen mit einem Wagenrücklauf - Zeilenvorschub in der Ausgabe ersetzt. Diese Ersetzung hat keine Auswirkung auf den Rückgabewert.

Wenn die Datei im Unicode-Übersetzungsmodus geöffnet wird – z. B. wenn *fd* wird geöffnet, mit **_open** oder **_sopen** und ein Modusparameter, der enthält **_O_ WTEXT**, **_O_U16TEXT**, oder **_O_U8TEXT**, oder wenn sie mithilfe von geöffnet ist **Fopen** und ein Modusparameter, der enthält **ccs = UNICODE**, **ccs = UTF-16LE**, oder **ccs = UTF-8**, oder wenn der Modus auf einen Unicode-Übersetzungsmodus geändert wird, mithilfe von **_setmode**–*Puffer* wird als Zeiger auf ein Array von interpretiert **"wchar_t"** , enthält **UTF-16** Daten. Der Versuch, in diesem Modus eine ungerade Anzahl von Bytes zu schreiben, führt zu einem Parametervalidierungsfehler.

## <a name="remarks"></a>Hinweise

Die **_write** -Funktion schreibt *Anzahl* Bytes vom *Puffer* in der Datei zugeordneten *fd*. Der Schreibvorgang beginnt an der aktuellen Position des Dateizeigers (falls vorhanden) für die betreffende Datei. Wenn die Datei zum Anhängen geöffnet ist, beginnt der Vorgang am aktuellen Dateiende. Nach dem Schreibvorgang wird der Dateizeiger um die Anzahl der tatsächlich geschriebenen Bytes erhöht.

Beim Schreiben in Dateien, die im Textmodus geöffnet **_write** behandelt ein STRG + Z-Zeichen als das logische Ende-des-Datei. Beim Schreiben auf einem Gerät **_write** behandelt ein STRG + Z-Zeichen im Puffer als ausgabeabschlusszeichen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_write**|\<io.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt__write.c
//
// This program opens a file for output and uses _write to write
// some bytes to the file.

#include <io.h>
#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <errno.h>
#include <share.h>

char buffer[] = "This is a test of '_write' function";

int main( void )
{
   int         fileHandle = 0;
   unsigned    bytesWritten = 0;

   if ( _sopen_s(&fileHandle, "write.o", _O_RDWR | _O_CREAT,
                  _SH_DENYNO, _S_IREAD | _S_IWRITE) )
      return -1;

   if (( bytesWritten = _write( fileHandle, buffer, sizeof( buffer ))) == -1 )
   {
      switch(errno)
      {
         case EBADF:
            perror("Bad file descriptor!");
            break;
         case ENOSPC:
            perror("No space left on device!");
            break;
         case EINVAL:
            perror("Invalid parameter: buffer was NULL!");
            break;
         default:
            // An unrelated error occured
            perror("Unexpected error!");
      }
   }
   else
   {
      printf_s( "Wrote %u bytes to file.\n", bytesWritten );
   }
   _close( fileHandle );
}
```

```Output
Wrote 36 bytes to file.
```

## <a name="see-also"></a>Siehe auch

[E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_setmode](setmode.md)<br/>
