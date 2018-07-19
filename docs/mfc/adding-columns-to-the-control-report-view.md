---
title: Hinzufügen von Spalten zum Steuerelement (Berichtsansicht) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], adding columns
- report view in CListCtrl class [MFC]
- views [MFC], report
- columns [MFC], adding to CListCtrl
- CListCtrl class [MFC], report view
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 975d65119ba0ae24b236d96cbe67e73b70be6bac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341828"
---
# <a name="adding-columns-to-the-control-report-view"></a>Hinzufügen von Spalten zum Steuerelement (Berichtsansicht)
> [!NOTE]
>  Das folgende Verfahren gilt für entweder eine [CListView](../mfc/reference/clistview-class.md) oder [CListCtrl](../mfc/reference/clistctrl-class.md) Objekt.  
  
 Wenn ein Listenfeld-Steuerelement in der Berichtsansicht ist, werden Spalten bietet eine Methode zum Organisieren von verschiedenen Unterelemente für jedes Listenelement-Steuerelement angezeigt. Diese Organisation wird mit einer 1: 1-Entsprechung zwischen einer Spalte in das Strukturelement-Steuerelement und dem Unterelement des Listenelements Steuerelement implementiert. Weitere Informationen über Unterelemente finden Sie unter [Hinzufügen von Elementen zum Steuerelement](../mfc/adding-items-to-the-control.md). Ein Beispiel für ein Listenfeld-Steuerelement in der Berichtsansicht wird durch die Detailansicht in Windows 95 und Windows 98-Explorer bereitgestellt. Die erste Spalte enthält die Ordner, Dateisymbole und Bezeichnungen. Andere Spalten enthalten die Dateigröße, Dateityp, Datum der letzten Änderung und So weiter.  
  
 Obwohl Spalten ein Listenfeld-Steuerelement zu einem beliebigen Zeitpunkt hinzugefügt werden können, die Spalten sind sichtbar nur, wenn das Steuerelement hat den `LVS_REPORT` Formatbit eingeschaltet.  
  
 Jede Spalte verfügt über eine zugeordnete Headerelement (finden Sie unter [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) Objekt, das die Spalte "Bezeichnungen", und ermöglicht es Benutzern, die Größe der Spalte ändern.  
  
 Wenn das Listensteuerelement eine Berichtsansicht unterstützt, müssen Sie eine Spalte für jedes mögliche Unterelement in einem Steuerelement ein Element hinzuzufügen. Eine Spalte hinzufügen, indem Sie die Vorbereitung einer [LV_COLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743) Struktur und nehmen Sie dann auf einen Aufruf von [InsertColumn](../mfc/reference/clistctrl-class.md#insertcolumn). Nach dem Hinzufügen der erforderlichen Spalten (auch als Headerelemente bezeichnet), Sie können Reihenfolge mithilfe von Memberfunktionen und Formate, die auf das eingebettete Headersteuerelement gehören. Weitere Informationen finden Sie unter [Anordnen von Elementen im Headersteuerelement](../mfc/ordering-items-in-the-header-control.md).  
  
> [!NOTE]
>  Wenn das Strukturelement-Steuerelement erstellt wird, mit der **LVS_NOCOLUMNHEADER** Stil jeder Versuch, fügen Sie Spalten ignoriert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

