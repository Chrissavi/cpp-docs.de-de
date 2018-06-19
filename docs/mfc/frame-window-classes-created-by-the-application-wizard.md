---
title: Rahmenfensterklassen erstellt vom Anwendungs-Assistenten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CMainFrame
dev_langs:
- C++
helpviewer_keywords:
- application wizards [MFC], frame window classes created by
- window classes [MFC]
- classes [MFC], frame-window
- CMDIFrameWnd class [MFC], frame windows
- window classes [MFC], frame
- CFrameWnd class [MFC], frame windows
- CMDIChildWnd class [MFC], frame windows
- frame window classes [MFC], created by application wizards
- CMainFrame class [MFC]
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3446de072266fdf7661d2e8d8ca0fc968279646
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345042"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>Vom Anwendungs-Assistenten erstellte Rahmenfensterklassen
Bei Verwendung der [Anwendungs-Assistent](../ide/creating-desktop-projects-by-using-application-wizards.md) zum Erstellen einer skelettanwendung zusätzlich zur Anwendung, Dokument und Ansichtsklassen, erstellt der Anwendungs-Assistent für Hauptrahmenfenster für Ihre Anwendung eine abgeleiteten Rahmenfenster-Klasse. Die Klasse heißt `CMainFrame` standardmäßig und die Dateien, die sie enthalten bezeichnet. H und MAINFRM. CPP.  
  
 Wenn Ihre Anwendung SDI, ist Ihre `CMainFrame` von Klasse abgeleitete Klasse [CFrameWnd](../mfc/reference/cframewnd-class.md).  
  
 Wenn die Anwendung MDI, `CMainFrame` Klasse abgeleitet ist [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md). In diesem Fall `CMainFrame` implementiert den Hauptframe, die die Menüs, Symbolleisten und Status Balken enthält. Der Anwendungs-Assistent ist eine neue Rahmenfenster Dokumentklasse für Sie nicht abgeleitet werden. Stattdessen wird die standardmäßige Implementierung in [CMDIChildWnd-Klasse](../mfc/reference/cmdichildwnd-class.md). Das MFC-Framework erstellt ein untergeordnetes Fenster, sodass jede Ansicht enthält (erfolgen kann vom Typ `CScrollView`, `CEditView`, `CTreeView`, `CListView`usw.), die die Anwendung erforderlich sind. Wenn Sie Ihre Dokumentrahmenfenster anpassen müssen, können, erstellen Sie eine neue Dokument Rahmenfenster Klasse (siehe [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)).  
  
 Falls gewünscht, um eine Symbolleiste zu unterstützen, verfügt die Klasse auch Membervariablen des Typs [CToolBar](../mfc/reference/ctoolbar-class.md) und [CStatusBar](../mfc/reference/cstatusbar-class.md) und ein `OnCreate` Meldungshandler Funktion initialisiert werden, die beiden [ die Steuerleisten](../mfc/control-bars.md).  
  
 Diese Rahmenfensterklassen funktionieren, wie erstellt, aber um ihre Funktionalität zu erweitern, müssen Sie die Membervariablen und Memberfunktionen hinzufügen. Sie sollten auch Ihre Fensterklassen, die andere Windows-Meldungen verarbeitet wurden. Weitere Informationen finden Sie unter [Ändern der Stile von einer mit MFC erstellten Fensters](../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Rahmenfensterklassen](../mfc/frame-window-classes.md)   
 [MFC-Programm oder Steuern von Quell- und Headerdateien](../ide/mfc-program-or-control-source-and-header-files.md)

