---
title: __ull_rshift
ms.date: 09/02/2019
f1_keywords:
- __ull_rshift
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
ms.openlocfilehash: e914a019877482058c6b2842d3138cda02f1e228
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219708"
---
# <a name="__ull_rshift"></a>__ull_rshift

**Microsoft-spezifisch**

in x64 verschiebt einen 64-Bit-Wert, der durch den ersten Parameter angegeben wird, um eine Anzahl von Bits, die durch den zweiten Parameter angegeben werden, nach rechts.

## <a name="syntax"></a>Syntax

```C
unsigned __int64 __ull_rshift(
   unsigned __int64 mask, 
   int nBit
);
```

### <a name="parameters"></a>Parameter

*chel*\
in Der ganzzahlige 64-Bit-Wert für die Verschiebung nach rechts.

*nBit*\
in Die Anzahl der zu Verschiebe enden Bits, modulo 32 auf x86 und modulo 64 auf x64.

## <a name="return-value"></a>Rückgabewert

Die Maske, die `nBit` von Bits verschoben wurde.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__ull_rshift`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Wenn der zweite Parameter auf x86 (63 auf x64) größer als 31 ist, wird diese Zahl in modulo 32 (64 auf x64) verwendet, um die Anzahl der zu Verschiebe Bits zu bestimmen. Der `ull` im Namen gibt `unsigned long long (unsigned __int64)`an.

## <a name="example"></a>Beispiel

```cpp
// ull_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ull_rshift)

int main()
{
   unsigned __int64 mask = 0x100;
   int nBit = 8;
   mask = __ull_rshift(mask, nBit);
   cout << hex << mask << endl;
}
```

```Output
1
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ll_rshift](../intrinsics/ll-rshift.md)\
[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
