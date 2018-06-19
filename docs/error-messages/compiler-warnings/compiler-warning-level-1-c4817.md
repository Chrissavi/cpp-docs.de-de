---
title: Compilerwarnung (Stufe 1) C4817 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4817
dev_langs:
- C++
helpviewer_keywords:
- C4817
ms.assetid: a68f5486-6940-4934-9f93-bfd4d71f92a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa1dfa3cf0e63e319198cd9394f194864f87eacf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286187"
---
# <a name="compiler-warning-level-1-c4817"></a>Compilerwarnung (Stufe 1) C4817
„member“: Unzulässige Verwendung des Punkts (.) zum Zugreifen auf diesen Member. Compiler wurde durch „->“ ersetzt.  
  
 Es wurde der falsche Memberzugriffsoperator verwendet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4817 generiert.  
  
```  
// C4817.cpp  
// compile with: /clr /W1  
using namespace System;  
int main() {  
   array<Int32> ^ a = gcnew array<Int32>(100);  
   Console::WriteLine( a.Length );   // C4817  
   Console::WriteLine( a->Length );   // OK  
}  
```  
