---
title: _unlink, _wunlink
ms.date: 11/04/2016
apiname:
- _unlink
- _wunlink
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tunlink
- _unlink
- wunlink
- _wunlink
helpviewer_keywords:
- files [C++], deleting
- _wunlink function
- wunlink function
- unlink function
- _unlink function
- tunlink function
- files [C++], removing
- _tunlink function
ms.assetid: 5e4f5f1b-1e99-4391-9b18-9ac63c32fae8
ms.openlocfilehash: 7565679c58af83d64fd59419e8e841ee48133edf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544196"
---
# <a name="unlink-wunlink"></a>_unlink, _wunlink

Löschen einer Datei.

## <a name="syntax"></a>Syntax

```C
int _unlink(
   const char *filename
);
int _wunlink(
   const wchar_t *filename
);
```

### <a name="parameters"></a>Parameter

*filename*<br/>
Name der zu entfernenden Datei.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt bei Erfolg 0 zurück. Anderenfalls gibt die Funktion-1 zurück und legt **Errno** zu **EACCES**, was bedeutet, dass den Pfad eine schreibgeschützte Datei angibt oder **ENOENT**, d.h. Datei oder Pfad wurde nicht gefunden oder der Pfad ein Verzeichnis angegeben.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_unlink** Funktion löscht die angegebene Datei *Filename*. **_wunlink** ist eine Breitzeichen-Version von **_unlink**; die *Filename* Argument **_wunlink** ist eine Breitzeichen-Zeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tunlink**|**_unlink**|**_unlink**|**_wunlink**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_unlink**|\<io.h> und \<stdio.h>|
|**_wunlink**|\<io.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="code-example"></a>Codebeispiel

Dieses Programm verwendet _unlink, um CRT_UNLINK.TXT zu löschen.

```C
// crt_unlink.c

#include <stdio.h>

int main( void )
{
   if( _unlink( "crt_unlink.txt" ) == -1 )
      perror( "Could not delete 'CRT_UNLINK.TXT'" );
   else
      printf( "Deleted 'CRT_UNLINK.TXT'\n" );
}
```

### <a name="input-crtunlinktxt"></a>Eingabe: crt_unlink.txt

```Input
This file will be deleted.
```

### <a name="sample-output"></a>Beispielausgabe

```Output
Deleted 'CRT_UNLINK.TXT'
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[remove, _wremove](remove-wremove.md)<br/>
