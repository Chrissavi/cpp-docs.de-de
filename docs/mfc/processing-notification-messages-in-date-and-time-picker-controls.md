---
title: Verarbeiten von Benachrichtigungsmeldungen in Steuerelementen für Zeit und Datum
ms.date: 11/04/2016
f1_keywords:
- DTN_CLOSEUP
- DTN_DATETIMECHANGE
- DTN_DROPDOWN
helpviewer_keywords:
- DTN_DROPDOWN notification [MFC]
- DTN_DATETIMECHANGE notification [MFC]
- DTN_CLOSEUP notification [MFC]
- DateTimePicker control [MFC], handling notifications
- CDateTimeCtrl class [MFC], handling notifications
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
ms.openlocfilehash: fead5643299aee4beace55abde0b6a6c801a324f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507877"
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in Steuerelementen für Zeit und Datum

Wenn Benutzer mit dem Steuerelement für die Datums-und Uhrzeit Auswahl interagieren`CDateTimeCtrl`, sendet das Steuerelement () Benachrichtigungs Meldungen an das übergeordnete Fenster, in der Regel eine Ansicht oder ein Dialog Objekt. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Wenn der Benutzer z. b. die Datums-und Zeitauswahl öffnet, um das eingebettete Monatskalender-Steuerelement anzuzeigen, wird die DTN_DROPDOWN-Benachrichtigung gesendet.

Verwenden Sie das Eigenschaftenfenster, um der übergeordneten Klasse Benachrichtigungshandler für die Nachrichten hinzuzufügen, die Sie implementieren möchten.

In der folgenden Liste werden die verschiedenen Benachrichtigungen beschrieben, die vom Steuerelement für Datums-und Zeitauswahl gesendet werden.

- DTN_DROPDOWN benachrichtigt das übergeordnete Element, dass das eingebettete Monatskalender-Steuerelement angezeigt wird. Diese Benachrichtigung wird nur gesendet, wenn der DTS_UPDOWN-Stil nicht festgelegt wurde. Weitere Informationen zu dieser Benachrichtigung finden Sie unter [zugreifen auf das eingebettete Monatskalender-Steuer](../mfc/accessing-the-embedded-month-calendar-control.md)Element.

- DTN_CLOSEUP benachrichtigt das übergeordnete Element, dass das eingebettete Monatskalender-Steuerelement geschlossen wird. Diese Benachrichtigung wird nur gesendet, wenn der DTS_UPDOWN-Stil nicht festgelegt wurde.

- DTN_DATETIMECHANGE benachrichtigt das übergeordnete Element, dass eine Änderung im Steuerelement aufgetreten ist.

- DTN_FORMAT benachrichtigt das übergeordnete Element, dass Text in einem Rückruf Feld angezeigt werden muss. Weitere Informationen zu diesen Benachrichtigungs-und Rückruf Feldern finden [Sie unter Verwenden von Rückruf Feldern in einem Steuerelement für Datums-und Zeit](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)Auswahl.

- DTN_FORMATQUERY fordert das übergeordnete Element auf, die maximal zulässige Größe der Zeichenfolge anzugeben, die in einem Rückruf Feld angezeigt wird. Wenn Sie diese Benachrichtigung verarbeiten, kann das Steuerelement die Ausgabe jederzeit ordnungsgemäß anzeigen, sodass Flimmern innerhalb der Anzeige des Steuer Elements reduziert wird. Weitere Informationen zu dieser Benachrichtigung finden Sie unter [Verwenden von Rückruf Feldern in einem Steuerelement für Datums-und Zeit](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)Auswahl.

- DTN_USERSTRING benachrichtigt das übergeordnete Element, dass der Benutzer die Bearbeitung des Inhalts des Steuer Elements für die Datums-und Uhrzeit Auswahl abgeschlossen hat. Diese Benachrichtigung wird nur gesendet, wenn der DTS_APPCANPARSE-Stil festgelegt wurde.

- DTN_WMKEYDOWN benachrichtigt das übergeordnete Element, wenn der Benutzer ein Rückruf Feld eingibt. Behandeln Sie diese Benachrichtigung, um dieselbe Tastatur Antwort zu emulieren, die für nicht-Rückruf Felder in einem Datums-und Zeitauswahl Steuerelement unterstützt wird. Weitere Informationen zu dieser Benachrichtigung finden Sie [unter unterstützen von Rückruf Feldern in einem DTP-Steuer](/windows/win32/Controls/date-and-time-picker-controls) Element in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
