---
title: Win32ThreadTraits Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits::CreateThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], Windows threads
- threading [ATL], creation functions
- Win32ThreadTraits class
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b863808a2367cae8878728403dbf11265b9e819
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362015"
---
# <a name="win32threadtraits-class"></a>Win32ThreadTraits-Klasse
Diese Klasse stellt die Funktion für einen Windows-Thread. Verwenden Sie diese Klasse, wenn der Thread CRT-Funktionen nicht verwenden.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class Win32ThreadTraits
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Win32ThreadTraits::CreateThread](#createthread)|(Statisch) Mit dieser Funktion wird zur Erstellung eines Threads, das CRT-Funktionen nicht verwendet werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Thread-Merkmale sind Klassen, die eine Funktion für einen bestimmten Typ des Threads zu ermöglichen. Die Erstellungsfunktion weist die gleiche Signatur und die Semantik wie die Windows [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) Funktion.  
  
 Thread-Merkmale werden durch die folgenden Klassen verwendet:  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 Wenn der Thread CRT-Funktionen verwenden, verwenden Sie [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) stattdessen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="createthread"></a>  Win32ThreadTraits::CreateThread  
 Mit dieser Funktion wird zur Erstellung eines Threads, das CRT-Funktionen nicht verwendet werden soll.  
  
```
static HANDLE CreateThread(
    LPSECURITY_ATTRIBUTES lpsa,
    DWORD dwStackSize,
    LPTHREAD_START_ROUTINE pfnThreadProc,
    void* pvParam,
    DWORD dwCreationFlags,
    DWORD* pdwThreadId) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpsa`  
 Die Sicherheitsattribute für den neuen Thread.  
  
 `dwStackSize`  
 Die Stapelgröße für den neuen Thread.  
  
 `pfnThreadProc`  
 Die Threadprozedur des neuen Threads.  
  
 `pvParam`  
 Der Parameter an die Threadprozedur übergeben werden.  
  
 `dwCreationFlags`  
 Die Erstellung flags (0 oder CREATE_SUSPENDED).  
  
 `pdwThreadId`  
 [out] Die Adresse der DWORD-Variablen, die bei Erfolg, die Thread-ID des neu erstellten Threads empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Handle an den neu erstellten Thread oder NULL bei einem Fehler zurück. Rufen Sie [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) um erweiterte Fehlerinformationen abzurufen.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) für Weitere Informationen zu den Parametern für diese Funktion.  
  
 Diese Funktion ruft `CreateThread` um den Thread erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
