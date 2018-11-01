---
title: _malloca
ms.date: 11/04/2016
apiname:
- _malloca
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
- malloca
- _malloca
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
ms.openlocfilehash: 8c8ce8bdf8ab40cae45ecec9c4b182bdf3d6bc82
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563981"
---
# <a name="malloca"></a>_malloca

Belegt Speicher für den Stapel. Dies ist eine sicherere Version von [_alloca](alloca.md), wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.

## <a name="syntax"></a>Syntax

```C
void *_malloca(
   size_t size
);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Bytes, die vom Stapel zugeordnet werden.

## <a name="return-value"></a>Rückgabewert

Die **_malloca** -Routine gibt einen **"void"** Zeiger auf den zugewiesenen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet. Wenn *Größe* ist 0 (null) **_malloca** weist ein Element der Länge 0 (null) und gibt einen gültigen Zeiger auf dieses Element zurück.

Eine Stapelüberlaufausnahme wird generiert, wenn der Speicherplatz nicht zugeordnet werden kann. Die Stapelüberlaufausnahme ist keine C++-Ausnahme, sondern eine strukturierte Ausnahme. Sie müssen anstelle der C++-Ausnahmebehandlung die [Strukturierte Ausnahmebehandlung](../../cpp/structured-exception-handling-c-cpp.md) (Structured Exception Handling, SEH) verwenden.

## <a name="remarks"></a>Hinweise

**_malloca** ordnet *Größe* Bytes aus dem Programmstapel oder dem Heap, wenn die Anforderung eine bestimmte Größe in Bytes, die vom überschreitet **_ALLOCA_S_THRESHOLD**. Der Unterschied zwischen **_malloca** und **_alloca** ist, die **_alloca** immer auf dem Stapel, unabhängig von der Größe zuordnet. Im Gegensatz zu **_alloca**, die nicht erfordern oder einen Aufruf von zulassen **kostenlose** um den zugeordneten, Arbeitsspeicher freizugeben **_malloca** erfordert die Verwendung von [_freea](freea.md)um Arbeitsspeicher freizugeben. Im Debugmodus befindet **_malloca** weist immer Speicher vom Heap.

Es gibt Einschränkungen beim expliziten Aufruf **_malloca** in einem Ausnahmehandler (EH). EH-Routinen, die auf x86-Klasse-Prozessoren ausgeführt werden, arbeiten in ihrem eigenen Speicherrahmen: Sie führen Ihre Tasks im Speicherplatz aus, der nicht auf der aktuellen Position des Stapelzeigers der einschließenden Funktion basiert. Die am häufigsten verwendeten Implementierungen umfassen die strukturierte Windows NT-Ausnahmebehandlung (SEH) und C++-Catch-Klauselausdrücke. Aus diesem Grund explizit aufrufen **_malloca** in einem der folgenden Szenarien Ergebnisse in einem Programmfehler während an die aufrufende EH-Routine zurückgegeben:

- Windows NT-SEH-Ausnahme-Filterausdruck: **__except** (`_malloca ()` )

- Endgültige Ausnahmehandler von Windows NT-SEH: **__finally** {`_malloca ()` }

- C++-EH-Catch-Klauselausdruck

Allerdings **_malloca** können direkt aufgerufen werden innerhalb einer EH-Routine oder von einer Anwendung bereitgestellten Rückruf, der aufgerufen wird, ruft einer der zuvor aufgeführten EH-Szenarios.

> [!IMPORTANT]
> In Windows XP Wenn **_malloca** wird aufgerufen, Sie müssen in einem Try/Catch-Block Aufrufen [_resetstkoflw](resetstkoflw.md) im Catch-Block.

Zusätzlich zu den oben genannten Einschränkungen kann bei Verwendung der [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) Option **_malloca** kann nicht verwendet werden, **__except** Blöcke. Weitere Informationen finden Sie unter [/clr Restrictions](../../build/reference/clr-restrictions.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_malloca**|\<malloc.h>|

## <a name="example"></a>Beispiel

```C
// crt_malloca_simple.c
#include <stdio.h>
#include <malloc.h>

void Fn()
{
   char * buf = (char *)_malloca( 100 );
   // do something with buf
   _freea( buf );
}

int main()
{
   Fn();
}
```

## <a name="example"></a>Beispiel

```C
// crt_malloca_exception.c
// This program demonstrates the use of
// _malloca and trapping any exceptions
// that may occur.

#include <windows.h>
#include <stdio.h>
#include <malloc.h>

int main()
{
    int     size;
    int     numberRead = 0;
    int     errcode = 0;
    void    *p = NULL;
    void    *pMarker = NULL;

    while (numberRead == 0)
    {
        printf_s("Enter the number of bytes to allocate "
                 "using _malloca: ");
        numberRead = scanf_s("%d", &size);
    }

    // Do not use try/catch for _malloca,
    // use __try/__except, since _malloca throws
    // Structured Exceptions, not C++ exceptions.

    __try
    {
        if (size > 0)
        {
            p =  _malloca( size );
        }
        else
        {
            printf_s("Size must be a positive number.");
        }
        _freea( p );
    }

    // Catch any exceptions that may occur.
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )
    {
        printf_s("_malloca failed!\n");

        // If the stack overflows, use this function to restore.
        errcode = _resetstkoflw();
        if (errcode)
        {
            printf("Could not reset the stack!");
            _exit(1);
        }
    };
}
```

### <a name="input"></a>Eingabe

```Input
1000
```

### <a name="sample-output"></a>Beispielausgabe

```Output
Enter the number of bytes to allocate using _malloca: 1000
```

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
