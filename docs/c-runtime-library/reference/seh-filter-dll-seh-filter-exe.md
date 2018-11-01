---
title: _seh_filter_dll, _seh_filter_exe
ms.date: 11/04/2016
apiname:
- _XcptFilter
- _seh_filter_dll
- _seh_filter_exe
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- XcptFilter
- _XcptFilter
- _seh_filter_dll
- _seh_filter_exe
- corecrt_startup/_seh_filter_exe
- corecrt_startup/_seh_filter_dll
helpviewer_keywords:
- XcptFilter function
- _XcptFilter function
- _seh_filter_dll function
- _seh_filter_exe function
ms.assetid: 747e5963-3a12-4bf5-b5c4-d4c1b6068e15
ms.openlocfilehash: 51d6a21b3867eb830a7d9f9b4b9b0ac844cd5aa1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573030"
---
# <a name="sehfilterdll-sehfilterexe"></a>_seh_filter_dll, _seh_filter_exe

Gibt die Ausnahme und die zugehörige Aktion an, die ausgeführt werden soll.

## <a name="syntax"></a>Syntax

```C
int __cdecl _seh_filter_dll(
   unsigned long _ExceptionNum,
   struct _EXCEPTION_POINTERS* _ExceptionPtr
);
int __cdecl _seh_filter_exe(
   unsigned long _ExceptionNum,
   struct _EXCEPTION_POINTERS* _ExceptionPtr
);
```

### <a name="parameters"></a>Parameter

*_ExceptionNum*<br/>
Der Bezeichner für die Ausnahme.

*_ExceptionPtr*<br/>
Ein Zeiger auf die Ausnahmeinformationen.

## <a name="return-value"></a>Rückgabewert

Eine ganze Zahl, die entsprechend dem Ergebnis der Ausnahmeverarbeitung die Aktion angibt, die ausgeführt werden soll.

## <a name="remarks"></a>Hinweise

Diese Methoden werden durch den Ausnahmefilterausdruck [try-except-Anweisung](../../cpp/try-except-statement.md) aufgerufen. Die Methode fragt eine interne Tabelle mit Konstanten ab, um die Ausnahme zu ermitteln und die geeignete Aktion zu bestimmen (siehe nächste Tabelle). Die Ausnahmenummern sind in „winnt.h“ definiert, und die Signalnummern sind in „signal.h“ definiert.

|Ausnahmenummer (unsigned long)|Signalnummer|
|----------------------------------------|-------------------|
|STATUS_ACCESS_VIOLATION|SIGSEGV|
|STATUS_ILLEGAL_INSTRUCTION|SIGILL|
|STATUS_PRIVILEGED_INSTRUCTION|SIGILL|
|STATUS_FLOAT_DENORMAL_OPERAND|SIGFPE|
|STATUS_FLOAT_DIVIDE_BY_ZERO|SIGFPE|
|STATUS_FLOAT_INEXACT_RESULT|SIGFPE|
|STATUS_FLOAT_INVALID_OPERATION|SIGFPE|
|STATUS_FLOAT_OVERFLOW|SIGFPE|
|STATUS_FLOAT_STACK_CHECK|SIGFPE|
|STATUS_FLOAT_UNDERFLOW|SIGFPE|

## <a name="requirements"></a>Anforderungen

**Header:** corecrt_startup.h

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
