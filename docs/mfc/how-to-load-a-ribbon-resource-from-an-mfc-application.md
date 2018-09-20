---
title: 'Vorgehensweise: Laden einer Menübandressource aus einer MFC-Anwendung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1643989a96a9003847fb53de624bff12cd51cd88
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434289"
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>Gewusst wie: Laden einer Menübandressource aus einer MFC-Anwendung

Um die menübandressource in Ihrer Anwendung verwenden möchten, ändern Sie die Anwendung die menübandressource laden.

### <a name="to-load-a-ribbon-resource"></a>Beim Laden einer menübandressource

1. Deklarieren Sie die `Ribbon Control` -Objekt in der `CMainFrame` Klasse.

```
    CMFCRibbonBar m_wndRibbonBar;
```

1. In `CMainFrame::OnCreate`, erstellen und Initialisieren des Menüband-Steuerelements.

```
    if (!m_wndRibbonBar.Create (this))
{
    return -1;
}

    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))
{
    return -1;
}
```

## <a name="see-also"></a>Siehe auch

[Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)

