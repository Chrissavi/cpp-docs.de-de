---
title: Helpstringdll | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstringdll
dev_langs:
- C++
helpviewer_keywords:
- helpstringdll attribute [C++]
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 94e33eea3dc367634b3cae9a025b0189598bbdd1
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648950"
---
# <a name="helpstringdll"></a>helpstringdll
Gibt den Namen der DLL zu verwenden, um die Suche nach Dokument (Lokalisierung) ausführen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
[ helpstringdll(  
   "string"  
) ]  
```  
  
### <a name="parameters"></a>Parameter  
 *string*  
 Die DLL zu verwenden, um die Suche nach Dokument auszuführen.  
  
## <a name="remarks"></a>Hinweise  
 Die **Helpstringdll** C++-Attribut hat die gleiche Funktionalität wie die [Helpstringdll](http://msdn.microsoft.com/library/windows/desktop/aa366860) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// cpp_attr_ref_helpstringdll.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib", helpstringdll="xx.dll")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI   
{  
   HRESULT xxx();  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, **Schnittstelle**,-Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   