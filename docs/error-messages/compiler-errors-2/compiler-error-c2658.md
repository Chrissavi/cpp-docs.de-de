---
title: Compiler-Fehler C2658 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2658
dev_langs:
- C++
helpviewer_keywords:
- C2658
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8e071e070b259dee7293d607d292a51ee608b71c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234736"
---
# <a name="compiler-error-c2658"></a>Compiler-Fehler C2658 generiert
'Member': Neudefinition in einer anonymen Struktur/Union  
  
 Zwei anonyme Strukturen oder Unions enthalten Memberdeklarationen mit dem gleichen Bezeichner jedoch mit unterschiedlichen Typen auf. Klicken Sie unter ["/ Za"](../../build/reference/za-ze-disable-language-extensions.md), Sie erhalten diesen Fehler auch für Member mit dem gleichen Bezeichner und Typ.  
  
 Im folgende Beispiel wird C2658 generiert:  
  
```  
// C2658.cpp  
// compile with: /c  
struct X {  
   union { // can be struct too  
      int i;  
   };  
   union {  
      int i;   // Under /Za, C2658  
      // int i not needed here because it is defined in the first union  
   };  
};  
  
struct Z {  
   union {  
      char *i;  
   };  
  
   union {  
      void *i;   // C2658 redefinition of 'i'  
      // try the following line instead  
      // void *ii;  
   };  
};  
```