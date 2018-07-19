---
title: __ll_rshift | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
dev_langs:
- C++
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e086339c41f789323cb4aab386a96dae27a0eeb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324927"
---
# <a name="llrshift"></a>__ll_rshift
**Microsoft-spezifisch**  
  
 Verschiebt einen 64-Bit-Wert, der durch den ersten Parameter auf der rechten Seite angegeben eine Anzahl von Bits, die durch den zweiten Parameter angegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
__int64 __ll_rshift(  
   __int64 Mask,  
   int nBit  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `Mask`  
 Der 64-Bit-Ganzzahl-Wert nach rechts verschoben werden soll.  
  
 [in] `nBit`  
 Die Anzahl der zu verschiebenden modulo 64 auf X64 und modulo auf X86 32 Bits.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Maske verschoben werden, indem `nBit` Bits.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__ll_rshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Wenn der zweite Parameter größer als 64 auf X64 (32 auf X86),, die Anzahl modulo 64 (32 auf X86) ausgeführt wird ist, um zu bestimmen, die Anzahl der zu verschiebenden Bits. Die `ll` Präfix gibt an, dass dies eine Operation auf `long long`, einen anderen Namen für `__int64`, signierten ganzzahligen 64-Bit-Typs.  
  
## <a name="example"></a>Beispiel  
  
```  
// ll_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_rshift)  
  
int main()  
{  
   __int64 Mask = - 0x100;  
   int nBit = 4;  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
   Mask = __ll_rshift(Mask, nBit);  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
ffffffffffffff00  
 - 100  
fffffffffffffff0  
 - 10  
```  
  
 **Hinweis** Wenn `_ull_rshift` wurde verwendet, die MSB des Werts nach rechts verschobene hätte 0 (null), damit das gewünschte Ergebnis nicht bei einem negativen Wert erzielt worden wäre.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__ll_lshift](../intrinsics/ll-lshift.md)   
 [__ull_rshift](../intrinsics/ull-rshift.md)