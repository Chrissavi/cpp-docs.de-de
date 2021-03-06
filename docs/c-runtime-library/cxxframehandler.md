---
title: __CxxFrameHandler
ms.date: 11/04/2016
api_name:
- __CxxFrameHandler
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __CxxFrameHandler
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
ms.openlocfilehash: b6350568bdba41da90609dfd5e2e60269e7d729f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217037"
---
# <a name="__cxxframehandler"></a>__CxxFrameHandler

Interne CRT-Funktion. Wird von CRT verwendet, um Frames für strukturierte Ausnahmen zu verarbeiten.

## <a name="syntax"></a>Syntax

```cpp
EXCEPTION_DISPOSITION __CxxFrameHandler(
      EHExceptionRecord  *pExcept,
      EHRegistrationNode *pRN,
      void               *pContext,
      DispatcherContext  *pDC
   )
```

#### <a name="parameters"></a>Parameter

*pExcept*<br/>
Der Ausnahme Daten Satz, der an die möglichen-Anweisungen übermittelt wird **`catch`** .

*pRN*<br/>
Dynamische Informationen über den Stapelrahmen, der zur Verarbeitung der Ausnahme verwendet wird. Weitere Informationen finden Sie unter ehdata.h.

*pContext*<br/>
Kontext. (Wird bei Intel-Prozessoren nicht verwendet.)

*PDC*<br/>
Zusätzliche Informationen über den Funktionsstart und den Stapelrahmen.

## <a name="return-value"></a>Rückgabewert

Einer der *Filterausdruckswerte*, die von der [try-except-Anweisung](../cpp/try-except-statement.md) verwendet werden.

## <a name="remarks"></a>Bemerkungen

## <a name="requirements"></a>Requirements (Anforderungen)

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__CxxFrameHandler|excpt.h, ehdata.h|
