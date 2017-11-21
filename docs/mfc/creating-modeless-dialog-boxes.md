---
title: Nicht modale Dialogfelder erstellen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7c5a701f42b2707b957753c1f8a22640c7818d72
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="creating-modeless-dialog-boxes"></a>Erstellen von nicht modalen Dialogfeldern
Für ein nicht modales Dialogfeld müssen Sie Ihren eigenen öffentlichen Konstruktor in eigener Dialogfeldklassen bereitstellen. Um ein nicht modales Dialogfeld erstellen, die public-Konstruktor aufrufen und dann des Dialogfeldobjekts [erstellen](../mfc/reference/cdialog-class.md#create) Memberfunktion versucht, die Ressource zu laden. Sie können Aufrufen **erstellen** während oder nach dem Konstruktoraufruf. Wenn die Ressource die Eigenschaft hat **WS_VISIBLE**, das Dialogfeld wird sofort angezeigt. Wenn nicht, die Sie aufrufen müssen dessen [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)
