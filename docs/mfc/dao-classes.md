---
title: DAO-Klassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.data
dev_langs: C++
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1fc852bf2becb429c5931341cfd426bc7c877ae
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="dao-classes"></a>DAO-Klassen
Diese Klassen arbeiten Sie mit der anderen Anwendung Framework-Klassen einfachen Zugriff gewähren möchten (Datenzugriffsobjekt)-Datenbanken, die das gleiche Datenbankmodul als Microsoft Visual Basic und Microsoft Access zu verwenden. DAO-Klassen können auch eine Vielzahl von Datenbanken zugreifen, für die Open Database Connectivity (ODBC)-Treiber zur Verfügung stehen.  
  
 Programme, die DAO-Datenbanken zugreifen müssen mindestens eine `CDaoDatabase` Objekt und ein `CDaoRecordset` Objekt.  
  
> [!NOTE]
>  Die Visual C++-Umgebung und den Assistenten nicht mehr unterstützt (obwohl die DAO-Klassen enthalten sind, und Sie weiterhin verwenden können,). Microsoft empfiehlt die Verwendung von ODBC für neue MFC-Projekte. Sie sollten nur DAO verwenden, in die Verwaltung bereits vorhandener Anwendungen.  
  
 [CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)  
 Verwaltet eine benannte, kennwortgeschützte datenbanksitzung von der Anmeldung bis zu Abmeldung. Die meisten Programme verwenden Sie den Arbeitsbereich "Standard".  
  
 [CDaoDatabase](../mfc/reference/cdaodatabase-class.md)  
 Eine Verbindung mit einer Datenbank, die über der die Daten bearbeitet werden können.  
  
 [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)  
 Stellt eine Gruppe von Datensätzen dar, die aus einer Datenquelle ausgewählt wurden.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Eine Sicht, die Datenbankdatensätze in Steuerelementen anzeigt.  
  
 [CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)  
 Stellt eine Abfragedefinition, in der Regel eine in einer Datenbank gespeichert.  
  
 [CDaoTableDef](../mfc/reference/cdaotabledef-class.md)  
 Stellt die gespeicherte Definition einer Basistabelle oder einer angefügten Tabelle dar.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 Stellt eine Ausnahmebedingung, die von den DAO-Klassen dar.  
  
 [CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)  
 Unterstützt die Routinen für den DAO-Datensatzfeldaustausch (DAO record field exchange, DFX), die von den DAO-Datenbankklassen verwendet werden. Diese Klasse wird normalerweise nicht direkt verwendet.  
  
## <a name="related-classes"></a>Verwandte Klassen  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 Kapselt ein Handle für den Speicher für ein binary large Object (BLOB), z. B. eine Bitmap an. `CLongBinary`Objekte werden verwendet, um große Datenmengen-Objekte, die in Datenbanktabellen gespeichert zu verwalten.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 Wrapper für den Typ der OLE-Automatisierung **Währung**, Festkommanotation in jedem Fall arithmetischen Typs, mit 15 Stellen vor dem Dezimaltrennzeichen und 4 Ziffern nach dem.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 Wrapper für den Typ der OLE-Automatisierung **Datum**. Stellt die Datums-und Uhrzeitwerte dar.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 Wrapper für den Typ der OLE-Automatisierung **VARIANT**. Daten in **VARIANT**s kann in vielen verschiedenen Formaten gespeichert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)
