---
title: 'Gewusst wie: Hinzufügen von Unterstützung für den Neustart-Manager'
ms.date: 11/04/2016
helpviewer_keywords:
- Restart manager [MFC]
- C++, application crash support
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
ms.openlocfilehash: 848cb3bb52ae13eb1b7798126becd13384fddeb6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625650"
---
# <a name="how-to-add-restart-manager-support"></a>Gewusst wie: Hinzufügen von Unterstützung für den Neustart-Manager

Der Neustart-Manager ist ein Feature, das Visual Studio für Windows Vista oder spätere Betriebssysteme hinzugefügt wird. Mit dem Neustart-Manager wird der Anwendung Unterstützung hinzugefügt, wenn sie unerwartet geschlossen oder neu gestartet wird. Das Verhalten des Neustart-Managers hängt vom Typ Ihrer Anwendung ab. Ist Ihre Anwendung ein Dokument-Editor, wird der Anwendung durch den Neustart-Manager ermöglicht, den Status und den Inhalt jedes geöffneten Dokuments automatisch zu speichern, und der Neustart-Manager startet Ihre Anwendung nach einem unerwarteten Schließen neu. Ist Ihre Anwendung kein Dokument-Editor, wird die Anwendung vom Neustart-Manager neu gestartet, dieser kann den Status der Anwendung jedoch nicht standardmäßig speichern.

Nach dem Neustart wird von der Anwendung ein Aufgabendialogfeld angezeigt, wenn die Anwendung eine Unicode-Anwendung ist. Wenn sie eine ANSI-Anwendung ist, zeigt die Anwendung ein Windows-Meldungsfeld an. An diesem Punkt wählt der Benutzer aus, ob die automatisch gespeicherten Dokumente wiederhergestellt werden sollen. Wenn der Benutzer die automatisch gespeicherten Dokumente nicht wiederherstellt, werden die temporären Dateien vom Neustart-Manager verworfen.

> [!NOTE]
> Sie können das Standardverhalten des Neustart-Managers hinsichtlich Speichern von Daten und Neustarten der Anwendung überschreiben.

Standardmäßig unterstützen MFC-Anwendungen, die mit dem Projekt-Assistenten in Visual Studio erstellt wurden, den Neustart-Manager, wenn die Anwendungen auf einem Computer ausgeführt werden, auf dem ein Betriebssystem Windows Vista oder höher ausgeführt wird. Wenn Sie nicht möchten, dass Ihre Anwendung den Neustart-Manager unterstützt, können Sie den Neustart-Manager im neuen Projekt-Assistenten deaktivieren.

### <a name="to-add-support-for-the-restart-manager-to-an-existing-application"></a>So fügen Sie einer vorhandenen Anwendung Unterstützung für den Neustart-Manager hinzu

1. Öffnen Sie in Visual Studio eine vorhandene MFC-Anwendung.

1. Öffnen Sie die Quelldatei für Ihre Hauptanwendung. Standardmäßig ist dies die CPP-Datei, die denselben Namen wie Ihre Anwendung hat. Die Hauptanwendungsquelldatei für „MeinProjekt“ ist beispielsweise „MeinProjekt.cpp“.

1. Suchen Sie nach dem Konstruktor für Ihre Hauptanwendung. Hat Ihr Projekt beispielsweise den Namen „MeinProjekt“, ist `CMyProjectApp::CMyProjectApp()`der Konstruktor.

1. Fügen Sie dem Konstruktor die folgende Codezeile hinzu.

```
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;
```

1. Stellen Sie sicher, dass in der `InitInstance` -Methode Ihrer Anwendung deren übergeordnete `InitInstance` -Methode aufgerufen wird: [CWinApp::InitInstance](reference/cwinapp-class.md#initinstance) oder `CWinAppEx::InitInstance`hinzugefügt wurde. Die- `InitInstance` Methode ist dafür verantwortlich, den *m_dwRestartManagerSupportFlags* -Parameter zu überprüfen.

1. Kompilieren Sie Ihre Anwendung, und führen Sie sie aus.

## <a name="see-also"></a>Siehe auch

[CDataRecoveryHandler-Klasse](reference/cdatarecoveryhandler-class.md)<br/>
[CWinApp:: m_dwRestartManagerSupportFlags](reference/cwinapp-class.md#m_dwrestartmanagersupportflags)<br/>
[CWinApp-Klasse](reference/cwinapp-class.md)<br/>
[CWinApp:: m_nAutosaveInterval](reference/cwinapp-class.md#m_nautosaveinterval)<br/>
[CDocument:: ondocumentevent](reference/cdocument-class.md#ondocumentevent)
