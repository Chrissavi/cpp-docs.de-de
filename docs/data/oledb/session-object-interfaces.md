---
title: Sitzungsobjekt-Schnittstellen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f591e62874bd6924dd60077b921bbfc67600af1c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112926"
---
# <a name="session-object-interfaces"></a>Sitzungsobjekt-Schnittstellen
Die folgende Tabelle zeigt die obligatorischen und optionalen Schnittstellen, die durch OLE DB für ein Sitzungsobjekt definiert.  
  
|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|  
|---------------|---------------|--------------------------------------|  
|[IGetDataSource](https://msdn.microsoft.com/en-us/library/ms709721.aspx)|Erforderlich|Ja|  
|[IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx)|Erforderlich|Ja|  
|[ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx)|Erforderlich|Ja|  
|[IAlterIndex](https://msdn.microsoft.com/en-us/library/ms714943.aspx)|Optional|Nein|  
|[IAlterTable](https://msdn.microsoft.com/en-us/library/ms719764.aspx)|Optional|Nein|  
|[IBindResource](https://msdn.microsoft.com/en-us/library/ms714936.aspx)|Optional|Nein|  
|[ICreateRow](https://msdn.microsoft.com/en-us/library/ms716832.aspx)|Optional|Nein|  
|[IDBCreateCommand](https://msdn.microsoft.com/en-us/library/ms711625.aspx)|Optional|Ja|  
|[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)|Optional|Ja|  
|[IIndexDefinition](https://msdn.microsoft.com/en-us/library/ms711593.aspx)|Optional|Nein|  
|[ISupportErrorInfo](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|Optional|Ja|  
|[ITableCreation](https://msdn.microsoft.com/en-us/library/ms713639.aspx)|Optional|Nein|  
|[ITableDefinition](https://msdn.microsoft.com/en-us/library/ms714277.aspx)|Optional|Nein|  
|[ITableDefinitionWithConstraints](https://msdn.microsoft.com/en-us/library/ms720947.aspx)|Optional|Nein|  
|[ITransaction](https://msdn.microsoft.com/en-us/library/ms723053.aspx)|Optional|Nein|  
|[ITransactionJoin](https://msdn.microsoft.com/en-us/library/ms718071.aspx)|Optional|Nein|  
|[ITransactionLocal](https://msdn.microsoft.com/en-us/library/ms714893.aspx)|Optional|Nein|  
|[ITransactionObject](https://msdn.microsoft.com/en-us/library/ms713659.aspx)|Optional|Nein|  
  
 Das Sitzungsobjekt erstellt ein Rowsetobjekt. Die Sitzung erstellt, wenn der Anbieter Befehle unterstützt, auch ein Command-Objekt (`CCommand`, implementieren den OLE DB- **TCommand**). Das Command-Objekt implementiert die `ICommand` Schnittstelle und verwendet die `ICommand::Execute` -Methode zum Ausführen von Befehlen für das Rowset, wie in der folgenden Abbildung dargestellt.  
  
 ![Konzeptionelles Diagramm zu Anbietern](../../data/oledb/media/vc4u551.gif "vc4u551")  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)