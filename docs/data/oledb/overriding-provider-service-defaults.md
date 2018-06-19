---
title: Überschreiben Anbieterdienste | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: be802c1c3c6ba4b77d1418c9c620840e9ab10170
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110079"
---
# <a name="overriding-provider-service-defaults"></a>Überschreiben der Standardwerte für Anbieterdienste
Der Anbieter-Registrierungswert für **OLEDB_SERVICES** wird zurückgegeben, als der Standardwert für die [DBPROP_INIT_OLEDBSERVICES](https://msdn.microsoft.com/en-us/library/ms716898.aspx) Initialisierungseigenschaft auf das Datenquellenobjekt.  
  
 Solange der Registrierungseintrag vorhanden ist, die Anbieterobjekte aggregiert, und der Benutzer kann der Anbieter Standardeinstellung für die aktivierten Dienste durch Festlegen von überschreiben die **DBPROP_INIT_OLEDBSERVICES** Eigenschaft vor der Initialisierung. Zum Aktivieren oder deaktivieren einen bestimmten Dienst, der Benutzer im Allgemeinen erhält den aktuellen Wert der die **DBPROP_INIT_OLEDBSERVICES** -Eigenschaft, legt sie fest oder löscht das Bit für die betreffende Eigenschaft aktiviert bzw. deaktiviert werden soll, und setzt die Eigenschaft zurück. **DBPROP_INIT_OLEDBSERVICES** kann festgelegt werden, direkt in OLE DB oder in der Verbindungszeichenfolge übergeben, ADO oder **IDataInitialize:: GetDatasource**. Die entsprechenden Werte zum Aktivieren/Deaktivieren Sie einzelne Dienste werden in der folgenden Tabelle aufgeführt.  
  
|Standarddienste aktiviert|DBPROP_INIT_OLEDBSERVICES-Eigenschaftswert|Wert in der Verbindungszeichenfolge|  
|------------------------------|------------------------------------------------|--------------------------------|  
|Alle Dienste (Standard)|**DBPROPVAL_OS_ENABLEALL**|"OLE DB-Dienste =-1;"|  
|Alle außer Pooling und AutoEnlistment|**DBPROPVAL_OS_ENABLEALL &AMP;**<br /><br /> **~DBPROPVAL_OS_RESOURCEPOOLING &**<br /><br /> **~DBPROPVAL_OS_TXNENLISTMENT**|"OLE DB-Dienste =-4;"|  
|Alle außer den Clientcursor|**DBPROPVAL_OS_ENABLEALL** &<br /><br /> ~**DBPROPVAL_OS_CLIENTCURSOR**|"OLE DB-Dienste =-5;"|  
|Alle Dienste außer Pooling, AutoEnlistment und Clientcursor|**DBPROPVAL_OS_ENABLEALL &AMP;**<br /><br /> **~DBPROPVAL_OS_TXNENLISTMENT &**<br /><br /> **~ DBPROPVAL_OS_CLIENTCURSOR**|"OLE DB-Dienste =-7;"|  
|Keine Dienste|~**DBPROPVAL_OS_ENABLEALL**|"OLE DB-Dienste = 0;"|  
  
 Wenn der Registrierungseintrag für den Anbieter nicht vorhanden ist, die Komponenten-Manager wird der Anbieter-Objekte nicht aggregiert und keine Dienste aufgerufen, auch wenn dies explizit vom Benutzer angefordert.  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcenpooling](https://msdn.microsoft.com/en-us/library/ms713655.aspx)   
 [Verwendung von Consumern Ressourcenpooling](https://msdn.microsoft.com/en-us/library/ms715907.aspx)   
 [Funktionsweise von Anbietern effektiv mit Ressourcenpooling](https://msdn.microsoft.com/en-us/library/ms714906.aspx)   
 [Aktivieren und Deaktivieren von OLE DB-Diensten](../../data/oledb/enabling-and-disabling-ole-db-services.md)