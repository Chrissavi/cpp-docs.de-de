---
title: Inlineassembler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assembler [C++]
- assembler [C++], inline
- assembly language [C++], inline
- inline assembler [C++]
- inline assembly [C++]
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b45c55fbba37d27aa005480789cb490b891b103
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42571575"
---
# <a name="inline-assembler"></a>Inlineassembler
**Microsoft-spezifisch**  
  
 Die Assemblysprache dient vielen Zwecken, wie etwa der Verbesserung der Programmgeschwindigkeit, der Verringerung der Speicheranforderungen und der Steuerung der Hardware. Sie können den Inlineassembler verwenden, um Assemblysprachanweisungen ohne zusätzliche Assembly- und Verknüpfungsschritte direkt in die C- und C++-Quellprogramme einzubetten. Der Inlineassembler wird in den Compiler integriert, daher benötigen Sie keinen getrennten Assembler wie den Microsoft Macro Assembler (MASM).  
  
> [!NOTE]
>  Programme mit Inlineassemblercode sind nicht vollständig auf andere Hardwareplattformen übertragbar. Wenn Ihnen Portabilität wichtig ist, vermeiden Sie beim Entwerfen die Verwendung des Inlineassemblers.  
  
 Inlineassembly wird nicht unterstützt, auf dem ARM und X64 Prozessoren.  In folgenden Themen wird erklärt, wie der Inlineassembler von Visual C/C++ mit x86-Prozessoren zu verwenden ist:  
  
-   [Übersicht über Inlineassembler](../../assembler/inline/inline-assembler-overview.md)  
  
-   [Vorteile der Inlineassembly](../../assembler/inline/advantages-of-inline-assembly.md)  
  
-   [__asm](../../assembler/inline/asm.md)  
  
-   [Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)  
  
-   [Verwenden von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)  
  
-   [Verwenden und Beibehalten von Registern in der Inlineassembly](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)  
  
-   [Springen zu Bezeichnungen in der Inlineassembly](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)  
  
-   [Aufrufen von C-Funktionen in der Inlineassembly](../../assembler/inline/calling-c-functions-in-inline-assembly.md)  
  
-   [Aufrufen von C++-Funktionen in der Inlineassembly](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)  
  
-   [Definieren von __asm-Blöcken als C-Makros](../../assembler/inline/defining-asm-blocks-as-c-macros.md)  
  
-   [Optimieren der Inlineassembly](../../assembler/inline/optimizing-inline-assembly.md)  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen und Assemblysprache](../../intrinsics/compiler-intrinsics-and-assembly-language.md)   
 [C++-Programmiersprachenreferenz](../../cpp/cpp-language-reference.md)