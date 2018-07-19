---
title: 'Comptr:: Asiid-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: d5a3cdb2-796d-4410-966a-847c0e8fb226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db5bc6b2547fb77dd887f96b6c33dee536e43f77
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2018
ms.locfileid: "39025902"
---
# <a name="comptrasiid-method"></a>ComPtr::AsIID-Methode
Gibt ein ComPtr-Objekt zurück, das die Schnittstelle darstellt, die durch die angegebene Schnittstellen-ID gekennzeichnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IUnknown>* p  
) const;  
```  
  
#### <a name="parameters"></a>Parameter  
 `riid`  
 Eine Schnittstellen-ID.  
  
 `p`  
 Wenn das Objekt eine Schnittstelle verfügt, deren ID gleich `riid`, ein doppelt indirekter Zeiger auf die angegebene Schnittstelle die `riid` Parameter ist, andernfalls ein Zeiger auf IUnknown.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)