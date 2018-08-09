---
title: CloakedIid-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
dev_langs:
- C++
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3b766858d0f558b4fdff3a703c612ec07c038abf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641919"
---
# <a name="cloakediid-structure"></a>CloakedIid-Struktur
Gibt an, um die `RuntimeClass`, `Implements` und `ChainInterfaces` Vorlagen, dass die angegebene Schnittstelle nicht zugegriffen werden kann, in der IID-Liste ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template<typename T>  
struct CloakedIid : T;  
```  
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Die Schnittstelle, die ausgeblendet ist (verdeckt).  
  
## <a name="remarks"></a>Hinweise  
 Im folgenden ist ein Beispiel dafür, wie **CloakedIid** wird verwendet: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `T`  
  
 `CloakedIid`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)