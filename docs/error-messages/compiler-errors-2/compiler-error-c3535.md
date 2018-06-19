---
title: Compilerfehler C3535 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3535
dev_langs:
- C++
helpviewer_keywords:
- C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff9935f4a46ba2c3a268ebb761153948ccd82f47
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33258772"
---
# <a name="compiler-error-c3535"></a>Compilerfehler C3535
Typ "Typ1" von "Typ2" kann nicht hergeleitet werden.  
  
 Der Typ der Variable deklariert, indem die `auto` Schlüsselwort kann nicht von dem Typ des Initialisierungsausdrucks abgeleitet werden. Dieser Fehler tritt z. B. auf, wenn der Initialisierungsausdruck ergibt `void`, d. h. es sich nicht um einen Typ.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass der Typ des Initialisierungsausdrucks nicht `void`.  
  
2.  Stellen Sie sicher, dass die Deklaration nicht über einen Zeiger auf ein grundlegender Typ ist. Weitere Informationen finden Sie unter [grundlegende Typen](../../cpp/fundamental-types-cpp.md).  
  
3.  Stellen Sie sicher, dass die Deklaration ein Zeiger auf einen Typ, der Initialisierungsausdruck ein Zeigertyp ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3535 erzeugt, da der Initialisierungsausdruck ergibt `void`.  
  
```  
// C3535a.cpp  
// Compile with /Zc:auto  
void f(){}  
int main()  
{  
   auto x = f();   //C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3535 erzeugt, da die Anweisung Variablen deklariert `x` als Zeiger auf einen abgeleiteten Typ, aber der Typ des Initialisierers ist double. Folglich nicht der Compiler den Typ der Variablen nicht ableiten.  
  
```  
// C3535b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto* x = 123.0;   // C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3535 erzeugt, da Variable `p` einen Zeiger auf einen abgeleiteten Typ deklariert, aber der Initialisierungsausdruck ist kein Zeigertyp.  
  
```  
// C3535c.cpp  
// Compile with /Zc:auto  
class A { };  
A x;  
auto *p = x;  // C3535  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auto-Schlüsselwort](../../cpp/auto-keyword.md)   
 [Grundlegende Typen](../../cpp/fundamental-types-cpp.md)