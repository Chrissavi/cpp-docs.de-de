---
title: Aufrufen von C-Funktionen in der Inlineassembly | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- function calls, C functions
- function calls, in inline assembly
- functions [C], calling in inline assembly
- Visual C, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3f6d03ba77c7a4cdb3478a1bfe8729019dea002
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32049517"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Aufrufen von C-Funktionen in der Inlineassembly
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Ein `__asm` Block C-Funktionen, einschließlich der C-Bibliotheksroutinen aufrufen kann. Im folgenden Beispiel wird die `printf` Bibliotheksroutine:  
  
```  
// InlineAssembler_Calling_C_Functions_in_Inline_Assembly.cpp  
// processor: x86  
#include <stdio.h>  
  
char format[] = "%s %s\n";  
char hello[] = "Hello";  
char world[] = "world";  
int main( void )  
{  
   __asm  
   {  
      mov  eax, offset world  
      push eax  
      mov  eax, offset hello  
      push eax  
      mov  eax, offset format  
      push eax  
      call printf  
      //clean up the stack so that main can exit cleanly  
      //use the unused register ebx to do the cleanup  
      pop  ebx  
      pop  ebx  
      pop  ebx  
   }  
}  
```  
  
 Da Funktionsargumente auf dem Stapel übergeben sind, drücken Sie einfach die erforderlichen Argumente – Zeigern, die im vorherigen Beispiel Zeichenfolge: vor dem Aufrufen der Funktion. Die Argumente werden in umgekehrter Reihenfolge abgelegt, damit sie vom Stapel in der gewünschten Reihenfolge eintreffen. Zum Emulieren der C-Anweisung  
  
```  
printf( format, hello, world );  
```  
  
 Im Beispiel wird der Zeiger auf `world`, `hello`, und `format`in dieser Reihenfolge und Aufrufe `printf`.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)