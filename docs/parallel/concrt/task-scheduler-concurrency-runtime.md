---
title: Aufgabenplaner (Concurrency Runtime)
ms.date: 11/04/2016
helpviewer_keywords:
- oversubscription [Concurrency Runtime]
- task scheduler [Concurrency Runtime], oversubscription
- schedule groups [Concurrency Runtime]
- task scheduler [Concurrency Runtime], lightweight tasks
- task scheduler [Concurrency Runtime]
- lightweight tasks [Concurrency Runtime]
- task scheduler [Concurrency Runtime], scheduler policies
- task scheduler [Concurrency Runtime], schedule groups
- wait function [Concurrency Runtime]
- task scheduler [Concurrency Runtime], scheduler instances
- scheduler instances [Concurrency Runtime]
- scheduler policies [Concurrency Runtime]
- task scheduler [Concurrency Runtime], wait function
ms.assetid: 9aba278c-e0c9-4ede-b7c6-fedf7a365d90
ms.openlocfilehash: 91ef4ed14fa1ddc25ff494f6666a50f5b39b8a54
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676706"
---
# <a name="task-scheduler-concurrency-runtime"></a>Aufgabenplaner (Concurrency Runtime)

Die Themen in diesem Teil der Dokumentation beschreiben die wichtigsten Funktionen des Taskplaners der Concurrency Runtime. Der Aufgabenplaner ist hilfreich, wenn Sie die Leistung von vorhandenem Code optimieren möchten, der die Concurrency Runtime verwendet.

> [!IMPORTANT]
>  Der Aufgabenplaner ist nicht verfügbar, über eine app (Universelle Windows Plattform). Weitere Informationen finden Sie unter [Erstellen von asynchronen Vorgängen in C++ für UWP-Apps](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).
>
>  In Visual Studio 2015 und höher die [Concurrency:: Task](../../parallel/concrt/reference/task-class.md) -Klasse und verwandte Typen in "ppltasks.h" verwenden Sie den Windows-ThreadPool als Aufgabenplaner. Dieses Thema gilt nicht mehr für Typen, die in „ppltasks.h“ definiert sind. Parallele Algorithmen, wie z. B. „parallel_for“, verwenden weiterhin die Concurrency Runtime als standardmäßigen Planer.

> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner die Leistung Ihrer Anwendungen optimieren können, es wird empfohlen, zunächst die [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) möchten noch nicht mit der Concurrency Runtime.

Der Aufgabenplaner plant und koordiniert die Aufgaben zur Laufzeit. Ein *Aufgabe* ist eine Arbeitseinheit, die einen bestimmten Auftrag ausführt. Eine Aufgabe kann in der Regel parallel mit anderen Aufgaben ausgeführt werden. Die Arbeit, die von Aufgabengruppenelementen ausgeführt wird, parallele Algorithmen und asynchrone Agents sind Beispiele für Aufgaben.

Der Taskplaner verwaltet die Details, die sich auf die effiziente Planung von Aufgaben auf Computern mit mehreren Computerressourcen beziehen. Der Taskplaner verwendet außerdem die neuesten Features des zugrunde liegenden Betriebssystems. Aus diesem Grund skalieren und verbessern Anwendungen, die die Concurrency Runtime automatisch verwenden, jede Hardware, die über erweiterte Funktionen verfügt.

[Vergleich mit anderen Parallelitätsmodellen](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md) beschreibt die Unterschiede zwischen präemptiven und kooperativen Planungsmechanismen. Der Aufgabenplaner verwendet die kooperative Planung und einen Arbeitsübernahmealgorithmus zusammen mit dem präemptiven Planer des Betriebssystems, um eine maximale Nutzung der Verarbeitungsressourcen zu erreichen.

Die Concurrency Runtime stellt einen Standardplaner bereit, sodass Sie keine Infrastrukturdetails verwalten müssen. Daher verwenden Sie den Taskplaner in der Regel nicht direkt. Um die Qualitätsanforderungen Ihrer Anwendung zu erfüllen, können Sie mit dem Taskplaner jedoch auch Ihre eigenen Planungsrichtlinien bereitstellen oder Planern bestimmte Aufgaben zuordnen. Nehmen wir beispielsweise an, Sie haben eine parallele Sortierungsroutine, die nicht auf mehr als vier Prozessoren skaliert werden kann. Sie können *Planerrichtlinien* einen Planer erstellen, die nicht mehr als vier gleichzeitige Aufgaben generiert. Wenn Sie die Sortierungsroutine auf diesem Planer ausführen, können andere aktive Planer die restlichen Verarbeitungsressourcen verwenden.

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Planerinstanzen](../../parallel/concrt/scheduler-instances.md)|Beschreibt Planerinstanzen und die Verwendung der `concurrency::Scheduler`- und `concurrency::CurrentScheduler`-Klassen für deren Verwaltung. Verwenden Sie Planerinstanzen, wenn Sie explizite Planungsrichtlinien bestimmten Arten von Arbeitslasten zuordnen möchten.|
|[Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)|Beschreibt die Rolle von Planerrichtlinien. Mithilfe von Planerrichtlinien können Sie die Strategie festlegen, die der Planer zum Verwalten von Aufgaben verwendet.|
|[Planungsgruppen](../../parallel/concrt/schedule-groups.md)|Beschreibt die Rolle von Planungsgruppen. Verwenden Sie Planungsgruppen, wenn Sie ein hohes Maß an Lokalität zwischen den Aufgaben benötigen. Dies ist zum Beispiel dann der Fall, wenn es für eine Gruppe verwandter Aufgaben vorteilhaft ist, auf dem gleichen Prozessorknoten ausgeführt zu werden.|
|[Einfache Aufgaben](../../parallel/concrt/lightweight-tasks.md)|Beschreibt die Rolle einfacher Aufgaben. Einfache Aufgaben sind nützlich, wenn Sie vorhandenen Code anpassen, um die Planungsfunktionalität der Concurrency Runtime zu verwenden.|
|[Kontext](../../parallel/concrt/contexts.md)|Beschreibt die Rolle von Kontexten, die `concurrency::wait`-Funktion und die `concurrency::Context`-Klasse. Verwenden Sie diese Funktion, wenn Sie steuern müssen, wann Kontexte blockieren, die Blockierung aufheben oder nachgeben, oder wenn Sie die Überzeichnung in der Anwendung aktivieren möchten.|
|[Speicherverwaltungsfunktionen](../../parallel/concrt/memory-management-functions.md)|Beschreibt die `concurrency::Alloc`- und `concurrency::Free`-Funktionen. Diese Funktionen können die Leistung des Arbeitsspeichers verbessern, indem sie Arbeitsspeicher parallel zuweisen und freigeben.|
|[Vergleich mit anderen Parallelitätsmodellen](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|Beschreibt die Unterschiede zwischen präemptiven und kooperativen Planungsmechanismen.|
|[Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Beschreibt, wie Sie verschiedene parallele Muster, z. B. parallele Algorithmen, in Anwendungen verwenden können.|
|[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)|Beschreibt, wie Sie asynchrone Agents in Ihren Anwendungen verwenden.|
|[Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)|Beschreibt die Concurrency Runtime, die die parallele Programmierung vereinfacht, und stellt Links zu verwandten Themen bereit.|

