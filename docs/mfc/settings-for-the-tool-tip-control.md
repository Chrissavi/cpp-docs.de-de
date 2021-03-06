---
title: Einstellungen für das QuickInfo-Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
ms.openlocfilehash: 5cc72401da95e63520b544865ea509a8ad219bda
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307613"
---
# <a name="settings-for-the-tool-tip-control"></a>Einstellungen für das QuickInfo-Steuerelement

Sie können das QuickInfo-Steuerelement ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) entweder als aktiv oder als inaktiv festlegen. Wenn Sie es als aktiv festlegen, wird das QuickInfo-Steuerelement angezeigt, wenn Sie den Cursor auf einem Tool platzieren. Wenn Sie es als inaktiv festlegen, wird das QuickInfo-Steuerelement auch dann nicht angezeigt, wenn sich der Cursor auf einem Tool befindet. Rufen Sie [Activate](../mfc/reference/ctooltipctrl-class.md#activate) auf, um ein QuickInfo-Steuerelement zu aktivieren oder deaktivieren.

Sie können festlegen, um die QuickInfo angezeigt wird, wenn der Cursor auf einem Tool befindet, und zwar unabhängig davon, ob Besitzerfensters für das QuickInfo-Steuerelements mithilfe des Stils TTS_ALWAYSTIP aktiv oder inaktiv ist, wird eine aktive QuickInfo. Wenn Sie dieses Formatvorlage nicht verwenden, wird das QuickInfo-Steuerelement angezeigt, wenn das besitzende Fenster des Steuerelements aktiv ist, aber nicht, wenn es nicht aktiv ist.

Die meisten Anwendungen enthalten Symbolleisten mit Tools, die Menübefehlen entsprechen. Für solche Tools ist es sinnvoll, wenn im QuickInfo-Steuerelement der gleiche Text wie im entsprechenden Menüelement angezeigt wird. Das System entfernt automatisch das kaufmännische und-Zeichen (&) Accelerator Zeichen aus allen Zeichenfolgen, die an ein QuickInfo-Steuerelement, es sei denn, das Steuerelement den TTS_NOPREFIX-Stil.

## <a name="see-also"></a>Siehe auch

[Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
