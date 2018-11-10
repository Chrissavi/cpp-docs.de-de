---
title: _heapset
ms.date: 11/04/2016
apiname:
- _heapset
apilocation:
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _heapset
- heapset
helpviewer_keywords:
- checking heap
- heapset function
- heaps, checking
- debugging [CRT], heap-related problems
- _heapset function
ms.assetid: 9667eeb0-55bc-4c19-af5f-d1fd0a142b3c
ms.openlocfilehash: c93624b8b56fb53eb15263dbd0d203cd9130eacf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528192"
---
# <a name="heapset"></a>_heapset

Überprüft Heaps auf minimale Konsistenz und legt für die freien Einträge einen angegebenen Wert fest.

> [!IMPORTANT]
>  Diese Funktion ist veraltet. Von Visual Studio 2015 an ist sie nicht in der CRT verfügbar.

## <a name="syntax"></a>Syntax

```
int _heapset(
   unsigned int fill
);
```

#### <a name="parameters"></a>Parameter

*fill*<br/>
Füllzeichen.

## <a name="return-value"></a>Rückgabewert

`_heapset` gibt eine der folgenden ganzzahligen Manifestkonstanten zurück, die in Malloc.h definiert sind.

|||
|-|-|
| `_HEAPBADBEGIN`  | Ursprüngliche Headerinformationen ungültig oder nicht gefunden.  |
| `_HEAPBADNODE`  | Heap beschädigt oder ungültiger Knoten gefunden.  |
| `_HEAPEMPTY`  | Heap wurde nicht initialisiert.  |
| `_HEAPOK`  | Der Heap scheint konsistent zu sein.  |

Wenn ein Fehler auftritt, setzt `_heapset``errno` zudem auf `ENOSYS`.

## <a name="remarks"></a>Hinweise

Die Funktion `_heapset` zeigt freie Speicherpositionen oder Knoten an, die unabsichtlich überschrieben wurden.

`_heapset` überprüft auf minimale Konsistenz auf dem Heap und legt dann jedes Byte der als frei eingetragenen Heappositionen auf den Wert von `fill` fest. Dieser bekannte Wert zeigt, welche Arbeitsspeicherpositionen des Heaps freie Knoten enthalten und welche Daten enthalten, die unabsichtlich an freigegebene Speicherpositionen geschrieben wurden. Wenn das Betriebssystem `_heapset` nicht unterstützt (z.B. Windows 98), gibt die Funktion `_HEAPOK` zurück und legt `errno` auf `ENOSYS` fest.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|`_heapset`|\<malloc.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md) in der Einführung.

## <a name="example"></a>Beispiel

```
// crt_heapset.c
// This program checks the heap and
// fills in free entries with the character 'Z'.

#include <malloc.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int heapstatus;
   char *buffer;

   if( (buffer = malloc( 1 )) == NULL ) // Make sure heap is
      exit( 0 );                        //    initialized
   heapstatus = _heapset( 'Z' );        // Fill in free entries
   switch( heapstatus )
   {
   case _HEAPOK:
      printf( "OK - heap is fine\n" );
      break;
   case _HEAPEMPTY:
      printf( "OK - heap is empty\n" );
      break;
   case _HEAPBADBEGIN:
      printf( "ERROR - bad start of heap\n" );
      break;
   case _HEAPBADNODE:
      printf( "ERROR - bad node in heap\n" );
      break;
   }
   free( buffer );
}
```

```Output
OK - heap is fine
```

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../c-runtime-library/heapadd.md)<br/>
[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapmin](../c-runtime-library/reference/heapmin.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)