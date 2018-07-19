---
title: Erstellen der Bildliste | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e5f5ac8396c32e56e4c0f2f951f45bb33714822
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341524"
---
# <a name="creating-the-image-lists"></a>Erstellen der Bildliste
Erstellen von Bildlisten identisch ist, sowohl bei Verwendung [CListView](../mfc/reference/clistview-class.md) oder [CListCtrl](../mfc/reference/clistctrl-class.md).  
  
> [!NOTE]
>  Sie nur müssen Bildlisten Strukturelement-Steuerelement enthält die `LVS_ICON` Stil.  
  
 Verwenden Sie die Klasse `CImageList` eine oder mehrere Bildlisten (für große Symbole, kleine Symbole und Zustände) zu erstellen. Finden Sie unter [CImageList](../mfc/reference/cimagelist-class.md), und finden Sie unter [Liste Ansicht Bilderlisten](http://msdn.microsoft.com/library/windows/desktop/bb774736) im Windows SDK.  
  
 Rufen Sie [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) für jede Liste image; übergeben Sie einen Zeiger auf die entsprechenden `CImageList` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

