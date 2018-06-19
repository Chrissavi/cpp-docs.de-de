---
title: 'Weakref:: CopyTo-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 817d984e995e7ac33ba80f978a282a8c0bac3e4f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890634"
---
# <a name="weakrefcopyto-method"></a>WeakRef::CopyTo-Methode
Weist einer Schnittstelle einen Zeiger zu, falls verfügbar zur angegebenen Zeigervariablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ IInspectable** ptr  
);  
  
template<typename U>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
);  
  
HRESULT CopyTo(  
   _Deref_out_ IWeakReference** ptr  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `U`  
 Zeiger auf eine „IInspectable“-Schnittstelle. Ein Fehler wird ausgegeben, wenn `U` nicht von „IInspectable“ abgeleitet ist.  
  
 `riid`  
 Eine Schnittstellen-ID. Ein Fehler wird ausgegeben, wenn `riid` nicht von **IWeakReference**abgeleitet ist.  
  
 `ptr`  
 Ein doppelt indirekter Zeiger auf „IInspectable“ oder „IWeakReference“.  
  
## <a name="return-value"></a>Rückgabewert  
 „S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt. Weitere Informationen finden Sie in den Hinweisen.  
  
## <a name="remarks"></a>Hinweise  
 Der Rückgabewert „S_OK“ bedeutet, dass dieser Vorgang erfolgreich war, gibt aber nicht an, ob der schwache Verweis zu einem starken Verweis aufgelöst wurde. Wenn „S_OK“ zurückgegeben wird, prüfen Sie, ob der Parameter `p` ein starker Verweis ist; das heißt, der Parameter `p` ist kein `nullptr`.  
  
 Beginnend mit dem Windows 10 SDK legt diese Methode die WeakRef-Instanz nicht auf `nullptr` fest, wenn der schwache Verweis nicht abgerufen werden konnte, daher sollten Sie Code zur Fehlerprüfung vermeiden, der WeakRef auf `nullptr`überprüft. Überprüfen Sie stattdessen `ptr` für `nullptr`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [WeakRef-Klasse](../windows/weakref-class.md)