---
title: _getcwd_dbg, _wgetcwd_dbg
ms.date: 11/04/2016
api_name:
- _wgetcwd_dbg
- _getcwd_dbg
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
- api-ms-win-crt-environment-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getcwd_dbg
- _wgetcwd_dbg
- getcwd_dbg
- wgetcwd_dbg
helpviewer_keywords:
- wgetcwd_dbg function
- working directory
- _getcwd_dbg function
- getcwd_dbg function
- current working directory
- _wgetcwd_dbg function
- directories [C++], current working
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
ms.openlocfilehash: 3eb318b9b2faa8716abdd26eafa926c8072b5614
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955280"
---
# <a name="_getcwd_dbg-_wgetcwd_dbg"></a>_getcwd_dbg, _wgetcwd_dbg

Debugversionen der Funktionen [_getcwd, _wgetcwd](getcwd-wgetcwd.md) (nur während des Debuggens verfügbar).

## <a name="syntax"></a>Syntax

```C
char *_getcwd_dbg(
   char *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wgetcwd_dbg(
   wchar_t *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Speicherort für den Pfad.

*maxlen*<br/>
Maximale Länge des Pfads in Zeichen: **char** für **_getcwd_dbg** und **wchar_t** für **_wgetcwd_dbg**.

*blockType*<br/>
Angeforderter Typ des Speicherblocks: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die den Zuordnungs Vorgang angefordert hat, oder **null**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der der Zuordnungs Vorgang angefordert wurde, oder **null**.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den *Puffer*zurück. Ein **null** -Rückgabewert gibt einen Fehler an, und **errno** wird entweder auf **ENOMEM**festgelegt, was darauf hinweist, dass nicht genügend Arbeitsspeicher vorhanden ist, um *maxlen* -Bytes zuzuordnen (wenn ein **null** -Argument als *Puffer*angegeben wird), oder zu **ERANGE.** gibt an, dass der Pfad länger als *maxlen* -Zeichen ist.

Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die Funktionen **_getcwd_dbg** und **_wgetcwd_dbg** sind mit **_getcwd** und **_wgetcwd** identisch, außer dass bei Definition von **_DEBUG** die Debugversion von **malloc** und **_malloc_dbg** in verwendet wird. Arbeitsspeicher zuweisen, wenn **null** als erster Parameter übergeben wird. Weitere Informationen finden Sie unter [_malloc_dbg](malloc-dbg.md).

In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen. Stattdessen können Sie das **_CRTDBG_MAP_ALLOC** -Flag definieren. Wenn **_CRTDBG_MAP_ALLOC** definiert ist, werden Aufrufe von **_getcwd** und **_wgetcwd** zu **_getcwd_dbg** bzw. **_wgetcwd_dbg**neu zugeordnet, wobei *blockType* auf **_NORMAL_BLOCK**festgelegt ist. Daher müssen Sie diese Funktionen nicht explizit aufzurufen, es sei denn, Sie möchten die Heap Blöcke als **_CLIENT_BLOCK**markieren. Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).

## <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd_dbg**|**_getcwd_dbg**|**_getcwd_dbg**|**_wgetcwd_dbg**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_getcwd_dbg**|\<crtdbg.h>|
|**_wgetcwd_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[Verzeichnissteuerung](../../c-runtime-library/directory-control.md)<br/>
[Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
