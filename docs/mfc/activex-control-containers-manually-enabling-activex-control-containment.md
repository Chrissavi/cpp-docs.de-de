---
title: 'ActiveX-Steuerelementcontainer: Manuelles Aktivieren von ActiveX-Steuerelementcontainern | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fde0ee4dc740826c9efdf7b86cd2f021699f8820
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339890"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX-Steuerelementcontainer: Manuelles Aktivieren von ActiveX-Steuerelementcontainern
Wenn Sie die ActiveX-Steuerelemente unterstützen nicht aktiviert haben, wenn Sie die MFC-Anwendung-Assistent verwendet, um Ihre Anwendung zu generieren, müssen Sie diese Unterstützung manuell hinzufügen. Dieser Artikel beschreibt das Verfahren zum manuellen Hinzufügen von ActiveX-Steuerelementcontainern für eine vorhandene OLE-Container-Anwendung. Wenn Sie im Voraus wissen, dass Sie in der OLE-Container ActiveX-Steuerelemente unterstützen möchten, finden Sie im Artikel [Erstellen eines MFC-ActiveX-Steuerelementcontainers](../mfc/reference/creating-an-mfc-activex-control-container.md).  
  
> [!NOTE]
>  In diesem Artikel verwendet eine Dialogfeldern basierende ActiveX-Steuerelementcontainer-Projekt mit dem Namen Container und ein eingebettetes Steuerelement mit dem Namen Circ als Beispiele in den Prozeduren und den Code.  
  
 Um die ActiveX-Steuerelemente unterstützen, müssen Sie eine Codezeile auf zwei Dateien des Projekts hinzufügen.  
  
-   Ändern des Hauptdialogfelds `InitInstance` -Funktion (im CONTAINER gefunden. CPP) vom MFC-Anwendungs-Assistenten, die einen Aufruf an [AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer), wie im folgenden Beispiel:  
  
     [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]  
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]  
  
-   Fügen Sie Folgendes hinzu STDAFX Ihres Projekts ein. H-Headerdatei:  
  
     [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]  
  
 Nachdem Sie diese Schritte abgeschlossen haben, erstellen Sie Ihr Projekt durch Klicken auf Neu **erstellen** auf die **erstellen** Menü.  
  
## <a name="see-also"></a>Siehe auch  
 [ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)

