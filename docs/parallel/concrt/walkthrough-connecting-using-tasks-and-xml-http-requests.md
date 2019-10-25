---
title: 'Exemplarische Vorgehensweise: Herstellen einer Verbindung mithilfe von Aufgaben und XML-HTTP-Anforderungen'
ms.date: 04/25/2019
helpviewer_keywords:
- connecting to web services, UWP apps [C++]
- IXMLHTTPRequest2 and tasks, example
- IXHR2 and tasks, example
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
ms.openlocfilehash: b11b56578cadc4b3bd037acf84014a718f9fad84
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "69512134"
---
# <a name="walkthrough-connecting-using-tasks-and-xml-http-requests"></a>Exemplarische Vorgehensweise: Herstellen einer Verbindung mithilfe von Aufgaben und XML-HTTP-Anforderungen

Dieses Beispiel zeigt, wie die [IXMLHTTPRequest2](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2) -und [IXMLHTTPRequest2Callback](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2callback) -Schnittstellen in Verbindung mit Aufgaben verwendet werden, um HTTP Get-und Post-Anforderungen an einen Webdienst in einer universelle Windows-Plattform-app (UWP) zu senden. Beim Kombinieren von `IXMLHTTPRequest2` mit Aufgaben können Sie Code schreiben, der mit anderen Aufgaben zusammen erstellt wird. Beispielsweise können Sie die Downloadaufgabe als Teil einer Kette von Aufgaben verwenden. Wenn Arbeit abgebrochen wird, kann die Downloadaufgabe auch weiterhin antworten.

> [!TIP]
>  Sie können das C++ Rest-SDK auch zum Ausführen von HTTP-Anforderungen aus einer UWP C++ -App verwenden, indem C++ Sie eine APP oder eine Desktop-App verwenden. Weitere Informationen finden [ C++ Sie unter Rest-SDK (Codename "Casablanca")](https://github.com/Microsoft/cpprestsdk).

Weitere Informationen zu Aufgaben finden Sie Unteraufgaben [Parallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Weitere Informationen zum Verwenden von Aufgaben in einer UWP-App finden Sie unter [asynchrone Programmierung in C++ ](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) und [Erstellen von asynchronen Vorgängen in C++ für UWP-apps](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).

Dieses Dokument erläutert zunächst, wie die `HttpRequest`-Klasse und unterstützende Klassen erstellt werden. Anschließend wird gezeigt, wie diese Klasse aus einer UWP-App verwendet wird C++ , die und XAML verwendet.

Ein Beispiel, in dem `IXMLHTTPRequest2` verwendet wird, aber keine Aufgaben verwendet [, finden Sie unter Schnellstart: Herstellen einer Verbindung mithilfe einer XML-HTTP](/previous-versions/windows/apps/hh770550\(v=win.10\))-Anforderung (IXMLHTTPRequest2).

> [!TIP]
>  `IXMLHTTPRequest2`und `IXMLHTTPRequest2Callback` sind die Schnittstellen, die wir für die Verwendung in einer UWP-App empfehlen. Darüber hinaus können Sie dieses Beispiel auch für die Verwendung in einer Desktop-App anpassen.

## <a name="prerequisites"></a>Erforderliche Komponenten

UWP-Unterstützung ist in Visual Studio 2017 und höher optional. Öffnen Sie die Visual Studio-Installer über das Windows-Startmenü, und wählen Sie die Version von Visual Studio aus, die Sie verwenden, um Sie zu installieren. Klicken Sie auf die Schaltfläche **ändern** , und vergewissern Sie sich, dass die Kachel **UWP Development** aktiviert ist. Stellen Sie sicher, dass unter **optionale Komponenten** die  **C++ Option UWP-Tools** aktiviert ist. Verwenden Sie v141 für Visual Studio 2017 oder v142 für Visual Studio 2019.

## <a name="defining-the-httprequest-httprequestbufferscallback-and-httprequeststringcallback-classes"></a>Definieren der HttpRequest-, HttpRequestBuffersCallback- und HttpRequestStringCallback-Klassen

Wenn Sie die `IXMLHTTPRequest2`-Schnittstelle verwenden, um Webanforderungen über HTTP zu erstellen, implementieren Sie die `IXMLHTTPRequest2Callback`-Schnittstelle, um die Serverantwort zu empfangen und auf andere Ereignisse zu reagieren. In diesem Beispiel werden die `HttpRequest`-Klasse zum Erstellen von Webanforderungen und die Klassen `HttpRequestBuffersCallback` und `HttpRequestStringCallback` zum Verarbeiten der Antworten definiert. Die `HttpRequestBuffersCallback`-Klasse und die `HttpRequestStringCallback`-Klasse unterstützen die `HttpRequest`-Klasse; Sie arbeiten im Anwendungscode nur mit der `HttpRequest`-Klasse.

Die `GetAsync`-Methode und die `PostAsync`-Methode der `HttpRequest`-Klasse ermöglichen Ihnen das Durchführen von HTTP-Anforderungen (GET, POST). Diese Methoden verwenden die `HttpRequestStringCallback`-Klasse, um die Serverantwort als Zeichenfolge zu lesen. Die `SendAsync`-Methode und die `ReadAsync`-Methode ermöglichen das Übertragen von umfangreichen Inhalten in Blöcken. Diese Methoden geben jeweils " [parallelcurrency:: Task](../../parallel/concrt/reference/task-class.md) " zurück, um den Vorgang darzustellen. Die `GetAsync`-Methode und die `PostAsync`-Methode generieren `task<std::wstring>`-Wert, wobei der `wstring`-Teil die Antwort des Servers darstellt. Die `SendAsync`-Methode und die `ReadAsync`-Methode generieren `task<void>`-Werte. Diese Aufgaben werden abgeschlossen, wenn die „Send“- und „Read“-Vorgänge abgeschlossen werden.

Da die `IXMLHTTPRequest2` Schnittstellen asynchron agieren, wird in diesem Beispiel " [parallelcurrency:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) " verwendet, um eine Aufgabe zu erstellen, die abgeschlossen wird, nachdem das Rückruf Objekt den Downloadvorgang abgeschlossen oder abgebrochen hat. Die `HttpRequest`-Klasse erstellt eine aufgabenbasierte Fortsetzung aus dieser Aufgabe, um das Endergebnis festzulegen. Die `HttpRequest`-Klasse verwendet eine aufgabenbasierte Fortsetzung, um sicherzustellen, dass die Fortsetzungsaufgabe ausgeführt wird, auch wenn die vorherige Aufgabe einen Fehler erzeugt oder abgebrochen wird. Weitere Informationen zu Task basierten Fortsetzungen finden Sie unter [Aufgaben Parallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md) .

Um ein Abbrechen zu unterstützen, verwenden die Klassen `HttpRequest`, `HttpRequestBuffersCallback` und `HttpRequestStringCallback` Abbruchtoken. Die `HttpRequestBuffersCallback` - `HttpRequestStringCallback` Klasse und die-Klasse verwenden die [parallelcurrency:: cancellation_token:: Register_callback](reference/cancellation-token-class.md#register_callback) -Methode, um das Aufgaben Abschluss Ereignis für die Reaktion auf den Abbruch zu aktivieren. Dieser Abbruchsrückruf bricht den Download ab. Weitere Informationen zum Abbruch finden Sie unter [Abbruch](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

#### <a name="to-define-the-httprequest-class"></a>So definieren Sie die HttpRequest-Klasse

1. Klicken Sie im Hauptmenü auf **Datei** > **neu** > **Projekt**. 

1. Verwenden Sie C++ die Vorlage **leere app (universelle Windows** -Vorlage), um ein leeres XAML-App-Projekt zu erstellen. In diesem Beispiel wird das Projekt `UsingIXMLHTTPRequest2`genannt.

1. Fügen Sie dem Projekt eine Headerdatei mit dem Namen "HttpRequest.h" und eine Quelldatei mit dem Namen "HttpRequest.cpp" hinzu.

1. Fügen Sie "pch.h" diesen Code hinzu:

   [!code-cpp[concrt-using-ixhr2#1](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_1.h)]

1. Fügen Sie "HttpRequest.h" diesen Code hinzu:

   [!code-cpp[concrt-using-ixhr2#2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_2.h)]

1. Fügen Sie "HttpRequest.cpp" diesen Code hinzu:

   [!code-cpp[concrt-using-ixhr2#3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_3.cpp)]

## <a name="using-the-httprequest-class-in-a-uwp-app"></a>Verwenden der HttpRequest-Klasse in einer UWP-App

In diesem Abschnitt wird veranschaulicht, wie `HttpRequest` die-Klasse in einer UWP-App verwendet wird. Die App enthält ein Eingabefeld, das eine URL-Ressource definiert, und Schaltflächen zum Durchführen von GET- und POST-Anforderungen und zum Abbrechen des aktuellen Vorgangs.

#### <a name="to-use-the-httprequest-class"></a>So verwenden Sie die HttpRequest-Klasse

1. Definieren Sie in "MainPage. XAML" das [StackPanel](/uwp/api/Windows.UI.Xaml.Controls.StackPanel) -Element wie folgt.

   [!code-xml[concrt-using-ixhr2#A1](../../parallel/concrt/codesnippet/xaml/walkthrough-connecting-using-tasks-and-xml-http-requests_4.xaml)]

2. In "MainPage.xaml.h" fügen Sie diese `#include`-Anweisung hinzu:

   [!code-cpp[concrt-using-ixhr2#A2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_5.h)]

3. Fügen Sie diese `private`-Membervariablen der `MainPage`-Klasse in "MainPage.xaml.h" hinzu:

   [!code-cpp[concrt-using-ixhr2#A3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_6.h)]

4. Deklarieren Sie in "MainPage.xaml.h" die `private`-Methode `ProcessHttpRequest`:

   [!code-cpp[concrt-using-ixhr2#A4](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_7.h)]

5. Fügen Sie "MainPage.xaml.cpp" diese `using`-Anweisungen hinzu:

   [!code-cpp[concrt-using-ixhr2#A5](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_8.cpp)]

6. Implementieren Sie in "MainPage.xaml.cpp" die Methoden `GetButton_Click`, `PostButton_Click` und `CancelButton_Click` aus der `MainPage`-Klasse.

   [!code-cpp[concrt-using-ixhr2#A6](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_9.cpp)]

   > [!TIP]
   > Wenn Ihre APP keine Unterstützung für den Abbruch benötigt, übergeben Sie " [parallelcurrency:: cancellation_token:: None](reference/cancellation-token-class.md#none) " an die-Methode und die `HttpRequest::GetAsync` - `HttpRequest::PostAsync` Methode.

1. Implementieren Sie die `MainPage::ProcessHttpRequest`-Methode in "MainPage.xaml.cpp".

   [!code-cpp[concrt-using-ixhr2#A7](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_10.cpp)]

8. `msxml6.lib`Geben SieindenProjekteigenschaftenunterLinker,Eingabe,und`shcore.lib` an.

Hier ist die ausgeführte App:

![Die Windows-Runtime APP wird ausgeführt](../../parallel/concrt/media/concrt_usingixhr2.png "Die Windows-Runtime APP wird ausgeführt") .

## <a name="next-steps"></a>Nächste Schritte

[Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

## <a name="see-also"></a>Siehe auch

[Aufgaben Parallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Abbruch in der PPL](cancellation-in-the-ppl.md)<br/>
[Asynchrone Programmierung inC++](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)<br/>
[Erstellen von asynchronen Vorgängen in C++ für UWP-Apps](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)<br/>
[Schnellstart: Herstellen einer Verbindung mithilfe der IXMLHTTPRequest2](/previous-versions/windows/apps/hh770550\(v=win.10\))
-Aufgaben Klasse (XML HTTP Request[) (Concurrency Runtime)](../../parallel/concrt/reference/task-class.md)<br/>
[task_completion_event-Klasse](../../parallel/concrt/reference/task-completion-event-class.md)
