---
title: Implementieren der Statusleiste in MFC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- COldStatusBar
dev_langs:
- C++
helpviewer_keywords:
- status bars [MFC], implementing in MFC
- CStatusBarCtrl class [MFC], and MFC status bars
- CStatusBar class [MFC], and CStatusBarCtrl class [MFC]
- CStatusBarCtrl class [MFC], and CStatusBar class [MFC]
- status bars [MFC], backward compatibility
- status bars [MFC], old with COldStatusBar class [MFC]
- COldStatusBar class [MFC]
- status bars [MFC], and CStatusBarCtrl class
- CStatusBar class [MFC], and MFC status bars
- status indicators
- status bars [MFC], Windows 95 implementation
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cadb06076ff7a3dd481a1bcedc9cd0afe4989f28
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950447"
---
# <a name="status-bar-implementation-in-mfc"></a>Implementieren der Statusleiste mit MFC
Ein [CStatusBar](../mfc/reference/cstatusbar-class.md) Objekt ist eine Steuerleiste mit einer Zeile von Textausgabebereichen. Die Ausgabebereiche werden häufig als Nachricht Linien und als Statusindikatoren verwendet. Beispiele sind im Menü Hilfe-Nachricht Zeilen, die den ausgewählten Menübefehl kurz und die Indikatoren, die den Status von Rollen, NUM- und andere Schlüssel anzuzeigen.  
  
 Ab MFC 4.0 werden Statusleisten implementiert, mit der Klasse [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md), die eine Statusleiste Standardsteuerelements kapselt. Für die Abwärtskompatibilität behält MFC die ältere Status Befehlsleisten-Standardimplementierung in Klasse `COldStatusBar`. Die Dokumentation für frühere Versionen von MFC beschreibt `COldStatusBar` unter `CStatusBar`.  
  
 [GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl), eine Memberfunktion neue MFC 4.0, können Sie das allgemeine Windows-Steuerelement-Unterstützung für Statusleiste Anpassung und zusätzliche Funktionen nutzen. `CStatusBar` Memberfunktionen geben Ihnen die meisten Funktionen des allgemeinen Windows-Steuerelemente; allerdings beim Aufruf `GetStatusBarCtrl`, Ihre Statusleisten noch länger die Merkmale einer Statusleiste erteilen. Beim Aufruf `GetStatusBarCtrl`, er wird zurückgegeben, einen Verweis auf ein `CStatusBarCtrl` Objekt. Dieser Verweis können Sie um das StatusBar-Steuerelement zu bearbeiten.  
  
 Die folgende Abbildung zeigt eine Statusleiste, in dem mehrere Indikatoren angezeigt.  
  
 ![Statusleiste](../mfc/media/vc37dy1.gif "vc37dy1")  
Statusleiste  
  
 Wie die Symbolleiste das Statusleiste Objekt ist in seiner übergeordneten Rahmenfensters eingebettet und wird automatisch erstellt, wenn das Rahmenfenster erstellt wird. Die Statusleiste, wie alle Steuerleisten automatisch ebenfalls zerstört, wenn der übergeordneten Frame zerstört wird.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Aktualisieren des Textes in der eine Status-Leistenbereich](../mfc/updating-the-text-of-a-status-bar-pane.md)  
  
-   MFC-Klassen [CStatusBar](../mfc/reference/cstatusbar-class.md) und [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
  
-   [Steuerleisten](../mfc/control-bars.md)  
  
-   [Dialogleisten](../mfc/dialog-bars.md)  
  
-   [Symbolleisten (MFC-Symbolleistenimplementierung)](../mfc/mfc-toolbar-implementation.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Statusleisten](../mfc/status-bars.md)

