---
title: Intrinsische _InterlockedAnd-Funktionen
ms.date: 09/02/2019
f1_keywords:
- _InterlockedAnd_rel
- _InterlockedAnd_cpp
- _InterlockedAnd8_nf
- _InterlockedAnd
- _InterlockedAnd_HLERelease
- _InterlockedAnd8_np
- _InterlockedAnd16_rel
- _InterlockedAnd64_np
- _InterlockedAnd_np
- _InterlockedAnd64_HLERelease
- _InterlockedAnd64
- _InterlockedAnd64_nf
- _InterlockedAnd64_HLEAcquire
- _InterlockedAnd16
- _InterlockedAnd16_nf
- _InterlockedAnd8
- _InterlockedAnd_HLEAcquire
- _InterlockedAnd_acq
- _InterlockedAnd16_np
- _InterlockedAnd64_cpp
- _InterlockedAnd64_acq
- _InterlockedAnd16_acq
- _InterlockedAnd8_acq
- _InterlockedAnd64_rel
- _InterlockedAnd_nf
- _InterlockedAnd8_rel
helpviewer_keywords:
- _InterlockedAnd64_np intrinsic
- _InterlockedAnd intrinsic
- _InterlockedAnd64 intrinsic
- _InterlockedAnd8_rel intrinsic
- InterlockedAnd64 intrinsic
- _InterlockedAnd16_np intrinsic
- _InterlockedAnd64_nf intrinsic
- _InterlockedAnd_nf intrinsic
- _InterlockedAnd_np intrinsic
- _InterlockedAnd64_HLERelease intrinsic
- _InterlockedAnd16_rel intrinsic
- _InterlockedAnd_HLERelease intrinsic
- _InterlockedAnd64_acq intrinsic
- _InterlockedAnd16 intrinsic
- _InterlockedAnd8_nf intrinsic
- _InterlockedAnd64_rel intrinsic
- _InterlockedAnd8_np intrinsic
- _InterlockedAnd_rel intrinsic
- InterlockedAnd intrinsic
- _InterlockedAnd8_acq intrinsic
- _InterlockedAnd_acq intrinsic
- _InterlockedAnd64_HLEAcquire intrinsic
- _InterlockedAnd16_acq intrinsic
- _InterlockedAnd16_nf intrinsic
- _InterlockedAnd8 intrinsic
- _InterlockedAnd_HLEAcquire intrinsic
ms.assetid: ad271dc3-42cd-47d0-9f65-30d5cfeb66fc
ms.openlocfilehash: e22b463a5229de4745f71aaa0240374a5c057508
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217774"
---
# <a name="_interlockedand-intrinsic-functions"></a>Intrinsische _InterlockedAnd-Funktionen

**Microsoft-spezifisch**

Zum Ausführen einer atomarischen bitweisen AND-Operation für eine Variable, die von mehreren Threads genutzt wird.

## <a name="syntax"></a>Syntax

```C
long _InterlockedAnd(
   long volatile * value,
   long mask
);
long _InterlockedAnd_acq(
   long volatile * value,
   long mask
);
long _InterlockedAnd_HLEAcquire(
   long volatile * value,
   long mask
);
long _InterlockedAnd_HLERelease(
   long volatile * value,
   long mask
);
long _InterlockedAnd_nf(
   long volatile * value,
   long mask
);
long _InterlockedAnd_np(
   long volatile * value,
   long mask
);
long _InterlockedAnd_rel(
   long volatile * value,
   long mask
);
char _InterlockedAnd8(
   char volatile * value,
   char mask
);
char _InterlockedAnd8_acq(
   char volatile * value,
   char mask
);
char _InterlockedAnd8_nf(
   char volatile * value,
   char mask
);
char _InterlockedAnd8_np(
   char volatile * value,
   char mask
);
char _InterlockedAnd8_rel(
   char volatile * value,
   char mask
);
short _InterlockedAnd16(
   short volatile * value,
   short mask
);
short _InterlockedAnd16_acq(
   short volatile * value,
   short mask
);
short _InterlockedAnd16_nf(
   short volatile * value,
   short mask
);
short _InterlockedAnd16_np(
   short volatile * value,
   short mask
);
short _InterlockedAnd16_rel(
   short volatile * value,
   short mask
);
__int64 _InterlockedAnd64(
   __int64 volatile* value,
   __int64 mask
);
__int64 _InterlockedAnd64_acq(
   __int64 volatile* value,
   __int64 mask
);
__int64 _InterlockedAnd64_HLEAcquire(
   __int64 volatile* value,
   __int64 mask
);
__int64 _InterlockedAnd64_HLERelease(
   __int64 volatile* value,
   __int64 mask
);
__int64 _InterlockedAnd64_nf(
   __int64 volatile* value,
   __int64 mask
);
__int64 _InterlockedAnd64_np(
   __int64 volatile* value,
   __int64 mask
);
__int64 _InterlockedAnd64_rel(
   __int64 volatile* value,
   __int64 mask
);
```

### <a name="parameters"></a>Parameter

*value*\
[in, out] Ein Zeiger auf den ersten Operanden, der durch das Ergebnis ersetzt werden soll.

*chel*\
in Der zweite Operand.

## <a name="return-value"></a>Rückgabewert

Der ursprüngliche Wert des ersten Operanden.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_InterlockedAnd`, `_InterlockedAnd8`, `_InterlockedAnd16`|x86, ARM, x64, ARM64|\<intrin.h>|
|`_InterlockedAnd64`|Arm, x64, ARM64|\<intrin.h>|
|`_InterlockedAnd_acq`, `_InterlockedAnd_nf`, `_InterlockedAnd_rel`, `_InterlockedAnd8_acq`, `_InterlockedAnd8_nf`, `_InterlockedAnd8_rel`, `_InterlockedAnd16_acq`, `_InterlockedAnd16_nf`, `_InterlockedAnd16_rel`, `_InterlockedAnd64_acq`, `_InterlockedAnd64_nf`, `_InterlockedAnd64_rel`|ARM, ARM64|\<intrin.h>|
|`_InterlockedAnd_np`, `_InterlockedAnd8_np`, `_InterlockedAnd16_np`, `_InterlockedAnd64_np`|x64|\<intrin.h>|
|`_InterlockedAnd_HLEAcquire`, `_InterlockedAnd_HLERelease`, `_InterlockedAnd64_HLEAcquire`, `_InterlockedAnd64_HLERelease`|x86, x64|\<immintrin.h>|

## <a name="remarks"></a>Hinweise

Die Nummer im Namen jeder einzelnen Funktion gibt die Bitgröße der Argumente an.

Verwenden Sie auf Arm-und ARM64-Plattformen die `_acq` System `_rel` internen Funktionen mit den Suffixen und zum Abrufen und Freigeben der Semantik, z. b. am Anfang und Ende eines kritischen Abschnitts. Die systeminternen Funktionen mit einer `_nf`-Suffix ("no fence") fungieren nicht als Speicherbarriere.

Die systeminternen Funktionen mit dem Suffix `_np` („no prefetch“) verhindern, dass ein möglicher Vorabrufvorgang vom Compiler eingefügt wird.

Auf Intel-Plattformen, die Hardware Lock Elision (HLE)-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis für den Prozessor, wie die Leistung durch den Wegfall der Schreibsperre in der Hardware beschleunigt werden kann. Wenn diese systeminternen Funktionen auf Plattformen aufgerufen werden, die HLE nicht unterstützen, wird der Hinweis ignoriert.

## <a name="example"></a>Beispiel

```cpp
// InterlockedAnd.cpp
// Compile with: /Oi
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_InterlockedAnd)

int main()
{
        long data1 = 0xFF00FF00;
        long data2 = 0x00FFFF00;
        long retval;
        retval = _InterlockedAnd(&data1, data2);
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);
}
```

```Output
0xff00 0xffff00 0xff00ff00
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[Konflikt mit dem x86-Compiler](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
