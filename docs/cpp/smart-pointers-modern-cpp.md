---
title: Intelligente Zeiger (Modern C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 909ef870-904c-49b6-b8cd-e9d0b7dc9435
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9142ba85a78259c0a6e5ae06f3745d414e62e908
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425626"
---
# <a name="smart-pointers-modern-c"></a>Intelligente Zeiger (Modern C++)

Im modernen C++-Programmierung enthält die Standardbibliothek *intelligente Zeiger*, die verwendet werden, um sicherzustellen, dass Programme sind frei von Speicher- und Ressourcen von Speicherverlusten und sind.

## <a name="uses-for-smart-pointers"></a>Anwendungsmöglichkeiten für intelligente Zeiger

Intelligente Zeiger werden definiert, der `std` -Namespace in der [ \<Arbeitsspeicher >](../standard-library/memory.md) Headerdatei. Sie sind entscheidend, um die [RAII](../cpp/objects-own-resources-raii.md) oder *Resource Acquisition Is Initialization* Programmierung Idiom. Das wichtigste Ziel dieses Technik ist sicherzustellen, dass die Ressourcenerfassung zur gleichen Zeit erfolgt wie die Initialisierung des Objekts, damit alle Ressourcen für das Objekt in einer Codezeile erstellt und vorbereitet werden können. Praktisch ist es das Hauptprinzip von RAII, die Verfügung über jede auf dem Heap zugeordnete Ressource (beispielsweise dynamisch zugeordneter Arbeitsspeicher oder Systemobjekthandles) einem auf dem Stapel zugeordneten Objekt zu übertragen, dessen Destruktor sowohl den Code enthält, um die Ressource zu löschen oder freizugeben, als auch jeden zugehörigen Bereinigungscode.

Wenn Sie einen Rohzeiger oder ein Ressourcenhandle für eine aktuelle Ressource initialisieren, sollten Sie den Zeiger in den meisten Fällen sofort einem intelligenten Zeiger zuweisen. In modernem C++ werden Rohzeiger nur in kleinen Codeblöcken mit begrenztem Gültigkeitsbereich, in Schleifen oder Hilfsfunktionen verwendet, in denen Leistung ausschlaggebend ist und keine Verwirrung über den Besitzer entstehen kann.

Im folgenden Beispiel wird die Deklaration eines Rohzeigers mit der eines intelligenten Zeigers verglichen.

[!code-cpp[smart_pointers_intro#1](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_1.cpp)]

Wie im Beispiel gezeigt, ist ein intelligenter Zeiger eine Klassenvorlage, die auf dem Stapel deklariert wird. Die Initialisierung erfolgt mit einem Rohzeiger auf ein auf dem Stapel zugeordnetes Objekt. Nachdem der intelligente Zeiger initialisiert wurde, besitzt er den Rohzeiger. Dies bedeutet, dass der intelligente Zeiger für das Löschen des Arbeitsspeichers zuständig ist, den der Rohzeiger angibt. Der Destruktor des intelligenten Zeigers enthält den Aufruf zum Löschen, und weil der intelligente Zeiger auf dem Stapel deklariert wurde, wird sein Destruktor aufgerufen, sobald der intelligente Zeiger ungültig wird, auch wenn eine Ausnahme irgendwo weiter oben im Stapel ausgelöst wird.

Greifen Sie auf den gekapselten Zeiger mit den vertrauten Zeigeroperatoren `->` und `*` zu, die von der Klasse des intelligenten Zeigers so überladen werden, dass der gekapselte Rohzeiger zurückgegeben wird.

Die Wirkungsweise eines intelligenten C++-Zeigers ähnelt dem Vorgehen bei der Objekterstellung in Sprachen wie C#: Sie erstellen das Objekt und überlassen es dann dem System, das Objekt zur richtigen Zeit zu löschen. Der Unterschied besteht darin, dass im Hintergrund keine separate Speicherbereinigung ausgeführt wird – der Arbeitsspeicher wird durch die C++-Standardregeln für den Gültigkeitsbereich verwaltet, sodass die Laufzeitumgebung schneller und effizienter ist.

> [!IMPORTANT]
>  Erstellen Sie intelligente Zeiger immer in einer eigenen Codezeile und nie in einer Parameterliste, damit aufgrund bestimmter Speicherbelegungsregeln für Parameterlisten kein kleines Ressourcenleck auftritt.

Das folgende Beispiel zeigt wie eine `unique_ptr` intelligenten Zeigertyp aus der C++-Standardbibliothek verwendet werden, um einen Zeiger auf ein großes Objekt zu kapseln.

[!code-cpp[smart_pointers_intro#2](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_2.cpp)]

Dieses Beispiel verdeutlicht die folgenden wesentlichen Schritte für die Verwendung von intelligenten Zeigern.

1. Deklarieren Sie den intelligenten Zeiger als automatische (lokale) Variable. (Verwenden Sie nicht die **neue** oder `malloc` Ausdruck, für den intelligenten Zeiger selbst.)

1. Als Typparameter geben Sie den Typ an, auf den der gekapselte Zeiger zeigt.

1. Übergeben Sie einen unformatierten Zeiger auf eine **neue**-deklariertes Objekt im Konstruktor intelligenten Zeigers. (Einige Hilfsfunktionen oder Konstruktoren für intelligente Zeiger übernehmen das für Sie.)

1. Verwenden Sie die überladenen Operatoren `->` und `*` für den Zugriff auf das Objekt.

1. Lassen Sie den intelligenten Zeiger das Objekt löschen.

Intelligente Zeiger sind dafür konzipiert, im Hinblick auf Leistung und Arbeitsspeicher so effizient wie möglich sein. Beispielsweise ist der einzige Datenmember in `unique_ptr` der gekapselte Zeiger. Dies bedeutet, dass `unique_ptr` genau die gleiche Größe hat wie dieser Zeiger, entweder vier oder acht Bytes. Der Zugriff auf gekapselte Zeiger mithilfe der überladenen Methoden * und -> des intelligenten Zeigers ist nicht wesentlich langsamer als der direkte Zugriff auf Rohzeiger.

Intelligente Zeiger verfügen über eigene Memberfunktionen, auf die mithilfe der Punktnotation zugegriffen wird. Beispielsweise verfügen einige intelligente Zeiger der C++-Standardbibliothek eine rücksetzungsmemberfunktion, die Besitz des Zeigers freigibt. Dies ist hilfreich, wenn Sie den Arbeitsspeicher des intelligenten Zeigers freigeben möchten, bevor dieser ungültig wird, wie im folgenden Beispiel gezeigt.

[!code-cpp[smart_pointers_intro#3](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_3.cpp)]

Intelligente Zeiger stellen normalerweise eine Möglichkeit für den direkten Zugriff auf ihre Rohzeiger bereit. Intelligente Zeiger der C++-Standardbibliothek haben eine `get` Memberfunktion zu diesem Zweck und `CComPtr` verfügt über eine öffentliche `p` Klassenmember. Wenn Sie direkten Zugriff auf den zugrunde liegende Zeiger bereitstellen, können Sie den intelligenten Zeiger verwenden, um Arbeitsspeicher in Ihrem eigenen Code zu verwalten, und Sie können den Rohzeiger weiterhin an Code übergeben, der keine intelligenten Zeiger unterstützt.

[!code-cpp[smart_pointers_intro#4](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_4.cpp)]

## <a name="kinds-of-smart-pointers"></a>Arten von intelligenten Zeigern

Im folgenden Abschnitt werden die in der Windows-Programmierumgebung verfügbaren verschiedenen Arten von intelligenten Zeigern aufgeführt, und es wird beschrieben, wann sie zu verwenden sind.

### <a name="c-standard-library-smart-pointers"></a>Intelligente Zeiger der C++-Standardbibliothek

Verwenden Sie vorrangig diese intelligenten Zeiger zum Kapseln von Zeigern auf einfache alte C++-Objekte (Plain Old CLR Objects, POCOs).

- `unique_ptr` Ermöglicht genau einen Besitzer für den zugrunde liegenden Zeiger. Verwenden Sie diesen Zeiger als Standardwahl für POCOs, es sei denn, Sie sind sicher, dass Sie einen `shared_ptr` benötigen. Kann zu einem neuen Besitzer verschoben werden, kann aber nicht kopiert oder freigegeben werden. Ersetzt `auto_ptr`, der veraltet ist. Ist vergleichbar mit `boost::scoped_ptr`. `unique_ptr` ist klein und effizient. die Größe ist ein Zeiger, und Rvalue-Referenzen für schnelles Einfügen und Abrufen von C++-standardbibliotheksauflistungen unterstützt. Headerdatei: `<memory>`. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen und Verwenden von Unique_ptr-Instanzen](../cpp/how-to-create-and-use-unique-ptr-instances.md) und [Unique_ptr-Klasse](../standard-library/unique-ptr-class.md).

- `shared_ptr` Intelligenter Zeiger mit referenzzählung. Verwenden Sie diesen Zeiger, wenn Sie mehreren Besitzern einen Rohzeiger zuweisen möchten. Beispiel: Sie geben eine Kopie eines Zeigers von einem Container zurück, möchten aber das Original behalten. Der Rohzeiger wird erst gelöscht, wenn alle `shared_ptr`-Besitzer den Gültigkeitsbereich verlassen haben oder auf andere Weise nicht mehr Besitzer sind. Die Größe beträgt zwei Zeiger; einen für das Objekt und einen für den freigegebenen Kontrollblock, der den Referenzzähler enthält. Headerdatei: `<memory>`. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen und Verwenden von Shared_ptr-Instanzen](../cpp/how-to-create-and-use-shared-ptr-instances.md) und [Shared_ptr-Klasse](../standard-library/shared-ptr-class.md).

- `weak_ptr` Spezielle intelligente Zeiger für die Verwendung in Verbindung mit `shared_ptr`. Ein `weak_ptr` ermöglicht den Zugriff auf ein Objekt, das einer oder mehreren `shared_ptr`-Instanzen gehört, ist aber nicht an der Referenzzählung beteiligt ist. Verwenden Sie diesen Zeiger, wenn Sie ein Objekt beobachten möchten, dieses aber nicht gültig bleiben muss. Ist in einigen Fällen erforderlich, um Zirkelverweise zwischen `shared_ptr`-Instanzen zu unterbrechen. Headerdatei: `<memory>`. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen und Verwenden von Weak_ptr-Instanzen](../cpp/how-to-create-and-use-weak-ptr-instances.md) und [Weak_ptr-Klasse](../standard-library/weak-ptr-class.md).

### <a name="smart-pointers-for-com-objects-classic-windows-programming"></a>Intelligente Zeiger für COM-Objekte (klassische Windows-Programmierung)

Wenn Sie mit COM-Objekten arbeiten, sollten Sie Schnittstellenzeiger mit einem geeigneten Typ eines intelligenten Zeigers kapseln. Die ATL (Active Template Library) definiert mehrere intelligente Zeiger für verschiedene Zwecke. Sie können auch den Typ `_com_ptr_t` eines intelligenten Zeigers verwenden, den der Compiler einsetzt, wenn er Wrapperklassen von .tlb-Dateien erstellt. Er ist die beste Wahl, wenn Sie die ATL-Headerdateien nicht einschließen möchten.

[CComPtr-Klasse](../atl/reference/ccomptr-class.md)<br/>
Verwenden Sie diesen, sofern Sie ATL nicht verwenden können. Führt Referenzzählung mithilfe der Methoden `AddRef` und `Release` aus. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen und Verwenden von CComPtr- und CComQIPtr-Instanzen](../cpp/how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md).

[CComQIPtr-Klasse](../atl/reference/ccomqiptr-class.md)<br/>
Ähnelt `CComPtr`, stellt jedoch zusätzlich vereinfachte Syntax zum Aufrufen von `QueryInterface` in COM-Objekten bereit. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen und Verwenden von CComPtr- und CComQIPtr-Instanzen](../cpp/how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md).

[CComHeapPtr-Klasse](../atl/reference/ccomheapptr-class.md)<br/>
Intelligenter Zeiger auf Objekte, die `CoTaskMemFree` verwenden, um Arbeitsspeicher freizugeben.

[CComGITPtr-Klasse](../atl/reference/ccomgitptr-class.md)<br/>
Intelligenter Zeiger für Schnittstellen, die aus der globalen Schnittstellentabelle (Global Interface Table, Git) abgerufen werden.

[_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)<br/>
Ähnelt `CComQIPtr` bezüglich der Funktionalität, ist jedoch nicht von ATL-Headern abhängig.

### <a name="atl-smart-pointers-for-poco-objects"></a>Intelligente Zeiger der ATL für POCO-Objekte

Zusätzlich zu den intelligenten Zeigern für COM-Objekte definiert ATL auch intelligente Zeiger sowie Auflistungen von intelligenten Zeigern für einfache alte C++-Objekte. In der klassischen Windows-Programmierung werden diese Typen nützliche Alternativen zu den C++-Standardbibliothek-Auflistungen, insbesondere wenn Codeportabilität nicht erforderlich ist, oder wenn Sie nicht, kombinieren Sie die Programmiermodelle von der C++-Standardbibliothek und ATL möchten

[CAutoPtr-Klasse](../atl/reference/cautoptr-class.md)<br/>
Intelligenter Zeiger, der eindeutigen Besitz erzwingt, indem er den Besitz auf die Kopie überträgt. Vergleichbar mit der veralteten `std::auto_ptr`-Klasse.

[CHeapPtr-Klasse](../atl/reference/cheapptr-class.md)<br/>
Intelligenter Zeiger für Objekte, die zugewiesen werden, mit der C [Malloc](../c-runtime-library/reference/malloc.md) Funktion.

[CAutoVectorPtr-Klasse](../atl/reference/cautovectorptr-class.md)<br/>
Intelligenter Zeiger für Arrays, die mit `new[]` zugeordnet werden.

[CAutoPtrArray-Klasse](../atl/reference/cautoptrarray-class.md)<br/>
Klasse, die ein Array mit `CAutoPtr`-Elementen kapselt.

[CAutoPtrList-Klasse](../atl/reference/cautoptrlist-class.md)<br/>
Klasse, die Methoden zum Bearbeiten einer Liste von `CAutoPtr`-Knoten kapselt.

## <a name="see-also"></a>Siehe auch

[Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)