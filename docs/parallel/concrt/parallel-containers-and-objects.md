---
title: Parallele Container und Objekte
ms.date: 03/27/2019
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
ms.openlocfilehash: 04b38fdc66a5c37a1780deaae4ae165f63238d93
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142903"
---
# <a name="parallel-containers-and-objects"></a>Parallele Container und Objekte

Die Parallel Patterns Library (PPL) umfasst mehrere Container und Objekte, die Thread sicheren Zugriff auf ihre Elemente bereitstellen.

Ein *gleichzeitiger Container* bietet neben läufigkeits sicheren Zugriff auf die wichtigsten Vorgänge. Die Parallelitäts Sicherheit bedeutet, dass Zeiger oder Iteratoren immer gültig sind. Es handelt sich nicht um eine Garantie der Element Initialisierung oder einer bestimmten Durchlauf Reihenfolge. Die Funktionen dieser Container ähneln denen, die von der C++ Standard Bibliothek bereitgestellt werden. Die Klasse " [parallelcurrency:: Concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) " ähnelt z. b. der [Std:: Vector](../../standard-library/vector-class.md) -Klasse, mit dem Unterschied, dass Sie mit der `concurrent_vector`-Klasse Elemente parallel anfügen können. Verwenden Sie gleichzeitige Container, wenn Sie über parallelen Code verfügen, der sowohl Lese-als auch Schreibzugriff auf denselben Container erfordert.

Ein *gleichzeitiges-Objekt* wird gleichzeitig zwischen-Komponenten freigegeben Ein Prozess, der den Status eines gleichzeitigen-Objekts parallel berechnet, erzeugt dasselbe Ergebnis wie ein anderer Prozess, der den gleichen Zustand serialisiert berechnet. Die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) -Klasse ist ein Beispiel für einen gleichzeitigen Objekttyp. Mit der `combinable`-Klasse können Sie Berechnungen parallel ausführen und diese Berechnungen dann zu einem endgültigen Ergebnis kombinieren. Verwenden Sie gleichzeitige Objekte, wenn Sie andernfalls einen Synchronisierungs Mechanismus verwenden möchten, z. b. einen Mutex, um den Zugriff auf eine freigegebene Variable oder Ressource zu synchronisieren.

## <a name="top"></a> Abschnitte

In diesem Thema werden die folgenden parallelen Container und Objekte ausführlich beschrieben.

Gleichzeitige Container:

- [concurrent_vector-Klasse](#vector)

   - [Unterschiede zwischen Concurrent_vector und Vektor](#vector-differences)

   - [Parallelitäts sichere Vorgänge](#vector-safety)

   - [Ausnahme Sicherheit](#vector-exceptions)

- [concurrent_queue-Klasse](#queue)

   - [Unterschiede zwischen Concurrent_queue und Warteschlange](#queue-differences)

   - [Parallelitäts sichere Vorgänge](#queue-safety)

   - [Iteratorunterstützung](#queue-iterators)

- [concurrent_unordered_map-Klasse](#unordered_map)

   - [Unterschiede zwischen concurrent_unordered_map und unordered_map](#map-differences)

   - [Parallelitäts sichere Vorgänge](#map-safety)

- [concurrent_unordered_multimap-Klasse](#unordered_multimap)

- [concurrent_unordered_set-Klasse](#unordered_set)

- [concurrent_unordered_multiset-Klasse](#unordered_multiset)

Gleichzeitige Objekte:

- [combinable-Klasse](#combinable)

   - [Methoden und Features](#combinable-features)

   - [Beispiele](#combinable-examples)

## <a name="vector"></a>concurrent_vector-Klasse

Die " [parallelcurrency:: Concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) "-Klasse ist eine Sequenz Container Klasse, die Sie genau wie die [Std:: Vector](../../standard-library/vector-class.md) -Klasse nach dem Zufallsprinzip auf die Elemente zugreifen können. Die `concurrent_vector`-Klasse ermöglicht Parallelitäts sichere Anfüge-und Element Zugriffs Vorgänge. Durch Anfüge Vorgänge werden vorhandene Zeiger oder Iteratoren nicht für ungültig erklärt. Iteratorzugriffe und Durchlauf Vorgänge sind ebenfalls Parallelitäts sicher. Die Parallelitäts Sicherheit bedeutet, dass Zeiger oder Iteratoren immer gültig sind. Es handelt sich nicht um eine Garantie der Element Initialisierung oder einer bestimmten Durchlauf Reihenfolge.

### <a name="vector-differences"></a>Unterschiede zwischen Concurrent_vector und Vektor

Die `concurrent_vector`-Klasse ähnelt der `vector`-Klasse. Die Komplexität von Anfüge-, Element-und iteratorzugriffsvorgängen für ein `concurrent_vector` Objekt ist identisch mit denen für ein `vector` Objekt. Die folgenden Punkte veranschaulichen, wo sich `concurrent_vector` von `vector`unterscheidet:

- Anfügen, Element Zugriff, iteratorzugriff und iteratortraversal-Vorgänge auf einem `concurrent_vector` Objekt sind Parallelitäts sicher.

- Sie können Elemente nur am Ende eines `concurrent_vector` Objekts hinzufügen. Die `concurrent_vector`-Klasse stellt die `insert`-Methode nicht bereit.

- Ein `concurrent_vector` Objekt verwendet keine Verschiebungs [Semantik](../../cpp/rvalue-reference-declarator-amp-amp.md) , wenn Sie es anfügen.

- Die `concurrent_vector`-Klasse stellt nicht die Methoden `erase` oder `pop_back` bereit. Verwenden Sie wie bei `vector`die [Clear](reference/concurrent-vector-class.md#clear) -Methode, um alle Elemente aus einem `concurrent_vector`-Objekt zu entfernen.

- Die `concurrent_vector`-Klasse speichert ihre Elemente nicht im Arbeitsspeicher zusammenhängend. Daher können Sie die `concurrent_vector`-Klasse nicht in allen Möglichkeiten verwenden, wie Sie ein Array verwenden können. Beispielsweise erzeugt der `&v[0]+2` Ausdruck für eine Variable mit dem Namen `v` vom Typ `concurrent_vector`ein nicht definiertes Verhalten.

- Die `concurrent_vector`-Klasse definiert die Methoden [grow_by](reference/concurrent-vector-class.md#grow_by) und [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) . Diese Methoden ähneln der [Größe](reference/concurrent-vector-class.md#resize) -Methode, mit dem Unterschied, dass Sie Parallelitäts sicher sind.

- Ein `concurrent_vector` Objekt verlagert seine Elemente nicht, wenn Sie es anfügen oder die Größe ändern. Dadurch können vorhandene Zeiger und Iteratoren während gleichzeitiger Vorgänge gültig bleiben.

- Die Laufzeit definiert keine spezialisierte Version von `concurrent_vector` für den Typ `bool`.

### <a name="vector-safety"></a>Parallelitäts sichere Vorgänge

Alle Methoden, die an die Größe eines `concurrent_vector` Objekts anfügen oder die Größe vergrößern oder auf ein Element in einem `concurrent_vector` Objekt zugreifen, sind Parallelitäts sicher. Die Parallelitäts Sicherheit bedeutet, dass Zeiger oder Iteratoren immer gültig sind. Es handelt sich nicht um eine Garantie der Element Initialisierung oder einer bestimmten Durchlauf Reihenfolge. Die Ausnahme von dieser Regel ist die `resize` Methode.

In der folgenden Tabelle sind die allgemeinen `concurrent_vector` Methoden und Operatoren aufgeführt, die Parallelitäts sicher sind.

||||
|-|-|-|
|[at](reference/concurrent-vector-class.md#at)|[end](reference/concurrent-vector-class.md#end)|[operator[]](reference/concurrent-vector-class.md#operator_at)|
|[begin](reference/concurrent-vector-class.md#begin)|[Vorderseite](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)|
|[Rückseite](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)|
|[Kapazität](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)|
|[empty](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[size](reference/concurrent-vector-class.md#size)|

Vorgänge, die die Laufzeit für die Kompatibilität mit C++ der Standard Bibliothek bereitstellt, z. b. `reserve`, sind nicht Parallelitäts sicher. In der folgenden Tabelle sind die allgemeinen Methoden und Operatoren aufgeführt, die nicht Parallelitäts sicher sind.

|||
|-|-|
|[assign](reference/concurrent-vector-class.md#assign)|[reserve](reference/concurrent-vector-class.md#reserve)|
|[Löschen](reference/concurrent-vector-class.md#clear)|[resize](reference/concurrent-vector-class.md#resize)|
|[operator=](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|

Vorgänge, bei denen der Wert vorhandener Elemente geändert wird, sind nicht Parallelitäts sicher. Verwenden Sie ein Synchronisierungs Objekt, z. b. ein [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) Objekt, um gleichzeitige Lese-und Schreibvorgänge mit demselben Datenelement zu synchronisieren. Weitere Informationen zu Synchronisierungs Objekten finden Sie unter [Synchronisierungs Datenstrukturen](../../parallel/concrt/synchronization-data-structures.md).

Wenn Sie vorhandenen Code konvertieren, der `vector` verwendet, um `concurrent_vector`zu verwenden, können gleichzeitige Vorgänge bewirken, dass sich das Verhalten der Anwendung ändert. Stellen Sie sich z. b. das folgende Programm vor, das gleichzeitig zwei Aufgaben für ein `concurrent_vector` Objekt ausführt. Der erste Task fügt weitere Elemente an ein `concurrent_vector` Objekt an. Der zweite Task berechnet die Summe aller Elemente im selben-Objekt.

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

Obwohl die `end`-Methode Parallelitäts sicher ist, bewirkt ein gleichzeitiger Aufrufe der [push_back](reference/concurrent-vector-class.md#push_back) -Methode, dass der von `end` zurückgegebene Wert geändert wird. Die Anzahl der Elemente, die der Iterator durchläuft, ist unbestimmt. Daher kann dieses Programm jedes Mal, wenn Sie es ausführen, ein anderes Ergebnis liefern. Wenn der Elementtyp nicht trivial ist, kann eine Racebedingung zwischen `push_back` und `end` aufrufen bestehen. Die `end`-Methode kann ein Element zurückgeben, das zugeordnet, aber nicht vollständig initialisiert wurde.

### <a name="vector-exceptions"></a>Ausnahme Sicherheit

Wenn eine Vergrößerung oder ein Zuweisungs Vorgang eine Ausnahme auslöst, wird der Status des `concurrent_vector` Objekts ungültig. Das Verhalten eines `concurrent_vector` Objekts, das sich in einem ungültigen Zustand befindet, ist nicht definiert, sofern nicht anders angegeben. Der Dekonstruktor gibt jedoch immer den Speicher frei, den das Objekt zuordnet, auch wenn sich das Objekt in einem ungültigen Zustand befindet.

Der Datentyp der Vektor Elemente (`T`) muss die folgenden Anforderungen erfüllen. Andernfalls ist das Verhalten der `concurrent_vector` Klasse nicht definiert.

- Der Dekonstruktor darf nicht auslösen.

- Wenn der Standard-oder Kopierkonstruktor auslöst, darf der Dekonstruktor nicht mit dem `virtual`-Schlüsselwort deklariert werden, und er muss ordnungsgemäß mit NULL initialisiertem Arbeitsspeicher funktionieren.

[[Nach oben](#top)]

## <a name="queue"></a>Concurrent_queue-Klasse

Die Klasse " [parallelcurrency:: Concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) " ermöglicht Ihnen genau wie die [Std:: Queue](../../standard-library/queue-class.md) -Klasse den Zugriff auf Ihre Front-und Back-Elemente. Die `concurrent_queue`-Klasse ermöglicht Parallelitäts sichere Einreihen in Warteschlangen-und Dequeue-Vorgänge. Die Parallelitäts Sicherheit bedeutet, dass Zeiger oder Iteratoren immer gültig sind. Es handelt sich nicht um eine Garantie der Element Initialisierung oder einer bestimmten Durchlauf Reihenfolge. Die `concurrent_queue`-Klasse bietet auch iteratorunterstützung, die nicht Parallelitäts sicher ist.

### <a name="queue-differences"></a>Unterschiede zwischen Concurrent_queue und Warteschlange

Die `concurrent_queue`-Klasse ähnelt der `queue`-Klasse. Die folgenden Punkte veranschaulichen, wo sich `concurrent_queue` von `queue`unterscheidet:

- Enqueue-und Dequeue-Vorgänge für ein `concurrent_queue` Objekt sind Parallelitäts sicher.

- Die `concurrent_queue`-Klasse stellt iteratorunterstützung bereit, die nicht Parallelitäts sicher ist.

- Die `concurrent_queue`-Klasse stellt nicht die Methoden `front` oder `pop` bereit. Die `concurrent_queue`-Klasse ersetzt diese Methoden durch Definieren der [try_pop](reference/concurrent-queue-class.md#try_pop) -Methode.

- Die `concurrent_queue`-Klasse stellt die `back`-Methode nicht bereit. Daher können Sie nicht auf das Ende der Warteschlange verweisen.

- Die `concurrent_queue`-Klasse stellt die [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) -Methode anstelle der `size`-Methode bereit. Die `unsafe_size`-Methode ist nicht Parallelitäts sicher.

### <a name="queue-safety"></a>Parallelitäts sichere Vorgänge

Alle Methoden, die in `concurrent_queue` eine Warteschlange eingereiht bzw. aus dieser entfernt werden, sind neben läufigkeits sicher. Die Parallelitäts Sicherheit bedeutet, dass Zeiger oder Iteratoren immer gültig sind. Es handelt sich nicht um eine Garantie der Element Initialisierung oder einer bestimmten Durchlauf Reihenfolge.

In der folgenden Tabelle sind die allgemeinen `concurrent_queue` Methoden und Operatoren aufgeführt, die Parallelitäts sicher sind.

|||
|-|-|
|[empty](reference/concurrent-queue-class.md#empty)|[push](reference/concurrent-queue-class.md#push)|
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|

Obwohl die `empty`-Methode Parallelitäts sicher ist, kann ein paralleler Vorgang dazu führen, dass die Warteschlange vergrößert oder verkleinert wird, bevor die `empty`-Methode zurückgegeben wird.

In der folgenden Tabelle sind die allgemeinen Methoden und Operatoren aufgeführt, die nicht Parallelitäts sicher sind.

|||
|-|-|
|[Löschen](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|

### <a name="queue-iterators"></a>Iteratorunterstützung

Der `concurrent_queue` stellt Iteratoren bereit, die nicht Parallelitäts sicher sind. Es wird empfohlen, diese Iteratoren nur zum Debuggen zu verwenden.

Ein `concurrent_queue` Iterator durchläuft nur Elemente in Vorwärtsrichtung. In der folgenden Tabelle sind die Operatoren aufgeführt, die jeder Iterator unterstützt.

|Operator|BESCHREIBUNG|
|--------------|-----------------|
|`operator++`|Wechselt zum nächsten Element in der Warteschlange. Dieser Operator ist überladen, um die Semantik für die präinkrement-und Postinkrement bereitzustellen.|
|`operator*`|Ruft einen Verweis auf das aktuelle Element ab.|
|`operator->`|Ruft einen Zeiger auf das aktuelle Element ab.|

[[Nach oben](#top)]

## <a name="unordered_map"></a>concurrent_unordered_map-Klasse

Die Klasse " [parallelcurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) " ist eine assoziative Container Klasse, die genau wie die [Std:: unordered_map](../../standard-library/unordered-map-class.md) -Klasse eine Element Sequenz variabler Länge vom Typ [Std::p Air\<Konstanten Schlüssel, Ty >](../../standard-library/pair-structure.md)steuert. Stellen Sie sich eine ungeordnete Zuordnung als Wörterbuch vor, dem Sie ein Schlüssel-Wert-Paar hinzufügen können, oder suchen Sie nach einem Wert nach Schlüssel. Diese Klasse ist hilfreich, wenn Sie über mehrere Threads oder Tasks verfügen, die gleichzeitig auf einen freigegebenen Container zugreifen, ihn einfügen oder aktualisieren müssen.

Das folgende Beispiel zeigt die grundlegende Struktur für die Verwendung von `concurrent_unordered_map`. In diesem Beispiel werden Zeichen Schlüssel im Bereich [' a ', ' i '] eingefügt. Da die Reihenfolge der Vorgänge nicht bestimmt ist, wird der endgültige Wert für jeden Schlüssel ebenfalls nicht bestimmt. Es ist jedoch sicher, dass die Einfügungen parallel durchgeführt werden.

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

Ein Beispiel, in dem `concurrent_unordered_map` verwendet wird, um eine Zuordnung auszuführen und den Vorgang parallel zu reduzieren, finden Sie unter Gewusst [wie: Paralleles Ausführen von Map-und Reduzierungs Vorgängen](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).

### <a name="map-differences"></a>Unterschiede zwischen concurrent_unordered_map und unordered_map

Die `concurrent_unordered_map`-Klasse ähnelt der `unordered_map`-Klasse. Die folgenden Punkte veranschaulichen, wo sich `concurrent_unordered_map` von `unordered_map`unterscheidet:

- Die Methoden `erase`, `bucket`, `bucket_count`und `bucket_size` heißen `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`bzw. `unsafe_bucket_size`. Die `unsafe_` Benennungs Konvention gibt an, dass diese Methoden nicht Parallelitäts sicher sind. Weitere Informationen zur Parallelitäts Sicherheit finden Sie unter Parallelitäts [sichere Vorgänge](#map-safety).

- Einfügevorgänge machen vorhandene Zeiger oder Iteratoren nicht ungültig und ändern nicht die Reihenfolge der Elemente, die bereits in der Zuordnung vorhanden sind. INSERT-und traversiingvorgänge können gleichzeitig erfolgen.

- `concurrent_unordered_map` unterstützt nur Forward-Iterationen.

- Durch Einfügen werden die Iteratoren, die von `equal_range`zurückgegeben werden, nicht ungültig oder aktualisiert. Beim Einfügen können am Ende des Bereichs ungleiche Elemente angefügt werden. Der BEGIN-Iterator zeigt auf ein Gleichheits Element.

Um Deadlocks zu vermeiden, bietet keine Methode `concurrent_unordered_map` eine Sperre, wenn Sie die Speicherzuweisung, Hash Funktionen oder anderen benutzerdefinierten Code aufruft. Außerdem müssen Sie sicherstellen, dass die Hash Funktion immer gleichwertige Schlüssel mit demselben Wert auswertet. Die besten Hash Funktionen verteilen Schlüssel gleichmäßig über den Hash Code Bereich.

### <a name="map-safety"></a>Parallelitäts sichere Vorgänge

Die `concurrent_unordered_map`-Klasse ermöglicht Parallelitäts sichere Einfüge-und Element Zugriffs Vorgänge. Einfügevorgänge machen vorhandene Zeiger oder Iteratoren ungültig. Iteratorzugriffe und Durchlauf Vorgänge sind ebenfalls Parallelitäts sicher. Die Parallelitäts Sicherheit bedeutet, dass Zeiger oder Iteratoren immer gültig sind. Es handelt sich nicht um eine Garantie der Element Initialisierung oder einer bestimmten Durchlauf Reihenfolge. In der folgenden Tabelle werden die häufig verwendeten `concurrent_unordered_map` Methoden und Operatoren, die Parallelitäts sicher sind, angezeigt.

|||||
|-|-|-|-|
|[at](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|
|`begin`|`empty`|`get_allocator`|`max_size`|
|`cbegin`|`end`|`hash_function`|[operator[]](reference/concurrent-unordered-map-class.md#operator_at)|
|`cend`|`equal_range`|[insert](reference/concurrent-unordered-map-class.md#insert)|`size`|

Obwohl die `count`-Methode sicher von gleichzeitig ausgeführten Threads aufgerufen werden kann, können unterschiedliche Threads andere Ergebnisse empfangen, wenn ein neuer Wert gleichzeitig in den Container eingefügt wird.

Die folgende Tabelle zeigt die häufig verwendeten Methoden und Operatoren, die nicht Parallelitäts sicher sind.

||||
|-|-|-|
|`clear`|`max_load_factor`|`rehash`|
|`load_factor`|[operator=](reference/concurrent-unordered-map-class.md#operator_eq)

Zusätzlich zu diesen Methoden ist jede Methode, die mit `unsafe_` beginnt, ebenfalls nicht Parallelitäts sicher.

[[Nach oben](#top)]

## <a name="unordered_multimap"></a>concurrent_unordered_multimap-Klasse

Die Klasse " [parallelcurrency:: concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) " ähnelt der `concurrent_unordered_map` Klasse, mit der Ausnahme, dass mehrere Werte dem gleichen Schlüssel zugeordnet werden können. Dies unterscheidet sich auch von `concurrent_unordered_map` auf folgende Weise:

- Die [concurrent_unordered_multimap:: Insert](reference/concurrent-unordered-multimap-class.md#insert) -Methode gibt einen Iterator anstelle von `std::pair<iterator, bool>`zurück.

- Die `concurrent_unordered_multimap`-Klasse stellt weder `operator[]` noch die `at`-Methode bereit.

Das folgende Beispiel zeigt die grundlegende Struktur für die Verwendung von `concurrent_unordered_multimap`. In diesem Beispiel werden Zeichen Schlüssel im Bereich [' a ', ' i '] eingefügt. `concurrent_unordered_multimap` ermöglicht es, dass ein Schlüssel mehrere Werte hat.

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[[Nach oben](#top)]

## <a name="unordered_set"></a>concurrent_unordered_set-Klasse

Die Klasse " [parallelcurrency:: concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) " ähnelt der `concurrent_unordered_map` Klasse, mit der Ausnahme, dass Sie Werte anstelle von Schlüssel-Wert-Paaren verwaltet. Die `concurrent_unordered_set`-Klasse stellt weder `operator[]` noch die `at`-Methode bereit.

Das folgende Beispiel zeigt die grundlegende Struktur für die Verwendung von `concurrent_unordered_set`. In diesem Beispiel werden Zeichen Werte im Bereich [' a ', ' i '] eingefügt. Es ist sicher, dass die Einfügungen parallel durchgeführt werden.

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[[Nach oben](#top)]

## <a name="unordered_multiset"></a>concurrent_unordered_multiset-Klasse

Die Klasse " [parallelcurrency:: concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) " ähnelt der `concurrent_unordered_set` Klasse, mit der Ausnahme, dass Sie doppelte Werte zulässt. Dies unterscheidet sich auch von `concurrent_unordered_set` auf folgende Weise:

- Die [concurrent_unordered_multiset:: Insert](reference/concurrent-unordered-multiset-class.md#insert) -Methode gibt einen Iterator anstelle von `std::pair<iterator, bool>`zurück.

- Die `concurrent_unordered_multiset`-Klasse stellt weder `operator[]` noch die `at`-Methode bereit.

Das folgende Beispiel zeigt die grundlegende Struktur für die Verwendung von `concurrent_unordered_multiset`. In diesem Beispiel werden Zeichen Werte im Bereich [' a ', ' i '] eingefügt. `concurrent_unordered_multiset` ermöglicht, dass ein Wert mehrmals auftritt.

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[[Nach oben](#top)]

## <a name="combinable"></a>combinable-Klasse

Die Klasse " [parallelcurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) " stellt einen wiederverwendbaren lokalen Thread Speicher bereit, mit dem Sie differenzierte Berechnungen ausführen und diese Berechnungen anschließend in ein Endergebnis zusammenführen können. Stellen Sie sich ein `combinable`-Objekt wie eine Reduktionsvariable vor.

Die `combinable`-Klasse ist nützlich, wenn Sie über eine Ressource verfügen, die von mehreren Threads oder Tasks gemeinsam genutzt wird. Mit der `combinable`-Klasse können Sie den freigegebenen Zustand eliminieren, indem Sie den Zugriff auf freigegebene Ressourcen auf Sperr freie Weise bereitstellen. Daher bietet diese Klasse eine Alternative zur Verwendung eines Synchronisierungs Mechanismus, z. b. eines Mutex, um den Zugriff auf freigegebene Daten aus mehreren Threads zu synchronisieren.

### <a name="combinable-features"></a>Methoden und Features

In der folgenden Tabelle werden einige der wichtigen Methoden der `combinable`-Klasse angezeigt. Weitere Informationen zu allen `combinable`-Klassen Methoden finden Sie unter [combinable Class](../../parallel/concrt/reference/combinable-class.md).

|Methode|BESCHREIBUNG|
|------------|-----------------|
|[local](reference/combinable-class.md#local)|Ruft einen Verweis auf die lokale Variable ab, die dem aktuellen Thread Kontext zugeordnet ist.|
|[Löschen](reference/combinable-class.md#clear)|Entfernt alle lokalen Thread Variablen aus dem `combinable`-Objekt.|
|[combine](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|Verwendet die bereitgestellte Combine-Funktion, um einen endgültigen Wert aus dem Satz aller Thread lokalen Berechnungen zu generieren.|

Die `combinable`-Klasse ist eine Vorlagen Klasse, die nach dem abschließenden zusammengeführten Ergebnis parametrisiert wird. Wenn Sie den Standardkonstruktor aufrufen, muss der `T` Template-Parametertyp über einen Standardkonstruktor und einen Kopierkonstruktor verfügen. Wenn der `T` Template-Parametertyp nicht über einen Standardkonstruktor verfügt, müssen Sie die überladene Version des Konstruktors aufrufen, der eine Initialisierungsfunktion als Parameter annimmt.

Sie können zusätzliche Daten in einem `combinable` Objekt speichern, nachdem Sie die Methoden zum [kombinieren](reference/combinable-class.md#combine) oder [combine_each](reference/combinable-class.md#combine_each) aufgerufen haben. Sie können auch die Methoden `combine` und `combine_each` mehrmals aufzurufen. Wenn kein lokaler Wert in einem `combinable`-Objekt geändert wird, führen die Methoden `combine` und `combine_each` jedes Mal, wenn Sie aufgerufen werden, zum gleichen Ergebnis.

### <a name="combinable-examples"></a> Beispiele

Beispiele zur Verwendung der `combinable`-Klasse finden Sie in den folgenden Themen:

- [Vorgehensweise: Verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [Vorgehensweise: Kombinieren von Gruppen mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[[Nach oben](#top)]

## <a name="related-topics"></a>Verwandte Themen

[Vorgehensweise: Erhöhen der Effizienz mithilfe von parallelen Containern](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
Zeigt, wie parallele Container verwendet werden, um Daten effizient zu speichern und parallel auf Sie zuzugreifen.

[Vorgehensweise: Verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
Zeigt, wie die `combinable`-Klasse verwendet wird, um den Freigabe Zustand zu eliminieren und damit die Leistung zu verbessern.

[Vorgehensweise: Kombinieren von Gruppen mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
Zeigt, wie eine `combine` Funktion verwendet wird, um Thread lokale Datensätze zusammenzuführen.

[Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Beschreibt die ppl, die ein Imperatives Programmiermodell bereitstellt, das die Skalierbarkeit und Benutzerfreundlichkeit für die Entwicklung gleichzeitiger Anwendungen fördert.

## <a name="reference"></a>Verweis

[concurrent_vector-Klasse](../../parallel/concrt/reference/concurrent-vector-class.md)

[concurrent_queue-Klasse](../../parallel/concrt/reference/concurrent-queue-class.md)

[concurrent_unordered_map-Klasse](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[concurrent_unordered_multimap-Klasse](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[concurrent_unordered_set-Klasse](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[concurrent_unordered_multiset-Klasse](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[combinable-Klasse](../../parallel/concrt/reference/combinable-class.md)
