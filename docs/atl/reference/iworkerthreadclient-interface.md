---
title: IWorkerThreadClient Schnittstelle | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
dev_langs:
- C++
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8336edb07d02bbbcd5775eaf3ef8fe0f735d3adb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359816"
---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient-Schnittstelle
`IWorkerThreadClient` ist die Schnittstelle implementiert, die von Clients von der [CWorkerThread](../../atl/reference/cworkerthread-class.md) Klasse.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
__interface IWorkerThreadClient
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CloseHandle](#closehandle)|Implementieren Sie diese Methode, um das diesem Objekt zugeordnete Handle nicht geschlossen.|  
|[Führen Sie](#execute)|Implementieren Sie diese Methode, um Code auszuführen, wenn das Handle, das diesem Objekt zugeordneten signalisiert wird.|  
  
## <a name="remarks"></a>Hinweise  
 Implementieren Sie diese Schnittstelle, wenn Sie über Code verfügen, die in Reaktion auf ein Handle signalisiert einem Arbeitsthread ausgeführt werden muss.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle  
 Implementieren Sie diese Methode, um das diesem Objekt zugeordnete Handle nicht geschlossen.  
  
```
HRESULT CloseHandle(HANDLE  hHandle);
```  
  
### <a name="parameters"></a>Parameter  
 *hHandle*  
 Das Handle geschlossen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Geben Sie S_OK zurück, auf Erfolg oder einen HRESULT-Fehler bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Das Handle übergeben an diese Methode wurde zuvor mit diesem Objekt verknüpften durch einen Aufruf von [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Beispiel  
 Der folgende Code zeigt eine einfache Implementierung der `IWorkerThreadClient::CloseHandle`.  
  
 [!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]  
  
##  <a name="execute"></a>  IWorkerThreadClient::Execute  
 Implementieren Sie diese Methode, um Code auszuführen, wenn das Handle, das diesem Objekt zugeordneten signalisiert wird.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>Parameter  
 `dwParam`  
 Der Benutzerparameter.  
  
 `hObject`  
 Das Handle, das signalisiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Geben Sie S_OK zurück, auf Erfolg oder einen HRESULT-Fehler bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Das Handle und die DWORD/Zeiger an diese Methode übergebenen wurden zuvor mit diesem Objekt durch einen Aufruf von verknüpften [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Beispiel  
 Der folgende Code zeigt eine einfache Implementierung der `IWorkerThreadClient::Execute`.  
  
 [!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../atl/reference/atl-classes.md)   
 [CWorkerThread-Klasse](../../atl/reference/cworkerthread-class.md)
