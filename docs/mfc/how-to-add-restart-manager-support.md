---
title: 'Vorgehensweise: Hinzufügen von Unterstützung für Neustart-Manager'
ms.date: 11/04/2016
helpviewer_keywords:
- Restart manager [MFC]
- C++, application crash support
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
ms.openlocfilehash: 23f860c43c63e3153f4b87f8eaf05d61709af82f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389527"
---
# <a name="how-to-add-restart-manager-support"></a>Vorgehensweise: Hinzufügen von Unterstützung für Neustart-Manager

Der Neustart-Manager ist ein Feature, das Visual Studio für Windows Vista oder höher hinzugefügt. Mit dem Neustart-Manager wird der Anwendung Unterstützung hinzugefügt, wenn sie unerwartet geschlossen oder neu gestartet wird. Das Verhalten des Neustart-Managers hängt vom Typ Ihrer Anwendung ab. Ist Ihre Anwendung ein Dokument-Editor, wird der Anwendung durch den Neustart-Manager ermöglicht, den Status und den Inhalt jedes geöffneten Dokuments automatisch zu speichern, und der Neustart-Manager startet Ihre Anwendung nach einem unerwarteten Schließen neu. Ist Ihre Anwendung kein Dokument-Editor, wird die Anwendung vom Neustart-Manager neu gestartet, dieser kann den Status der Anwendung jedoch nicht standardmäßig speichern.

Nach dem Neustart wird von der Anwendung ein Aufgabendialogfeld angezeigt, wenn die Anwendung eine Unicode-Anwendung ist. Wenn sie eine ANSI-Anwendung ist, zeigt die Anwendung ein Windows-Meldungsfeld an. An diesem Punkt wählt der Benutzer aus, ob die automatisch gespeicherten Dokumente wiederhergestellt werden sollen. Wenn der Benutzer die automatisch gespeicherten Dokumente nicht wiederherstellt, werden die temporären Dateien vom Neustart-Manager verworfen.

> [!NOTE]
>  Sie können das Standardverhalten des Neustart-Managers hinsichtlich Speichern von Daten und Neustarten der Anwendung überschreiben.

Standardmäßig unterstützen MFC-Anwendungen, die mit der Projekt-Assistent in Visual Studio erstellt den Neustart-Manager aus, wenn die Anwendungen auf einem Computer ausgeführt werden, die Windows Vista oder höher verwendet wird. Wenn Sie nicht möchten, dass Ihre Anwendung den Neustart-Manager unterstützt, können Sie den Neustart-Manager im neuen Projekt-Assistenten deaktivieren.

### <a name="to-add-support-for-the-restart-manager-to-an-existing-application"></a>So fügen Sie einer vorhandenen Anwendung Unterstützung für den Neustart-Manager hinzu

1. Öffnen Sie eine vorhandene MFC-Anwendung in Visual Studio.

1. Öffnen Sie die Quelldatei für Ihre Hauptanwendung. Standardmäßig ist dies die CPP-Datei, die denselben Namen wie Ihre Anwendung hat. Die Hauptanwendungsquelldatei für „MeinProjekt“ ist beispielsweise „MeinProjekt.cpp“.

1. Suchen Sie nach dem Konstruktor für Ihre Hauptanwendung. Hat Ihr Projekt beispielsweise den Namen „MeinProjekt“, ist `CMyProjectApp::CMyProjectApp()`der Konstruktor.

1. Fügen Sie dem Konstruktor die folgende Codezeile hinzu.

```
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;
```

1. Stellen Sie sicher, dass die `InitInstance` Methodenaufrufe von Ihrer Anwendung das übergeordnete Element `InitInstance` Methode: [CWinApp:: InitInstance](../mfc/reference/cwinapp-class.md#initinstance) oder `CWinAppEx::InitInstance`. Die `InitInstance` Methode ist verantwortlich für die Überprüfung der *M_dwRestartManagerSupportFlags* Parameter.

1. Kompilieren Sie Ihre Anwendung, und führen Sie sie aus.

## <a name="see-also"></a>Siehe auch

[CDataRecoveryHandler-Klasse](../mfc/reference/cdatarecoveryhandler-class.md)<br/>
[CWinApp::m_dwRestartManagerSupportFlags](../mfc/reference/cwinapp-class.md#m_dwrestartmanagersupportflags)<br/>
[CWinApp-Klasse](../mfc/reference/cwinapp-class.md)<br/>
[CWinApp::m_nAutosaveInterval](../mfc/reference/cwinapp-class.md#m_nautosaveinterval)<br/>
[CDocument::OnDocumentEvent](../mfc/reference/cdocument-class.md#ondocumentevent)
