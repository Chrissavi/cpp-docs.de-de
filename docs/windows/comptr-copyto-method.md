---
title: 'Comptr:: CopyTo-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: 8801bc49-6db4-4393-a55f-a701ae3b8718
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 680c1278ca2b17c7ea35e72946fb5d5030c5e7c0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33870870"
---
# <a name="comptrcopyto-method"></a>ComPtr::CopyTo-Methode
Kopiert die aktuelle oder angegebene-Schnittstelle, die diesem comptr-Objekt an den angegebenen Zeiger zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CopyTo(  
   _Deref_out_ InterfaceType** ptr  
);  
  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ void** ptr  
) const;  

template<typename U>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
) const;  
```  
  
#### <a name="parameters"></a>Parameter  
 `U`  
 Ein Typname.  
  
 `ptr`  
 Wenn dieser Vorgang abgeschlossen wird, einen Zeiger auf die angeforderte Schnittstelle.  
  
 `riid`  
 Eine Schnittstellen-ID.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, der angibt, warum die implizite QueryInterface-Vorgang fehlgeschlagen ist.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Funktion gibt eine Kopie des einen Zeiger auf die Schnittstelle, die diesem comptr-Objekt zugeordnet. Diese Funktion gibt immer S_OK zurück.  
  
 Die zweite Funktion führt eine QueryInterface-Operation für die Schnittstelle, die diesem comptr-Objekt für die angegebene Schnittstelle zugeordneten der `riid` Parameter.  
  
 Die dritte Funktion führt eine QueryInterface-Operation für die Schnittstelle, die diesem comptr-Objekt für die zugrunde liegende Schnittstelle des zugeordneten der `U` Parameter.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)