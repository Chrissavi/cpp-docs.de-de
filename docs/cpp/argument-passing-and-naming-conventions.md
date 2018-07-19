---
title: Argumentübergabe und Benennungskonventionen für | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- argument passing [C++], conventions
- arguments [C++], widening
- coding conventions, arguments
- arguments [C++], passing
- registers, return values
- thiscall keyword [C++]
- naming conventions [C++], arguments
- arguments [C++], naming
- passing arguments [C++], conventions
- conventions [C++], argument names
ms.assetid: de468979-eab8-4158-90c5-c198932f93b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43aa3430b641f6333c6c35d618f9e9de123b7390
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413485"
---
# <a name="argument-passing-and-naming-conventions"></a>Argumentübergabe und Benennungskonventionen
**Microsoft-spezifisch**  
  
 Mithilfe der Visual C++-Compiler können Sie Konventionen zum Übergeben von Argumenten und Zurückgeben von Werten zwischen Funktionen und Aufrufern festlegen. Nicht alle Konventionen sind auf allen unterstützten Plattformen verfügbar, und einige Konventionen verwenden plattformspezifische Implementierungen. In den meisten Fällen werden Schlüsselwörter oder Compilerschalter, die eine nicht unterstützte Konvention auf einer bestimmten Plattform angeben, ignoriert und die Plattformstandardkonvention wird verwendet.  
  
 Auf x86-Plattformen werden alle Argumente bei Übergabe auf 32 Bits erweitert. Rückgabewerte werden ebenfalls auf 32 Bit erweitert und im EAX-Register zurückgegeben. Eine Ausnahme bilden 8-Byte-Strukturen, die im EDX:EAX-Registerpaar zurückgegeben werden. Größere Strukturen werden im EAX-Register als Zeiger auf ausgeblendete Rückgabestrukturen zurückgegeben. Parameter werden auf von rechts nach links auf den Stapel verschoben. Strukturen, die keine PODs sind, werden nicht in Registern zurückgegeben.  
  
 Vom Compiler wird Prolog- und Epilogcode zum Speichern und Wiederherstellen von ESI-, EDI-, EBX- sowie EBP-Registern verwendet, sofern sie in der Funktion verwendet werden.  
  
> [!NOTE]
>  Wenn eine Struktur, Union oder Klasse nach Wert aus einer Funktion zurückgegeben wird, müssen alle Definitionen des Typs identisch sein, andernfalls können zur Laufzeit Fehler im Programm auftreten.  
  
 Informationen zum Definieren Ihrer eigenen Funktionscode Prolog und Epilog finden Sie unter [Naked-Funktionsaufrufe](../cpp/naked-function-calls.md).  
  
 Informationen zum Standard-Aufrufkonventionen in Code, der Ziele X64-Plattformen finden Sie unter [Überblick X64 Aufrufkonventionen](../build/overview-of-x64-calling-conventions.md). Informationen zum Aufrufen von Konvention Probleme im Code, der ARM-Plattformen ausgerichtet ist, finden Sie unter [häufige Visual C++ ARM-Migrationsprobleme](../build/common-visual-cpp-arm-migration-issues.md).  
  
 Die folgenden Aufrufkonventionen werden vom Visual C/C++-Compiler unterstützt.  
  
|Stichwort|Stapelcleanup|Parameterübergabe|  
|-------------|-------------------|-----------------------|  
|[__cdecl](../cpp/cdecl.md)|Aufrufer|Schiebt Parameter in umgekehrter Reihenfolge (von rechts nach links) auf den Stapel|  
|[__clrcall](../cpp/clrcall.md)|n/v|Parameter der Reihe nach (von links nach rechts) auf den CLR-Ausdrucksstapel laden.|  
|[__stdcall](../cpp/stdcall.md)|Aufgerufener|Schiebt Parameter in umgekehrter Reihenfolge (von rechts nach links) auf den Stapel|  
|[__fastcall](../cpp/fastcall.md)|Aufgerufener|Wird in Registern gespeichert und dann auf dem Stapel abgelegt|  
|[__thiscall](../cpp/thiscall.md)|Aufgerufener|Auf dem Stapel abgelegt werden; **dies** Zeiger in ECX gespeichert|  
|[__vectorcall](../cpp/vectorcall.md)|Aufgerufener|Wird in Registern gespeichert und anschließend in umgekehrter Reihenfolge auf dem Stapel abgelegt (rechts nach links)|  
  
 Weitere Informationen finden Sie unter [veraltete Aufrufkonventionen](../cpp/obsolete-calling-conventions.md).  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonventionen](../cpp/calling-conventions.md)