---
title: Taskplaner (Concurrency Runtime)
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
ms.openlocfilehash: e4a2e66afe656f9588ed3040218d1f70b3684190
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143312"
---
# <a name="task-scheduler-concurrency-runtime"></a>Taskplaner (Concurrency Runtime)

Die Themen in diesem Teil der Dokumentation beschreiben die wichtigsten Features des Taskplaners der Concurrency Runtime. Der Aufgabenplaner ist hilfreich, wenn Sie die Leistung von vorhandenem Code optimieren möchten, der die Concurrency Runtime verwendet.

> [!IMPORTANT]
> Der Taskplaner ist in einer universelle Windows-Plattform-app (UWP) nicht verfügbar. Weitere Informationen finden Sie unter [Erstellen von asynchronen Vorgängen in C++ für UWP-apps](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).
>
> In Visual Studio 2015 und höher verwenden die " [parallelcurrency:: Task](../../parallel/concrt/reference/task-class.md) "-Klasse und verwandte Typen in "ppltasks. h" den Windows-Thread Pool als Scheduler. Dieses Thema gilt nicht mehr für Typen, die in „ppltasks.h“ definiert sind. Parallele Algorithmen, wie z. B. „parallel_for“, verwenden weiterhin die Concurrency Runtime als standardmäßigen Planer.

> [!TIP]
> Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie bei der Feinabstimmung der Leistung Ihrer Anwendungen unterstützt, empfehlen wir Ihnen, mit der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) zu beginnen, wenn Sie mit der Concurrency Runtime noch nicht vertraut sind.

Der Taskplaner plant und koordiniert die Aufgaben zur Laufzeit. Bei einem *Task* handelt es sich um eine Arbeitseinheit, die einen bestimmten Auftrag ausführt. Eine Aufgabe kann in der Regel parallel mit anderen Aufgaben ausgeführt werden. Die Arbeit, die von Aufgabengruppenelementen ausgeführt wird, parallele Algorithmen und asynchrone Agents sind Beispiele für Aufgaben.

Der Aufgabenplaner verwaltet die Details, die sich auf die effiziente Planung von Aufgaben auf Computern mit mehreren Computerressourcen beziehen. Der Taskplaner verwendet außerdem die neuesten Features des zugrunde liegenden Betriebssystems. Aus diesem Grund skalieren und verbessern Anwendungen, die die Concurrency Runtime automatisch verwenden, jede Hardware, die über erweiterte Funktionen verfügt.

Im [Vergleich zu anderen](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md) Parallelitäts Modellen werden die Unterschiede zwischen präemptiven und kooperativen Planungsmechanismen beschrieben. Der Aufgabenplaner verwendet die kooperative Planung und einen Arbeitsübernahmealgorithmus zusammen mit dem präemptiven Planer des Betriebssystems, um eine maximale Nutzung der Verarbeitungsressourcen zu erreichen.

Die Concurrency Runtime stellt einen Standardplaner bereit, sodass Sie keine Infrastrukturdetails verwalten müssen. Daher verwenden Sie den Taskplaner in der Regel nicht direkt. Um die Qualitätsanforderungen Ihrer Anwendung zu erfüllen, können Sie mit dem Taskplaner jedoch auch Ihre eigenen Planungsrichtlinien bereitstellen oder Planern bestimmte Aufgaben zuordnen. Nehmen wir beispielsweise an, Sie haben eine parallele Sortierungsroutine, die nicht auf mehr als vier Prozessoren skaliert werden kann. Mithilfe von *Scheduler-Richtlinien* können Sie einen Planer erstellen, der nicht mehr als vier gleichzeitige Aufgaben generiert. Wenn Sie die Sortierungsroutine auf diesem Planer ausführen, können andere aktive Planer die restlichen Verarbeitungsressourcen verwenden.

## <a name="related-topics"></a>Verwandte Themen

|Titel|BESCHREIBUNG|
|-----------|-----------------|
|[Planerinstanzen](../../parallel/concrt/scheduler-instances.md)|Beschreibt Planerinstanzen und die Verwendung der `concurrency::Scheduler`- und `concurrency::CurrentScheduler`-Klassen für deren Verwaltung. Verwenden Sie Planerinstanzen, wenn Sie explizite Planungsrichtlinien bestimmten Arten von Arbeitslasten zuordnen möchten.|
|[Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)|Beschreibt die Rolle von Planerrichtlinien. Mithilfe von Planerrichtlinien können Sie die Strategie festlegen, die der Planer zum Verwalten von Aufgaben verwendet.|
|[Planungsgruppen](../../parallel/concrt/schedule-groups.md)|Beschreibt die Rolle von Planungsgruppen. Verwenden Sie Planungsgruppen, wenn Sie ein hohes Maß an Lokalität zwischen den Aufgaben benötigen. Dies ist zum Beispiel dann der Fall, wenn es für eine Gruppe verwandter Aufgaben vorteilhaft ist, auf dem gleichen Prozessorknoten ausgeführt zu werden.|
|[Einfache Aufgaben](../../parallel/concrt/lightweight-tasks.md)|Beschreibt die Rolle einfacher Aufgaben. Einfache Aufgaben sind nützlich, wenn Sie vorhandenen Code anpassen, um die Planungsfunktionalität der Concurrency Runtime zu verwenden.|
|[Kontext](../../parallel/concrt/contexts.md)|Beschreibt die Rolle von Kontexten, die `concurrency::wait`-Funktion und die `concurrency::Context`-Klasse. Verwenden Sie diese Funktion, wenn Sie steuern müssen, wann Kontexte blockieren, die Blockierung aufheben oder nachgeben, oder wenn Sie die Überzeichnung in der Anwendung aktivieren möchten.|
|[Speicherverwaltungsfunktionen](../../parallel/concrt/memory-management-functions.md)|Beschreibt die `concurrency::Alloc`- und `concurrency::Free`-Funktionen. Diese Funktionen können die Leistung des Arbeitsspeichers verbessern, indem sie Arbeitsspeicher parallel zuweisen und freigeben.|
|[Vergleich mit anderen Parallelitäts Modellen](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|Beschreibt die Unterschiede zwischen präemptiven und kooperativen Planungsmechanismen.|
|[Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Beschreibt, wie Sie verschiedene parallele Muster, z. B. parallele Algorithmen, in Anwendungen verwenden können.|
|[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)|Beschreibt, wie Sie asynchrone Agents in Ihren Anwendungen verwenden.|
|[Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)|Beschreibt die Concurrency Runtime, die die parallele Programmierung vereinfacht, und stellt Links zu verwandten Themen bereit.|
