---
title: Compiler-Fehler C2683 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2683
dev_langs:
- C++
helpviewer_keywords:
- C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35619d93200c2f0e61dbf903f56a70bbe0c48d73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233645"
---
# <a name="compiler-error-c2683"></a>Compiler-Fehler C2683 generiert
'cast': 'Typ' ist kein polymorphen Typ  
  
 Sie können keine [Dynamic_cast](../../cpp/dynamic-cast-operator.md) zum Konvertieren von einer nicht polymorphen Klasse (eine Klasse keine virtuellen Funktionen).  
  
 Sie können [Static_cast](../../cpp/static-cast-operator.md) zum Durchführen von Konvertierungen von nicht polymorphen Typen. Allerdings `static_cast` führt eine Überprüfung zur Laufzeit keine.  
  
 Im folgende Beispiel wird C2683 generiert:  
  
```  
// C2683.cpp  
// compile with: /c  
class B { };  
class D : public B { };  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  // C2683  
   D* pd1 = static_cast<D*>(pb);   // OK  
}  
```