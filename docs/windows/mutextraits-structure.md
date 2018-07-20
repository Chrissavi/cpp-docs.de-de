---
title: MutexTraits-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
dev_langs:
- C++
helpviewer_keywords:
- MutexTraits structure
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0406ec7938a623be7b16e0535e9d2c0c769f8392
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874589"
---
# <a name="mutextraits-structure"></a>MutexTraits-Struktur
Definiert die gemeinsame Merkmale der [Mutex](../windows/mutex-class1.md) Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct MutexTraits : HANDLENullTraits;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[MutexTraits::Unlock-Methode](../windows/mutextraits-unlock-method.md)|Gibt die exklusive Kontrolle über eine freigegebene Ressource frei.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `HANDLENullTraits`  
  
 `MutexTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers::HandleTraits-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)