---
title: Ereignisbehandlung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], event handling
- intrinsic functions [C++], event handling
- event handling [C++], Visual C++
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09029f3afef0a9a28fdc572b9b7d8685cf76e811
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32414619"
---
# <a name="event-handling"></a>Ereignisbehandlung
Ereignisbehandlung wird hauptsächlich für COM-Klassen unterstützt (C++-Klassen, COM-Objekten, die in der Regel mit ATL-Klassen implementieren, oder die [Coclass](../windows/coclass.md) Attribut).  Weitere Informationen finden Sie unter [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md).  
  
 Ereignisbehandlung wird auch für native C++-Klassen (C++-Klassen, die keine COM-Objekte implementieren) unterstützt. Die Unterstützung ist jedoch veraltet und wird in einem der nächsten Releases entfernt werden.  Weitere Informationen finden Sie unter [Ereignisbehandlung in systemeigenem C++](../cpp/event-handling-in-native-cpp.md).  
  
 Die Ereignisbehandlung unterstützt Einzel- und Multithreadverwendung und schützt Daten vor gleichzeitigem Multithreadzugriff. Sie ermöglicht Ihnen auch das Ableiten von Unterklassen aus Ereignisquellklassen oder Ereignisempfängerklassen und unterstützt die erweiterte Ereignisquellentnahme bzw. den Ereignisempfang in der abgeleiteten Klasse.  
  
 Visual C++ enthält Attribute und Schlüsselwörter zum Deklarieren von Ereignissen und Ereignishandlern. Die Ereignisattribute und Schlüsselwörter können in CLR-Programmen und in systemeigenen C++-Programmen verwendet werden.  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[event_source](../windows/event-source.md)|Erstellt eine Ereignisquelle.|  
|[event_receiver](../windows/event-receiver.md)|Erstellt einen Ereignisempfänger (Senke).|  
|[__event](../cpp/event.md)|Deklariert ein Ereignis.|  
|[__raise](../cpp/raise.md)|Hebt die Aufrufsite eines Ereignisses hervor.|  
|[__hook](../cpp/hook.md)|Ordnet eine Handlermethode einem Ereignis zu.|  
|[__unhook](../cpp/unhook.md)|Trennt eine Handlermethode von einem Ereignis.|  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Beispiele für die Ereignisbehandlung](http://msdn.microsoft.com/en-us/cc0287d4-f92b-4da5-85fc-a0f186e16424)