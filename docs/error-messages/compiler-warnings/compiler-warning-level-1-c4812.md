---
title: Compilerwarnung (Stufe 1) C4812 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4812
dev_langs:
- C++
helpviewer_keywords:
- C4812
ms.assetid: a7f5721f-2019-44de-ad62-ed30bac8b1f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05ff26f9adf9548553cd76033bba3aa9cefe9417
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282794"
---
# <a name="compiler-warning-level-1-c4812"></a>Compilerwarnung (Stufe 1) C4812
Veralteter Deklarationsstil: Verwenden Sie stattdessen „new_syntax“.  
  
 In der aktuellen Version von Visual C++ wird die explizite Konstruktorspezialisierung noch unterstützt, in einer zukünftigen Version aber möglicherweise nicht mehr.  
  
 Im folgenden Beispiel wird C4812 generiert.  
  
```  
// C4812.cpp  
// compile with: /W1 /c  
template <class T>   
class MyClass;  
  
template<class T>  
class MyClass<T*> {  
   MyClass();  
};  
  
template<class T>  
MyClass<T*>::MyClass<T*>() {}   // C4812  
// try the following line instead  
// MyClass<T*>::MyClass() {}  
```