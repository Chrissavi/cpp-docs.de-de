---
title: __fastfail
ms.date: 11/04/2016
ms.assetid: 9cd32639-e395-4c75-9f3a-ac3ba7f49921
ms.openlocfilehash: a9f75cbf3c572401ef26fb16ced221eb24d35534
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041501"
---
# <a name="fastfail"></a>__fastfail

**Microsoft-spezifisch**

Beendet den aufrufenden Prozess mit minimalem Aufwand sofort.

## <a name="syntax"></a>Syntax

```
void __fastfail(unsigned int code);
```

#### <a name="parameters"></a>Parameter

*Code*<br/>
[in] Ein `FAST_FAIL_<description>` symbolische-Konstante von winnt.h oder wdm.h, die den Grund für die prozessbeendigung angibt.

## <a name="return-value"></a>Rückgabewert

Die systeminterne `__fastfail`-Funktion gibt keinen Wert zurück.

## <a name="remarks"></a>Hinweise

Die `__fastfail` systeminterne bietet einen Mechanismus für eine *schnell Fehler* Anforderung – eine Möglichkeit für einen möglicherweise beschädigten Prozess, sofortige Beendigung anzufordern. Kritische Fehler, die den Status des Programms und des Stapels unwiederbringlich beschädigt haben können, können von der regulären Ausnahmebehandlungsfunktion nicht verarbeitet werden. Mit `__fastfail` können Sie den Prozess mit minimalem Aufwand beenden.

Intern wird `__fastfail` mithilfe mehrerer architekturspezifischer Mechanismen implementiert:

|Architektur|Anweisung|Speicherort für das Code-Argument|
|------------------|-----------------|-------------------------------|
|x86|int 0x29|ecx|
|x64|int 0x29|rcx|
|ARM|Opcode 0xDEFB|r0|
|ARM64|Opcode 0xF003|x0|

Eine Fast-Fail-Anforderung ist in sich abgeschlossen und erfordert in der Regel nur zwei Anweisungen, die ausgeführt werden müssen. Nachdem eine Fast-Fail-Anforderung ausgeführt wurde, leitet der Kernel die entsprechende Aktion ein. Im Benutzermoduscode bestehen keine Speicherabhängigkeiten über den Anweisungszeiger selbst hinaus, wenn ein Fast-Fail-Ereignis ausgelöst wird. Dadurch wird eine maximale Zuverlässigkeit erreicht, selbst wenn eine schwerwiegende Speicherbeschädigung vorliegt.

Das `code`-Argument – eine der symbolischen `FAST_FAIL_<description>`-Konstanten von winnt.h oder wdm.h – beschreibt den Typ der Fehlerbedingung und wird auf umgebungsspezifische Weise in Fehlerberichte integriert.

Fast-Fail-Anforderungen im Benutzermodus werden als nicht vernachlässigbare Ausnahme im zweiten Versuch mit Ausnahmecode 0xC0000409 und mindestens einem Ausnahmeparameter angezeigt. Der erste Ausnahmeparameter ist der `code`-Wert. Dieser Ausnahmecode zeigt der Windows Error Reporting (WER)- und Debuginfrastruktur, dass der Prozess beschädigt ist und dass minimale prozessinterne Maßnahmen ergriffen werden sollten, um auf den Fehler zu reagieren. Fast-Fail-Anforderungen im Kernelmodus werden mithilfe eines dedizierten Fehlercodes implementiert: `KERNEL_SECURITY_CHECK_FAILURE` (0x139). In beiden Fällen werden keine Ausnahmehandler aufgerufen, da davon ausgegangen wird, dass das Programm sich in einem beschädigten Zustand befindet. Wenn ein Debugger vorhanden ist, besteht die Möglichkeit, den Zustand des Programms vor dem Beenden zu untersuchen.

Unterstützung für systemeigene Fast-Fail-Mechanismen begann mit Windows 8. Windows-Betriebssysteme, die keine systemeigene Unterstützung der Fast-Fail-Anweisung bieten, behandeln eine Fast-Fail-Anforderung in der Regel als Zugriffsverletzung oder einen `UNEXPECTED_KERNEL_MODE_TRAP`-Fehlercode. In diesen Fällen wird das Programm dennoch beendet, aber nicht unbedingt so schnell.

`__fastfail` ist nur als systeminterne Funktion verfügbar.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__fastfail`|x86, x64, ARM, ARM64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
