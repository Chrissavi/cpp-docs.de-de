---
title: Übersicht über die Concurrency Runtime | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Concurrency Runtime, requirements
- Concurrency Runtime, architecture
- Concurrency Runtime, overview
- Concurrency Runtime, lambda expressions
ms.assetid: 56237d96-10b0-494a-9cb4-f5c5090436c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 67f0497f600cf5d528b2c41601b7a02c08771861
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692427"
---
# <a name="overview-of-the-concurrency-runtime"></a>Übersicht über die Concurrency Runtime
Dieses Dokument enthält eine Übersicht über die Concurrency Runtime. Es beschreibt die Vorteile der Concurrency Runtime, wann sie verwendet wird und wie ihre Komponenten miteinander und mit dem Betriebssystem und den Anwendungen interagieren.  
  
> [!IMPORTANT]
>  In Visual Studio 2015 und höher ist der Concurrency Runtime-Taskplaner nicht mehr der Planer für die Aufgabenklasse und verwandte Typen in „ppltasks.h“. Diese Typen verwenden jetzt den Windows-Threadpool für eine bessere Leistung und Interoperabilität mit Windows-Synchronisierungsprimitiven. Parallele Algorithmen, wie z. B. „parallel_for“ verwenden weiterhin den Concurrency Runtime-Aufgabenplaner.  
  
##  <a name="top"></a> Abschnitte  
 Dieses Dokument enthält folgende Abschnitte:  
  
-   [Warum eine Laufzeit für die Parallelität wichtig ist](#runtime)  
  
-   [Architektur](#architecture)  
  
-   [C++-Lambda-Ausdrücke](#lambda)  
  
-   [Anforderungen](#requirements)  
  
##  <a name="runtime"></a> Warum eine Laufzeit für die Parallelität wichtig ist  
 Eine Laufzeit für die Parallelität bietet die Einheitlichkeit und Vorhersagbarkeit für Anwendungen und Anwendungskomponenten, die gleichzeitig ausgeführt werden. Zwei Beispiele für die Vorteile der Concurrency Runtime sind *kooperative aufgabenplanung* und *Kooperative Blockierung*.  
  
 Die Concurrency Runtime verwendet einen kooperativen Aufgabenplaner, der einen Arbeitsübernahme-Algorithmus implementiert, um die Arbeit effizient auf die Computerressourcen zu verteilen. Betrachten Sie beispielsweise eine Anwendung mit zwei Threads, die beide von der gleichen Laufzeit verwaltet werden. Wenn ein Thread die geplante Aufgabe abgeschlossen hat, kann dieser die Arbeit des anderen Threads auslagern. Dieser Mechanismus gleicht die gesamte Arbeitsauslastung der Anwendung aus.  
  
 Die Concurrency Runtime stellt außerdem Synchronisierungsprimitiven zur Verfügung, die die kooperative Blockierung zum Synchronisieren des Zugriffs auf die Ressourcen nutzen. Betrachten Sie z. B. eine Aufgabe, bei der der exklusive Zugriff auf eine freigegebene Ressource gewährleistet sein muss. Durch die kooperative Blockierung kann die Laufzeit das verbleibende Quantum verwenden, um eine andere Aufgabe ausführen, während die erste Aufgabe auf die Ressource wartet. Durch diesen Mechanismus wird die maximale Auslastung der Computerressourcen hochgestuft.  
  
 [[Nach oben](#top)]  
  
##  <a name="architecture"></a> Architektur  
 Die Concurrency Runtime ist in vier Komponenten unterteilt: die Parallel Patterns Library (PPL), die Asynchronous Agents Library, der Aufgabenplaner und der Ressourcen-Manager. Diese Komponenten befinden sich zwischen dem Betriebssystem und den Anwendungen. Die folgende Abbildung zeigt, wie die Concurrency Runtime-Komponenten zwischen dem Betriebssystem und den Anwendungen interagieren:  
  
 **Architektur von Concurrency Runtime**  
  
 ![Architektur von Concurrency Runtime](../../parallel/concrt/media/concurrencyrun.png "Concurrencyrun")  
  
> [!IMPORTANT]
>  Die Taskplaner- und die Ressourcen-Manager-Komponenten sind nicht verfügbar, aus einer app für die universelle Windows-Plattform (UWP), oder wenn Sie die Aufgabenklasse oder andere Typen in "ppltasks.h" verwenden.  
  
 Die Concurrency Runtime ist hochgradig *zusammensetzbar*, d. h. Sie können die vorhandene Funktionalität kombinieren hierzu mehr. Die Concurrency Runtime kombiniert viele Funktionen aus Komponenten auf niedrigerer Ebene, wie z. B. parallele Algorithmen.  
  
 Die Concurrency Runtime stellt außerdem Synchronisierungsprimitiven zur Verfügung, die die kooperative Blockierung zum Synchronisieren des Zugriffs auf die Ressourcen nutzen. Weitere Informationen zu diesen Synchronisierungsprimitiven finden Sie unter [Strukturen für Synchronisierungsdaten](../../parallel/concrt/synchronization-data-structures.md).  
  
 Die folgenden Abschnitte bieten einen kurzen Überblick über die jeweilige Komponente und deren Verwendung.  
  
### <a name="parallel-patterns-library"></a>Parallel Patterns Library  
 Die Parallel Patterns Library (PPL) bietet allgemeine Container und Algorithmen zum Ausführen der differenzierten Parallelität. Die PPL aktiviert *imperative Datenparallelität* mithilfe parallele Algorithmen, die Berechnungen in Auflistungen oder für einen Satz von Daten auf die Computerressourcen verteilen. Sie können auch *Aufgabenparallelität* durch Bereitstellung von Aufgabenobjekten, mehrere unabhängige Vorgänge auf die Computerressourcen verteilen.  
  
 Verwenden Sie die Parallel Patterns Library bei lokalen Berechnungen, die von der parallelen Ausführung profitieren können. Beispielsweise können Sie die [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus zum Transformieren einer vorhandenen `for` -Schleife für die parallele Ausführung.  
  
 Weitere Informationen zur Parallel Patterns Library finden Sie unter [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md).  
  
### <a name="asynchronous-agents-library"></a>Asynchronous Agents Library  
 Die Asynchronous Agents Library (oder einfach *Agents Library*) ein akteurbasiertes Programmiermodell und übergeben von Schnittstellen für Simple Datenfluss-und Pipelineaufgaben bietet. Asynchrone Agents ermöglichen es Ihnen, die Latenz produktiv zu nutzen, indem Sie Arbeiten ausführen, während andere Komponenten auf die Daten warten.  
  
 Verwenden Sie die Agents Library, wenn Sie über mehrere Entitäten verfügen, die miteinander asynchron kommunizieren. Beispielsweise können Sie einen Agent erstellen, der die Daten aus einer Datei oder einer Netzwerkverbindung liest und anschließend die Schnittstellen der Meldungsübergabe verwendet, um diese Daten an einen anderen Agent zu senden.  
  
 Weitere Informationen zur Agents Library finden Sie unter [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md).  
  
### <a name="task-scheduler"></a>Aufgabenplaner  
 Der Taskplaner plant und koordiniert die Aufgaben zur Laufzeit. Der Taskplaner ist kooperativ und verwendet einen Arbeitsübernahme-Algorithmus, um die maximale Auslastung der Verarbeitungsressourcen zu erreichen.  
  
 Die Concurrency Runtime stellt einen Standardplaner bereit, sodass Sie keine Infrastrukturdetails verwalten müssen. Um die Qualitätsanforderungen Ihrer Anwendung zu erfüllen, können Sie jedoch auch Ihre eigene Planungsrichtlinie zur Verfügung stellen oder bestimmten Planern bestimmte Aufgaben zuordnen.  
  
 Weitere Informationen zum Taskplaner finden Sie unter [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
### <a name="resource-manager"></a>Ressourcen-Manager  
 Die Aufgabe des Ressourcen-Managers besteht darin, die Computerressourcen, wie beispielsweise Prozessoren und Arbeitsspeicher, zu verwalten. Der Ressourcen-Manager reagiert auf Arbeitslasten, die sich zur Laufzeit ändern, indem die Ressourcen dorthin zugewiesen werden, wo sie am effektivsten sind.  
  
 Der Ressourcen-Manager stellt eine Abstraktionsebene für die Computerressourcen dar und interagiert in erster Linie mit dem Taskplaner. Obwohl Sie den Ressourcen-Manager zur Optimierung der Leistung Ihrer Bibliotheken und Anwendungen verwenden können, verwenden Sie in der Regel die Funktionalität, die von der Parallel Patterns Library, der Agents Library und dem Aufgabenplaner bereitgestellt wird. Diese Bibliotheken verwenden den Ressourcen-Manager, um die Ressourcen dynamisch neu zu verteilen, wenn sich die Arbeitslasten ändern.  
  
 [[Nach oben](#top)]  
  
##  <a name="lambda"></a> C++-Lambda-Ausdrücke  
 Viele der Typen und Algorithmen, die von der Concurrency Runtime definiert werden, werden als C++-Vorlagen implementiert. Einige dieser Typen und Algorithmen nehmen als Parameter eine Routine an, die die Arbeit ausführt. Dieser Parameter kann eine Lambda-Funktion, ein Funktionsobjekt oder ein Funktionszeiger sein. Diese Entitäten werden auch als bezeichnet *Arbeitsfunktionen* oder *Arbeitsroutinen*.  
  
 Die Lambdaausdrücke sind eine wichtige neue Sprachfunktion in Visual C++, da sie eine kompakte Art und Weise zum Definieren von Arbeitsfunktionen für die Parallelverarbeitung bieten. Funktionsobjekte und Funktionszeiger ermöglichen Ihnen die Verwendung der Concurrency Runtime mit dem vorhandenen Code. Microsoft empfiehlt jedoch, Lambdaausdrücke beim Schreiben von neuem Code zu verwenden, da diese bezüglich der Sicherheit und Produktivität viele Vorteile bieten.  
  
 Im folgenden Beispiel wird die Syntax von Lambda-Funktionen, Funktionsobjekten und Funktionszeigern in mehreren Aufrufen an die [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) Algorithmus. Jeder Aufruf von `parallel_for_each` eine andere Technik verwendet, berechnet das Quadrat jedes Elements in einem [Std:: Array](../../standard-library/array-class-stl.md) Objekt.  
  
 [!code-cpp[concrt-comparing-work-functions#1](../../parallel/concrt/codesnippet/cpp/overview-of-the-concurrency-runtime_1.cpp)]  
  
 **Ausgabe**  
  
```Output  
1  
256  
6561  
65536  
390625  
```  
  
 Weitere Informationen zu Lambdafunktionen in C++ finden Sie unter [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="requirements"></a> Anforderungen  
 Die folgende Tabelle zeigt die Headerdateien, die jeder einzelnen Komponente der Concurrency Runtime zugeordnet sind:  
  
|Komponente|Headerdateien|  
|---------------|------------------|  
|Parallel Patterns Library (PPL)|ppl.h<br /><br /> concurrent_queue.h<br /><br /> concurrent_vector.h|  
|Asynchronous Agents Library|agents.h|  
|Aufgabenplaner|concrt.h|  
|Ressourcen-Manager|concrtrm.h|  
  
 Die Concurrency Runtime wird deklariert, der [Parallelität](../../parallel/concrt/reference/concurrency-namespace.md) Namespace. (Sie können auch [Parallelität](../../parallel/concrt/reference/concurrency-namespace.md), dies ist ein Alias für diesen Namespace.) Der Namespace `concurrency::details` unterstützt das Concurrency Runtime-Framework und ist nicht für die direkte Verwendung im Code vorgesehen.  
  
 Die Concurrency Runtime wird als Teil der C-Laufzeitbibliothek (CRT) bereitgestellt. Weitere Informationen zum Erstellen einer Anwendung, die die CRT verwendet, finden Sie unter [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md).  
  
 [[Nach oben](#top)]



