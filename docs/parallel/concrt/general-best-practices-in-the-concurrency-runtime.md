---
title: Allgemein empfohlene Vorgehensweisen in der Concurrency Runtime
ms.date: 11/04/2016
helpviewer_keywords:
- Concurrency Runtime, general best practices
ms.assetid: ce5c784c-051e-44a6-be84-8b3e1139c18b
ms.openlocfilehash: e25011e2466d76c946cc55421ed228c8ea174161
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413917"
---
# <a name="general-best-practices-in-the-concurrency-runtime"></a>Allgemein empfohlene Vorgehensweisen in der Concurrency Runtime

Dieses Dokument beschreibt empfohlene Vorgehensweisen, die für mehrere Bereiche der Concurrency Runtime gelten.

##  <a name="top"></a> Abschnitte

Dieses Dokument enthält folgende Abschnitte:

- [Verwenden Sie nach Möglichkeit Konstrukte für kooperative Synchronisierung](#synchronization)

- [Vermeiden Sie langwierige Aufgaben, die nicht zurückgehalten werden](#yield)

- [Verwenden der Überzeichnung zum Offsetvorgänge an, die das Blockieren oder hohen Latenz](#oversubscription)

- [Verwenden Sie parallele Speicherverwaltungsfunktionen möglichst](#memory)

- [Verwenden Sie RAII zum Verwalten der Lebensdauer von Parallelitätsobjekten](#raii)

- [Keine Parallelitätsobjekte im globalen Gültigkeitsbereich erstellen](#global-scope)

- [Verwenden Sie keine Parallelitätsobjekte in freigegebenen Datensegmenten](#shared-data)

##  <a name="synchronization"></a> Verwenden Sie nach Möglichkeit Konstrukte für kooperative Synchronisierung

Die Concurrency Runtime stellt viele parallelitätssichere Konstrukte bereit, die kein externes Synchronisierungsobjekt erfordern. Z. B. die [Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) bietet-Klasse parallelitätssichere Anfügevorgänge und parallelitätssicheren Elementzugriff. In Fällen, in denen Sie exklusiven Zugriff auf eine Ressource benötigen, bietet die Laufzeit jedoch die [Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md), [Concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md), und [Parallelität :: Ereignis](../../parallel/concrt/reference/event-class.md) Klassen. Diese Typen weisen kooperatives Verhalten auf. Deshalb kann der Aufgabenplaner Verarbeitungsressourcen neu einem anderen Kontext zuteilen, während die erste Aufgabe auf Daten wartet. Verwenden Sie nach Möglichkeit diese Synchronisierungstypen statt anderer Synchronisierungsmechanismen, z. B. die von der Windows-API bereitgestellten Synchronisierungsmechanismen, die kein kooperatives Verhalten aufweisen. Weitere Informationen zu diesen Synchronisierungstypen und ein Codebeispiel finden Sie unter [Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md) und [Vergleich der Synchronisierungsdatenstrukturen mit der Windows-API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).

[[Nach oben](#top)]

##  <a name="yield"></a> Vermeiden Sie langwierige Aufgaben, die nicht zurückgehalten werden

Da sich der Taskplaner kooperativ verhält, stellt er keine Fairness zwischen Aufgaben bereit. Daher kann eine Aufgabe das Starten anderer Aufgaben verhindern. Dies ist zwar in manchen Fällen akzeptabel, kann jedoch in anderen Fällen Deadlocks oder Ressourcenmangel verursachen.

Im folgenden Beispiel übersteigt die Anzahl der ausgeführten Aufgaben die Anzahl der zugeteilten Verarbeitungsressourcen. Die erste Aufgabe wird nicht an den Taskplaner abgetreten, und daher wird die zweite Aufgabe erst gestartet, nachdem die erste Aufgabe beendet wurde.

[!code-cpp[concrt-cooperative-tasks#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_1.cpp)]

Dieses Beispiel erzeugt die folgende Ausgabe:

1: 250000000 1: 500000000 1: 750000000 1: 1000000000 2: 250000000 2: 500000000 2: 750000000 2: 1000000000

Es gibt mehrere Möglichkeiten, die Zusammenarbeit zwischen den beiden Aufgaben zu ermöglichen. Eine Möglichkeit besteht darin, eine Aufgabe mit langer Ausführungszeit gelegentlich an den Aufgabenplaner abzutreten. Das folgende Beispiel ändert die `task` aufzurufenden Funktion der [yield](reference/context-class.md#yield) Methode, um die Ausführung an den Aufgabenplaner ergeben, damit eine andere Aufgabe ausführen kann.

[!code-cpp[concrt-cooperative-tasks#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_2.cpp)]

Dieses Beispiel erzeugt die folgende Ausgabe:

```Output
1: 250000000
2: 250000000
1: 500000000
2: 500000000
1: 750000000
2: 750000000
1: 1000000000
2: 1000000000
```

Die `Context::Yield`-Methode gibt nur an einen anderen aktiven Thread des Planers, zu dem der aktuelle Thread gehört, an eine einfache Aufgabe oder an einen anderen Betriebssystemthread zurück. Diese Methode keine Arbeitsvorgänge zugunsten von arbeiten, die geplant wird, für die Ausführung im eine [Concurrency:: task_group](reference/task-group-class.md) oder [Concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) Objekt aber noch nicht gestartet.

Es gibt weitere Verfahren, die Zusammenarbeit zwischen Aufgaben mit langer Ausführungsdauer zu ermöglichen. Sie können eine große Aufgabe in kleinere Unteraufgaben aufteilen. Sie können auch Überzeichnung während einer langwierigen Aufgabe aktivieren. Durch Überzeichnung können Sie mehr Threads als die Anzahl der verfügbaren Hardwarethreads erstellen. Überzeichnung ist von besonderem Nutzen, wenn eine langwierige Aufgabe einen hohen Betrag an Wartezeit beinhaltet, z. B. das Lesen von Daten von einem Datenträger oder über eine Netzwerkverbindung. Weitere Informationen zu einfachen Aufgaben und Überzeichnung finden Sie unter [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

[[Nach oben](#top)]

##  <a name="oversubscription"></a> Verwenden der Überzeichnung zum Offsetvorgänge an, die das Blockieren oder hohen Latenz

Die Concurrency Runtime stellt Synchronisierungsprimitive, z. B. [Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md), mit denen Aufgaben kooperative Blockieren und zurückhalten. Wenn eine Aufgabe kooperativ blockiert oder zurückgehalten wird, kann der Taskplaner Verarbeitungsressourcen neu einem anderen Kontext zuteilen, während die erste Aufgabe auf Daten wartet.

Es gibt Fälle, in denen Sie den von der Concurrency Runtime bereitgestellten kooperativen Blockierungsmechanismus nicht verwenden können. Zum Beispiel verwendet eine externe Bibliothek möglicherweise einen anderen Synchronisierungsmechanismus. Ein weiteres Beispiel ist das Ausführen eines Vorgangs, der einen hohen Betrag an Wartezeit beinhalten kann, wenn Sie z. B. die `ReadFile`-Funktion der Windows-API zum Lesen von Daten über eine Netzwerkverbindung verwenden. In diesen Fällen kann Überzeichnung die Ausführung anderer Aufgaben ermöglichen, wenn sich eine andere Aufgabe im Leerlauf befindet. Durch Überzeichnung können Sie mehr Threads als die Anzahl der verfügbaren Hardwarethreads erstellen.

Betrachten Sie die folgende Funktion `download`, mit der die Datei an der angegebenen URL heruntergeladen wird. Dieses Beispiel verwendet die [Oversubscribe](reference/context-class.md#oversubscribe) Methode, um die Anzahl aktiver Threads vorübergehend erhöhen.

[!code-cpp[concrt-download-oversubscription#4](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_3.cpp)]

Da die `GetHttpFile`-Funktion einen Vorgang mit potenzieller Wartezeit ausführt, kann Überzeichnung die Ausführung anderer Aufgaben ermöglichen, während die aktuelle Aufgabe auf Daten wartet. Die vollständige Version dieses Beispiels, finden Sie unter [Vorgehensweise: Verwenden der Überzeichnung zum Versetzen der Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).

[[Nach oben](#top)]

##  <a name="memory"></a> Verwenden Sie parallele Speicherverwaltungsfunktionen möglichst

Verwenden Sie die Speicherverwaltungsfunktionen [Concurrency:: Alloc](reference/concurrency-namespace-functions.md#alloc) und [Concurrency](reference/concurrency-namespace-functions.md#free), wenn Sie differenzierte Aufgaben verfügen, das häufig kleine Objekte zugewiesen werden, die relativ kurzen Lebensdauer haben. Die Concurrency Runtime verwaltet für jeden ausgeführten Thread einen eigenen Arbeitsspeichercache. Die `Alloc`-Funktion und die `Free`-Funktion reservieren Arbeitsspeicher in diesen Caches und geben Arbeitsspeicher in den Caches frei, ohne Sperren oder Arbeitsspeicherbarrieren zu verwenden.

Weitere Informationen zu diesen Speicherverwaltungsfunktionen finden Sie unter [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Ein Beispiel, diese Funktionen verwendet, finden Sie unter [Vorgehensweise: Mithilfe von Alloc und Free Verbessern der Arbeitsspeicherleistung](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).

[[Nach oben](#top)]

##  <a name="raii"></a> Verwenden Sie RAII zum Verwalten der Lebensdauer von Parallelitätsobjekten

Die Concurrency Runtime verwendet die Ausnahmebehandlung zum Implementieren von Funktionen, z. B. Abbruch. Schreiben Sie daher ausnahmesicheren Code, wenn Sie die Laufzeit oder eine andere Bibliothek aufrufen, die die Laufzeit aufruft.

Die *Resource Acquisition Is Initialization* (RAII)-Muster ist eine Möglichkeit, die die Lebensdauer eines Parallelitätsobjekts in einem bestimmten Bereich sicher zu verwalten. Unter dem RAII-Muster wird dem Stapel eine Datenstruktur zugeordnet. Diese Datenstruktur initialisiert oder ruft eine Ressource ab, wenn sie erstellt wird, und zerstört oder gibt diese Ressource frei, wenn die Datenstruktur zerstört wird. Das RAII-Muster garantiert, dass der Destruktor aufgerufen wird, bevor der einschließende Bereich beendet wird. Dieses Muster ist hilfreich, wenn eine Funktion mehrere `return`-Anweisungen enthält. Das Muster erleichtert Ihnen außerdem das Schreiben von ausnahmesicherem Code. Wenn eine `throw`-Anweisung das Entladen des Stapels verursacht, wird der Destruktor für das RAII-Objekt aufgerufen. Daher wird die Ressource immer ordnungsgemäß gelöscht oder freigegeben.

Die Laufzeit definiert mehrere Klassen, mit denen das RAII-Muster, z. B. [Concurrency::critical_section::scoped_lock](../../parallel/concrt/reference/critical-section-class.md#critical_section__scoped_lock_class) und [Concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class). Diese Hilfsklassen werden als bezeichnet *bewertete Sperren*. Diese Klassen bieten mehrere Vorteile bei der Arbeit mit [Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) oder [Concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) Objekte. Der Konstruktor dieser Klassen erhält Zugriff auf das bereitgestellte `critical_section`-Objekt bzw. `reader_writer_lock`-Objekt, und der Destruktor gibt den Zugriff auf das Objekt frei. Da eine bewertete Sperre den Zugriff auf das gegenseitige Ausschlussobjekt automatisch freigibt, wenn es zerstört wird, muss das zugrunde liegende Objekt nicht manuell entsperrt werden.

Betrachten Sie die folgende Klasse `account`, die durch eine externe Bibliothek definiert ist und deshalb nicht geändert werden kann.

[!code-cpp[concrt-account-transactions#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_4.h)]

Im folgenden Beispiel werden mehrere Transaktionen für ein `account`-Objekt parallel ausgeführt. Im Beispiel wird ein `critical_section`-Objekt zum Synchronisieren des Zugriffs auf das `account`-Objekt verwendet, da die `account`-Klasse nicht parallelitätssicher ist. Für jeden parallelen Vorgang wird ein `critical_section::scoped_lock`-Objekt verwendet, um sicherzustellen, dass das `critical_section`-Objekt entsperrt wird, wenn der Vorgang erfolgreich ausgeführt wird oder fehlschlägt. Wenn der Kontostand negativ ist, löst der `withdraw`-Vorgang eine Ausnahme aus und schlägt fehl.

[!code-cpp[concrt-account-transactions#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_5.cpp)]

Dieses Beispiel erzeugt die folgende Beispielausgabe:

```Output
Balance before deposit: 1924
Balance after deposit: 2924
Balance before withdrawal: 2924
Balance after withdrawal: -76
Balance before withdrawal: -76
Error details:
    negative balance: -76
```

Weitere Beispiele, die das RAII-Muster, zum Verwalten der Lebensdauer von Parallelitätsobjekten verwenden finden Sie unter [Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächenthread](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md), [Vorgehensweise: Implementieren einer kooperativen Semaphore mithilfe der Context-Klasse](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md), und [Vorgehensweise: Verwenden der Überzeichnung zum Versetzen der Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).

[[Nach oben](#top)]

##  <a name="global-scope"></a> Keine Parallelitätsobjekte im globalen Gültigkeitsbereich erstellen

Wenn Sie ein Parallelitätsobjekt im globalen Gültigkeitsbereich erstellen, kann dies zu Problemen wie Deadlocks oder Arbeitsspeicher-Zugriffsverletzungen in der Anwendung führen.

Wenn Sie z. B. ein Concurrency Runtime-Objekt erstellen, erstellt die Laufzeit einen Standardplaner, sofern noch kein Planer erstellt wurde. Ein Laufzeitobjekt, das während der globalen Objekterstellung erstellt wird, führt dementsprechend dazu, dass die Laufzeit diesen Standardplaner erstellt. Dieser Vorgang verwendet jedoch eine interne Sperre, die die Initialisierung anderer Objekte behindern kann, die die Concurrency Runtime-Infrastruktur unterstützen. Diese interne Sperre wird eventuell von einem anderen Infrastrukturobjekt benötigt, das noch nicht initialisiert wurde, und daher tritt möglicherweise ein Deadlock in der Anwendung auf.

Das folgende Beispiel veranschaulicht die Erstellung eines globalen [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) Objekt. Dieses Muster gilt nicht nur für die `Scheduler`-Klasse, sondern auch für alle anderen Typen, die von der Concurrency Runtime bereitgestellt werden. Es wird empfohlen, dieses Muster nicht anzuwenden, da es zu einem unerwarteten Verhalten in der Anwendung führen kann.

[!code-cpp[concrt-global-scheduler#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_6.cpp)]

Beispiele für die ordnungsgemäße Vorgehensweise zum Erstellen `Scheduler` Objekten finden Sie [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

[[Nach oben](#top)]

##  <a name="shared-data"></a> Verwenden Sie keine Parallelitätsobjekte in freigegebenen Datensegmenten

Die Concurrency Runtime unterstützt nicht die Verwendung von Parallelitätsobjekten in einem freigegebenen Datenabschnitt, z. B. ein Data-Abschnitt, der erstellt wird die [Data_seg](../../preprocessor/data-seg.md) `#pragma` Richtlinie. Ein über Prozessgrenzen hinweg gemeinsam genutztes Parallelitätsobjekt kann einen inkonsistenten oder ungültigen Zustand der Laufzeit verursachen.

[[Nach oben](#top)]

## <a name="see-also"></a>Siehe auch

[Bewährte Methoden im Zusammenhang mit der Concurrency Runtime](../../parallel/concrt/concurrency-runtime-best-practices.md)<br/>
[Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md)<br/>
[Vergleich der Synchronisierungsdatenstrukturen mit der Windows-API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
[Vorgehensweise: Verbessern der Arbeitsspeicherleistung mithilfe von Alloc und Free](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)<br/>
[Vorgehensweise: Verwenden der Überzeichnung zum Kompensieren der Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)<br/>
[Vorgehensweise: Implementieren eines kooperativen Semaphors mithilfe der Context-Klasse](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br/>
[Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächenthread](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)<br/>
[Bewährte Methoden in der Parallel Patterns Library](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br/>
[Bewährte Methoden in der asynchronen Agents Library](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)
