---
title: 'Transaktion: Auswirkungen von Transaktionen auf Aktualisierungen (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
ms.openlocfilehash: 996b8410366661cb91cf82cfff823f17d3aad8b4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033106"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>Transaktion: Auswirkungen von Transaktionen auf Aktualisierungen (ODBC)

Updates für die [Datenquelle](../../data/odbc/data-source-odbc.md) verwaltet werden, während der Transaktionen, durch die Verwendung von Bearbeitungspuffer (die gleiche Methode außerhalb von Transaktionen verwendet). Die Felddatenmembern eines Recordset-Objekts dienen zusammen als Bearbeitungspuffer mit den aktuellen Datensatz, der das Recordset vorübergehend während der Sicherung ein `AddNew` oder `Edit`. Während einer `Delete` Vorgang, den aktuellen Datensatz werden nicht innerhalb einer Transaktion gesichert. Weitere Informationen zu den bearbeiten und wie Updates für den aktuellen Datensatz speichern, finden Sie unter [Recordset: Datensatzaktualisierung durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

> [!NOTE]
>  Wenn Sie die massenzeilenabruf implementiert haben, Sie nicht aufrufen, `AddNew`, `Edit`, oder `Delete`. Sie müssen stattdessen eigene Funktionen zum Durchführen von Updates mit der Datenquelle schreiben. Weitere Informationen zu gesammelten Abrufens von Zeilen, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Während einer Transaktion `AddNew`, `Edit`, und `Delete` Vorgänge ein Commit oder Rollback werden können. Die Auswirkungen der `CommitTrans` und `Rollback` kann dazu führen, dass den aktuellen Datensatz im Bearbeitungspuffer nicht wiederhergestellt werden. Um sicherzustellen, dass der aktuelle Datensatz ordnungsgemäß wiederhergestellt wird, ist es wichtig zu verstehen, wie die `CommitTrans` und `Rollback` Memberfunktionen der `CDatabase` arbeiten mit den Funktionen der Aktualisierung der `CRecordset`.

##  <a name="_core_how_committrans_affects_updates"></a> Wie wirkt sich auf CommitTrans Updates

Die folgende Tabelle erläutert die Auswirkungen der `CommitTrans` Transaktionen.

### <a name="how-committrans-affects-updates"></a>Wie wirkt sich auf CommitTrans Updates

|Vorgang|Status der Datenquelle|
|---------------|---------------------------|
|`AddNew` und `Update`, und klicken Sie dann `CommitTrans`|Neuer Datensatz Datenquelle hinzugefügt werden.|
|`AddNew` (ohne `Update`), und klicken Sie dann `CommitTrans`|Neuer Datensatz geht verloren. Der Datensatz nicht zur Datenquelle hinzugefügt.|
|`Edit` und `Update`, und klicken Sie dann `CommitTrans`|Änderungen, die an die Datenquelle übergeben werden.|
|`Edit` (ohne `Update`), und klicken Sie dann `CommitTrans`|Änderungen am Datensatz verloren. Datensatz bleibt in der Datenquelle unverändert.|
|`Delete` Klicken Sie dann `CommitTrans`|Datensätze, die aus der Datenquelle gelöscht werden.|

##  <a name="_core_how_rollback_affects_updates"></a> Auswirkungen von Transaktionen durch Rollback

Die folgende Tabelle erläutert die Auswirkungen der `Rollback` Transaktionen.

### <a name="how-rollback-affects-transactions"></a>Auswirkungen von Transaktionen durch Rollback

|Vorgang|Status des aktuellen Datensatzes|Sie müssen auch|Status der Datenquelle|
|---------------|------------------------------|-------------------|---------------------------|
|`AddNew` und `Update`, klicken Sie dann `Rollback`|Der Inhalt des aktuellen Datensatzes temporär gespeichert, um Platz für den neuen Datensatz zu schaffen. Neuer Datensatz wird in Bearbeitungspuffer eingegeben. Nach dem `Update` aufgerufen wird, wird der aktuelle Datensatz im Bearbeitungspuffer wiederhergestellt wird.||Zusätzlich zu der Datenquelle, die von `Update` wird umgekehrt.|
|`AddNew` (ohne `Update`), klicken Sie dann `Rollback`|Der Inhalt des aktuellen Datensatzes temporär gespeichert, um Platz für den neuen Datensatz zu schaffen. Bearbeiten Sie Puffer enthält den neuen Datensatz.|Rufen Sie `AddNew` erneut aus, um einen leeren, neuen Datensatz Bearbeitungspuffer wiederherzustellen. Oder rufen Sie `Move`(0), um die alten Werte im Bearbeitungspuffer wiederherzustellen.|Da `Update` nicht aufgerufen wurde, gab es keine Änderungen an der Datenquelle vorgenommen wurden.|
|`Edit` und `Update`, klicken Sie dann `Rollback`|Eine unveränderte Version des aktuellen Datensatzes ist temporär gespeichert. Änderungen werden auf den Inhalt des Bearbeitungspuffer vorgenommen. Nach dem `Update` aufgerufen wird, der nicht bearbeitete Version des Datensatzes wird weiterhin temporär gespeichert.|*Dynaset*: Führen Sie einen Bildlauf aus dem aktuellen Datensatz, und klicken Sie dann an die unveränderte Version des Datensatzes im Bearbeitungspuffer wiederherzustellen.<br /><br /> *Snapshot*: Rufen Sie `Requery` das Recordset aus der Datenquelle zu aktualisieren.|Änderungen an der Datenquelle, die von `Update` rückgängig gemacht werden.|
|`Edit` (ohne `Update`), klicken Sie dann `Rollback`|Eine unveränderte Version des aktuellen Datensatzes ist temporär gespeichert. Änderungen werden auf den Inhalt des Bearbeitungspuffer vorgenommen.|Rufen Sie `Edit` erneut aus, um die unveränderte Version des Datensatzes im Bearbeitungspuffer wiederherzustellen.|Da `Update` nicht aufgerufen wurde, gab es keine Änderungen an der Datenquelle vorgenommen wurden.|
|`Delete` Klicken Sie dann `Rollback`|Der Inhalt des aktuellen Datensatzes wird gelöscht.|Rufen Sie `Requery` den Inhalt des aktuellen Datensatzes aus der Datenquelle wiederhergestellt.|Löschen von Daten aus der Datenquelle wird umgekehrt.|

## <a name="see-also"></a>Siehe auch

[Transaktion (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[Transaktion (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)<br/>
[CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset-Klasse](../../mfc/reference/crecordset-class.md)