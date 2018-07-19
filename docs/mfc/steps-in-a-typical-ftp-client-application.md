---
title: Die Schritte in einer Typischen FTP-Clientanwendung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], FTP table
- FTP (File Transfer Protocol)
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fe5a55afda9e77db6e8baddd68c09f4250071bb
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951200"
---
# <a name="steps-in-a-typical-ftp-client-application"></a>Schritte in einer typischen FTP-Clientanwendung
Erstellt von eine typischen FTP-Clientanwendung eine [CInternetSession](../mfc/reference/cinternetsession-class.md) und ein [CFtpConnection](../mfc/reference/cftpconnection-class.md) Objekt. Beachten Sie, dass diese MFC-WinInet-Klassen nicht tatsächlich der Einstellungen für den Proxy gesteuert. IIS ist.  
  
 Darüber hinaus finden Sie in folgenden Knowledge Base-Artikeln:  
  
-   So wird's gemacht: FTP mit CERN basierenden Proxy mit WinInet API (Artikel-ID: Q166961)  
  
-   Beispiel: FTP mit CERN-basierte Kennwort-geschützt Proxy (Artikel-ID: Q216214)  
  
-   Internetdienste-Manager kann keine installierten Proxydienste anzeigen (Artikel-ID: Q216802)  
  
 Die folgende Tabelle zeigt die Schritte, dass Sie möglicherweise in einer typischen FTP-Client-Anwendung ausführen.  
  
|Ihr Ziel|Die Aktion|Effekte|  
|---------------|----------------------|-------------|  
|Eine FTP-Sitzung zu starten.|Erstellen einer [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|WinInet initialisiert, und eine Verbindung mit dem Server her.|  
|Verbinden Sie mit einem FTP-Server.|Verwendung [CInternetSession:: GetFTPConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Gibt eine [CFtpConnection](../mfc/reference/cftpconnection-class.md) Objekt.|  
|Ändern Sie in einer neuen FTP-Verzeichnis auf dem Server.|Verwendung [CFtpConnection:: SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Ändert das Verzeichnis, das Sie gerade auf dem Server verbunden sind.|  
|Suchen Sie die erste Datei in das FTP-Verzeichnis.|Verwendung [CFtpFileFind:: FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|Sucht die erste Datei an. Gibt "false" zurück, wenn keine Dateien gefunden werden.|  
|Suchen Sie die nächste Datei im FTP-Verzeichnis.|Verwendung [CFtpFileFind:: FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Sucht die nächste Datei. Gibt "false" zurück, wenn die Datei nicht gefunden wird.|  
|Öffnen Sie die Datei, die vom gefundenen `FindFile` oder `FindNextFile` zum Lesen oder schreiben.|Verwendung [CFtpConnection:: OpenFile](../mfc/reference/cftpconnection-class.md#openfile), mit dem Dateinamen zurückgegebenes [FindFile](../mfc/reference/cftpfilefind-class.md#findfile) oder [FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Öffnet die Datei auf dem Server zum Lesen oder schreiben. Gibt eine [CInternetFile](../mfc/reference/cinternetfile-class.md) Objekt.|  
|Lesen oder Schreiben in die Datei.|Verwendung [CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read) oder [CInternetFile:: Write](../mfc/reference/cinternetfile-class.md#write).|Liest oder schreibt die angegebene Anzahl von Bytes, die unter Verwendung eines Puffers an, das Sie angeben.|  
|Behandeln von Ausnahmen|Verwenden der [CInternetException](../mfc/reference/cinternetexception-class.md) Klasse.|Verarbeitet alle common Internet Ausnahmetypen an.|  
|Die FTP-Sitzung zu beenden.|Löschen Sie die [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|Automatisch bereinigt Handles von offenen Dateien und Verbindungen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)   
 [Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
