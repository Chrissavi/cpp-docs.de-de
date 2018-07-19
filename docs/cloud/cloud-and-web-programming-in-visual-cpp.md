---
title: Cloud- und Web-Programmierung in Visual C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-azure
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 360404530df8d07a3cd8fc35654c0c9563ae29fe
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412399"
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Cloud- und Webprogrammierung in Visual C++

In C++ haben Sie mehrere Optionen, um eine Verbindung mit dem Web und der Cloud herzustellen.

## <a name="cloud-programming-options"></a>Cloud-Programmierung Optionen

- [Microsoft Azure Mobile Services](http://www.windowsazure.com/develop/mobile/)

   Stellt systemeigene APIs, die Sie in die universelle Windows-Plattform (UWP) oder Windows desktop-apps verwenden können, für die Verbindung mit Windows Azure Mobile Services bereit. Obwohl die meisten Beispiele auf der Website in C# geschrieben sind, können Sie auch C++ verwenden. Weitere Informationen finden Sie im Schnellstart zum [Hinzufügen eines mobilen Diensts mit C++](http://msdn.microsoft.com/library/windows/apps/dn263181.aspx).

- [Microsoft Azure-Speicherclientbibliothek für C++](https://blogs.msdn.microsoft.com/windowsazurestorage/2015/04/29/microsoft-azure-storage-client-library-for-c-v1-0-0-general-availability/)

   Die Azure-Speicherclientbibliothek für C++ bietet eine umfassende API zum Arbeiten mit Azure-Speicher, einschließlich, aber nicht beschränkt auf die folgenden Möglichkeiten:

  - Erstellen, lesen, löschen und Auflisten von Blob-Containern, Tabellen und Warteschlangen.
  - Erstellen Sie, lesen Sie, löschen Sie, kopieren und Auflisten von Blobs plus lesen und Schreiben von Blob-Bereiche.
  - INSERT-, DELETE-, Replace, Merge und Abfragen von Entitäten in einer Azure-Tabelle.
  - In die Warteschlange einreihen und Entfernen von Nachrichten in einer Azure-Warteschlange.
  - Verzögert auflisten, Container, Blobs, Tabellen und Warteschlangen und verzögert Abfragen von Entitäten

- [OneDrive-API](https://dev.onedrive.com/README.htm)

   Die OneDrive-API bietet eine Reihe von HTTP-Diensten verbinden Sie Ihre Anwendung auf Dateien und Ordner in Office 365 und SharePoint Server 2016.

- [C++ REST SDK (Codename „Casablanca“)](https://github.com/Microsoft/cpprestsdk)

   Stellt eine moderne, plattformübergreifende und asynchrone API für die Interaktion mit REST-Dienste bereit.

  - Ausführen von REST-Aufrufe für alle HTTP-Server mit integrierter Unterstützung für JSON-Dokument analysieren und Serialisierung
  - Unterstützt OAuth-1 und 2, einschließlich eines Listeners lokalen umleiten
  - Verbindungen Sie Websockets für Remotedienste
  - Ein vollständig asynchrones Task API anhand der PPL, z. B. eine integrierte threadpool

   Unterstützt die Windows-Desktop (7 und höher), Windows Server (2012 +), universelle Windows-Plattform, Linux, OS x, Android und iOS. 

- [Windows::Web::Http::HttpClient](https://msdn.microsoft.com/en-us/library/windows/apps/windows.web.http.httpclient.aspx)

   Eine Windows-Runtime-HTTP-Clientklasse, die in der .NET Framework-Klasse des gleichen Namens im System.Web-Namespace modelliert ist. `HttpClient` unterstützt vollständig den asynchronen Upload und Download über HTTP und Pipelinefilter, die das Einfügen von benutzerdefinierten HTTP-Handlern in die Pipeline ermöglichen. Das Windows SDK umfasst Beispielfilter für gemessene Netzwerke, OAuth-Authentifizierung und mehr. Für apps, nur universelle Windows-Plattform abzielen, empfehlen wir die Verwendung der `Windows::Web:HttpClient` Klasse. 

- [IXMLHTTPRequest2-Schnittstelle](http://msdn.microsoft.com/library/windows/apps/hh831151.aspx)

   Bietet eine systemeigene COM-Schnittstelle, dass Sie in Windows-Runtime-apps oder Windows-desktop-apps verwenden können, über HTTP eine Verbindung mit dem Internet und Get-, PUT- und andere HTTP-Befehle auszugeben. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML-HTTP-Anforderungen](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md).

- [Windows Internet (WinInet)](http://msdn.microsoft.com/library/windows/desktop/aa385331\(v=vs.85\).aspx)

   Eine Windows-API, die Sie in Windows-Desktop-Apps verwenden können, um eine Verbindung mit dem Internet herzustellen.

## <a name="see-also"></a>Siehe auch

[Visual C++](../visual-cpp-in-visual-studio.md) <br/>
[Netzwerke und Webdienste](/windows/uwp/networking/)
