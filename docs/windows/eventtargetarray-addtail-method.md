---
title: 'Eventtargetarray:: Addtail-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
dev_langs:
- C++
helpviewer_keywords:
- AddTail method
ms.assetid: d0fafab9-049c-40e0-a40c-d126c9ee63e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0bc56e13c8d07841ceb1f341228d7a963fda2dd8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872282"
---
# <a name="eventtargetarrayaddtail-method"></a>EventTargetArray::AddTail-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
void AddTail(  
   _In_ IUnknown* element  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `element`  
 Zeiger auf der Ereignishandler angefügt werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Fügt den angegebenen Ereignishandler an das Ende des internen Arrays von Ereignishandlern an.  
  
 AddTail() soll von EventSource-Klasse intern verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [EventTargetArray-Klasse](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)