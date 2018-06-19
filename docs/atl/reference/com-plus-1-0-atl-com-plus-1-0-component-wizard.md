---
title: COM+ 1.0, ATL COM+ 1.0-Assistenten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.mts.options
dev_langs:
- C++
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a23f148fbdc611c8a11d8116b2e7dff34fc9d8f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358204"
---
# <a name="com-10-atl-com-10-component-wizard"></a>COM+ 1.0, ATL COM+ 1.0-Komponenten-Assistent
Verwenden Sie diese Seite des ATL COM+ 1.0 Komponenten-Assistenten an Schnittstellentyp und weitere Schnittstellen unterstützt werden müssen.  
  
 Weitere Informationen über ATL-Projekte und ATL-COM-Klassen finden Sie unter [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md).  
  
 **Interface**  
 Gibt den Typ der Schnittstelle, die das Objekt unterstützt. Das Objekt unterstützt standardmäßig eine duale Schnittstelle.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Dual**|Gibt an, dass das Objekt eine duale Schnittstelle unterstützt (die Vtable hat benutzerdefinierte Oberfläche Funktionen und spätes Binden `IDispatch` Methoden). Ermöglicht es COM-Clients sowohl Automatisierungscontroller Zugriff auf das Objekt.|  
|**Benutzerdefiniert**|Gibt an, dass das Objekt eine benutzerdefinierte Schnittstelle unterstützt (die Vtable enthält benutzerdefinierte Oberfläche Funktionen). Eine benutzerdefinierte Schnittstelle kann insbesondere über Prozessgrenzen hinweg schneller als eine duale Schnittstelle sein.<br /><br /> -   **Automatisierung kompatibel** die benutzerdefinierte Schnittstelle-Unterstützung hinzugefügt. Legt für die attributierte Projekte die **Oleautomation** -Attribut in der Co-Klasse.|  
  
 **Queueable**  
 Gibt an, dass Clients diese Komponente mithilfe von Nachrichtenwarteschlangen asynchron aufrufen können. Fügt die Komponente, die mit Attributen versehen Custom (TLBATTR_QUEUEABLE-Komponentenattributmakro, 0), der .h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte).  
  
 **Unterstützung**  
 Gibt zusätzliche Unterstützung für die Behandlung und Objekt-Steuerelement für Fehlermeldungen an.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**ISupportErrorInfo**|Unterstützung für die [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) Benutzeroberfläche, sodass das Objekt Fehlerinformationen an den Client zurückgegeben werden kann.|  
|**IObjectControl**|Ermöglicht dem Objektzugriff auf die drei [IObjectControl](http://msdn.microsoft.com/library/windows/desktop/ms686474) Methoden: [aktivieren](http://msdn.microsoft.com/library/windows/desktop/ms681303), [CanBePooled](http://msdn.microsoft.com/library/windows/desktop/ms684322), und [deaktivieren](http://msdn.microsoft.com/library/windows/desktop/ms687094).|  
|**IObjectConstruct**|Unterstützung für die [IObjectConstruct](http://msdn.microsoft.com/library/windows/desktop/ms680583) Schnittstelle, übergeben Parameter von anderen Methoden oder Objekten zu verwalten.|  
  
 **Transaktion**  
 Gibt an, dass das Objekt Transaktionen unterstützt. Die mtxattr.h Datei IDL-Datei (nicht attributierte Projekte).  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Unterstützt**|Gibt an, dass das Objekt nie den Stamm eines Streams Transaktion von der Komponente Attribut-Makro custom(TLBATTR_TRANS_SUPPORTED,0) .h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte) hinzufügen.|  
|**Erforderlich**|Gibt an, dass das Objekt möglicherweise nicht oder nicht den Stamm eines Streams Transaktion komplett durch Hinzufügen der Komponente Attribut-Makro custom(TLBATTR_TRANS_REQUIRED,0) .h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte).|  
|**Nicht unterstützt.**|Gibt an, dass das Objekt Transaktionen ausschließt. Fügt der Custom(TLBATTR_TRANS_NOTSUPP,0)-Komponentenattributmakro hinzu, um .h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte).|  
|**Erfordert neu**|Gibt an, dass das Objekt immer den Stamm eines Streams Transaktion von der Komponente Attribut-Makro custom(TLBATTR_TRANS_REQNEW,0) .h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte) hinzufügen.|  
  
## <a name="see-also"></a>Siehe auch  
 [ATL COM+ 1.0 Komponenten-Assistent](../../atl/reference/atl-com-plus-1-0-component-wizard.md)   
 [ATL COM+ 1.0-Komponente](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)

