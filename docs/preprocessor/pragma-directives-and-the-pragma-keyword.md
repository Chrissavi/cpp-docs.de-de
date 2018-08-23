---
title: Pragma-Direktiven und das __Pragma-Schlüsselwort | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#pragma'
dev_langs:
- C++
helpviewer_keywords:
- '#pragma directives, C/C++'
- __pragma keyword
- pragma directives, C/C++
- pragmas, C/C++
- preprocessor
- pragmas
- preprocessor, pragmas
- pragma directives (#pragma)
ms.assetid: 9867b438-ac64-4e10-973f-c3955209873f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 76a29a7ae4734e5d1f1930d5309163d1e1519aa4
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540600"
---
# <a name="pragma-directives-and-the-pragma-keyword"></a>Pragma-Anweisungen und das __Pragma-Schlüsselwort
Pragma-Anweisungen geben computer- oder betriebssystemspezifische Compilerfunktionen an. Die **__pragma** -Schlüsselwort, das an den Microsoft-Compiler spezifisch ist, können Sie Code Pragma-Anweisungen innerhalb von Makrodefinitionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma token-string  
__pragma(token-string)  
```  
  
## <a name="remarks"></a>Hinweise  
 
Jede Implementierung von C und C++ unterstützt mehrere Funktionen, die auf dem Hostcomputer oder Betriebssystem einzigartig sind. Einige Programme beispielsweise müssen die Speicherbereiche genau kontrollieren, in denen Daten abgelegt werden, oder die Art und Weise steuern, wie bestimmte Funktionen Parameter empfangen. Die **#pragma** Anweisungen bieten eine Möglichkeit für jeden Compiler für Computer und Betriebssystem-spezifischen-Funktionen bereitzustellen und dabei die gesamtkompatibilität mit anderen C- und C++-Programmiersprachen beizubehalten.  
  
Pragmas sind definitionsgemäß computer- oder betriebssystemspezifisch, und sie sind normalerweise für jeden Compiler unterschiedlich. Pragmas können in bedingten Anweisungen verwendet werden, um neue Präprozessorfunktionen oder von der Implementierung abhängige Informationen für den Compiler bereitzustellen.  
  
`token-string` ist eine Reihe von Zeichen, die einem bestimmten Compiler Anweisungen und Argumente gibt, falls vorhanden. Das Nummernzeichen (**#**) muss die erste nicht-Leerzeichen in der Zeile, die das Pragma enthält; Leerzeichen können das Nummernzeichen und das Wort "Pragma" trennen. Folgende **#pragma**, Schreiben Sie beliebigen Text ein, die das Konvertierungsprogramm als vorverarbeitungstoken analysieren kann. Das Argument für **#pragma** unterliegt der makroerweiterung.  
  
Wenn der Compiler ein Pragma findet, das er nicht erkennt, gibt er eine Warnung aus und setzt die Kompilierung fort.  
  
Die Microsoft C- und C++-Compiler erkennen die folgenden Pragmas:  
  
||||  
|-|-|-|  
|[alloc_text](../preprocessor/alloc-text.md)|[auto_inline](../preprocessor/auto-inline.md)|[bss_seg](../preprocessor/bss-seg.md)|  
|[check_stack](../preprocessor/check-stack.md)|[code_seg](../preprocessor/code-seg.md)|[comment](../preprocessor/comment-c-cpp.md)|  
|[component](../preprocessor/component.md)|[entsprechen](../preprocessor/conform.md) <sup>1</sup>|[const_seg](../preprocessor/const-seg.md)|  
|[data_seg](../preprocessor/data-seg.md)|[Veraltet](../preprocessor/deprecated-c-cpp.md)|[detect_mismatch](../preprocessor/detect-mismatch.md)|  
|[fenv_access](../preprocessor/fenv-access.md)|[float_control](../preprocessor/float-control.md)|[fp_contract](../preprocessor/fp-contract.md)|  
|[function](../preprocessor/function-c-cpp.md)|[hdrstop](../preprocessor/hdrstop.md)|[include_alias](../preprocessor/include-alias.md)|  
|[init_seg](../preprocessor/init-seg.md) <sup>1</sup>|[inline_depth](../preprocessor/inline-depth.md)|[inline_recursion](../preprocessor/inline-recursion.md)|  
|[intrinsic](../preprocessor/intrinsic.md)|[Schleife](../preprocessor/loop.md) <sup>1</sup>|[make_public](../preprocessor/make-public.md)|  
|[Verwaltet](../preprocessor/managed-unmanaged.md)|[message](../preprocessor/message.md)||  
|[omp](../preprocessor/omp.md)|[once](../preprocessor/once.md)||  
|[optimize](../preprocessor/optimize.md)|[pack](../preprocessor/pack.md)|[Pointers_to_members](../preprocessor/pointers-to-members.md) <sup>1</sup>|  
|[pop_macro](../preprocessor/pop-macro.md)|[push_macro](../preprocessor/push-macro.md)|[region, endregion](../preprocessor/region-endregion.md)|  
|[runtime_checks](../preprocessor/runtime-checks.md)|[section](../preprocessor/section.md)|[setlocale](../preprocessor/setlocale.md)|  
|[strict_gs_check](../preprocessor/strict-gs-check.md)|[nicht verwaltete](../preprocessor/managed-unmanaged.md)|[Vtordisp](../preprocessor/vtordisp.md) <sup>1</sup>|  
|[warning](../preprocessor/warning.md)|||  
  
 1. Wird nur vom C++-Compiler unterstützt.  
  
## <a name="pragmas-and-compiler-options"></a>Pragmas und Compileroptionen  
 
Einige Pragmas stellen die gleichen Funktionen wie Compileroptionen bereit. Wenn im Quellcode ein Pragma gefunden wird, überschreibt dieses das Verhalten, das mit der Compileroption angegeben wird. Wenn Sie angegeben haben z. B. ["/ zp8"](../build/reference/zp-struct-member-alignment.md), können Sie diese compilereinstellung für bestimmte Codeabschnitte mit überschreiben [Pack](../preprocessor/pack.md):  
  
```  
cl /Zp8 ...  
  
<file> - packing is 8  
// ...  
#pragma pack(push, 1) - packing is now 1  
// ...  
#pragma pack(pop) - packing is 8  
</file>  
```  
  
## <a name="the-pragma-keyword"></a>Das __pragma()-Schlüsselwort  
 
**Microsoft-spezifisch**  
  
Der Compiler unterstützt ebenfalls die **__pragma** -Schlüsselwort, das die gleiche Funktion hat wie die **#pragma** -Direktive aber Inline in einer Makrodefinition verwendet werden kann. Die **#pragma** Richtlinie kann nicht in einer Makrodefinition verwendet werden, da der Compiler das Nummernzeichen ('#') in der Anweisung interpretiert die [Zeichenfolgenoperator (#)](../preprocessor/stringizing-operator-hash.md).  
  
Im folgenden Codebeispiel wird veranschaulicht, wie die **__pragma** -Schlüsselwort kann in einem Makro verwendet werden. Dieser Code wurde dem mfcdual.h-Header im ACDUAL-Beispiel in den Beispielen für die COM-Unterstützung des Compilers entnommen:  
  
```  
#define CATCH_ALL_DUAL \  
CATCH(COleException, e) \  
{ \  
_hr = e->m_sc; \  
} \  
AND_CATCH_ALL(e) \  
{ \  
__pragma(warning(push)) \  
__pragma(warning(disable:6246)) /*disable _ctlState prefast warning*/ \  
AFX_MANAGE_STATE(pThis->m_pModuleState); \  
__pragma(warning(pop)) \  
_hr = DualHandleException(_riidSource, e); \  
} \  
END_CATCH_ALL \  
return _hr; \  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 
[C/C++-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md)   
[C-Pragmas](../c-language/c-pragmas.md)   
[Schlüsselwörter](../cpp/keywords-cpp.md)