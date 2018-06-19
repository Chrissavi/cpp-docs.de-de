---
title: Linkertoolwarnung Lnk4248 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4248
dev_langs:
- C++
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3b67661d1ad260f388f8425420711ae2f708ce3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302632"
---
# <a name="linker-tools-warning-lnk4248"></a>Linkertoolwarnung LNK4248
nicht aufgelöste Typeref-Token (Token) für 'Typ'; Abbild kann möglicherweise nicht ausgeführt.  
  
 Ein Typ aufweisen keine Definition in MSIL-Metadaten.  
  
 LNK4248 kann auftreten, wenn es nur eine Vorwärtsdeklaration für einen Typ in einem MSIL-Modul ist (kompiliert mit **"/ CLR"**), auf den Typ im MSIL-Modul verwiesen wird, und die MSIL-Modul mit einem systemeigenen Modul verknüpft ist, die eine Definition für verfügt Der Typ.  
  
 In diesem Fall kann der Linker wird die Definition der systemeigene Typ in den MSIL-Metadaten bereitstellen, und dies kann eine für das richtige Verhalten.  
  
 Jedoch, wenn eine Vorwärts-Typdeklaration ein CLR-Typ ist, systemeigene Typdefinition für den Linker nicht richtig möglicherweise  
  
 Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Geben Sie die Typdefinition in der MSIL-Modul.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird LNK4248 generiert. Definieren Sie die Struktur ein aufgelöst.  
  
```  
// LNK4248.cpp  
// compile with: /clr /W1  
// LNK4248 expected  
struct A;  
void Test(A*){}  
  
int main() {  
   Test(0);  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wurde eine Rollforward Definition eines Typs.  
  
```  
// LNK4248_2.cpp  
// compile with: /clr /c  
class A;   // provide a definition for A here to resolve  
A * newA();  
int valueA(A * a);  
  
int main() {  
   A * a = newA();  
   return valueA(a);  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird LNK4248 generiert.  
  
```  
// LNK4248_3.cpp  
// compile with: /c  
// post-build command: link LNK4248_2.obj LNK4248_3.obj  
class A {  
public:   
   int b;  
};  
  
A* newA() {  
   return new A;  
}  
  
int valueA(A * a) {  
   return (int)a;  
}  
```