---
title: CRTThreadTraits-Klasse
ms.date: 11/04/2016
f1_keywords:
- CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits::CreateThread
helpviewer_keywords:
- CRTThreadTraits class
- threading [ATL], creation functions
- threading [ATL], CRT threads
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
ms.openlocfilehash: 1e54b4db2605c3006697d0a26d34066de666f0fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641947"
---
# <a name="crtthreadtraits-class"></a>CRTThreadTraits-Klasse

Diese Klasse stellt die Erstellungsfunktion für einen Thread CRT. Verwenden Sie diese Klasse aus, wenn der Thread die CRT-Funktionen verwenden möchten.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CRTThreadTraits
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRTThreadTraits::CreateThread](#createthread)|(Statisch) Rufen Sie diese Funktion zur Erstellung eines Threads, das CRT-Funktionen verwenden können.|

## <a name="remarks"></a>Hinweise

Thread "traits" sind Klassen, die eine Funktion für einen bestimmten Typ des Threads zu ermöglichen. Die Erstellungsfunktion weist die gleiche Signatur und die gleiche Semantik wie die Windows [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) Funktion.

Thread "traits" werden die folgenden Klassen verwendet:

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

Wenn der Thread nicht CRT-Funktionen verwenden, verwenden Sie [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md) stattdessen.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="createthread"></a>  CRTThreadTraits::CreateThread

Rufen Sie diese Funktion zur Erstellung eines Threads, das CRT-Funktionen verwenden können.

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

*lpsa*<br/>
Die Sicherheitsattribute für den neuen Thread.

*dwStackSize*<br/>
Die Stapelgröße für den neuen Thread.

*pfnThreadProc*<br/>
Die Threadprozedur des neuen Threads.

*pvParam*<br/>
Der Parameter an die Threadprozedur übergeben werden.

*"dwCreationFlags"*<br/>
Die Erstellung flags ("0" oder "CREATE_SUSPENDED").

*pdwThreadId*<br/>
[out] Adresse der DWORD-Variable, die bei Erfolg die Thread-ID des neu erstellten Threads empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt das Handle auf das neu erstellte Thread oder NULL bei einem Fehler zurück. Rufen Sie [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) um erweiterte Fehlerinformationen abzurufen.

### <a name="remarks"></a>Hinweise

Finden Sie unter [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) für Weitere Informationen zu den Parametern für diese Funktion.

Diese Funktion ruft [_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) um den Thread erstellen.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
