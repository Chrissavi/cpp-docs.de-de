---
title: Validieren von Dialogfelddaten
ms.date: 11/04/2016
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
ms.openlocfilehash: 9de2db002d7f06e797531c09af0a021c402eec7d
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502279"
---
# <a name="dialog-data-validation"></a>Validieren von Dialogfelddaten

Sie können die Überprüfung zusätzlich zum Datenaustausch angeben, indem Sie DDV-Funktionen aufrufen, wie im Beispiel in [Dialog Datenaustausch](dialog-data-exchange.md)gezeigt. Der-Befehl `DDV_MaxChars` im Beispiel überprüft, ob die Zeichenfolge, die im Textfeld-Steuerelement eingegeben wird, nicht länger als 20 Zeichen ist. Die DDV-Funktion warnt den Benutzer in der Regel mit einem Meldungs Feld, wenn die Validierung fehlschlägt, und legt den Fokus auf das verletzende Steuerelement, sodass der Benutzer die Daten erneut eingeben kann. Eine DDV-Funktion für ein bestimmtes Steuerelement muss unmittelbar nach der DDX-Funktion für dasselbe Steuerelement aufgerufen werden.

Sie können auch eigene benutzerdefinierte DDX-und DDV-Routinen definieren. Ausführliche Informationen zu diesen und anderen Aspekten von DDX und DDV finden [Sie unter MFC Technical Note 26](tn026-ddx-and-ddv-routines.md).

Mit dem [Assistenten zum Hinzufügen von Mitgliedsvariablen](../ide/adding-a-member-variable-visual-cpp.md#add-member-variable-wizard) werden alle DDX-und DDV-Aufrufe in der Datenzuordnung geschrieben.

## <a name="see-also"></a>Weitere Informationen

[Dialog Datenaustausch und-Validierung](dialog-data-exchange-and-validation.md)<br/>
[Arbeiten mit Dialogfeldern in MFC](life-cycle-of-a-dialog-box.md)<br/>
[Dialogdatenaustausch](dialog-data-exchange.md)
