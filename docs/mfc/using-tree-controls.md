---
title: Verwenden von Struktursteuerelementen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], using
- tree controls [MFC], about tree controls
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9cb5c8892583adac01ca883034b8c0af18595c9
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954594"
---
# <a name="using-tree-controls"></a>Verwenden von Struktursteuerelementen
Typische Verwendung des Strukturansicht-Steuerelements ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) entspricht dem folgenden Muster:  
  
-   Das Steuerelement wird erstellt. Wenn das Steuerelement in einer Dialogfeldvorlage angegeben ist, oder bei Verwendung von `CTreeView`, Erstellung erfolgt automatisch, wenn das Dialogfeld oder eine Sicht erstellt wird. Wenn Sie das Strukturansicht-Steuerelement als untergeordnetes Fenster eines anderen Fensters erstellen möchten, verwenden Sie die [erstellen](../mfc/reference/ctreectrl-class.md#create) Memberfunktion.  
  
-   Wenn Sie die Strukturansicht-Steuerelements Bilder verwenden möchten, legen Sie eine Bildliste durch Aufrufen von [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist). Sie können auch den Einzug ändern, durch den Aufruf [SetIndent](../mfc/reference/ctreectrl-class.md#setindent). Ein guter Zeitpunkt, zu diesem Zweck wird [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) (für Steuerelemente in Dialogfeldern) oder [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) (für Ansichten).  
  
-   Fügen Sie Daten in das Steuerelement durch Aufrufen der `CTreeCtrl`des [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) Funktion einmal für jedes Datenelement. `InsertItem` Gibt ein Handle auf das Element, das Sie verwenden können, z. B. Wenn später darauf verweisen Hinzufügen untergeordneter Elemente. Ein guter Zeitpunkt, um die Daten zu initialisieren ist `OnInitDialog` (für Steuerelemente in Dialogfeldern) oder `OnInitialUpdate` (für Ansichten).  
  
-   Wie der Benutzer mit dem Steuerelement interagiert, sendet er verschiedene benachrichtigungsmeldungen. Sie können angeben, dass eine Funktion, um jede der Nachrichten zu verarbeiten, die Sie durch Hinzufügen eines ON_NOTIFY_REFLECT-Makros in Ihrem Steuerelementfensters meldungszuordnung oder indem Sie eine ON_NOTIFY-Makro auf das übergeordnete Fenster meldungszuordnung behandeln möchten. Finden Sie unter [Benachrichtigungsmeldungen von Struktursteuerelementen](../mfc/tree-control-notification-messages.md) weiter unten in diesem Thema eine Liste der möglichen Benachrichtigungen.  
  
-   Rufen Sie die verschiedenen Satz Memberfunktionen können Sie Werte für das Steuerelement festlegen. Änderungen, die Sie vornehmen können, gehören das Festlegen von des Einzugs, und der Text, Image oder einem Element zugeordneten Daten ändern.  
  
-   Verwenden Sie die verschiedenen Get-Funktionen, um den Inhalt des Steuerelements zu untersuchen. Sie können auch den Inhalt des Strukturansicht-Steuerelements mit Funktionen durchsuchen, mit die Sie Handles für übergeordnete, untergeordnete oder gleichgeordnete Elemente eines angegebenen Elements abrufen können. Sie können auch die untergeordneten Elemente eines bestimmten Knotens sortieren.  
  
-   Wenn Sie mit dem Steuerelement fertig sind, stellen Sie sicher, dass es ordnungsgemäß zerstört wird. Ist das Strukturansicht-Steuerelement in einem Dialogfeld oder eine Sicht ist es und `CTreeCtrl` Objekt wird automatisch zerstört werden. Wenn nicht der Fall, Sie sicherstellen, dass sowohl im Steuerelement müssen und dem `CTreeCtrl` Objekt ordnungsgemäß zerstört werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

