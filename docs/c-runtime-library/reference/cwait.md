---
title: _cwait
ms.date: 11/04/2016
apiname:
- _cwait
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cwait
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
ms.openlocfilehash: f7a49497ac71ec15261e1215bd2bbed2e49f42ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489621"
---
# <a name="cwait"></a>_cwait

Wartet, bis ein anderer Prozess beendet wird.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
intptr_t _cwait(
   int *termstat,
   intptr_t procHandle,
   int action
);
```

### <a name="parameters"></a>Parameter

*termstat*<br/>
Zeiger auf einen Puffer, in dem der Ergebniscode des angegebenen Prozesses gespeichert werden, oder **NULL**.

*procHandle*<br/>
Das Handle für den Prozess auf die gewartet (d. h. den Prozess, der vor dem Beenden **_cwait** zurückgeben kann).

*Aktion*<br/>
NULL = Von Anwendungen für Windows-Betriebssystems ignoriert. für andere Anwendungen: Code für die Aktion auszuführenden *ProcHandle*.

## <a name="return-value"></a>Rückgabewert

Wenn der angegebene Prozess erfolgreich abgeschlossen wurde, gibt das Handle des angegebenen Prozesses zurück und legt sie fest *Termstat* auf den Ergebniscode, die vom angegebenen Prozess zurückgegeben wird. Andernfalls-1 zurück und setzt **Errno** wie folgt.

|Wert|Beschreibung|
|-----------|-----------------|
|**ECHILD**|Es ist kein angegebener Prozess vorhanden, *ProcHandle* ist ungültig, oder der Aufruf der [GetExitCodeProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess) oder [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject) -API ist fehlgeschlagen.|
|**EINVAL**|*Aktion* ist ungültig.|

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_cwait** Funktion wartet, bis die Beendigung der Prozess-ID des angegebenen Prozesses, die von bereitgestellte *ProcHandle*. Der Wert des *ProcHandle* übergebene **_cwait** muss der Wert, der durch den Aufruf zurückgegeben wird das [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) -Funktion, die den angegebenen Prozess erstellt hat. Wenn die Prozess-ID vor dem Beenden **_cwait** aufgerufen wird, **_cwait** kehrt sofort zurück. **_cwait** kann von jedem Prozess verwendet werden, um zu warten, für jeden anderen bekannten Prozess für den ein gültiges Handle (*ProcHandle*) vorhanden ist.

*Termstat* verweist auf einen Puffer, in dem der Rückgabecode des angegebenen Prozesses gespeichert. Der Wert des *Termstat* gibt an, ob der angegebene Prozess ordnungsgemäß beendet wurde, durch den Aufruf der Windows [ExitProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitprocess) API. **ExitProcess** wird intern aufgerufen, wenn der angegebene Prozess **beenden** oder **_exit**, gibt aus **main**, oder das Ende erreicht **main** . Weitere Informationen zu den Wert, der wieder übergeben wird *Termstat*, finden Sie unter [GetExitCodeProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess). Wenn **_cwait** wird aufgerufen, mit einem **NULL** Wert für *Termstat*, der Rückgabecode des angegebenen Prozesses nicht gespeichert.

Die *Aktion* Parameter wird durch das Windows-Betriebssystem ignoriert, da über-/ unterordnungsbeziehung in diesen Umgebungen nicht implementiert werden.

Es sei denn, *ProcHandle* nicht-1 oder-2 (handles für den aktuellen Prozess oder Thread), wird das Handle geschlossen werden. Daher sollte in dieser Situation das zurückgegebene Handle nicht verwendet werden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_cwait**|\<process.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_cwait.c
// compile with: /c
// This program launches several processes and waits
// for a specified process to finish.

#define _CRT_RAND_S

#include <windows.h>
#include <process.h>
#include <stdlib.h>
#include <stdio.h>
#include <time.h>

// Macro to get a random integer within a specified range
#define getrandom( min, max ) (( (rand_s (&number), number) % (int)((( max ) + 1 ) - ( min ))) + ( min ))

struct PROCESS
{
   int     nPid;
   char    name[40];
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };

int main( int argc, char *argv[] )
{
   int termstat, c;
   unsigned int number;

   srand( (unsigned)time( NULL ) );    // Seed randomizer

   // If no arguments, this is the calling process
   if ( argc == 1 )
   {
      // Spawn processes in numeric order
      for ( c = 0; c < 4; c++ ) {
         _flushall();
         process[c].nPid = _spawnl( _P_NOWAIT, argv[0], argv[0],
                                    process[c].name, NULL );
      }

      // Wait for randomly specified process, and respond when done
      c = getrandom( 0, 3 );
      printf( "Come here, %s.\n", process[c].name );
      _cwait( &termstat, process[c].nPid, _WAIT_CHILD );
      printf( "Thank you, %s.\n", process[c].name );

   }
   // If there are arguments, this must be a spawned process
   else
   {
      // Delay for a period that's determined by process number
      Sleep( (argv[1][0] - 'A' + 1) * 1000L );
      printf( "Hi, Dad. It's %s.\n", argv[1] );
   }
}
```

```Output
Hi, Dad. It's Ann.
Come here, Ann.
Thank you, Ann.
Hi, Dad. It's Beth.
Hi, Dad. It's Carl.
Hi, Dad. It's Dave.
```

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
