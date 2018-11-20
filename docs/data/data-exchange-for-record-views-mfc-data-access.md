---
title: Datenaustausch für Datensatzansichten (MFC-Datenzugriff)
ms.date: 11/19/2018
helpviewer_keywords:
- RFX (record field exchange), data exchange mechanism
- RFX (record field exchange), record views
- record views, data exchange
- DDX (dialog data exchange), record views
- RFX (record field exchange)
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
ms.openlocfilehash: bf9f32e970becd1ef8dc4e347512dcfaa7cf62ac
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175409"
---
# <a name="data-exchange-for-record-views---mfc-data-access"></a>Datenaustausch für Datensatzansichten (MFC-Datenzugriff)

Bei Verwendung von [Klasse hinzufügen](../mfc/reference/adding-an-mfc-odbc-consumer.md) um die Steuerelemente in der Dialogfeldvorlagen-Ressource einer Datensatzansicht den Feldern eines Recordsets zuzuordnen, verwaltet das Framework den Datenaustausch in beide Richtungen – vom Recordset zu den Steuerelementen und umgekehrt. Wenn Sie den DDX-Mechanismus verwenden, müssen Sie den Code zur Datenübertragung nicht selbst schreiben.

DDX für Datensatzansichten funktioniert in Verbindung mit [RFX](../data/odbc/record-field-exchange-rfx.md) für Recordsets der Klasse `CRecordset` (ODBC).  RFX verschiebt Daten zwischen den aktuellen Datensatz der Datenquelle und den Felddatenmembern eines Recordset-Objekts. DDX verschiebt die Daten aus den Felddatenmembern in die Steuerelemente im Formular. Durch diese Kombination werden die Steuerelemente des Formulars am Anfang und immer dann gefüllt, wenn der Benutzer sich von Datensatz zu Datensatz bewegt. Zudem können aktualisierte Daten zurück in das Recordset und anschließend in die Datenquelle verschoben werden.

Die folgende Abbildung zeigt die Beziehung zwischen DDX und RFX für Datensatzansichten.

![Dialogfeld&#45;Datenaustausch und eines Eintrags&#45;Feld Exchange](../data/media/vc37xt1.gif "Dialogfeld&#45;Datenaustausch und eines Eintrags&#45;Feld Exchange")<br/>
Dialogdatenaustausch und Datensatzfeldaustausch

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../mfc/dialog-data-exchange-and-validation.md). Weitere Informationen über RFX finden Sie unter [Datensatzfeldaustausch (RFX)](../data/odbc/record-field-exchange-rfx.md).

## <a name="see-also"></a>Siehe auch

[Datensatzansichten (MFC-Datenzugriff)](../data/record-views-mfc-data-access.md)<br/>
[Liste der ODBC-Treiber](../data/odbc/odbc-driver-list.md)