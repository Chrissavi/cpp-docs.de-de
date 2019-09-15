---
title: _expand_dbg
ms.date: 11/04/2016
api_name:
- _expand_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- expand_dbg
- _expand_dbg
helpviewer_keywords:
- memory blocks, changing size
- expand_dbg function
- _expand_dbg function
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
ms.openlocfilehash: 836b9cffcf0367f248a14469b30c1a355e2bdec2
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941578"
---
# <a name="_expand_dbg"></a>_expand_dbg

Ändert die Größe eines angegebenen Speicherblocks im Heap durch Erweitern oder Verkürzen des Blocks (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void *_expand_dbg(
   void *userData,
   size_t newSize,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parameter

*userData*<br/>
Zeiger zum vorherigen belegten Speicherblock.

*newSize*<br/>
Angeforderte neue Größe des Blocks (in Bytes).

*blockType*<br/>
Angeforderter Typ für Block mit Größenänderung: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die den Erweiterungs Vorgang angefordert hat, oder **null**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der der Erweiterungs Vorgang angefordert wurde, oder **null**.

Die Parameter " *filename* " und " *LineNumber* " sind nur verfügbar, wenn " **_expand_dbg** " explizit aufgerufen wurde oder die [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) -präprozessorkonstante definiert wurde.

## <a name="return-value"></a>Rückgabewert

Nach erfolgreichem Abschluss gibt **_expand_dbg** einen Zeiger auf den Speicherblock mit Größenänderung zurück. Da der Speicher nicht verschoben wird, ist die Adresse identisch mit "userData". Wenn ein Fehler aufgetreten ist oder der Block nicht auf die angeforderte Größe erweitert werden konnte, wird **null**zurückgegeben. Wenn ein Fehler auftritt, ist **errno** mit Informationen des Betriebssystems über die Art des Fehlers zu tun. Weitere Informationen zu **errno**finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_expand_dbg** -Funktion ist eine Debugversion der _[Expand](expand.md) -Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder **_expand_dbg** -Rückruf auf einen **_expand**-aufrufenden Wert reduziert. Sowohl **_expand** als auch **_expand_dbg** ändern die Größe eines Speicherblocks im Basisheap, **_expand_dbg** bietet jedoch mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzer Teils des Blocks zum Prüfen auf Speicher Verluste, einen Blocktyp Parameter zum Nachverfolgen bestimmte Zuordnungs Typen und *Dateiname*/-*LineNumber* -Informationen, um den Ursprung von Zuordnungs Anforderungen zu bestimmen.

**_expand_dbg** ändert die Größe des angegebenen Speicherblocks mit etwas mehr Speicherplatz als der angeforderte *newSize*. *newSize* ist möglicherweise größer oder kleiner als die Größe des ursprünglich zugeordneten Speicherblocks. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Die Größenänderung wird erreicht, indem der ursprüngliche Speicherblock erweitert oder verkürzt wird. **_expand_dbg** verschiebt den Speicherblock nicht wie die [_realloc_dbg](realloc-dbg.md) -Funktion.

Wenn *newSize* größer als die ursprüngliche Blockgröße ist, wird der Speicherblock erweitert. Wenn während einer Erweiterung der Speicherblock nicht auf die angeforderte Größe erweitert werden kann, wird **null** zurückgegeben. Wenn *newSize* kleiner als die ursprüngliche Blockgröße ist, wird der Speicherblock so lange gebunden, bis die neue Größe abgerufen wird.

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild finden Sie unter [Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

Diese Funktion überprüft ihre Parameter. Wenn *memblock* ein NULL-Zeiger ist oder die Größe größer als **_HEAP_MAXREQ**ist, ruft diese Funktion einen Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird **errno** auf **EINVAL** festgelegt, und die Funktion gibt **null**zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_expand_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_expand_dbg.c
//
// This program allocates a block of memory using _malloc_dbg
// and then calls _msize_dbg to display the size of that block.
// Next, it uses _expand_dbg to expand the amount of
// memory used by the buffer and then calls _msize_dbg again to
// display the new amount of memory allocated to the buffer.
//

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>
#include <crtdbg.h>

int main( void )
{
   long *buffer;
   size_t size;

   // Call _malloc_dbg to include the filename and line number
   // of our allocation request in the header
   buffer = (long *)_malloc_dbg( 40 * sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );
   if( buffer == NULL )
      exit( 1 );

   // Get the size of the buffer by calling _msize_dbg
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );

   // Expand the buffer using _expand_dbg and show the new size
   buffer = (long *)_expand_dbg( buffer, size + sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );

   if( buffer == NULL )
      exit( 1 );
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _expand_dbg of 1 more long: %u\n",
           size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after _malloc_dbg of 40 longs: 160
Size of block after _expand_dbg of 1 more long: 164
```

## <a name="comment"></a>Kommentar

Die Ausgabe dieses Programms hängt von der Funktionalität des Computers ab, ob alle Abschnitte erweitert werden können. Wenn alle Abschnitte erweitert wurden, wird die Ausgabe im Ausgabeabschnitt wiedergegeben.

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
