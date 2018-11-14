---
title: __movsd
ms.date: 11/04/2016
f1_keywords:
- __movsd
helpviewer_keywords:
- rep movsd instruction
- __movsd intrinsic
- movsd instruction
ms.assetid: eb5cccf3-aa76-47f0-b9fc-eeca38fd943f
ms.openlocfilehash: 89c2e7bf6045821d01b23608552776aaf389b0cf
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331008"
---
# <a name="movsd"></a>__movsd

**Microsoft-spezifisch**

Generiert eine Zeichenfolge zu verschieben (`rep movsd`) Anweisung.

## <a name="syntax"></a>Syntax

```
void __movsd(
   unsigned long* Dest,
   unsigned long* Source,
   size_t Count
);
```

#### <a name="parameters"></a>Parameter

*dest*<br/>
[out] Das Ziel des Vorgangs.

*Quelle*<br/>
[in] Die Quelle des Vorgangs.

*Anzahl*<br/>
[in] Die Anzahl der Doppelwort kopieren.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__movsd`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Das Ergebnis ist, die erste `Count` die zeigt Doppelwort `Source` kopiert werden, um die `Dest` Zeichenfolge.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```
// movsd.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsd)

int main()
{
    unsigned long a1[10];
    unsigned long a2[10] = {950, 850, 750, 650, 550, 450, 350,
                            250, 150, 50};
    __movsd(a1, a2, 10);

    for (int i = 0; i < 10; i++)
        printf_s("%d ", a1[i]);
    printf_s("\n");
}
```

```Output
950 850 750 650 550 450 350 250 150 50
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)