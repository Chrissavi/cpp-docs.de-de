---
title: Pointer_default | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pointer_default
dev_langs:
- C++
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ee904f9243cf642d3a942d4bc323f5ec381b0480
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877461"
---
# <a name="pointerdefault"></a>pointer_default
Gibt das Standardattribut für die Zeiger für alle Zeiger, mit Ausnahme der obersten Ebene Zeiger, die in Parameterlisten angezeigt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ pointer_default(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *Wert*  
 Ein Wert, der beschreibt, den Zeigertyp: **Ptr**, `ref`, oder **eindeutige**.  
  
## <a name="remarks"></a>Hinweise  
 Die **Pointer_default** C++-Attribut hat die gleiche Funktionalität wie die [Pointer_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für ["DefaultValue"](../windows/defaultvalue.md) für ein Beispiel für die Verwendung von **Pointer_default**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|`interface`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
