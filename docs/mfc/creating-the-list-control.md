---
title: Erstellen des Listensteuerelements | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42457e223bb7e12da64be54d757e05d0bac3a028
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342045"
---
# <a name="creating-the-list-control"></a>Erstellen des Listensteuerelements
Wie das Listensteuerelement ([CListCtrl](../mfc/reference/clistctrl-class.md)) erstellt wird, ob Sie das Steuerelement direkt verwenden oder mithilfe der Klasse hängt [CListView](../mfc/reference/clistview-class.md) stattdessen. Bei Verwendung von `CListView`, das Framework erstellt die Sicht als Teil seiner Dokument-/Ansichtarchitektur Erstellung Sequenz. Beim Erstellen der Listenansicht erstellt das Strukturelement-Steuerelement auch (beide sind identisch). Das Steuerelement wird in der Ansicht erstellt [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handlerfunktion. In diesem Fall wird das Steuerelement anschließend bereit für das Hinzufügen von Elementen, die über einen Aufruf an [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl).  
  
### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>Verwenden von CListCtrl direkt in einem Dialogfeld  
  
1.  Der Dialog-Editor fügen Sie ein Listenfeld-Steuerelement um der Dialogfeldvorlagen-Ressource hinzu. Geben Sie die Steuerelement-ID.  
  
2.  Verwenden der [Assistenten zum Hinzufügen von Variablen](../ide/adding-a-member-variable-visual-cpp.md) eine Membervariable des Typs hinzufügen `CListCtrl` mit der Eigenschaft des Steuerelements. Können Sie bei diesem Member Aufrufen `CListCtrl` Memberfunktionen.  
  
3.  Verwendet im Eigenschaftenfenster Handlerfunktionen in Dialogklasse zuordnen, für alle steuerelementebenachrichtigung Liste angezeigt werden, behandeln müssen (siehe [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).  
  
4.  In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), legen Sie die Formate für die `CListCtrl`. Finden Sie unter [Ändern der Stile von Listensteuerelementen](../mfc/changing-list-control-styles.md). Dies bestimmt die Art "View" erhalten Sie in das Steuerelement, obwohl Sie die Ansicht später ändern können.  
  
### <a name="to-use-clistctrl-in-a-nondialog-window"></a>Verwenden von CListCtrl in einem Dialogfenster  
  
1.  Definieren Sie das Steuerelement in der Ansicht oder Fenster-Klasse.  
  
2.  Rufen Sie das Steuerelement [erstellen](../mfc/reference/clistctrl-class.md#create) Memberfunktion, möglicherweise in [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), möglicherweise so früh wie des übergeordnete Fensters [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handlerfunktion (Wenn Sie sind Erstellen von Unterklassen für das Steuerelement). Legen Sie die Formate für das Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

