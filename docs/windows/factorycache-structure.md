---
title: FactoryCache-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
dev_langs:
- C++
helpviewer_keywords:
- FactoryCache structure
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 04356316b67f3c341fe1dd1821750fcd3136aa40
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874030"
---
# <a name="factorycache-structure"></a>FactoryCache-Struktur
Unterstützt die Windows Runtime C++ Template Library-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct FactoryCache;  
```  
  
## <a name="remarks"></a>Hinweise  
 Enthält den Speicherort einer Klassenfactory und ein Wert, der einem registrierten wrt identifiziert oder COM-Klassenobjekt.  
  
## <a name="members"></a>Member  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[FactoryCache::cookie-Datenmember](../windows/factorycache-cookie-data-member.md)|Enthält einen Wert, der ein registrierten Windows-Runtime oder COM-Klassenobjekt bezeichnet und wird später verwendet werden, um stattdessen das Aufheben der Registrierung.|  
|[FactoryCache::factory-Datenmember](../windows/factorycache-factory-data-member.md)|Verweist auf ein Windows-Runtime oder COM-Klassenfactory.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `FactoryCache`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)