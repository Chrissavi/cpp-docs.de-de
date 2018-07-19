---
title: Grenzwerte für Gleitkommakonstanten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- float.h header file
- limits, floating-point constants
- floating-point numbers [C++]
- floating limits
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7bba2bef20cbe5820d2a7feaae5743f151aea9da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417467"
---
# <a name="floating-limits"></a>Grenzwerte für Gleitkommakonstanten
**Microsoft-spezifisch**  
  
 In der folgenden Tabelle sind die Limits für die Werte von Gleitkommakonstanten aufgeführt. Diese Begrenzungen werden auch in der Standardheaderdatei definiert \<float.h >.  
  
### <a name="limits-on-floating-point-constants"></a>Grenzwerte für Gleitkommakonstanten  
  
|Konstante|Bedeutung|Wert|  
|--------------|-------------|-----------|  
|FLT_DIG DBL_DIG LDBL_DIG|Anzahl von Ziffern q, sodass eine Gleitkommazahl mit q Dezimalstellen ohne Genauigkeitsverlust auf eine Gleitkommadarstellung und zurück gerundet werden kann.|6 15 15|  
|FLT_EPSILON DBL_EPSILON LDBL_EPSILON|Kleinste positive Zahl x, sodass x + 1,0 ungleich 1,0 ist.|1.192092896e-07F 2.2204460492503131e-016 2.2204460492503131e-016|  
|FLT_GUARD||0|  
|FLT_MANT_DIG DBL_MANT_DIG LDBL_MANT_DIG|Anzahl von Ziffern in der Basis, die von FLT_RADIX in der Gleitkomma-Mantisse angegeben wird. Die Basis ist 2; Diese Werte geben daher Bits.|24 53 53|  
|FLT_MAX DBL_MAX LDBL_MAX|Darstellbare höchstgleitkommazahl.|3.402823466e+38F 1.7976931348623158e+308 1.7976931348623158e+308|  
|FLT_MAX_10_EXP DBL_MAX_10_EXP LDBL_MAX_10_EXP|Maximale ganze Zahl, sodass 10 auf diese Zahl eine darstellbare Gleitkommazahl ist.|38 308 308|  
|FLT_MAX_EXP DBL_MAX_EXP LDBL_MAX_EXP|Maximale ganze Zahl, sodass FLT_RADIX erhöht auf diese Zahl eine darstellbare Gleitkommazahl ist.|128 1024 1024|  
|FLT_MIN DBL_MIN LDBL_MIN|Minimaler positiver Wert.|1.175494351e-38F 2.2250738585072014e-308 2.2250738585072014e-308|  
|FLT_MIN_10_EXP DBL_MIN_10_EXP LDBL_MIN_10_EXP|Minimale negative Ganzzahl, sodass 10 auf diese Zahl eine darstellbare Gleitkommazahl ist.|-37<br /><br /> -307<br /><br /> -307|  
|FLT_MIN_EXP DBL_MIN_EXP LDBL_MIN_EXP|Minimale negative Ganzzahl, sodass FLT_RADIX erhöht auf diese Zahl eine darstellbare Gleitkommazahl ist.|-125<br /><br /> -1021<br /><br /> -1021|  
|FLT_NORMALIZE||0|  
|FLT_RADIX _DBL_RADIX _LDBL_RADIX|Basis der Exponentendarstellung.|2 2 2|  
|FLT_ROUNDS-_DBL_ROUNDS _LDBL_ROUNDS|Rundungsverhalten für gleitkommaaddition.|1 (Nähe) 1 (Nähe) 1 (Nähe)|  
  
> [!NOTE]
>  Die Informationen in der Tabelle können sich in zukünftigen Versionen des Produkts unterscheiden.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Ganzzahlige Grenzen](../cpp/integer-limits.md)