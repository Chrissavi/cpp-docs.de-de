---
title: Compilerfehler C3530 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3530
dev_langs:
- C++
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6514d655ab813ae21ecb440415f87bce63f3591
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253517"
---
# <a name="compiler-error-c3530"></a>Compilerfehler C3530
'Auto' kann nicht mit einem anderen Typspezifizierer kombiniert werden  
  
 Ein Typspezifizierer wird verwendet, mit dem `auto` Schlüsselwort.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Verwenden Sie keinen Typspezifizierer in einer Variablendeklaration, die mithilfe der `auto` Schlüsselwort.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel wird C3530 erzeugt, da Variable `x` wird deklariert, mit der `auto` -Schlüsselwort und Datentyp `int`, und da im Beispiel mit kompiliert wird **/Zc: Auto**.  
  
```  
// C3530.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto int x;   // C3530  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auto-Schlüsselwort](../../cpp/auto-keyword.md)