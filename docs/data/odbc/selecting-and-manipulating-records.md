---
title: Auswählen und Verändern von Datensätzen
ms.date: 05/09/2019
helpviewer_keywords:
- records, selecting
- record selection, MFC ODBC classes
- ODBC recordsets, selecting records
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
ms.openlocfilehash: 745c0c35e42426242d92d720d5dcd3de631fb17b
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707809"
---
# <a name="selecting-and-manipulating-records"></a>Auswählen und Verändern von Datensätzen

> [!NOTE] 
> Der MFC-ODBC-Consumer-Assistent ist in Visual Studio 2019 und höher nicht verfügbar. Sie können einen Consumer weiterhin manuell erstellen.

Wenn Sie Datensätze in einer Datenquelle mit einer **SELECT**-SQL-Anweisung auswählen, erhalten Sie normalerweise ein Resultset, das eine Menge von Datensätzen aus einer Tabelle oder Abfrage ist. Mit den Datenbankklassen verwenden Sie ein Recordset-Objekt, um das Resultset auszuwählen und auf es zuzugreifen. Dies ist ein Objekt einer anwendungsspezifischen-Klasse, die Sie aus der Klasse [CRecordset](../../mfc/reference/crecordset-class.md) ableiten. Wenn Sie eine Recordset-Klasse definieren, geben Sie die Datenquelle, die ihr zugeordnet werden soll, die zu verwendende Tabelle und die Spalten der Tabelle an. Der MFC-Anwendungs-Assistent oder **Klasse hinzufügen** (wie unter [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md) beschrieben) erstellt eine Klasse mit einer Verbindung mit einer bestimmten Datenquelle. Die Assistenten schreiben die [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql)-Memberfunktion der Klasse `CRecordset`, um den Tabellennamen zurückzugegeben.

Durch Verwenden eines [CRecordset](../../mfc/reference/crecordset-class.md)-Objekts zur Laufzeit haben Sie folgende Möglichkeiten:

- Überprüfen der Datenfelder des aktuellen Datensatzes

- Filtern oder Sortieren des Recordsets

- Anpassen der standardmäßigen **SELECT**-SQL-Anweisung

- Durchlaufen der ausgewählten Datensätze

- Hinzufügen, Aktualisieren oder Löschen von Datensätzen (wenn sowohl die Datenquelle als auch das Recordset aktualisierbar sind)

- Testen, ob das Recordset erneutes Abfragen und Aktualisieren des Inhalts des Recordsets zulässt

Wenn Sie das Recordset-Objekt nicht mehr benötigen, schließen und zerstören Sie es. Weitere Informationen zu Recordsets finden Sie unter [Recordset (ODBC)](../../data/odbc/recordset-odbc.md).

## <a name="see-also"></a>Siehe auch

[ODBC und MFC](../../data/odbc/odbc-and-mfc.md)