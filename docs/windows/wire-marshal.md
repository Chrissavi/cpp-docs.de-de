---
title: Wire_marshal | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.wire_marshal
dev_langs:
- C++
helpviewer_keywords:
- wire_marshal attribute
ms.assetid: 244f9d72-776d-4ebd-b60a-cee600a126b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4c13889c15476ff263658d7b5b4024e7a5deebe5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890212"
---
# <a name="wiremarshal"></a>wire_marshal
Gibt einen Datentyp, der für die Übertragung anstelle eines Typs programmspezifische Daten verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[wire_marshal]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **Wire_marshal** C++-Attribut hat die gleiche Funktionalität wie die [Wire_marshal](http://msdn.microsoft.com/library/windows/desktop/aa367309) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code veranschaulicht die Verwendung der **Wire_marshal**:  
  
```  
// cpp_attr_ref_wire_marshal.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[export, public] typedef unsigned long _FOUR_BYTE_DATA;  
  
[export] typedef struct _TWO_X_TWO_BYTE_DATA {  
   unsigned short low;  
   unsigned short high;  
} TWO_X_TWO_BYTE_DATA ;  
  
[export, wire_marshal(TWO_X_TWO_BYTE_DATA)] typedef _FOUR_BYTE_DATA FOUR_BYTE_DATA;  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|`typedef`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
