---
title: Transaktionsobjekt-Schnittstellen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- interfaces, OLE DB
- transaction object interfaces
- OLE DB, interfaces
- OLE DB providers, transaction support
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 415fdec8397b72bf8f391865fb5af418f95fdf03
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104551"
---
# <a name="transaction-object-interfaces"></a>Transaktionsobjekt-Schnittstellen
Das Transaktionsobjekt, das eine unteilbare Arbeitseinheit für eine Datenquelle definiert und bestimmt, wie diese Arbeitseinheiten miteinander in Beziehung stehen. Dieses Objekt wird von der OLE DB-Anbietervorlagen nicht direkt unterstützt (d. h. Sie müssen ein eigenes Objekt erstellen).  
  
 Die folgende Tabelle zeigt die obligatorischen und optionalen Schnittstellen, die durch OLE DB für ein Transaktionsobjekt definiert.  
  
|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|  
|---------------|---------------|--------------------------------------|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Erforderlich|Nein|  
|[ITransaction](https://msdn.microsoft.com/en-us/library/ms723053.aspx)|Erforderlich|Nein|  
|[ISupportErrorInfo](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|Optional|Nein|  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)