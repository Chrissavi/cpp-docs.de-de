---
title: __movsq | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __movsq
dev_langs:
- C++
helpviewer_keywords:
- __movsq intrinsic
- rep movsq instruction
- movsq instruction
ms.assetid: be116a6e-2176-4ca4-93b1-9ccf3e7e7835
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9386a35d7cfab67d0a981bd75d889f27e0ef4631
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443828"
---
# <a name="movsq"></a>__movsq

**Microsoft-spezifisch**

Generiert eine Zeichenfolge mit einem wiederholten verschieben (`rep movsq`) Anweisung.

## <a name="syntax"></a>Syntax

```
void __movsq( 
   unsigned char* Dest, 
   unsigned char* Source, 
   size_t Count 
);
```

#### <a name="parameters"></a>Parameter

*dest*<br/>
[out] Das Ziel des Vorgangs.

*Source*<br/>
[in] Die Quelle des Vorgangs.

*Anzahl*<br/>
[in] Die Anzahl der Vierfachwörtern kopieren.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__movsq`|x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Das Ergebnis ist, die erste `Count` Vierfachwörtern verweist `Source` kopiert werden, um die `Dest` Zeichenfolge.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```
// movsq.cpp
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsq)

int main()
{
    unsigned __int64 a1[10];
    unsigned __int64 a2[10] = {950, 850, 750, 650, 550, 450, 350, 250,
                               150, 50};
    __movsq(a1, a2, 10);

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