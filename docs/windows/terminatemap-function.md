---
title: TerminateMap-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
ms.openlocfilehash: efee7edfc1085288b3220698024cb0deeb4e71af
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643221"
---
# <a name="terminatemap-function"></a>TerminateMap-Funktion

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
inline bool TerminateMap(
   _In_ ModuleBase *module,
   _In_opt_z_ const wchar_t *serverName,
    bool forceTerminate) throw()
```

### <a name="parameters"></a>Parameter

*module*<br/>
Ein [Modul](../windows/module-class.md).

*ServerName*<br/>
Der Name einer Teilmenge von Klassenfactorys in das Modul, das vom Parameter angegebene *Modul*.

*forceTerminate*<br/>
**"true"** zum Beenden der Klasse sind Factorys unabhängig von der sie aktiv ist; **"false"** Klassenfactorys nicht beendet, wenn jede Factory aktiv ist.

## <a name="return-value"></a>Rückgabewert

**"true"** wären alle Klassenfactorys beendet ist, andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

Klassenfactorys im angegebenen Modul wird heruntergefahren.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)