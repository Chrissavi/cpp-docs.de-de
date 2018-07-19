---
title: 'Vorgehensweise: Steuern der Aufrufeigenschaften und Methoden des Windows Forms | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- method calls, Windows Forms
- calling methods, Windows Forms control
- calling properties, Windows Forms control
- Windows Forms controls [C++], methods
- calling properties
- Windows Forms controls [C++], properties
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 206c7bc89ce2bbc48beb1d95f3929ea4694fce20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131354"
---
# <a name="how-to-call-properties-and-methods-of-the-windows-forms-control"></a>Gewusst wie: Aufrufen von Ereignissen und Methoden des Windows Forms-Steuerelements
Da [CWinFormsView::](../mfc/reference/cwinformsview-class.md#getcontrol) gibt einen Zeiger auf <xref:System.Windows.Forms.Control?displayProperty=fullName>, und nicht um einen Zeiger auf `WindowsControlLibrary1::UserControl1`, ist es ratsam, Hinzufügen eines Mitglieds des Steuerelementtyps für Benutzer und ihre Initialisierung in [iView:: OnInitialUpdate ](../mfc/reference/iview-interface.md#oninitialupdate). Nachdem Sie aufrufen können, Methoden und Eigenschaften, die mit `m_ViewControl`.  
  
 In diesem Thema wird vorausgesetzt, Sie haben zuvor abgeschlossen [Vorgehensweise: Erstellen des Benutzersteuerelements und Host in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) und [Vorgehensweise: Erstellen des Benutzersteuerelements und MDI Hostansicht](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
### <a name="to-create-the-mfc-host-application"></a>So erstellen Sie die MFC-Hostanwendung  
  
1.  Öffnen Sie die MFC-Anwendung, die Sie erstellt, im haben [Vorgehensweise: Erstellen des Benutzersteuerelements und MDI Hostansicht](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
2.  Fügen Sie die folgende Zeile Abschnitt Öffentliche überschreibt die `CMFC02View` -Klassendeklaration in MFC02View.h.  
  
     `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`  
  
3.  Fügen Sie eine Außerkraftsetzung für OnInitialupdate hinzu.  
  
     Anzeigen der **Eigenschaften** Fenster (F4). In **Klassenansicht** (STRG + UMSCHALT + C), wählen Sie CMFC02View-Klasse. In der **Eigenschaften** Fenster, wählen Sie das Symbol für Außerkraftsetzungen. Scoll die Dropdownliste OnInitialUpdate. Klicken Sie auf die Dropdown-Liste, und wählen \<hinzufügen >. In MFC02View.cpp. Stellen Sie sicher, dass der Text der OnInitialUpdate-Funktion wie folgt:  
  
    ```  
    CWinFormsView::OnInitialUpdate();  
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());  
    m_ViewControl->textBox1->Text = gcnew System::String("hi");  
    ```  
  
4.  Erstellen Sie das Projekt, und führen Sie es aus.  
  
     Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Auf der **Debuggen** Menü klicken Sie auf **Starten ohne Debuggen**.  
  
     Beachten Sie, dass das Textfeld jetzt initialisiert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten eines Windows Forms-Benutzersteuerelements als MFC-Ansicht](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)