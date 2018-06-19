---
title: Hinzufügen einer MFC-Klasse aus einer Typbibliothek | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 349d06d7fecb82af64fbf2d3b2ebe54689b3b292
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355115"
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>Hinzufügen einer MFC-Klasse aus einer Typbibliothek
Verwenden Sie diesen Assistenten zum Erstellen einer MFC-Klasse von einer Schnittstelle in einer Typbibliothek verfügbar. Sie können eine MFC-Klasse zum Hinzufügen ein [MFC-Anwendung](../../mfc/reference/creating-an-mfc-application.md), wird eine [MFC-DLL](../../mfc/reference/creating-an-mfc-dll-project.md), oder ein [MFC-ActiveX-Steuerelement](../../mfc/reference/creating-an-mfc-activex-control.md).  
  
> [!NOTE]
>  Sie müssen nicht das MFC-Projekt mit Automatisierung aktiviert, um das Hinzufügen einer Klasse aus einer Typbibliothek zu erstellen.  
  
 Eine Typbibliothek enthält eine binäre Beschreibung der Schnittstellen, die von einer Komponente, definieren die Methoden sowie ihre Parameter und Rückgabetypen verfügbar gemacht werden. Die Typbibliothek muss registriert werden, für die in angezeigt werden die **verfügbaren Typbibliotheken** Liste im Hinzufügen von Klassen aus der Typbibliothek-Assistenten. Finden Sie unter "In Distributed COM: Type-Bibliotheken und Language Integration" in der MSDN Library für Weitere Informationen.  
  
### <a name="to-add-an-mfc-class-from-a-type-library"></a>Hinzufügen eine MFC-Klasse aus einer Typbibliothek  
  
1.  In beiden **Projektmappen-Explorer** oder [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), mit der rechten Maustaste in des Namens des Projekts, dem Sie die Klasse hinzufügen möchten.  
  
2.  Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Klasse hinzufügen**.  
  
3.  In der [Klasse hinzufügen](../../ide/add-class-dialog-box.md) (Dialogfeld), klicken Sie im Bereich "Vorlagen" klicken Sie auf **MFC-Klasse aus der Typbibliothek**, und klicken Sie dann auf **öffnen** zum Anzeigen der [Hinzufügen von Klassen aus der Typbibliothek-Assistenten ](../../mfc/reference/add-class-from-typelib-wizard.md).  
  
 Im Assistenten können Sie mehr als eine Klasse in einer Typbibliothek hinzufügen. Ebenso können Sie Klassen aus mehr als eine Typbibliothek in einer einzelnen Assistenten-Sitzung hinzufügen.  
  
 Der Assistent erstellt eine MFC-Klasse abgeleitet [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md), für jede Schnittstelle, die Sie aus der ausgewählten Typbibliothek hinzufügen. `COleDispatchDriver` implementiert die Clientseite der OLE-Automatisierung.  
  
## <a name="see-also"></a>Siehe auch  
 [Automatisierungsclients](../../mfc/automation-clients.md)   
 [Automatisierungsclients: Verwenden von Typbibliotheken](../../mfc/automation-clients-using-type-libraries.md)

