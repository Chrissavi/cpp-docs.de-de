---
title: Compilerwarnung (Stufe 1) C4461 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4461
dev_langs:
- C++
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2884daeb7497f6664cecf864ec705891cac62f48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278632"
---
# <a name="compiler-warning-level-1-c4461"></a>Compilerwarnung (Stufe 1) C4461
'Typ' : Diese Klasse hat einen Finalizer 'Finalizer', jedoch keinen Destruktor 'dtor'  
  
 Das Vorhandensein eines Finalizers in einem Typ impliziert, dass zu löschende Ressourcen vorhanden sind. Sofern ein Finalizer nicht explizit durch den Destruktor des Typs aufgerufen wird, ermittelt die Common Language Runtime den Zeitpunkt für die Ausführung des Finalizers, nachdem der Gültigkeitsbereich des Objekts verlassen wurde.  
  
 Wenn Sie einen Destruktor in einem Typ definieren und den Finalizer explizit im Destruktor aufrufen, können Sie auf diese Weise den Ausführungszeitpunkt des Finalizers eindeutig festlegen.  
  
 Weitere Informationen finden Sie unter [Destruktoren und Finalizer](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4461 generiert.  
  
```  
// C4461.cpp  
// compile with: /W1 /clr /c  
ref class A {  
protected:  
   !A() {}   // C4461  
};  
  
// OK  
ref struct B {  
   ~B() {  
      B::!B();  
   }  
  
   !B() {}  
};  
```