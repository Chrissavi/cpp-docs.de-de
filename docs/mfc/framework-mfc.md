---
title: Framework (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- encapsulation [MFC], Win32 API
- MFC, application framework
- wrapper classes [MFC], explained
- Win32 [MFC], API encapsulation by MFC
- application framework [MFC], about MFC application framework
- APIs [MFC], encapsulation by MFC Win32
- encapsulation [MFC]
- Windows API [MFC], encapsulation by MFC
- encapsulated Win32 API [MFC]
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd75d29ce907b089d698c066e5a6cb41fcae3281
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344395"
---
# <a name="framework-mfc"></a>Framework (MFC)
Die Arbeit mit dem Framework für die Microsoft Foundation Class (MFC)-Bibliothek basiert größtenteils auf einige wichtigsten Berechtigungsklassen und verschiedene Visual C++-Tools. Einige Klassen kapseln einen großen Teil der Win32-Anwendungsprogrammierschnittstelle (API). Andere Klassen kapseln Anwendungskonzepte wie z. B. Dokumente, Ansichten und die Anwendung selbst. Weiterhin kapseln andere OLE-Features und Funktionen von ODBC und DAO-Datenzugriffs.  
  
 Beispielsweise wird die Win32 Konzept der Fenster von MFC-Klasse gekapselt `CWnd`. Das heißt, eine C++-Klasse aufgerufen `CWnd` kapselt, oder "dient als Wrapper für" der `HWND` -Handle, das ein Windows-Fenster darstellt. Ebenso-Klasse `CDialog` kapselt Win32-Dialogfelder.  
  
 Kapselung bedeutet, dass die C++-Klasse `CWnd`, enthält z. B. eine Membervariable des Typs `HWND`, und der Klassenmemberfunktionen zu kapseln, Aufrufe von Win32-Funktionen, akzeptieren ein `HWND` als Parameter. Der Klassenmemberfunktionen weisen in der Regel den gleichen Namen wie die Win32-Funktion, die sie kapseln.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SDI und MDI](../mfc/sdi-and-mdi.md)  
  
 [Dokumente, Ansichten und das Framework](../mfc/documents-views-and-the-framework.md)  
  
 [Assistenten und die Ressourcen-Editoren](../mfc/wizards-and-the-resource-editors.md)  
  
## <a name="in-related-sections"></a>In verwandten Abschnitten  
 [Erstellen im Framework](../mfc/building-on-the-framework.md)  
  
 [So ruft das Framework Ihren Code auf](../mfc/how-the-framework-calls-your-code.md)  
  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)  
  
 [Dokumentvorlagen und der Erstellungsvorgang für die Dokument-/Ansichtarchitektur](../mfc/document-templates-and-the-document-view-creation-process.md)  
  
 [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)  
  
 [Fensterobjekte](../mfc/window-objects.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
