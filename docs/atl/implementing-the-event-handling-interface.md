---
title: Implementieren der Schnittstelle für die Ereignisbehandlung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea37aa4c84cb0824d11f0081e38d9e8157b77ed1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356307"
---
# <a name="implementing-the-event-handling-interface"></a>Implementieren der Schnittstelle für die Ereignisbehandlung
ATL unterstützt Sie bei allen drei Elementen, die für die Behandlung von Ereignissen erforderlich: Ereignisschnittstelle implementieren, Ereignisquelle anmelden und Abmelden der Ereignisquelle. Die genauen Schritte, die Sie ergreifen müssen, hängen von der Typ der Ereignisschnittstelle und den leistungsanforderungen der Anwendung ab.  
  
 Die am häufigsten verwendeten Methoden zum Implementieren einer Schnittstelle mit ATL sind:  
  
-   Direkt Ableiten von einer benutzerdefinierten Schnittstelle.  
  
-   Ableiten von [IDispatchImpl](../atl/reference/idispatchimpl-class.md) für duale Schnittstellen, die in einer Typbibliothek beschrieben.  
  
-   Ableiten von [IDispEventImpl](../atl/reference/idispeventimpl-class.md) für Disp-Schnittstellen in einer Typbibliothek beschrieben.  
  
-   Ableiten von [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) für Disp-Schnittstellen nicht beschrieben werden, in einer Typbibliothek oder wenn Sie die Effizienz verbessern, indem Sie die Typinformationen zur Laufzeit nicht laden möchten.  
  

 Wenn Sie eine benutzerdefinierte oder duale Schnittstelle implementieren, sollten Sie die Ereignisquelle informieren, durch den Aufruf [AtlAdvise](reference/connection-point-global-functions.md#atladvise) oder [CComPtrBase:: Advise](../atl/reference/ccomptrbase-class.md#advise). Sie müssen zum Nachverfolgen des Cookies, die vom Aufruf zurückgegebene selbst. Rufen Sie [AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise) die Verbindung unterbrochen.  

  
 Wenn Sie eine Dispinterface mit implementieren `IDispEventImpl` oder `IDispEventSimpleImpl`, informiert Sie der Ereignisquelle durch Aufrufen von [IDispEventSimpleImpl:: DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise). Rufen Sie [IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise) die Verbindung unterbrochen.  
  
 Bei Verwendung von `IDispEventImpl` als Basisklasse für ein zusammengesetztes Steuerelement, die Ereignisquellen aus, in der Zuordnung der Senke aufgelistet werden empfohlen und automatisch mit unadvised [:: AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).  
  
 Die `IDispEventImpl` und `IDispEventSimpleImpl` Klassen verwalten das Cookie für Sie.  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisbehandlung](../atl/event-handling-and-atl.md)

