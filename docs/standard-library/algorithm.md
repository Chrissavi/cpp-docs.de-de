---
title: '&lt;algorithm&gt;'
ms.date: 11/04/2016
f1_keywords:
- <algorithm>
helpviewer_keywords:
- algorithm header [C++]
- C++ Standard Library, algorithms
- <algorithm> header
ms.assetid: 19f97711-7a67-4a65-8fd1-9a2bd3ca327d
ms.openlocfilehash: 0b9b259d49808002442492ce2912b4f9aa96d2b8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456501"
---
# <a name="ltalgorithmgt"></a>&lt;algorithm&gt;

Definiert C++-Standardbibliothek-Containervorlagenfunktionen, die Algorithmen ausführen.

## <a name="syntax"></a>Syntax

```cpp
(see relevant links below for specific algorithm syntax)
```

> [!NOTE]
> Der \<Algorithmus > Bibliothek verwendet auch die `#include <initializer_list>` -Anweisung.

## <a name="remarks"></a>Hinweise

Die C++-Standardbibliotheksalgorithmen sind generisch, da sie für verschiedene Datenstrukturen ausgeführt werden können. Die Datenstrukturen, für die sie ausgeführt werden können, umfassen nicht nur die C++-Standardbibliothek-Containerklassen wie `vector` und `list`, sondern auch programmdefinierte Datenstrukturen und Arrays von Elementen, die den Anforderungen eines bestimmten Algorithmus entsprechen. C++-Standardbibliotheksalgorithmen erzielen dieses Maß an Allgemeingültigkeit, indem sie indirekt über Iteratoren auf die Elemente eines Containers zugreifen und diese durchlaufen.

Die C++-Standardbibliothek-Iteratorbereiche für Algorithmen werden in der Regel durch ihre Start- oder Zielpositionen angegeben. Die Bereiche, die angegeben werden, müssen in dem Sinne gültig sein, dass alle Zeiger in den Bereichen dereferenzierbar sind und innerhalb der Sequenzen der einzelnen Bereiche liegen. Die letzte Position muss außerdem von der ersten mittels Zunahme erreichbar sein.

Die C++-Standardbibliothekalgorithmen erweitern die Aktionen, die durch die Vorgänge und die Memberfunktionen jedes C++-Standardbibliothekcontainers unterstützt werden, und lassen das gleichzeitige Arbeiten zum Beispiel mit anderen Typen von Containerobjekten zu. Zwei Suffixe werden verwendet, um Informationen über den Zweck der Algorithmen zu übergeben.

- Das `_if`-Suffix gibt an, dass der Algorithmus mit den Funktionsobjekten verwendet wird, die für die Werte der Elemente statt für die Elemente selbst ausgeführt werden. Der `find_if`-Algorithmus sucht nach Elementen, deren Werte dem Kriterium entsprechen, das durch ein Funktionsobjekt angegeben ist, und der `find`-Algorithmus sucht nach einem bestimmten Wert.

- Das _copy-Suffix gibt an, dass der Algorithmus nicht nur die Werte der Elemente bearbeitet, sondern die geänderten Werte auch in einen Zielbereich kopiert. Der `reverse`-Algorithmus kehrt die Reihenfolge der Elemente innerhalb eines Bereichs um, und der `reverse_copy`-Algorithmus kopiert das Ergebnis außerdem in einen Zielbereich.

C++-Standardbibliotheksalgorithmen werden häufig in Gruppen klassifiziert, die Informationen über ihren Zweck oder ihre Anforderungen angeben. Diese schließen Änderungsalgorithmen ein, die den Wert der Elemente ändern. Im Gegensatz dazu stehen Nichtänderungsalgorithmen, die den Wert nicht ändern. Mit Mutationsalgorithmen wird zwar die Reihenfolge von Elementen geändert, jedoch nicht die Werte ihrer Elemente. Mit Entfernungsalgorithmen können Elemente aus einem Bereich oder aus einer Kopie eines Bereichs entfernt werden. Sortieralgorithmen ordnen die Elemente in einem Bereich auf verschiedene Weise neu an, und sortierte Bereichs Algorithmen agieren nur für Bereiche, deren Elemente auf eine bestimmte Weise sortiert wurden.

Die numerischen C++-Standardbibliotheksalgorithmen, die für die numerische Verarbeitung bereitgestellt werden, verfügen über eine eigene Headerdatei [\<numeric>](../standard-library/numeric.md), und Funktionsobjekte und Adapter werden im Header [\<functional>](../standard-library/functional.md) in Funktionsobjekten definiert, die als Prädikate bezeichnete boolesche Werte zurückgeben. Das binäre Standardprädikat ist der Vergleichs-`operator<`. Im Allgemeinen müssen die zu sortierenden Elemente etwas weniger als vergleichbar sein, sodass für zwei Elemente bestimmt werden kann, dass sie gleichwertig sind (in dem Sinne, dass keins geringer als das andere ist) oder dass eins geringer als das andere ist. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen.

### <a name="function-templates"></a>Funktionsvorlagen

|||
|-|-|
|[adjacent_find](../standard-library/algorithm-functions.md#adjacent_find)|Sucht zwei benachbarte Elemente, die entweder gleich sind oder eine angegebene Bedingung erfüllen.|
|[all_of](../standard-library/algorithm-functions.md#all_of)|Gibt **true** zurück, wenn eine Bedingung bei jedem Element im angegebenen Bereich vorhanden ist.|
|[any_of](../standard-library/algorithm-functions.md#any_of)|Gibt **true** zurück, wenn eine Bedingung mindestens einmal im angegebenen Bereich von Elementen vorhanden ist.|
|[binary_search](../standard-library/algorithm-functions.md#binary_search)|Testet, ob ein Element in einem sortierten Bereich einem angegebenen Wert entspricht oder ihm auf eine von einem binären Prädikat angegebene Weise gleicht.|
|[clamp](../standard-library/algorithm-functions.md#clamp)||
|[copy](../standard-library/algorithm-functions.md#copy)|Weist die Werte von Elementen aus einem Quellbereich einem Zielbereich zu, durchläuft die Quellelementsequenz und weist ihnen vorwärts neue Positionen zu.|
|[copy_backward](../standard-library/algorithm-functions.md#copy_backward)|Weist die Werte von Elementen aus einem Quellbereich einem Zielbereich zu, durchläuft die Quellelementsequenz und weist ihnen rückwärts neue Positionen zu.|
|[copy_if](../standard-library/algorithm-functions.md#copy_if)|Alle Elemente in einem bestimmten Bereich kopieren, die für eine angegebene Bedingung " **true** " testen|
|[copy_n](../standard-library/algorithm-functions.md#copy_n)|Kopiert eine angegebene Anzahl von Elementen.|
|[count](../standard-library/algorithm-functions.md#count)|Gibt die Anzahl von Elementen in einem Bereich zurück, dessen Werte mit einem angegebenen Wert übereinstimmen.|
|[count_if](../standard-library/algorithm-functions.md#count_if)|Gibt die Anzahl von Elementen in einem Bereich zurück, dessen Werte mit einer angegebenen Bedingung übereinstimmen.|
|[equal](../standard-library/algorithm-functions.md#equal)|Vergleicht zwei Bereiche elementweise entweder auf Gleichheit oder Äquivalenz in dem durch ein binäres Prädikat angegebenen Sinn.|
|[equal_range](../standard-library/algorithm-functions.md#equal_range)|Sucht ein Paar Positionen in einem sortierten Bereich, wobei die erste Position kleiner als oder gleich der Position eines bestimmten Elements und die zweite Position größer als die Position des Elements ist. Die Äquivalenz oder Sortierung zur Festlegung der Positionen in der Sequenz kann durch ein binäres Prädikat angegeben werden.|
|[fill](../standard-library/algorithm-functions.md#fill)|Weist den gleichen neuen Wert jedem Element in einem angegebenen Bereich zu.|
|[fill_n](../standard-library/algorithm-functions.md#fill_n)|Weist einer angegebenen Anzahl von Elementen in einem Bereich, der mit einem bestimmten Element beginnt, einen neuen Wert zu.|
|[find](../standard-library/algorithm-functions.md#find)|Sucht die Position des ersten Vorkommens eines Elements in einem Bereich, der einen angegebenen Wert enthält.|
|[find_end](../standard-library/algorithm-functions.md#find_end)|Sucht in einem Bereich nach der letzten Untersequenz, die mit einer angegebenen Sequenz identisch ist oder die in durch ein binäres Prädikat angegebenen Sinne äquivalent ist.|
|[find_first_of](../standard-library/algorithm-functions.md#find_first_of)|Sucht das erste Vorkommen mehrerer Werte innerhalb eines Zielbereichs oder das erste Vorkommen mehrerer Elemente, die wie durch ein binäres Prädikat angegeben mit einem angegebenen Satz der Elemente äquivalent sind.|
|[find_if](../standard-library/algorithm-functions.md#find_if)|Sucht die Position des ersten Vorkommens eines Elements in einem Bereich, der eine bestimmte Bedingung erfüllt.|
|[find_if_not](../standard-library/algorithm-functions.md#find_if_not)|Gibt das erste Element im angegebenen Bereich zurück, der eine Bedingung nicht erfüllt.|
|[for_each](../standard-library/algorithm-functions.md#for_each)|Wendet ein angegebenes Funktionsobjekt auf jedes Element in einer Vorwärtsreihenfolge innerhalb eines Bereichs an und gibt das Funktionsobjekt zurück.|
|[for_each_n](../standard-library/algorithm-functions.md#for_each_n)||
|[generate](../standard-library/algorithm-functions.md#generate)|Weist die Werte, die von einem Funktionsobjekt generiert werden, jedem Element in einem Bereich zu.|
|[generate_n](../standard-library/algorithm-functions.md#generate_n)|Weist die Werte, die von einem Funktionsobjekt generiert werden, einer angegebenen Anzahl von Elementen eines Bereichs zu und kehrt zu der Position zurück, die direkt nach dem letzten zugewiesenen Wert liegt.|
|[includes](../standard-library/algorithm-functions.md#includes)|Testet, ob ein sortierter Bereich alle Elemente enthält, die in einem zweiten sortierten Bereich enthalten sind, wobei das Sortier- oder Äquivalenzkriterium für die Elemente durch ein binäres Prädikat angegeben werden kann.|
|[inplace_merge](../standard-library/algorithm-functions.md#inplace_merge)|Kombiniert die Elemente von zwei aufeinander folgenden sortierten Bereichen in einen einzelnen sortierten Bereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|
|[is_heap](../standard-library/algorithm-functions.md#is_heap)|Gibt **true** zurück, wenn die Elemente im angegebenen Bereich einen Heap bilden.|
|[is_heap_until](../standard-library/algorithm-functions.md#is_heap_until)|Gibt **true** zurück, wenn der angegebene Bereich einen Heap bis zum letzten Element bildet.|
|[is_partitioned](../standard-library/algorithm-functions.md#is_partitioned)|Gibt **true** zurück, wenn alle Elemente im angegebenen Bereich, die für eine Bedingung **true** testen, vor allen Elementen stehen, die **false**testen.|
|[is_permutation](../standard-library/algorithm-functions.md#is_permutation)|Legt fest, ob die Elemente in einem angegebenen Bereich eine gültige Permutation bilden.|
|[is_sorted](../standard-library/algorithm-functions.md#is_sorted)|Gibt **true** zurück, wenn die Elemente im angegebenen Bereich in sortierter Reihenfolge angeordnet sind.|
|[is_sorted_until](../standard-library/algorithm-functions.md#is_sorted_until)|Gibt **true** zurück, wenn die Elemente im angegebenen Bereich in sortierter Reihenfolge angeordnet sind.|
|[iter_swap](../standard-library/algorithm-functions.md#iter_swap)|Tauscht zwei Werte aus, auf die durch ein Paar angegebener Iteratoren verwiesen wird.|
|[lexicographical_compare](../standard-library/algorithm-functions.md#lexicographical_compare)|Vergleicht zwei Sequenzen elementweise, um zu bestimmen, welche der beiden kleiner ist.|
|[lower_bound](../standard-library/algorithm-functions.md#lower_bound)|Sucht die Position des ersten Elements in einem sortierten Bereich, der über einen Wert größer als oder gleich einem angegebenen Wert verfügt. Dabei wird das Sortierkriterium möglicherweise von einen binären Prädikat bestimmt.|
|[make_heap](../standard-library/algorithm-functions.md#make_heap)|Konvertiert Elemente aus einem angegebenen Bereich in einen Heap, in dem das erste Element das größte ist und für den ein Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|
|[max](../standard-library/algorithm-functions.md#max)|Vergleicht zwei Objekte und gibt das größere der beiden zurück, wobei das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.|
|[max_element](../standard-library/algorithm-functions.md#max_element)|Sucht das erste Vorkommen des größten Elements in einem angegebenen Bereich, in dem das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.|
|[merge](../standard-library/algorithm-functions.md#merge)|Kombiniert alle Elemente von zwei sortierten Quellbereichen in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|
|[Min.](../standard-library/algorithm-functions.md#min)|Vergleicht zwei Objekte und gibt das kleinere der beiden zurück, wobei das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.|
|[min_element](../standard-library/algorithm-functions.md#min_element)|Sucht das erste Vorkommen des kleinsten Elements in einem angegebenen Bereich, in dem das Sortierkriterium von einem binären Prädikat angegeben werden kann.|
|[minmax](../standard-library/algorithm-functions.md#minmax)|Vergleicht zwei Eingabeparameter und gibt diese als Paar, in der Reihenfolge "kleiner zu größer", zurück.|
|[minmax_element](../standard-library/algorithm-functions.md#minmax_element)|Führt die Aufgaben aus, die von [min_element](../standard-library/algorithm-functions.md#min_element) und [max_element](../standard-library/algorithm-functions.md#max_element) in einem Aufruf erlegt werden.|
|[mismatch](../standard-library/algorithm-functions.md#mismatch)|Vergleicht zwei Bereiche elementweise entweder auf Gleichheit oder Äquivalenz, wie von einem binären Prädikat angegeben, und sucht die erste Position, an der ein Unterschied auftritt.|
|[&lt;alg&gt; move](../standard-library/algorithm-functions.md#alg_move)|Verschiebt Elemente, die einem angegebenen Bereich zugeordnet sind.|
|[move_backward](../standard-library/algorithm-functions.md#move_backward)|Verschiebt die Elemente eines Iterators in einen anderen. Die Verschiebung beginnt mit dem letzten Element in einem angegebenen Bereich und endet mit dem ersten Element in diesem Bereich.|
|[next_permutation](../standard-library/algorithm-functions.md#next_permutation)|Ordnet die Elemente in einem Bereich neu, damit die ursprüngliche Reihenfolge von der lexikografisch nächsthöheren Permutation ersetzt wird, falls vorhanden, wobei die Bedeutung von „nächsthöher“ durch ein binäres Prädikat angegeben werden kann.|
|[none_of](../standard-library/algorithm-functions.md#none_of)|Gibt **true** zurück, wenn eine Bedingung nicht zwischen Elementen im angegebenen Bereich vorhanden ist.|
|[nth_element](../standard-library/algorithm-functions.md#nth_element)|Partitioniert einen Bereich von Elementen und ermittelt das *n*-te Element der Sequenz im Bereich, sodass alle Elemente davor kleiner oder gleich sind und alle Elemente, die in der Sequenz folgen, größer oder gleich sind.|
|[partial_sort](../standard-library/algorithm-functions.md#partial_sort)|Ordnet eine bestimmte Anzahl von kleineren Elementen in einem Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird.|
|[partial_sort_copy](../standard-library/algorithm-functions.md#partial_sort_copy)|Kopiert Elemente aus einem Quellbereich in einen Zielbereich, in dem die Quellelemente entweder durch kleiner als oder durch ein anderes festgelegtes binäres Prädikat sortiert werden.|
|[partition](../standard-library/algorithm-functions.md#partition)|Klassifiziert Elemente in einem Bereich in zwei zusammenhanglose Sätze, wenn diese Elemente ein unäres Prädikat erfüllen, das denen direkt vorausgeht, die es nicht erfüllen können.|
|[partition_copy](../standard-library/algorithm-functions.md#partition_copy)|Kopiert Elemente, für die eine Bedingung **true** ist, in ein Ziel, für das die Bedingung **false** ist. Die Elemente müssen von einem angegebenen Bereich stammen.|
|[partition_point](../standard-library/algorithm-functions.md#partition_point)|Gibt das erste Element im angegebenen Bereich zurück, der die Bedingung nicht erfüllt. Die Elemente werden so sortiert, dass die, die die Bedingung erfüllen, vor denen angeordnet werden, die die Bedingung nicht erfüllen.|
|[pop_heap](../standard-library/algorithm-functions.md#pop_heap)|Entfernt das größte Element von der Vorderseite eines Heaps und fügt es in die vorletzte Position des Bereichs ein und bildet dann einen neuen Heap aus den übrigen Elementen.|
|[prev_permutation](../standard-library/algorithm-functions.md#prev_permutation)|Ordnet die Elemente in einem Bereich neu, damit die ursprüngliche Reihenfolge von der lexikografisch nächsthöheren Permutation ersetzt wird, falls vorhanden, wobei die Bedeutung von „nächsthöher“ durch ein binäres Prädikat angegeben werden kann.|
|[push_heap](../standard-library/algorithm-functions.md#push_heap)|Fügt ein Element hinzu, das sich am Ende eines Bereichs in einem vorhandenen Heap befindet, der aus den vorherigen Elementen im Bereich besteht.|
|[random_shuffle](../standard-library/algorithm-functions.md#random_shuffle)|Sortiert eine Sequenz von *N* Elementen in einem Bereich in einer von *N*! möglichen per Zufall ausgewählten Anordnungen neu.|
|[remove](../standard-library/algorithm-functions.md#remove)|Eliminiert einen angegebenen Wert von einem angegebenen Bereich, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Bereichs zurückzugeben, der den angegebenen Wert nicht enthält.|
|[remove_copy](../standard-library/algorithm-functions.md#remove_copy)|Kopiert Elemente aus einem Quellbereich in einen Zielbereich, ohne dass Elemente eines angegebenen Werts kopiert werden und ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Zielbereichs zurückzugeben.|
|[remove_copy_if](../standard-library/algorithm-functions.md#remove_copy_if)|Kopiert Elemente aus einem Quellbereich in einen Zielbereich, ohne dass Elemente, die ein Prädikat erfüllen, kopiert werden und ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Zielbereichs zurückzugeben.|
|[remove_if](../standard-library/algorithm-functions.md#remove_if)|Eliminiert Elemente, die ein Prädikat aus einem angegebenen Bereich erfüllen, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Bereichs zurückzugeben, der den angegebenen Wert nicht enthält.|
|[replace](../standard-library/algorithm-functions.md#replace)|Überprüft jedes Element in einem Bereich und ersetzt es, sofern es einem angegebenen Wert entspricht.|
|[replace_copy](../standard-library/algorithm-functions.md#replace_copy)|Überprüft jedes Element in einem Quellbereich und ersetzt es, sofern es einem angegebenen Wert entspricht, während das Ergebnis in einen neuen Zielbereich kopiert wird.|
|[replace_copy_if](../standard-library/algorithm-functions.md#replace_copy_if)|Überprüft jedes Element in einem Quellbereich und ersetzt es, sofern es ein angegebenes Prädikat erfüllt, während das Ergebnis in einen neuen Zielbereich kopiert wird.|
|[replace_if](../standard-library/algorithm-functions.md#replace_if)|Überprüft jedes Element in einem Bereich und ersetzt es, sofern es das angegebene Prädikat erfüllt.|
|[reverse](../standard-library/algorithm-functions.md#reverse)|Kehrt die Reihenfolge der Elemente innerhalb eines Bereichs um.|
|[reverse_copy](../standard-library/algorithm-functions.md#reverse_copy)|Kehrt die Reihenfolge der Elemente in einem Quellbereich beim Kopieren in einen Zielbereich um.|
|[rotate](../standard-library/algorithm-functions.md#rotate)|Vertauscht die Elemente in zwei benachbarten Bereichen.|
|[rotate_copy](../standard-library/algorithm-functions.md#rotate_copy)|Vertauscht die Elemente in zwei benachbarten Bereiche innerhalb eines Quellbereichs und kopiert das Ergebnis in einen Zielbereich.|
|[sample](../standard-library/algorithm-functions.md#sample)||
|[search](../standard-library/algorithm-functions.md#search)|Sucht das erste Vorkommen einer Sequenz in einem Zielbereich, dessen Elemente gleich den Elementen in einer bestimmten Elementsequenz sind oder dessen Elemente äquivalent sind mit den Elementen in der angegebenen Sequenz, wie durch ein binäres Prädikat festgelegt.|
|[search_n](../standard-library/algorithm-functions.md#search_n)|Sucht nach der ersten Untersequenz in einem Bereich, der aus einer angegebenen Anzahl von Elementen besteht, die einen bestimmten Wert oder eine Beziehung zu diesem durch ein binäres Prädikat angegebenen Wert haben.|
|[set_difference](../standard-library/algorithm-functions.md#set_difference)|Vereinigt alle Elemente, die zu dem einen, jedoch nicht zu einem anderen sortierten Quellbereich gehören, in einen einzelnen, sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|
|[set_intersection](../standard-library/algorithm-functions.md#set_intersection)|Vereinigt alle Elemente, die zu beiden sortierten Quellbereichen gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|
|[set_symmetric_difference](../standard-library/algorithm-functions.md#set_symmetric_difference)|Vereinigt alle Elemente, die zu einem, jedoch nicht zu beiden sortierten Quellbereichen gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|
|[set_union](../standard-library/algorithm-functions.md#set_union)|Vereinigt alle Elemente, die mindestens zu einem der beiden sortierten Quellbereiche gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|
|[sort](../standard-library/algorithm-functions.md#sort)|Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird.|
|[shuffle](../standard-library/algorithm-functions.md#shuffle)|Mischt (sortiert) Elemente für einen gegebenen Bereich mithilfe eines Zufallszahlengenerators.|
|[sort_heap](../standard-library/algorithm-functions.md#sort_heap)|Konvertiert einen Heap in einen sortierten Bereich.|
|[stable_partition](../standard-library/algorithm-functions.md#stable_partition)|Klassifiziert Elemente in einem Bereich in zwei zusammenhanglose Sätze, wobei die Elemente, die ein unäres Prädikat erfüllen, direkt den Elementen vorausgehen, die es nicht erfüllen können. Die relative Reihenfolge der äquivalenten Elemente wird dabei beibehalten.|
|[stable_sort](../standard-library/algorithm-functions.md#stable_sort)|Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird, und behält die relative Reihenfolge der äquivalenten Elemente bei.|
|[swap](../standard-library/algorithm-functions.md#swap)|Vertauscht die Werte der Elemente von zwei Objekttypen und weist den Inhalt des ersten Objekts dem zweiten Objekt und den Inhalt des zweiten dem ersten zu.|
|[swap_ranges](../standard-library/algorithm-functions.md#swap_ranges)|Vertauscht die Elemente eines Bereichs mit den Elementen eines anderen gleich großen Bereichs.|
|[transform](../standard-library/algorithm-functions.md#transform)|Wendet ein angegebenes Funktionsobjekt auf jedes Element in einem Quellbereich oder auf ein Elementpaar aus zwei Quellbereichen an und kopiert die Rückgabewerte des Funktionsobjekts in einen Zielbereich.|
|[unique](../standard-library/algorithm-functions.md#unique)|Entfernt doppelte Elemente, die in einem angegebenen Bereich nebeneinander angeordnet sind.|
|[unique_copy](../standard-library/algorithm-functions.md#unique_copy)|Kopiert Elemente aus einem Quellbereich in einen Zielbereich mit Ausnahmen von doppelten Elementen, die nebeneinander angeordnet sind.|
|[upper_bound](../standard-library/algorithm-functions.md#upper_bound)|Sucht die Position des ersten Elements in einem sortierten Bereich, der über einen Wert größer als einen angegebenen Wert verfügt. Dabei wird das Sortierkriterium möglicherweise von einen binären Prädikat bestimmt.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
