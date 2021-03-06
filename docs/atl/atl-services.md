---
title: ATL-Dienste
ms.date: 11/04/2016
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
ms.openlocfilehash: 052169154a62cbd07a82f08087fc2c2db8ae46c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62251914"
---
# <a name="atl-services"></a>ATL-Dienste

Um Ihr ATL-COM-Objekt zu erstellen, damit es in einem Dienst ausgeführt wird, wählen Sie einfach Service (EXE), aus der Liste von Optionen im ATL-Projekt-Assistenten. Der Assistent erstellt dann eine Klasse, die von abgeleiteten `CAtlServiceModuleT` Implementieren des Diensts.

Wenn das ATL-COM-Objekt als einen Dienst erstellt wird, wird nur als lokaler Server registriert werden, und er erscheint nicht in der Liste der Dienste in der Systemsteuerung. Dies ist, weil es einfacher, um den Dienst als lokaler Server als als Dienst Debuggen ist. Um es als Dienst installieren, führen Sie Folgendes an der Eingabeaufforderung ein:

`YourEXE` `.exe /Service`

Führen Sie zum Deinstallieren der Datei die folgenden Schritte aus:

`YourEXE` `.exe /UnregServer`

Die ersten vier Themen in diesem Abschnitt erläutern die Aktionen, die während der Ausführung auftreten `CAtlServiceModuleT` Memberfunktionen. Diese Themen werden in der gleichen Reihenfolge angezeigt, wie die Funktionen in der Regel aufgerufen werden. Um Ihre Kenntnisse dieser Themen zu verbessern, ist es ratsam, den Quellcode, die vom ATL-Projektassistenten als Referenz verwenden. Diese ersten vier Themen sind:

- [CAtlServiceModuleT:: Start-Funktion](../atl/reference/catlservicemodulet-class.md#start)

- [CAtlServiceModuleT:: ServiceMain-Funktion](../atl/reference/catlservicemodulet-class.md#servicemain)

- [CAtlServiceModuleT:: Start-Funktion](../atl/reference/catlservicemodulet-class.md#run)

- [CAtlServiceModuleT:: Handler-Funktion](../atl/reference/catlservicemodulet-class.md#handler)

In den letzten drei Themen erläutern Konzepte im Zusammenhang mit der Entwicklung eines Diensts:

- [Registrierungseinträge](../atl/registry-entries.md) für ATL-Dienste

- [DCOMCNFG](../atl/dcomcnfg.md)

- [Tipps zum Debuggen](../atl/debugging-tips.md) für ATL-Dienste

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)
