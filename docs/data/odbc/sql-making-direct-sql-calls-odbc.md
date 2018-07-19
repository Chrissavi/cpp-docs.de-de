---
title: 'SQL: Durchführen direkter SQL-Aufrufe (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- SQL, direct calls from ODBC
- SQL, calling directly from ODBC
- ODBC, SQL calls
- SQL calls
- direct SQL calls from ODBC
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2134fc41b604ffd659f9ee075abc9d462ff4f0db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093372"
---
# <a name="sql-making-direct-sql-calls-odbc"></a>SQL: Durchführen direkter SQL-Aufrufe (ODBC)
In diesem Thema wird Folgendes erläutert:  
  
-   Verwendung von direkter SQL aufruft.  
  
-   [Wie können Sie direkte SQL Aufrufe von der Datenquelle](#_core_making_direct_sql_function_calls).  
  
> [!NOTE]
>  Diese Informationen gelten für die MFC-ODBC-Klassen. Wenn Sie mit den MFC-DAO-Klassen arbeiten, finden Sie im Thema "Vergleich von Microsoft Jet-Datenbank-Engine-SQL und ANSI-SQL" DAO-Hilfe.  
  
##  <a name="_core_when_to_call_sql_directly"></a> Wenn SQL direkt aufrufen  
 Zum Erstellen neuer Tabellen, löschen (Delete) Tabellen, Ändern von vorhandenen Tabellen, Indizes zu erstellen und Ausführen von anderen SQL-Funktionen, die sich ändern die [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md) Schema, müssen Sie eine SQL-Anweisung ausgeben, direkt mit der Datenquelle, die mit der Datenbank Definition Language (DDL). Wenn Sie einen Assistenten verwenden, erstellen Sie ein Recordset für eine Tabelle (Entwurfszeit), können Sie die Spalten der Tabelle, die im Recordset darstellen auswählen. Dies lässt sich nicht für Spalten, die Sie oder ein anderer Benutzer der Datenquelle der Tabelle später hinzufügen, nachdem das Programm kompiliert wurde. Die Datenbankklassen unterstützen DDL nicht direkt, aber Sie können immer noch Code schreiben, um eine neue Spalte zur Laufzeit dynamisch an das Recordset zu binden. Weitere Informationen dazu, wie auf diese Bindung verwenden, finden Sie unter [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 Das DBMS selbst können Sie die alter Schema oder ein anderes Tool, mit der DDL-Funktionen ausgeführt werden können. Sie können auch die ODBC-Funktionsaufrufe verwenden, für das Senden von SQL-Anweisungen, wie das Aufrufen einer vordefinierten Abfrage (gespeicherten Prozedur), die keinen Datensätze zurückgibt.  
  
##  <a name="_core_making_direct_sql_function_calls"></a> Festlegen, dass direkter SQL-Funktionsaufrufe  
 Sie können direkt ausführen, einen SQL-Aufruf mithilfe einer [CDatabase-Klasse](../../mfc/reference/cdatabase-class.md) Objekt. Richten Sie Ihre SQL-Anweisungszeichenfolge (in der Regel in einer `CString`) und übergeben sie an der [CDatabase:: ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) Memberfunktion von Ihrer `CDatabase` Objekt. Wenn Sie ODBC-Funktionsaufrufe verwenden, um eine SQL-Anweisung zu senden, die normalerweise Datensätze zurückgibt, werden die Einträge ignoriert.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL](../../data/odbc/sql.md)