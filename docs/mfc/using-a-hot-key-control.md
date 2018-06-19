---
title: Verwenden eines Abkürzungstasten-Steuerelements | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4442d45cffdae63600fa3a405e29a139b149175
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382943"
---
# <a name="using-a-hot-key-control"></a>Verwenden eines Abkürzungstasten-Steuerelements
Typische Verwendung eines Abkürzungstasten-Steuerelements entspricht dem folgenden Muster:  
  
-   Das Steuerelement wird erstellt. Wenn das Steuerelement in einer Dialogfeldvorlage angegeben wird, erfolgt die Erstellung automatisch, wenn das Dialogfeld erstellt wird. (Sie müssen eine [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) Member in der Dialogfeldklasse, die die Abkürzungstasten-Steuerelements entspricht.) Alternativ können Sie die [erstellen](../mfc/reference/chotkeyctrl-class.md#create) Memberfunktion beim Erstellen des Steuerelements als untergeordnetes Fenster von einem beliebigen Fenster.  
  
-   Wenn Sie einen Standardwert für das Steuerelement festlegen möchten, rufen Sie die [Memberfunktion SetHotKey](../mfc/reference/chotkeyctrl-class.md#sethotkey) Memberfunktion. Wenn Sie bestimmte Umschaltzustände verhindern möchten, rufen Sie [SetRules](../mfc/reference/chotkeyctrl-class.md#setrules). Für Steuerelemente in einem Dialogfeld, ist ein guter Zeitpunkt, zu diesem Zweck in des Dialogfelds [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) Funktion.  
  
-   Der Benutzer interagiert mit dem Steuerelement, indem Sie die Tastenkombination drücken, während die Abkürzungstasten-Steuerelement den Fokus besitzt. Der Benutzer gibt dann aus irgendeinem Grund an, dass diese Aufgabe abgeschlossen ist, z. B. wird durch Klicken auf eine Schaltfläche im Dialogfeld.  
  
-   Wenn Ihr Programm benachrichtigt wird, dass der Benutzer die Zugriffstaste ausgewählt hat, sollten sie die Memberfunktion verwenden [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) zum Abrufen der virtuellen Schlüssel und UMSCHALT-Status-Werte aus der Abkürzungstasten-Steuerelements.  
  
-   Nachdem Sie wissen, was vom Benutzer ausgewählten Schlüssel, können Sie festlegen, dass die Abkürzungstaste mit einer der Methoden, die in beschriebenen [Festlegen einer Abkürzungstaste](../mfc/setting-a-hot-key.md).  
  
-   Wenn die Abkürzungstasten-Steuerelements in einem Dialogfeld ist es und `CHotKeyCtrl` Objekt wird automatisch zerstört werden. Wenn nicht der Fall, Sie sicherstellen, dass sowohl im Steuerelement müssen und dem `CHotKeyCtrl` Objekt ordnungsgemäß zerstört werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

