---
title: Compilerwarnung (Stufe 1) C4395 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4395
dev_langs:
- C++
helpviewer_keywords:
- C4395
ms.assetid: 8051469a-3a39-4677-80f7-1300fbffe8ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95b52322b7114a16fcd0f447ba6fd628751c250e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277854"
---
# <a name="compiler-warning-level-1-c4395"></a>Compilerwarnung (Stufe 1) C4395
'Funktion': Memberfunktion wird auf eine Kopie des Datenmembers Initonly 'Member' aufgerufen werden  
  
 Eine Memberfunktion aufgerufen wurde, auf ein [Initonly (C + c++ / CLI)](../../dotnet/initonly-cpp-cli.md) -Datenmember.  C4395 weist darauf hin, die die **Initonly** Datenmember nicht von der Funktion geändert werden.  
  
 Im folgenden Beispiel wird C4395 generiert:  
  
```  
// C4395.cpp  
// compile with: /W1 /clr  
public value class V {  
public:  
   V(int data) : m_data(data) {}  
  
   void Mutate() {  
      System::Console::WriteLine("Enter Mutate: m_data = {0}", m_data);  
      m_data *= 2;  
      System::Console::WriteLine("Leave Mutate: m_data = {0}", m_data);  
   }  
  
   int m_data;  
};  
  
public ref class R {  
public:  
   static void f() {  
      System::Console::WriteLine("v.m_data = {0}", v.m_data);  
      v.Mutate();   // C4395  
      System::Console::WriteLine("v.m_data = {0}", v.m_data);  
   }  
  
private:  
   initonly static V v = V(4);  
};  
  
int main() {  
   R::f();  
}  
```