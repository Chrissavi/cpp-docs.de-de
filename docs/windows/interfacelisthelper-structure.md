---
title: InterfaceListHelper-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceListHelper
dev_langs:
- C++
helpviewer_keywords:
- InterfaceListHelper structure
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8ad091114d6be6f35f1a0341961dc5122840ace8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878046"
---
# <a name="interfacelisthelper-structure"></a>InterfaceListHelper-Struktur
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename T0,  
   typename T1 = Nil,  
   typename T2 = Nil,  
   typename T3 = Nil,  
   typename T4 = Nil,  
   typename T5 = Nil,  
   typename T6 = Nil,  
   typename T7 = Nil,  
   typename T8 = Nil,  
   typename T9 = Nil  
>  
struct InterfaceListHelper;  
  
template <  
   typename T0  
>  
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T0`  
 Vorlagenparameter 0 (null) ist erforderlich.  
  
 `T1`  
 Template-Parameter 1, die standardmäßig nicht angegeben wird.  
  
 `T2`  
 Template-Parameter 2, die standardmäßig nicht angegeben wird. Der dritte Vorlagenparameter.  
  
 `T3`  
 Template-Parameter 3, die standardmäßig nicht angegeben wird.  
  
 `T4`  
 Vorlagenparameter 4, die standardmäßig nicht angegeben wird.  
  
 `T5`  
 Vorlagenparameter 5, die standardmäßig nicht angegeben wird.  
  
 `T6`  
 Vorlagenparameter 6, die standardmäßig nicht angegeben wird.  
  
 `T7`  
 Vorlagenparameter 7, die standardmäßig nicht angegeben wird.  
  
 `T8`  
 Vorlagenparameter 8, die standardmäßig nicht angegeben wird.  
  
 `T9`  
 Vorlagenparameter 9, die standardmäßig nicht angegeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Erstellt einen InterfaceList-Typ durch Anwenden der angegebenen Parameter Vorlagenargumente rekursiv.  
  
 InterfaceListHelper-Vorlage verwendet Vorlagenparameter `T0` definieren die ersten Daten Member in einem InterfaceList-Struktur, und klicken Sie dann rekursiv die InterfaceListHelper-Vorlage auf alle verbleibenden Vorlagenparameter angewendet. InterfaceListHelper wird beendet, wenn keine verbleibenden Vorlagenparameter vorhanden sind.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`TypeT`|Ein Synonym für den InterfaceList-Typ.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `InterfaceListHelper`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)