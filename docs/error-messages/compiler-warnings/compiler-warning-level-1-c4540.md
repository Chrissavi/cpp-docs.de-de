---
title: Compilerwarnung (Stufe 1) C4540 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4540
dev_langs:
- C++
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3939ad2bbcba1ab3b492d83bdbb8f7076c2c5f2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283061"
---
# <a name="compiler-warning-level-1-c4540"></a>Compilerwarnung (Stufe 1) C4540
Dynamic_cast zum Konvertieren in nicht zugegriffen werden kann oder mehrdeutige Basisklasse; Laufzeittest fehl ("Typ1" in "Typ2")  
  
 Sie verwendet `dynamic_cast` von einem Typ in einen anderen konvertieren. Der Compiler bestimmt, dass die Umwandlung immer fehlschlägt (zurückgeben **NULL**) ist eine Basisklasse kann nicht zugegriffen werden (`private`, z. B.) oder mehrdeutig (mehrmals in der Klassenhierarchie für die Instanz).  
  
 Das folgende Beispiel zeigt ein Beispiel für diese Warnung. Klasse **B** Klasse abgeleitet ist **ein**. Die Anwendung verwendet `dynamic_cast` von Klasse umgewandelt **B** (der abgeleiteten Klasse) Klasse **ein**, dem schlägt immer fehl, da Klasse **B** ist `private` und somit kann nicht zugegriffen werden. Ändern den Zugriff des **ein** auf **öffentlichen** die Warnung aufgelöst wird.  
  
```  
// C4540.cpp  
// compile with: /W1  
  
struct A {   
   virtual void g() {}  
};  
  
struct B : private A {  
   virtual void g() {}  
};  
  
int main() {  
   B b;  
   A * ap = dynamic_cast<A*>(&b);   // C4540  
}  
```