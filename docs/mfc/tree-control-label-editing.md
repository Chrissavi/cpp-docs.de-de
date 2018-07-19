---
title: Struktursteuerelement-Bezeichnung bearbeiten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d665ae37bfc843fc2ab0f24fe4489b76935e62d2
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956264"
---
# <a name="tree-control-label-editing"></a>Bearbeiten der Struktursteuerelement-Bezeichnung
Der Benutzer kann direkt bearbeiten der Bezeichnungen von Elementen in einem Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)), hat die **TVS_EDITLABELS** Stil. Der Benutzer beginnt, bearbeiten, indem Sie auf die Bezeichnung des Elements, das den Fokus besitzt. Eine Anwendung beginnt mit der Bearbeitung mithilfe der [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel) Memberfunktion. Strukturansicht-Steuerelements sendet die Benachrichtigung, wenn Bearbeitung beginnt und wann er abgebrochen oder beendet wird. Wenn die Bearbeitung abgeschlossen ist, sind Sie verantwortlich für das Aktualisieren der Elementnamen, bei Bedarf.  
  
 Wenn Bezeichnung Bearbeitung beginnt, ein Strukturansicht-Steuerelement sendet eine [TVN_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506) Benachrichtigung. Durch die Verarbeitung dieser benachrichtigungs, können bearbeitet einige Bezeichnungen und Bearbeitung von anderen verhindern. Zurückgeben von 0 ermöglicht das Bearbeiten und ungleich NULL zurückgeben es verhindert.  
  
 Beim Bearbeiten von Bezeichnungen abgebrochen wird oder abgeschlossen ist, sendet ein Strukturansicht-Steuerelement eine [TVN_ENDLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773515) benachrichtigungsmeldung. Die *lParam* Parameter ist die Adresse einer [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418) Struktur. Die **Element** Member ist ein [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) -Struktur, die das Element identifiziert und den bearbeiteten Text enthält. Sie sind verantwortlich für die Aktualisierung Bezeichnung für das Element, bei Bedarf möglicherweise nach dem Validieren der bearbeiteten Zeichenfolge. Die *PszText* Mitglied `TV_ITEM` ist 0, wenn die Bearbeitung abgebrochen wird.  
  
 Beim Bearbeiten von Bezeichnungen, in der Regel als Antwort auf die [TVN_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506) Benachrichtigung, können Sie einen Zeiger für das Bearbeitungssteuerelement Bezeichnung bearbeiten, indem Sie zum erhalten der [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol) Member Funktion. Sie können des Bearbeitungssteuerelements Aufrufen [SetLimitText](../mfc/reference/cedit-class.md#setlimittext) Memberfunktion versucht, die Begrenzung des Umfangs der Text kann ein Benutzer eingeben oder Unterklassen das Bearbeitungssteuerelement zum Abfangen und verwerfen ungültige Zeichen. Beachten Sie jedoch, dass das Bearbeitungssteuerelement nur angezeigt wird, *nach* **TVN_BEGINLABELEDIT** gesendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

