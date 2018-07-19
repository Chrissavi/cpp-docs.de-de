---
title: Compilerfehler C2990 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2990
dev_langs:
- C++
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 669cfcd1e9a715b247c9264856e8877275d6407c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243028"
---
# <a name="compiler-error-c2990"></a>Compilerfehler C2990
'Klasse': nicht-Klassentyp wurde bereits als Typ einer Klasse deklariert  
  
 Die nicht generische oder Vorlagenklasse definiert eine generische oder Vorlagenklasse-Klasse. Überprüfen Sie die Headerdateien für Konflikte.  
  
 Im folgenden Beispiel wird C2990 generiert:  
  
```  
// C2990.cpp  
// compile with: /c  
template <class T>  
class C{};  
class C{};   // C2990  
```  
  
 C2990 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2990b.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC;  
  
ref struct GC {};   // C2990  
```  
  
 C2990 kann auch aufgrund eine wichtige Änderung in der Visual C++-Compiler für Visual C++ 2005 auftreten. der Compiler benötigt jetzt an, dass mehrere Deklarationen desselben Typs in Bezug auf die Vorlagenspezifikation identisch sein.  
  
 Im folgenden Beispiel wird C2990 generiert:  
  
```  
// C2990c.cpp  
// compile with: /c  
template<class T>  
class A;  
  
template<class T>  
struct A2 {  
   friend class A;   // C2990  
};  
  
// OK  
template<class T>  
struct B {  
   template<class T>  
   friend class A;  
};  
```