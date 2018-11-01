---
title: _mm_stream_si64x | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_stream_si64x
dev_langs:
- C++
helpviewer_keywords:
- movnti instruction
- _mm_stream_si64x intrinsic
ms.assetid: 114c2cd0-085f-41aa-846e-87bdd56c9ee7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 568f1c32553a07de7f1ac7bf8ad3d0652e26d437
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417656"
---
# <a name="mmstreamsi64x"></a>_mm_stream_si64x

**Microsoft-spezifisch**

Generiert die MOVNTI-Anweisung. Schreibt die Daten in `Source` auf einen Speicherbereich durch angegebene `Dest`, ohne die Caches zu entwickeln.

## <a name="syntax"></a>Syntax

```
void _mm_stream_si64x( 
   __int64 * Dest, 
   __int64 Source 
);
```

#### <a name="parameters"></a>Parameter

*dest*<br/>
[out] Ein Zeiger auf den Speicherort die Quelldaten zu schreiben.

*Source*<br/>
[in] Die Daten geschrieben werden soll.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_mm_stream_si64x`|x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```C
// _mm_stream_si64x.c
// processor: x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_mm_stream_si64x)

int main()
{
    __int64 val = 0xFFFFFFFFFFFFI64;
    __int64 a[10];

    memset(a, 0, sizeof(a));
    _mm_stream_si64x(a+1, val);
    printf_s( "%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);
}
```

```Output
0 ffffffffffff 0 0
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)