---
title: _heapchk
ms.date: 11/04/2016
apiname:
- _heapchk
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _heapchk
- heapchk
helpviewer_keywords:
- debugging [CRT], heap-related problems
- consistency checking of heaps
- heapchk function
- heaps, checking consistency
- _heapchk function
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
ms.openlocfilehash: b34b4ea1bb2512628213cabb55e26e2dad6d445c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580621"
---
# <a name="heapchk"></a>_heapchk

Führt Konsistenzüberprüfungen auf dem Heap aus.

## <a name="syntax"></a>Syntax

```C
int _heapchk( void );
```

## <a name="return-value"></a>Rückgabewert

**_heapchk** gibt einen der folgenden ganzzahligen Manifestkonstanten in Malloc.h definiert sind.

|Rückgabewert|Bedingung|
|-|-|
**_HEAPBADBEGIN**|Die ursprüngliche Headerinformation ist schlecht oder wurde nicht gefunden.
**_HEAPBADNODE**|Ein ungültiger Knoten wurde gefunden, oder Heap ist beschädigt.
**_HEAPBADPTR**|Der Zeiger auf einen Heap ist ungültig.
**_HEAPEMPTY**|Der Heap wurde noch nicht initialisiert.
**_HEAPOK**|Der Heap scheint konsistent zu sein.

Darüber hinaus, wenn ein Fehler auftritt **_heapchk** legt **Errno** zu **ENOSYS**.

## <a name="remarks"></a>Hinweise

Die **_heapchk** -Funktion hilft, Heap-bezogene Probleme zu debuggen, indem auf minimale Konsistenz des Heaps überprüfen. Wenn das Betriebssystem nicht unterstützt **_heapchk**(z. B. Windows 98), die Funktion gibt **_HEAPOK** und **Errno** zu **ENOSYS**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_heapchk**|\<malloc.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_heapchk.c
// This program checks the heap for
// consistency and prints an appropriate message.

#include <malloc.h>
#include <stdio.h>

int main( void )
{
   int  heapstatus;
   char *buffer;

   // Allocate and deallocate some memory
   if( (buffer = (char *)malloc( 100 )) != NULL )
      free( buffer );

   // Check heap status
   heapstatus = _heapchk();
   switch( heapstatus )
   {
   case _HEAPOK:
      printf(" OK - heap is fine\n" );
      break;
   case _HEAPEMPTY:
      printf(" OK - heap is empty\n" );
      break;
   case _HEAPBADBEGIN:
      printf( "ERROR - bad start of heap\n" );
      break;
   case _HEAPBADNODE:
      printf( "ERROR - bad node in heap\n" );
      break;
   }
}
```

```Output
OK - heap is fine
```

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapmin](heapmin.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
[_heapwalk](heapwalk.md)<br/>
