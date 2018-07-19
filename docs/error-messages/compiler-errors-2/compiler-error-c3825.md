---
title: Compilerfehler C3825 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3825
dev_langs:
- C++
helpviewer_keywords:
- C3825
ms.assetid: 18e204a1-f26e-42c6-8d74-2b49cc95f940
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e590596220fe0880a0b69bc15e4ebb4e879af80b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272606"
---
# <a name="compiler-error-c3825"></a>Compilerfehler C3825
'Klasse': eine verwaltete oder WinRTclass können nur verwaltete Unterstützung oder WinRTevents  
  
 In verwalteten Klassen werden nur .NET-Ereignisse unterstützt. Nur Windows-Runtime-Ereignisse werden in Windows-Runtime-Klassen unterstützt. Ändern Sie zum Beheben dieses Fehlers in verwaltetem Code den Typparameter von `event_source` und `event_receiver` von `native` zu `managed`. Entfernen Sie alternativ das Attribut.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3825 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3825a.cpp  
// compile with: /clr  
public delegate void del1();  
  
[event_source(native)]           // To fix, change 'native' to 'managed' or delete this line  
ref class CEventSrc  
{  
public:  
   event del1^ event1;       // C3825  
  
   void FireEvents() {  
      event1();  
   }  
};  
  
[event_receiver(native)]         // To fix, change 'native' to 'managed' or delete this line  
ref class CEventRec  
{  
public:  
   void handler1()  
   {  
      System::Console::WriteLine("Executing handler1().\n");  
   }  
   void HookEvents(CEventSrc^ pSrc)   
   {  
      pSrc->event1 += gcnew del1(this, &CEventRec::handler1);  
   }  
   void UnhookEvents(CEventSrc^ pSrc)   
   {  
      pSrc->event1 -= gcnew del1(this, &CEventRec::handler1);  
   }  
};  
  
int main()   
{  
   CEventSrc^ pEventSrc = gcnew CEventSrc;  
   CEventRec^ pEventRec = gcnew CEventRec;  
   pEventRec->HookEvents(pEventSrc);  
   pEventSrc->FireEvents();  
   pEventRec->UnhookEvents(pEventSrc);  
}  
```