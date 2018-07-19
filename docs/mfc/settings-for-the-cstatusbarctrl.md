---
title: Einstellungen für CStatusBarCtrl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1dde1f005e53aff7ebe505d1ce619bf5c94410f8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955455"
---
# <a name="settings-for-the-cstatusbarctrl"></a>Einstellungen für CStatusBarCtrl
Die Standardposition des eine [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) Statusfenster wird am unteren Rand des übergeordneten Fensters, aber Sie können angeben, dass das Format CCS_TOP-Format, damit diese am oberen Rand der Clientbereich des übergeordneten Fensters angezeigt.  
  
 Sie können angeben, dass das SBARS_SIZEGRIP-Format Einbeziehung einen Größenziehpunkt am rechten Ende der `CStatusBarCtrl` Statusfenster. Ein Größenziehpunkt ist vergleichbar mit einem Rahmen; Es ist ein rechteckigen Bereichs, der der Benutzer kann klicken und ziehen Sie zum Ändern der Größe des übergeordneten Fensters.  
  
> [!NOTE]
>  Wenn Sie die Stile CCS_TOP-Format und SBARS_SIZEGRIP kombinieren, ist der resultierende Größenziehpunkt nicht funktionsfähig, obwohl das System im Statusfenster zeichnet.  
  
 Die Fensterprozedur für das Statusfenster legt automatisch die anfängliche Größe und Position des Steuerelements. Die Breite entspricht den Clientbereich des übergeordneten Fensters. Die Höhe basiert auf den Metriken der Schriftart, die derzeit dem Statusfenster Gerätekontext ausgewählt ist und die Breite des Fensterrahmens.  
  
 Die Fensterprozedur passt automatisch die Größe des Fensters Status an, nach Empfang einer Nachricht WM_SIZE. Wenn die Größe des übergeordneten Fensters ändert, sendet das übergeordnete Element in der Regel eine WM_SIZE-Nachricht im Statusfenster.  
  
 Sie können die minimale Höhe der Zeichnungsbereich einer Statusfenster festlegen, durch den Aufruf [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight), die minimale Höhe in Pixel angibt. Der Zeichnungsbereich umfasst keine des Fensterrahmens.  
  
 Die Breite des Rahmens eines Fensters Status abrufen rufen Sie [GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders). Diese Memberfunktion umfasst die Zeiger auf ein Array mit drei Elementen, die die Breite des horizontalen Rands vertikalen Rands und dem Rahmen zwischen Rechtecke empfängt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

