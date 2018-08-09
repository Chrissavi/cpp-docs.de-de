---
title: 'WeakReference:: Setunknown-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::SetUnknown
dev_langs:
- C++
helpviewer_keywords:
- SetUnknown method
ms.assetid: 5dddb9e3-a7c1-4195-8166-97c5ab6e972f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d6adf747fd7612c2bcaa0964f91ecb585bbfbef0
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018051"
---
# <a name="weakreferencesetunknown-method"></a>WeakReference::SetUnknown-Methode
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void SetUnknown(  
   _In_ IUnknown* unk  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *UNK*  
 Ein Zeiger auf die `IUnknown` -Schnittstelle eines Objekts.  
  
## <a name="remarks"></a>Hinweise  
 Den starken Verweis des aktuellen legt **WeakReference** Objekt, das den angegebenen Schnittstellenzeiger auf.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch
 [WeakReference-Klasse](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)