---
title: Ausnahmebehandlung in MFC
ms.date: 11/04/2016
helpviewer_keywords:
- DAO [MFC], exceptions
- assertions [MFC], When to use exceptions
- exception handling [MFC], MFC
- resource allocation exception
- resources [MFC], allocating
- keywords [MFC], exception handling
- errors [MFC], detected by assertions
- ODBC exceptions [MFC]
- serialization [MFC], exceptions
- Automation [MFC], exceptions
- exception macros [MFC]
- predefined exceptions [MFC]
- C++ exception handling [MFC], enabling
- C++ exception handling [MFC], MFC applications
- requests for unsupported services [MFC]
- database exceptions [MFC]
- archive exceptions [MFC]
- MFC, exceptions
- C++ exception handling [MFC], types of
- macros [MFC], exception handling
- abnormal program execution [MFC]
- OLE exceptions [MFC], MFC exception handling
- error handling [MFC], exceptions and
- class libraries [MFC], exception support
- exceptions [MFC], MFC macros vs. C++ keywords
- memory [MFC], out-of-memory exceptions
- Windows [MFC], resource allocation exceptions
- macros [MFC], MFC exception macros
- function calls [MFC], results
- out-of-memory exceptions [MFC]
ms.assetid: 0926627d-2ba7-44a6-babe-d851a4a2517c
ms.openlocfilehash: e8c0f1feba566ef9b961edcfacb9124830f9851d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508618"
---
# <a name="exception-handling-in-mfc"></a>Ausnahmebehandlung in MFC

In diesem Artikel werden die in MFC verfügbaren Mechanismen zur Ausnahmebehandlung erläutert. Es stehen zwei Mechanismen zur Verfügung:

- C++Ausnahmen, verfügbar in MFC, Version 3,0 und höher

- Die MFC-Ausnahme Makros, die in den MFC-Versionen 1,0 und höher verfügbar sind.

Wenn Sie eine neue Anwendung mit MFC schreiben, sollten Sie den C++ -Mechanismus verwenden. Sie können den Makro basierten Mechanismus verwenden, wenn die vorhandene Anwendung diesen Mechanismus bereits ausgiebig verwendet.

Sie können vorhandenen Code problemlos konvertieren, um C++ Ausnahmen anstelle der MFC-Ausnahme Makros zu verwenden. Die Vorteile der Code-und Richtlinien für diese Vorgehensweise werden im Artikel [Ausnahmen beschrieben: Die Umstellung von MFC-](../mfc/exceptions-converting-from-mfc-exception-macros.md)Ausnahme Makros.

Wenn Sie bereits eine Anwendung mit den MFC-Ausnahme Makros entwickelt haben, können Sie diese Makros im vorhandenen Code weiterhin verwenden, während Sie C++ Ausnahmen im neuen Code verwenden. Der Artikel [Ausnahmen: Änderungen an Ausnahme Makros in Version 3,0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) bieten Richtlinien dafür.

> [!NOTE]
>  Um die C++ Ausnahmebehandlung im Code zu aktivieren, wählen C++ Sie im Dialogfeld [Eigenschaften Seiten](../build/reference/property-pages-visual-cpp.md) des Projekts auf derC++ Seite Codegenerierung die Option Ausnahmen aktivieren aus, oder verwenden Sie die [/EHsc](../build/reference/eh-exception-handling-model.md) -Compileroption.

In diesem Artikel werden die folgenden Themen behandelt:

- [Verwendungszwecke von Ausnahmen](#_core_when_to_use_exceptions)

- [Unterstützung für MFC-Ausnahmen](#_core_mfc_exception_support)

- [Weitere Informationen zu Ausnahmen](#_core_further_reading_about_exceptions)

##  <a name="_core_when_to_use_exceptions"></a>Verwendungszwecke von Ausnahmen

Es können drei Kategorien von Ergebnissen auftreten, wenn eine Funktion während der Programmausführung aufgerufen wird: normale Ausführung, fehlerhafte Ausführung oder ungewöhnliche Ausführung. Jede Kategorie wird unten beschrieben.

- Normale Ausführung

   Die Funktion kann normal ausgeführt werden und zurückgeben. Einige Funktionen geben dem Aufrufer einen Ergebniscode zurück, der das Ergebnis der Funktion angibt. Die möglichen Ergebnis Codes sind für die Funktion streng definiert und stellen den Bereich möglicher Ergebnisse der Funktion dar. Der Ergebniscode kann auf Erfolg oder Fehler hinweisen oder sogar auf eine bestimmte Art von Fehlern hindeuten, die innerhalb des normalen Bereichs von Erwartungen liegt. Beispielsweise kann eine File-Status-Funktion einen Code zurückgeben, der angibt, dass die Datei nicht vorhanden ist. Beachten Sie, dass der Begriff "Fehlercode" nicht verwendet wird, da ein Ergebniscode eines von vielen erwarteten Ergebnissen darstellt.

- Fehlerhafte Ausführung

   Der Aufrufer hat einen Fehler beim Übergeben von Argumenten an die Funktion oder die Funktion in einem ungeeigneten Kontext aufruft. Diese Situation verursacht einen Fehler und sollte bei der Programmentwicklung durch eine-Übersetzung erkannt werden. (Weitere Informationen zu Assertionen finden Sie unter [CC++ /](/visualstudio/debugger/c-cpp-assertions)Assertionen.)

- Ungewöhnliche Ausführung

   Die ungewöhnliche Ausführung umfasst Situationen, in denen Bedingungen außerhalb der Programmsteuerung, wie z. b. wenig Arbeitsspeicher oder e/a-Fehler, das Ergebnis der Funktion beeinflussen. Ungewöhnliche Situationen sollten durch abfangen und Auslösen von Ausnahmen behandelt werden.

Die Verwendung von Ausnahmen eignet sich besonders für die ungewöhnliche Ausführung.

##  <a name="_core_mfc_exception_support"></a>Unterstützung für MFC-Ausnahmen

Unabhängig davon, ob C++ Sie die Ausnahmen direkt verwenden oder die MFC-Ausnahme Makros verwenden, verwenden Sie die `CException` [CException-Klasse](../mfc/reference/cexception-class.md) oder von abgeleitete Objekte, die vom Framework oder von der Anwendung ausgelöst werden können.

Die folgende Tabelle zeigt die vordefinierten Ausnahmen, die von MFC bereitgestellt werden.

|Ausnahmeklasse|Bedeutung|
|---------------------|-------------|
|[CMemoryException-Klasse](../mfc/reference/cmemoryexception-class.md)|Nicht genügend Arbeitsspeicher|
|[CFileException-Klasse](../mfc/reference/cfileexception-class.md)|Datei Ausnahme|
|[CArchiveException-Klasse](../mfc/reference/carchiveexception-class.md)|Archiv-/Serialisierungsausnahme|
|[CNotSupportedException-Klasse](../mfc/reference/cnotsupportedexception-class.md)|Antwort auf Anforderung für nicht unterstützten Dienst|
|[CResourceException-Klasse](../mfc/reference/cresourceexception-class.md)|Windows-Ressourcen Zuordnungs Ausnahme|
|[CDaoException-Klasse](../mfc/reference/cdaoexception-class.md)|Daten Bank Ausnahmen (DAO-Klassen)|
|[CDBException-Klasse](../mfc/reference/cdbexception-class.md)|Daten Bank Ausnahmen (ODBC-Klassen)|
|[COleException-Klasse](../mfc/reference/coleexception-class.md)|OLE-Ausnahmen|
|[COleDispatchException-Klasse](../mfc/reference/coledispatchexception-class.md)|Dispatch-Ausnahmen (Automation)|
|[CUserException-Klasse](../mfc/reference/cuserexception-class.md)|Eine Ausnahme, die den Benutzer mit einem Meldungs Feld warnt und dann eine generische [CException-Klasse](../mfc/reference/cexception-class.md) auslöst.|

> [!NOTE]
>  MFC unterstützt C++ sowohl Ausnahmen als auch MFC-Ausnahme Makros. MFC unterstützt Windows NT-strukturierte Ausnahmehandler (SEH) nicht direkt, wie unter [strukturierte Ausnahmebehandlung](/windows/win32/debug/structured-exception-handling)erläutert.

##  <a name="_core_further_reading_about_exceptions"></a>Weitere Informationen zu Ausnahmen

In den folgenden Artikeln wird die Verwendung der MFC-Bibliothek für die Ausnahme Übergabe erläutert:

- [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md)

- [Ausnahmen: Untersuchen von Ausnahmeinhalten](../mfc/exceptions-examining-exception-contents.md)

- [Ausnahmen: Freigeben von Objekten in Ausnahmen](../mfc/exceptions-freeing-objects-in-exceptions.md)

- [Ausnahmen: Auslösen von Ausnahmen in eigenen Funktionen](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)

- [Ausnahmen: Datenbankausnahmen](../mfc/exceptions-database-exceptions.md)

- [Ausnahmen: OLE-Ausnahmen](../mfc/exceptions-ole-exceptions.md)

In den folgenden Artikeln werden die MFC-Ausnahme Makros C++ mit den Ausnahme Schlüsselwörtern verglichen und erläutert, wie Sie Ihren Code anpassen können:

- [Ausnahmen: Änderungen für Ausnahmemakros in Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)

- [Ausnahmen: Umwandeln von MFC-Ausnahmemakros](../mfc/exceptions-converting-from-mfc-exception-macros.md)

- [Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>Siehe auch

[C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)<br/>
[Gewusst wie: Erstellen eigener benutzerdefinierter Ausnahme Klassen](https://go.microsoft.com/fwlink/p/?linkid=128045)
