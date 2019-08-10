---
title: Benachrichtigungen von einem RichEdit-Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
ms.openlocfilehash: bc4c027ff26df89539b22c6d04f1d1dc95fc459a
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916401"
---
# <a name="notifications-from-a-rich-edit-control"></a>Benachrichtigungen von einem RichEdit-Steuerelement

Benachrichtigungs Meldungen melden Ereignisse, die ein Rich Edit-Steuerelement ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) betreffen. Sie können vom übergeordneten Fenster oder mithilfe der Nachrichten Reflektion durch das Rich Edit-Steuerelement selbst verarbeitet werden. Rich Edit-Steuerelemente unterstützen alle Benachrichtigungs Meldungen, die mit Bearbeitungs Steuerelementen verwendet werden, sowie mehrere zusätzliche. Sie können bestimmen, welche Benachrichtigungs Meldungen von einem Rich-Edit-Steuerelement durch Festlegen der "Ereignis Maske" gesendet werden.

Um die Ereignis Maske für ein Rich-Edit-Steuerelement festzulegen, verwenden Sie die Member-Funktion [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) . Sie können die aktuelle Ereignis Maske für ein Rich Edit-Steuerelement mithilfe der [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) -Member-Funktion abrufen.

In den folgenden Abschnitten werden einige spezifische Benachrichtigungen und ihre Verwendungsmöglichkeiten aufgelistet:

- EN_MSGFILTER durch die Verarbeitung der EN_MSGFILTER-Benachrichtigung kann eine Klasse, entweder das Rich Edit-Steuerelement oder das übergeordnete Fenster, alle Tastatur-und Maus Eingaben für das Steuerelement filtern. Der Handler kann die Verarbeitung der Tastatur-oder Maus Meldung verhindern oder die Meldung ändern, indem er die angegebene [msgfilter](/windows/desktop/api/richedit/ns-richedit-msgfilter) -Struktur ändert.

- EN_PROTECTED behandeln Sie die EN_PROTECTED-Benachrichtigungs Meldung, um zu ermitteln, wann der Benutzer versucht, geschützten Text zu ändern. Um einen Textbereich als geschützt zu markieren, können Sie den Effekt geschützter Zeichen festlegen. Weitere Informationen finden Sie unter [Zeichen Formatierung in Rich Edit](../mfc/character-formatting-in-rich-edit-controls.md)-Steuerelementen.

- EN_DROPFILES Sie können es Benutzern ermöglichen, Dateien in einem Rich-Edit-Steuerelement zu löschen, indem Sie die EN_DROPFILES-Benachrichtigungs Meldung verarbeiten. Die angegebene [endropfiles](/windows/desktop/api/richedit/ns-richedit-endropfiles) -Struktur enthält Informationen zu den Dateien, die gelöscht werden.

- EN_SELCHANGE eine Anwendung kann erkennen, wenn sich die aktuelle Auswahl ändert, indem die EN_SELCHANGE-Benachrichtigungs Meldung verarbeitet wird. Die Benachrichtigungs Meldung gibt eine [selChange](/windows/desktop/api/richedit/ns-richedit-selchange) -Struktur an, die Informationen über die neue Auswahl enthält.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
