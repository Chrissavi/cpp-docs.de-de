---
title: Compilerfehler C3713 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3713
dev_langs:
- C++
helpviewer_keywords:
- C3713
ms.assetid: 75c6b9b6-955b-49bd-9bc8-ced88b496a1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2f0e919add44075516deedfb339c8e1d7487f6ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33263871"
---
# <a name="compiler-error-c3713"></a>Compilerfehler C3713
'Methode': eine Ereignishandlermethode muss die Parameter für die gleichen wie die Quelle 'Methode' haben  
  
 Sie definiert eine Ereignishandlermethode, die nicht die gleichen Parameter wie die Quelle Ereignis-Methode verwendet haben. Um diesen Fehler zu beheben, geben Sie der Ereignishandlermethode die gleichen Parameter wie die von der Quelle Ereignis-Methode.  
  
 Im folgende Beispiel wird C3713 generiert:  
  
```  
// C3713.cpp  
// compile with: /c  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void event1(int nValue);  
   // try the following line instead  
   // __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3713  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3713  
   }  
};  
```