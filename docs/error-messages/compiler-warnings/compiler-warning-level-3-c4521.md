---
title: Compilerwarnung (Stufe 3) C4521 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4521
dev_langs:
- C++
helpviewer_keywords:
- C4521
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a81fe751521e5f2f43d3c96fb15098bac914c614
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298004"
---
# <a name="compiler-warning-level-3-c4521"></a>Compilerwarnung (Stufe 3) C4521
'Klasse': Mehrere Kopierkonstruktoren angegeben  
  
 Die Klasse verfügt über mehrere Kopierkonstruktoren eines einzelnen Typs. Diese Warnung dient nur zu Informationszwecken; die Konstruktoren sind im Programm aufgerufen werden kann.  
  
 Verwenden der [Warnung](../../preprocessor/warning.md) Pragma verwenden, um diese Warnung zu unterdrücken.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4521 generiert.  
  
```  
// C4521.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
  
using namespace std;  
class A {  
public:  
   A() { cout << "A's default constructor" << endl; }  
   A( A &o ) { cout << "A&" << endl; }  
   A( const A &co ) { cout << "const A&" << endl; }   // C4521  
};  
  
int main() {  
   A o1;         // Calls default constructor.  
   A o2( o1 );   // Calls A( A& ).  
   const A o3;   // Calls default constructor.  
   A o4( o3 );   // Calls A( const A& ).  
}  
```