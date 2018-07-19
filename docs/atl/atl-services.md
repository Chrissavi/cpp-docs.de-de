---
title: ATL-Dienste | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule
dev_langs:
- C++
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db13b443e605168389f0a9bc767ba29a75d4234d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354791"
---
# <a name="atl-services"></a>ATL-Dienste
Um das ATL-COM-Objekt zu erstellen, damit es in einem Dienst ausgeführt wird, wählen Sie einfach Service (EXE) aus der Liste der Serveroptionen im ATL-Projekt-Assistenten. Der Assistent erstellt dann eine Klasse abgeleitet `CAtlServiceModuleT` Implementieren des Diensts.  
  
 Wenn Sie ATL-COM-Objekts als ein Dienst erstellt wird, wird nur als lokaler Server registriert werden und erscheint nicht in der Liste der Dienste in der Systemsteuerung. Dies ist, da es einfacher, den Dienst als lokaler Server als als Dienst Debuggen ist. Um es als Dienst zu installieren, führen Sie Folgendes an der Eingabeaufforderung ein:  
  
 `YourEXE` `.exe /Service`  
  
 Führen Sie den folgenden Aktionen aus, um es zu deinstallieren:  
  
 `YourEXE` `.exe /UnregServer`  
  
 Die ersten vier Themen in diesem Abschnitt erläutern die Aktionen, die während der Ausführung auftreten `CAtlServiceModuleT` Memberfunktionen. Diese Themen werden in derselben Reihenfolge angezeigt, während die Funktionen in der Regel aufgerufen werden. Um Ihr Verständnis dieser Themen zu verbessern, ist es ratsam, den Quellcode, generiert der ATL-Projekt-Assistent als Referenz verwenden. Diese ersten vier Themen sind:  
  

-   [Die CServiceModule:: Start-Funktion](../atl/reference/catlservicemodulet-class.md#start)  
  
-   [Die CAtlServiceModuleT::ServiceMain-Funktion](../atl/reference/catlservicemodulet-class.md#servicemain)  
  
-   [Die CServiceModule:: Run-Funktion](../atl/reference/catlservicemodulet-class.md#run)  
  
-   [Die CAtlServiceModuleT::Handler-Funktion](../atl/reference/catlservicemodulet-class.md#handler)  
  
 Die letzten drei Themen erläutert Konzepte im Zusammenhang mit der Entwicklung von einem Dienst an:  
  
-   [Registrierungseinträge](../atl/registry-entries.md) für ATL-Dienste  
  
-   [DCOMCNFG](../atl/dcomcnfg.md)  
  
-   [Tipps zum Debuggen](../atl/debugging-tips.md) für ATL-Dienste  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)

