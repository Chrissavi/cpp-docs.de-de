---
title: CComCritSecLock Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98b6eb7a8e6df16134573b55a7c9666befe4e4a1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358885"
---
# <a name="ccomcritseclock-class"></a>CComCritSecLock-Klasse
Diese Klasse stellt Methoden zum Sperren und Entsperren von einem kritischen Abschnittsobjekt bereit.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class TLock> class CComCritSecLock
```  
  
#### <a name="parameters"></a>Parameter  
 *TLock*  
 Das Objekt gesperrt und entsperrt werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCritSecLock::CComCritSecLock](#ctor)|Der Konstruktor.|  
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCritSecLock::Lock](#lock)|Rufen Sie diese Methode, um die kritischen Abschnittsobjekt sperren.|  
|[CComCritSecLock::Unlock](#unlock)|Rufen Sie diese Methode, um die kritischen Abschnittsobjekt zu entsperren.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Klasse zum Sperren und Entsperren von Objekten auf sicherere Weise als mit der ["CComCriticalSection"-Klasse](../../atl/reference/ccomcriticalsection-class.md) oder [CComAutoCriticalSection Klasse](../../atl/reference/ccomautocriticalsection-class.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="ctor"></a>  CComCritSecLock::CComCritSecLock  
 Der Konstruktor.  
  
```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```  
  
### <a name="parameters"></a>Parameter  
 *cs*  
 Das Objekt kritischen Abschnitts.  
  
 `bInitialLock`  
 Der Zustand der ursprünglichen Sperre: **"true"** bedeutet, dass gesperrt.  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert das Objekt kritischen Abschnitts.  
  
##  <a name="dtor"></a>  CComCritSecLock:: ~ CComCritSecLock  
 Der Destruktor.  
  
```
~CComCritSecLock() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Entsperrt den kritischen Abschnittsobjekt an.  
  
##  <a name="lock"></a>  CComCritSecLock::Lock  
 Rufen Sie diese Methode, um die kritischen Abschnittsobjekt sperren.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn das Objekt erfolgreich gesperrt wurde oder einen HRESULT-Fehler zurückgegeben bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Objekt bereits gesperrt ist, tritt ein ASSERT-Fehler in der Debug-Builds.  
  
##  <a name="unlock"></a>  CComCritSecLock::Unlock  
 Rufen Sie diese Methode, um die kritischen Abschnittsobjekt zu entsperren.  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Objekt bereits nicht gesperrt ist, tritt ein ASSERT-Fehler in der Debug-Builds.  
  
## <a name="see-also"></a>Siehe auch  
 ["CComCriticalSection"-Klasse](../../atl/reference/ccomcriticalsection-class.md)   
 [CComAutoCriticalSection-Klasse](../../atl/reference/ccomautocriticalsection-class.md)
