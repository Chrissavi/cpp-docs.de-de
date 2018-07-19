---
title: Defaultvtable | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultvtable
dev_langs:
- C++
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cb853e10b1745151c12f1855f841a21c2a7e126b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882536"
---
# <a name="defaultvtable"></a>defaultvtable
Definiert eine Schnittstelle als die Vtable Standardschnittstelle für ein COM-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ defaultvtable(  
   interface  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 `interface`  
 Die angegebene Schnittstelle, die Vtable Standard für das COM-Objekt sein sollen.  
  
## <a name="remarks"></a>Hinweise  
 Die **Defaultvtable** C++-Attribut hat die gleiche Funktionalität wie die [Defaultvtable](http://msdn.microsoft.com/library/windows/desktop/aa366795) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt die Attribute für eine Klasse, mit denen **Defaultvtable** eine Standardschnittstelle an:  
  
```  
// cpp_attr_ref_defaultvtable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI1 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface IMyI2 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000003")]  
__interface IMyI3 {  
   HRESULT x();  
};  
  
[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),  
uuid("00000000-0000-0000-0000-000000000004")]  
class CMyC3 : public IMyI3 {};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**coclass**|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
