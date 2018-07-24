---
title: '&lt;Algorithmus&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- algorithm/std::adjacent_find
- algorithm/std::all_of
- algorithm/std::any_of
- algorithm/std::binary_search
- algorithm/std::copy
- algorithm/std::copy_backward
- algorithm/std::copy_if
- algorithm/std::copy_n
- algorithm/std::equal
- algorithm/std::equal_range
- algorithm/std::fill
- algorithm/std::fill_n
- algorithm/std::find
- algorithm/std::find_end
- algorithm/std::find_first_of
- algorithm/std::find_if
- algorithm/std::find_if_not
- algorithm/std::for_each
- algorithm/std::generate
- algorithm/std::generate_n
- algorithm/std::includes
- algorithm/std::inplace_merge
- algorithm/std::is_heap
- algorithm/std::is_heap_until
- algorithm/std::is_partitioned
- algorithm/std::is_permutation
- algorithm/std::is_sorted
- algorithm/std::is_sorted_until
- algorithm/std::iter_swap
- algorithm/std::lexicographical_compare
- algorithm/std::lower_bound
- algorithm/std::make_heap
- algorithm/std::max
- algorithm/std::max_element
- algorithm/std::merge
- algorithm/std::min
- algorithm/std::minmax
- algorithm/std::minmax_element
- algorithm/std::min_element
- algorithm/std::mismatch
- algorithm/std::move
- algorithm/std::move_backward
- algorithm/std::next_permutation
- algorithm/std::none_of
- algorithm/std::nth_element
- algorithm/std::partial_sort
- algorithm/std::partial_sort_copy
- algorithm/std::partition
- algorithm/std::partition_point
- algorithm/std::pop_heap
- algorithm/std::prev_permutation
- algorithm/std::push_heap
- algorithm/std::random_shuffle
- algorithm/std::remove
- algorithm/std::remove_copy
- algorithm/std::remove_copy_if
- algorithm/std::remove_if
- algorithm/std::replace
- algorithm/std::replace_copy
- algorithm/std::replace_copy_if
- algorithm/std::replace_if
- algorithm/std::reverse
- algorithm/std::reverse_copy
- algorithm/std::rotate
- algorithm/std::rotate_copy
- algorithm/std::search
- algorithm/std::search_n
- algorithm/std::set_difference
- algorithm/std::set_intersection
- algorithm/std::set_symmetric_difference
- algorithm/std::set_union
- algorithm/std::shuffle
- algorithm/std::sort
- algorithm/std::sort_heap
- algorithm/std::stable_partition
- algorithm/std::stable_sort
- algorithm/std::swap_ranges
- algorithm/std::transform
- algorithm/std::unique
- algorithm/std::unique_copy
- algorithm/std::upper_bound
- xutility/std::copy
- xutility/std::copy_backward
- xutility/std::copy_n
- xutility/std::count
- xutility/std::equal
- xutility/std::fill
- xutility/std::fill_n
- xutility/std::find
- xutility/std::is_permutation
- xutility/std::lexicographical_compare
- xutility/std::move
- xutility/std::move_backward
- xutility/std::reverse
- xutility/std::rotate
- algorithm/std::count_if
- algorithm/std::partition_copy
- algorithm/std::swap
dev_langs:
- C++
ms.assetid: c10b0c65-410c-4c83-abf8-8b7f61bba8d0
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::adjacent_find [C++]
- std::all_of [C++]
- std::any_of [C++]
- std::binary_search [C++]
- std::copy [C++]
- std::copy_backward [C++]
- std::copy_if [C++]
- std::copy_n [C++]
- std::equal [C++]
- std::equal_range [C++]
- std::fill [C++]
- std::fill_n [C++]
- std::find [C++]
- std::find_end [C++]
- std::find_first_of [C++]
- std::find_if [C++]
- std::find_if_not [C++]
- std::for_each [C++]
- std::generate [C++]
- std::generate_n [C++]
- std::includes [C++]
- std::inplace_merge [C++]
- std::is_heap [C++]
- std::is_heap_until [C++]
- std::is_partitioned [C++]
- std::is_permutation [C++]
- std::is_sorted [C++]
- std::is_sorted_until [C++]
- std::iter_swap [C++]
- std::lexicographical_compare [C++]
- std::lower_bound [C++]
- std::make_heap [C++]
- std::max [C++]
- std::max_element [C++]
- std::merge [C++]
- std::min [C++]
- std::minmax [C++]
- std::minmax_element [C++]
- std::min_element [C++]
- std::mismatch [C++]
- std::move [C++]
- std::move_backward [C++]
- std::next_permutation [C++]
- std::none_of [C++]
- std::nth_element [C++]
- std::partial_sort [C++]
- std::partial_sort_copy [C++]
- std::partition [C++]
- std::partition_point [C++]
- std::pop_heap [C++]
- std::prev_permutation [C++]
- std::push_heap [C++]
- std::random_shuffle [C++]
- std::remove [C++]
- std::remove_copy [C++]
- std::remove_copy_if [C++]
- std::remove_if [C++]
- std::replace [C++]
- std::replace_copy [C++]
- std::replace_copy_if [C++]
- std::replace_if [C++]
- std::reverse [C++]
- std::reverse_copy [C++]
- std::rotate [C++]
- std::rotate_copy [C++]
- std::search [C++]
- std::search_n [C++]
- std::set_difference [C++]
- std::set_intersection [C++]
- std::set_symmetric_difference [C++]
- std::set_union [C++]
- std::shuffle [C++]
- std::sort [C++]
- std::sort_heap [C++]
- std::stable_partition [C++]
- std::stable_sort [C++]
- std::swap_ranges [C++]
- std::transform [C++]
- std::unique [C++]
- std::unique_copy [C++]
- std::upper_bound [C++]
- std::copy [C++]
- std::copy_backward [C++]
- std::copy_n [C++]
- std::count [C++]
- std::equal [C++]
- std::fill [C++]
- std::fill_n [C++]
- std::find [C++]
- std::is_permutation [C++]
- std::lexicographical_compare [C++]
- std::move [C++]
- std::move_backward [C++]
- std::reverse [C++]
- std::rotate [C++]
- std::count_if [C++]
- std::partition_copy [C++]
- std::swap [C++]
ms.workload:
- cplusplus
ms.openlocfilehash: d905c8208bef98d584d3052c242de1ac127a4830
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2018
ms.locfileid: "39209299"
---
# <a name="ltalgorithmgt-functions"></a>&lt;Algorithmusfunktionen&gt;

||||
|-|-|-|
|[move](#alg_move)|[adjacent_find](#adjacent_find)|[all_of](#all_of)|
|[any_of](#any_of)|[binary_search](#binary_search)|[copy](#copy)|
|[copy_backward](#copy_backward)|[copy_if](#copy_if)|[copy_n](#copy_n)|
|[count](#count)|[count_if](#count_if)|[equal](#equal)|
|[equal_range](#equal_range)|[fill](#fill)|[fill_n](#fill_n)|
|[find](#find)|[find_end](#find_end)|[find_first_of](#find_first_of)|
|[find_if](#find_if)|[find_if_not](#find_if_not)|[for_each](#for_each)|
|[generate](#generate)|[generate_n](#generate_n)|[includes](#includes)|
|[inplace_merge](#inplace_merge)|[is_heap](#is_heap)|[is_heap_until](#is_heap_until)|
|[is_partitioned](#is_partitioned)|[is_permutation](#is_permutation)|[is_sorted](#is_sorted)|
|[is_sorted_until](#is_sorted_until)|[iter_swap](#iter_swap)|[lexicographical_compare](#lexicographical_compare)|
|[lower_bound](#lower_bound)|[make_heap](#make_heap)|[max](#max)|
|[max_element](#max_element)|[merge](#merge)|[Min.](#min)|
|[min_element](#min_element)|[minmax](#minmax)|[minmax_element](#minmax_element)|
|[mismatch](#mismatch)|[move_backward](#move_backward)|[next_permutation](#next_permutation)|
|[none_of](#none_of)|[nth_element](#nth_element)|[partial_sort](#partial_sort)|
|[partial_sort_copy](#partial_sort_copy)|[partition](#partition)|[partition_copy](#partition_copy)|
|[partition_point](#partition_point)|[pop_heap](#pop_heap)|[prev_permutation](#prev_permutation)|
|[push_heap](#push_heap)|[random_shuffle](#random_shuffle)|[remove](#remove)|
|[remove_copy](#remove_copy)|[remove_copy_if](#remove_copy_if)|[remove_if](#remove_if)|
|[replace](#replace)|[replace_copy](#replace_copy)|[replace_copy_if](#replace_copy_if)|
|[replace_if](#replace_if)|[reverse](#reverse)|[reverse_copy](#reverse_copy)|
|[rotate](#rotate)|[rotate_copy](#rotate_copy)|[search](#search)|
|[search_n](#search_n)|[set_difference](#set_difference)|[set_intersection](#set_intersection)|
|[set_symmetric_difference](#set_symmetric_difference)|[set_union](#set_union)|[sort](#sort)|
|[sort_heap](#sort_heap)|[stable_partition](#stable_partition)|[stable_sort](#stable_sort)|
|[shuffle](#shuffle)|[swap](#swap)|[swap_ranges](#swap_ranges)|
|[transform](#transform)|[unique](#unique)|[unique_copy](#unique_copy)|
|[upper_bound](#upper_bound)|

## <a name="adjacent_find"></a> adjacent_find

Sucht zwei benachbarte Elemente, die entweder gleich sind oder eine angegebene Bedingung erfüllen.

```cpp
template<class ForwardIterator>
    ForwardIterator adjacent_find(
        ForwardIterator first,
        ForwardIterator last);

template<class ForwardIterator , class BinaryPredicate>
    ForwardIterator adjacent_find(
        ForwardIterator first,
        ForwardIterator last,
        BinaryPredicate comp);
```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der die Position des ersten Elements im Bereich, gesucht werden soll.

*letzte* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich, gesucht werden soll.

*Comp* das binäre Prädikat, sodass die Bedingung, die durch die Werte der benachbarten Elemente im zu durchsuchenden Bereich erfüllt werden.

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator für das erste Element des benachbarten Paares, das entweder gleich ist (in der ersten Version) oder das die vorgegebene Bedingung durch das binäre Prädikat erfüllt (in der zweiten Version), vorausgesetzt, dass solch ein Paar von Elementen gefunden wird. Andernfalls einen Iterator, der auf *letzten* zurückgegeben wird.

### <a name="remarks"></a>Hinweise

Der `adjacent_find`-Algorithmus ist ein Algorithmus, der keine Änderungen bezüglich der Abfolge bewirkt. Der zu durchsuchende Bereich muss gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position ist von der Ersten durch Zunahme erreichbar. Die Zeitkomplexität des Algorithmus ist linear zur Anzahl der im Bereich enthaltenen Elemente.

Der zur Bestimmung des Gleichheitszustands zwischen Elementen verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

### <a name="example"></a>Beispiel

```cpp
// alg_adj_fnd.cpp
// compile with: /EHsc
#include <list>
#include <algorithm>
#include <iostream>

// Returns whether second element is twice the first
bool twice (int elem1, int elem2 )
{
   return elem1 * 2 == elem2;
}

int main()
{
   using namespace std;
   list <int> L;
   list <int>::iterator Iter;
   list <int>::iterator result1, result2;

   L.push_back( 50 );
   L.push_back( 40 );
   L.push_back( 10 );
   L.push_back( 20 );
   L.push_back( 20 );

   cout << "L = ( " ;
   for ( Iter = L.begin( ) ; Iter != L.end( ) ; Iter++ )
      cout << *Iter << " ";
   cout << ")" << endl;

   result1 = adjacent_find( L.begin( ), L.end( ) );
   if ( result1 == L.end( ) )
      cout << "There are not two adjacent elements that are equal."
           << endl;
   else
      cout << "There are two adjacent elements that are equal."
           << "\n They have a value of "
           <<  *( result1 ) << "." << endl;

   result2 = adjacent_find( L.begin( ), L.end( ), twice );
   if ( result2 == L.end( ) )
      cout << "There are not two adjacent elements where the "
           << " second is twice the first." << endl;
   else
      cout << "There are two adjacent elements where "
           << "the second is twice the first."
           << "\n They have values of " << *(result2++);
      cout << " & " << *result2 << "." << endl;
}
```

```Output
L = ( 50 40 10 20 20 )
There are two adjacent elements that are equal.
 They have a value of 20.
There are two adjacent elements where the second is twice the first.
 They have values of 10 & 20.
```

## <a name="all_of"></a> all_of

Gibt **"true"** Wenn eine Bedingung auf die einzelnen Elemente im angegebenen Bereich vorhanden ist.

```cpp
template<class InputIterator, class Predicate>
    bool all_of(
        InputIterator first,
        InputIterator last,
        BinaryPredicatecomp);
```

### <a name="parameters"></a>Parameter

*erste* ein Eingabe-Iterator, der angibt, wo Sie anfangen, um eine Bedingung zu überprüfen. Der Iterator zeigt an, an welcher Stelle ein Bereich von Elementen beginnt.

*letzte* ein Eingabe-Iterator, der das Ende des Bereichs von Elementen zu prüfen, bis eine Bedingung angibt.

*Comp* eine Bedingung zu testen. Hierbei handelt es sich um ein benutzerdefiniertes Prädikatfunktionsobjekt, das die Bedingung definiert, die vom zu prüfenden Element erfüllt werden muss. Ein Prädikat akzeptiert ein einzelnes Argument und gibt entweder **TRUE** oder **FALSE** zurück.

### <a name="return-value"></a>Rückgabewert

Gibt **"true"** , wenn die Bedingung in jedem Element im angegebenen Bereich erkannt wird und **"false"** , wenn die Bedingung mindestens einmal nicht erkannt wird.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt **"true"** nur dann für jeden `N` im Bereich von `[0,Last - first)`, das Prädikat `comp(*(_First + N))` ist **"true"**.

## <a name="any_of"></a> any_of

Gibt **"true"** Wenn eine Bedingung mindestens einmal im angegebenen Bereich von Elementen vorhanden ist.

```cpp
template<class InputIterator, class UnaryPredicate>
    bool any_of(
        InputIterator first,
        InputIterator last,
        UnaryPredicate comp);
```

### <a name="parameters"></a>Parameter

*erste* ein Eingabe-Iterator, der angibt, wo Sie anfangen, einen Bereich von Elementen für eine Bedingung zu überprüfen.

*letzte* ein Eingabe-Iterator, der das Ende des Bereichs von Elementen zu prüfen, bis eine Bedingung angibt.

*Comp* eine Bedingung zu testen. Diese wird von einem benutzerdefinierten Prädikatfunktionsobjekt bereitgestellt. Das Prädikat definiert die Bedingung, die das zu prüfende Element erfüllen muss. Ein Prädikat akzeptiert ein einzelnes Argument und gibt entweder **TRUE** oder **FALSE** zurück.

### <a name="return-value"></a>Rückgabewert

Gibt **"true"** , wenn die Bedingung mindestens einmal im angegebenen Bereich erkannt wird **"false"** , wenn die Bedingung nicht erfüllt wird.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt **"true"** nur dann für einige `N` im Bereich

`[0, last - first)`, das Prädikat `comp(*(first + N))` ist "true".

## <a name="binary_search"></a> binary_search

Testet, ob ein Element in einem sortierten Bereich einem angegebenen Wert entspricht oder ihm auf eine von einem binären Prädikat angegebene Weise gleicht.

```cpp
template<class ForwardIterator, class Type>
    bool binary_search(
        ForwardIterator first,
        ForwardIterator last,
        const Type& value);

template<class ForwardIterator,  class Type,  class BinaryPredicate>
    bool binary_search(
        ForwardIterator first,
        ForwardIterator last,
        const Type& value,
        BinaryPredicate comp);

```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der die Position des ersten Elements im Bereich, gesucht werden soll.

*letzte* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich, gesucht werden soll.

*Wert* der erforderlich, um den Wert des Elements oder die abzugleichenden Wert muss mit der vom binären Prädikat angegebenen Elementwert erfüllen die Bedingung.

*Comp* ermitteln benutzerdefiniertes prädikatfunktionsobjekt, das definiert, in dem ein Element kleiner als ein anderes ist. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn ein Element im Bereich gefunden wird, die oder gleich dem angegebenen Wert übereinstimmt, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Der sortierte Quellbereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position muss der innerhalb der Reihenfolge vom ersten von der ersten Position aus durch Zunahme erreichbar sein.

Jeder sortierte Bereich muss als Vorbedingung zur Anwendung des `binary_search`-Algorithmus entsprechend der gleichen Reihenfolge sortiert werden, die vom Algorithmus für die Sortierung der kombinierten Bereiche verwendet wird.

Die Quellbereiche werden von `binary_search` nicht geändert.

Die Werttypen der Forward-Iteratoren müssen weniger als vergleichbar sein, um sortiert zu werden, sodass zwei Elemente möglicherweise als gleichwertig bestimmt werden (in dem Sinne, dass keins geringer als das Andere ist), oder dass eins geringer als das Andere ist. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen.

Die Komplexität dieses Algorithmus ist bei zufallszugriffsiteratoren logarithmisch und andernfalls mit der Anzahl von Schritten proportional zu lineare (`last` - `first`).

### <a name="example"></a>Beispiel

```cpp
// alg_bin_srch.cpp
// compile with: /EHsc
#include <list>
#include <vector>
#include <algorithm>
#include <functional>      // greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser( int elem1, int elem2 )
{
    if (elem1 < 0)
        elem1 = - elem1;
    if (elem2 < 0)
        elem2 = - elem2;
    return elem1 < elem2;
}

int main( )
{
    using namespace std;

    list <int> List1;

    List1.push_back( 50 );
    List1.push_back( 10 );
    List1.push_back( 30 );
    List1.push_back( 20 );
    List1.push_back( 25 );
    List1.push_back( 5 );

    List1.sort();

    cout << "List1 = ( " ;
    for ( auto Iter : List1 )
        cout << Iter << " ";
    cout << ")" << endl;

    // default binary search for 10
    if( binary_search(List1.begin(), List1.end(), 10) )
        cout << "There is an element in list List1 with a value equal to 10."
        << endl;
    else
        cout << "There is no element in list List1 with a value equal to 10."
        << endl;

    // a binary_search under the binary predicate greater
    List1.sort(greater<int>());
    if( binary_search(List1.begin(), List1.end(), 10, greater<int>()) )
        cout << "There is an element in list List1 with a value greater than 10 "
        << "under greater than." << endl;
    else
        cout << "No element in list List1 with a value greater than 10 "
        << "under greater than." << endl;

    // a binary_search under the user-defined binary predicate mod_lesser
    vector<int> v1;

    for( auto i = -2; i <= 4; ++i )
    {
        v1.push_back(i);
    }

    sort(v1.begin(), v1.end(), mod_lesser);

    cout << "Ordered using mod_lesser, vector v1 = ( " ;
    for( auto Iter : v1 )
        cout << Iter << " ";
    cout << ")" << endl;

    if( binary_search(v1.begin(), v1.end(), -3, mod_lesser) )
        cout << "There is an element with a value equivalent to -3 "
        << "under mod_lesser." << endl;
    else
        cout << "There is not an element with a value equivalent to -3 "
        << "under mod_lesser." << endl;
}
```

## <a name="copy"></a>  copy

Weist die Werte von Elementen aus einem Quellbereich einem Zielbereich zu, durchläuft die Quellelementsequenz und weist ihnen vorwärts neue Positionen zu.

```cpp
template<class InputIterator, class OutputIterator>
    OutputIterator copy(
        InputIterator first,
        InputIterator last,
        OutputIterator destBeg);
```

### <a name="parameters"></a>Parameter

*erste* ein eingabeiterator, der die Position des ersten Elements im Quellbereich adressiert.

*letzte* ein eingabeiterator, der die Position direkt hinter dem letzten Element im Quellbereich.

*DestBeg* ein Ausgabeiterator, der die Position des ersten Elements im Zielbereich adressiert.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der die Position direkt hinter dem letzten Element im Zielbereich, d. h., der Iterator adressiert `result` + (*letzten* - *erste*).

### <a name="remarks"></a>Hinweise

Der Quellbereich muss gültig sein, und es muss genügend Speicherplatz am Ziel zur Verfügung stehen, um alle kopierten Elemente aufzunehmen.

Da der Algorithmus die Quellelemente mit dem ersten Element beginnend kopiert, der Zielbereich kann sich überschneiden, mit dem Quellbereich bereitgestellt der *letzten* -Position des Quellbereichs ist nicht enthalten, in das Ziel Bereich. `copy` kann verwendet werden, verschieben Elemente nach links aber nicht das Recht, es sei denn, es keine Überlappung zwischen den Quell- und Zielbereichen gibt. Verwenden Sie den [copy_backward](../standard-library/algorithm-functions.md#copy_backward)-Algorithmus, um Elemente um beliebig viele Positionen nach rechts zu verschieben.

Mit dem `copy`-Algorithmus werden nur die Werte geändert, auf die Iteratoren zeigen. Elementen im Zielbereich werden neuen Werte zugewiesen. Es können keine neuen Elemente erstellt und keine Elemente direkt in einen leeren Container eingefügt werden.

### <a name="example"></a>Beispiel

```cpp
// alg_copy.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
      v1.push_back( 10 * i );

   int ii;
   for ( ii = 0 ; ii <= 10 ; ii++ )
      v2.push_back( 3 * ii );

   cout << "v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // To copy the first 3 elements of v1 into the middle of v2
   copy( v1.begin( ), v1.begin( ) + 3, v2.begin( ) + 4 );

   cout << "v2 with v1 insert = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // To shift the elements inserted into v2 two positions
   // to the left
   copy( v2.begin( )+4, v2.begin( ) + 7, v2.begin( ) + 2 );

   cout << "v2 with shifted insert = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;
}
```

```Output
v1 = ( 0 10 20 30 40 50 )
v2 = ( 0 3 6 9 12 15 18 21 24 27 30 )
v2 with v1 insert = ( 0 3 6 9 0 10 20 21 24 27 30 )
v2 with shifted insert = ( 0 3 0 10 20 10 20 21 24 27 30 )
```

## <a name="copy_backward"></a> copy_backward

Weist die Werte von Elementen aus einem Quellbereich einem Zielbereich zu, durchläuft die Quellelementsequenz und weist ihnen rückwärts neue Positionen zu.

```cpp
template<class BidirectionalIterator1, class BidirectionalIterator2>
    BidirectionalIterator2 copy_backward(
        BidirectionalIterator1 first,
        BidirectionalIterator1 last,
        BidirectionalIterator2 destEnd);
```

### <a name="parameters"></a>Parameter

*erste* ein bidirektionaler Iterator, der die Position des ersten Elements im Quellbereich.

*letzte* ein bidirektionaler Iterator, der die Position direkt hinter dem letzten Element im Quellbereich.

*DestEnd* ein bidirektionaler Iterator, der die Position hinter dem letzten Element im Zielbereich.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der die Position direkt hinter dem letzten Element im Zielbereich, d. h., der Iterator adressiert *DestEnd* -(*letzten* - *erste*).

### <a name="remarks"></a>Hinweise

Der Quellbereich muss gültig sein, und es muss genügend Speicherplatz am Ziel zur Verfügung stehen, um alle kopierten Elemente aufzunehmen.

Der `copy_backward` - Algorithmus erlegt striktere Anforderungen als der Kopieralgorithmus auf. Eingabe- und Ausgabeiteratoren von beiden müssen bidirektional sein.

Die Algorithmen `copy_backward` und [move_backward](../standard-library/algorithm-functions.md#move_backward) sind die einzigen Algorithmen der C++-Standardbibliothek, die den Ausgabebereich mit einem auf das Ende des Zielbereichs weisenden Iterator festlegen.

Da der Algorithmus die Quellelemente mit dem letzten Element beginnend kopiert, der Zielbereich kann sich überschneiden, mit dem Quellbereich bereitgestellt der *erste* -Position des Quellbereichs ist nicht enthalten, in das Ziel Bereich. `copy_backward` kann verwendet werden, um Elemente nach rechts aber nicht nach links zu verschieben, es sei denn, es gibt keine Überlappung zwischen Quell und Zielbereich. Verwenden Sie den [copy](../standard-library/algorithm-functions.md#copy)-Algorithmus, um ein Element beliebig viele Positionen nach links zu verschieben.

Mit dem `copy_backward`-Algorithmus werden nur die Werte geändert, auf die Iteratoren zeigen. Elementen im Zielbereich werden neuen Werte zugewiesen. Es können keine neuen Elemente erstellt und keine Elemente direkt in einen leeren Container eingefügt werden.

### <a name="example"></a>Beispiel

```cpp
// alg_copy_bkwd.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 0 ; i <= 5 ; ++i )
      v1.push_back( 10 * i );

   int ii;
   for ( ii = 0 ; ii <= 10 ; ++ii )
      v2.push_back( 3 * ii );

   cout << "v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; ++Iter1 )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; ++Iter2 )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // To copy_backward the first 3 elements of v1 into the middle of v2
   copy_backward( v1.begin( ), v1.begin( ) + 3, v2.begin( ) + 7 );

   cout << "v2 with v1 insert = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; ++Iter2 )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // To shift the elements inserted into v2 two positions
   // to the right
   copy_backward( v2.begin( )+4, v2.begin( ) + 7, v2.begin( ) + 9 );

   cout << "v2 with shifted insert = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; ++Iter2 )
      cout << *Iter2 << " ";
   cout << ")" << endl;
}
```

## <a name="copy_if"></a> copy_if

In einem Bereich von Elementen, kopiert die Elemente, die **"true"** für die angegebene Bedingung.

```cpp
template<class InputIterator, class OutputIterator, class BinaryPredicate>
    OutputIterator copy_if(
        InputIterator first,
        InputIterator last,
        OutputIterator dest,
        Predicate pred);
```

### <a name="parameters"></a>Parameter

*erste* ein Eingabe-Iterator, der den Beginn eines Bereichs zu prüfen, die Bedingung angibt.

*letzte* ein Eingabe-Iterator, der das Ende des Bereichs angibt.

*Dest* Ausgabeiterator, der das Ziel der kopierten Elemente angibt.

*_Pred* die Bedingung, die mit der jedes Element in dem Bereich getestet. Diese Bedingung wird von einem benutzerdefinierten Prädikatfunktionsobjekt bereitgestellt. Ein Prädikat akzeptiert ein Argument und gibt **"true"** oder **"false"**.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der gleich *Dest* um eins erhöht wird für jedes Element, das die Bedingung erfüllt. Das heißt, der Rückgabewert minus *Dest* entspricht der Anzahl der kopierten Elemente.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion wertet

`if (_Pred(*_First + N)) * dest++ = *(_First + N))`

einmal für jedes `N` im Bereich von `[0, last - first)`, bei strikt ansteigenden Werten von `N` beginnend mit dem niedrigsten Wert. Wenn *Dest* und *erste* Bereiche des Speichers, bestimmt *Dest* darf nicht in den Bereich sein `[ first, last )`.

## <a name="copy_n"></a> copy_n

Kopiert eine angegebene Anzahl von Elementen.

```cpp
template<class InputIterator, class Size, class OutputIterator>
    OutputIterator copy_n(
        InputIterator first,
        Size count,
        OutputIterator dest);
```

### <a name="parameters"></a>Parameter

*erste* ein Eingabe-Iterator, der angibt, an die Elemente kopiert.

*Anzahl* ein signiert oder unsigned Integer-Datentyp gibt die Anzahl von Elementen kopieren.

*Dest* ein Ausgabeiterator, der angibt, an die Elemente kopiert.

### <a name="return-value"></a>Rückgabewert

Gibt einen Ausgabeiterator zurück, in den Elemente kopiert wurden. Es ist identisch mit den zurückgegebenen Wert des dritten Parameters *Dest*.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion wertet `*(dest + N) = *(first + N))` einmal für jedes `N` im Bereich von `[0, count)`, bei strikt ansteigenden Werten von `N` beginnend mit dem niedrigsten Wert. Dann wird `dest + N` zurückgegeben. Wenn *Dest* und *erste* Bereiche des Speichers, bestimmt *Dest* darf nicht in den Bereich sein `[first, last)`.

## <a name="count"></a> count

Gibt die Anzahl von Elementen in einem Bereich zurück, dessen Werte mit einem angegebenen Wert übereinstimmen.

```cpp
template<class InputIterator, class Type>
    typename iterator_traits<InputIterator>::difference_type count(
        InputIterator first,
        InputIterator last,
        const Type& val);
```

### <a name="parameters"></a>Parameter

*erste* ein Eingabe-Iterator, der die Position des ersten Elements im Bereich durchlaufen werden.

*letzte* ein eingabeiterator, der die Position hinter dem letzten Element im Bereich adressiert, die durchlaufen werden.

*Val* den Wert der Elemente, die gezählt werden.

### <a name="return-value"></a>Rückgabewert

Der Differenztyp des der `InputIterator` , die zählt der Anzahl der Elemente im Bereich [ *erste*, *letzten* ) Wert deren *Val*.

### <a name="remarks"></a>Hinweise

Der zur Bestimmung des Gleichheitszustands zwischen einem Element und dem angegebenen Wert verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Dieser Algorithmus wird so generalisiert, dass er Elemente zählt, die das Prädikat der Vorlagenfunktion [count_if](../standard-library/algorithm-functions.md#count_if) erfüllen.

### <a name="example"></a>Beispiel

```cpp
// alg_count.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> v1;
    vector<int>::iterator Iter;

    v1.push_back(10);
    v1.push_back(20);
    v1.push_back(10);
    v1.push_back(40);
    v1.push_back(10);

    cout << "v1 = ( " ;
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result;
    result = count(v1.begin(), v1.end(), 10);
    cout << "The number of 10s in v2 is: " << result << "." << endl;
}
```

```Output
v1 = ( 10 20 10 40 10 )
The number of 10s in v2 is: 3.
```

## <a name="count_if"></a> count_if

Gibt die Anzahl von Elementen in einem Bereich zurück, dessen Werte eine angegebene Bedingung erfüllen.

```cpp
template<class InputIterator, class Predicate>
    typename iterator_traits<InputIterator>::difference_type count_if(
        InputIterator first,
        InputIterator last,
        Predicate pred);
```

### <a name="parameters"></a>Parameter

*erste* ein eingabeiterator, der die Position des ersten Elements in dem Bereich adressiert, gesucht werden soll.

*letzte* ein eingabeiterator, der die Position hinter dem letzten Element im Bereich adressiert, gesucht werden soll.

*_Pred* User-defined Function, Prädikat-Objekt, das definiert die Bedingung erfüllt wird, wenn ein Element ist, die gezählt werden. Ein Prädikat akzeptiert ein einzelnes Argument und gibt entweder **TRUE** oder **FALSE** zurück.

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Elementen, die die vom Prädikat angegebenen Bedingungen erfüllen.

### <a name="remarks"></a>Hinweise

Diese Vorlagenfunktion ist eine Generalisierung des Algorithmus [count](../standard-library/algorithm-functions.md#count) und ersetzt das Prädikat „entspricht einem bestimmten Wert“ durch ein beliebiges Prädikat.

### <a name="example"></a>Beispiel

```cpp
// alg_count_if.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater10(int value)
{
    return value >10;
}

int main()
{
    using namespace std;
    vector<int> v1;
    vector<int>::iterator Iter;

    v1.push_back(10);
    v1.push_back(20);
    v1.push_back(10);
    v1.push_back(40);
    v1.push_back(10);

    cout << "v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    result1 = count_if(v1.begin(), v1.end(), greater10);
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;
}
```

```Output
v1 = ( 10 20 10 40 10 )
The number of elements in v1 greater than 10 is: 2.
```

## <a name="equal"></a> equal

Vergleicht zwei Bereiche elementweise auf Gleichheit oder Äquivalenz in dem durch ein binäres Prädikat angegebenen Sinn.

Verwenden Sie `std::equal` beim Vergleichen von Elementen in verschiedenen Containertypen (z.B. `vector` und `list`), beim Vergleichen von verschiedenen Elementtypen oder wenn Teilbereiche von Containern verglichen werden sollen. Ansonsten verwenden Sie den Nicht-Member `operator==` beim Vergleichen von Elementen des gleichen Typen im gleichen Containertypen.

Verwenden Sie die Überladungen mit zwei Bereichen im C++14-Code, da die Überladungen, die nur einen einzigen Iterator für den zweiten Bereich nutzen, keine Unterschiede erkennen, wenn der zweite Bereich länger als der erste Bereich ist. Darüber hinaus führt dies zu einem nicht definierten Verhalten, wenn der zweite Bereich kürzer als der erste Bereich ist.

```cpp
template<class InputIterator1, class InputIterator2>
bool equal(
    InputIterator1  First1,
    InputIterator1  Last1,
    InputIterator2  First2);

template<class InputIterator1, class InputIterator2, class BinaryPredicate>
bool equal(
    InputIterator1  First1,
    InputIterator1  Last1,
    InputIterator2  First2,
    BinaryPredicate Comp); // C++14

template<class InputIterator1, class InputIterator2>
bool equal(
    InputIterator1  First1,
    InputIterator1  Last1,
    InputIterator2  First2,
    InputIterator2  Last2);

template<class InputIterator1, class InputIterator2, class BinaryPredicate>
bool equal(
    InputIterator1  First1,
    InputIterator1  Last1,
    InputIterator2  First2,
    InputIterator2  Last2,
    BinaryPredicate Comp);
```

### <a name="parameters"></a>Parameter

*First1* ein Eingabe-Iterator, der die Position des ersten Elements im ersten Bereich getestet werden.

*Last1* ein Eingabe-Iterator, der die Position hinter dem letzten Element im ersten Bereich adressiert, die getestet werden.

*First2* ein Eingabe-Iterator, der die Position des ersten Elements im zweiten Bereich getestet werden.

*First2* ein Eingabe-Iterator, der die Position hinter dem letzten Element im zweiten Bereich getestet werden.

*Comp* User-defined Function, Prädikat-Objekt, das definiert die Bedingung erfüllt wird, wenn zwei Elemente enthalten sind, die ausgeführt werden als gleichwertig. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Bereiche unter dem binären Prädikat beim Vergleichen von Elementen identisch oder ähnlich sind; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der zu durchsuchende Bereich muss gültig sein. Alle Iteratoren müssen dereferenzierbar sein, und die letzte Position ist von der Ersten durch Zunahme erreichbar.

Wenn die beiden Bereich die gleiche Länge aufweisen, ist die Zeitkomplexität des Algorithmus linear zur Anzahl der im Bereich enthaltenen Elemente. Andernfalls gibt die Funktion sofort zurück **"false"**.

Weder das `operator==` noch das benutzerdefinierte Prädikat ist erforderlich, um eine Äquivalenzbeziehung vorzugeben, die zwischen den dazugehörigen Operanden symmetrisch, reflexiv und transitiv ist.

### <a name="example"></a>Beispiel

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

int main()
{
    vector<int> v1 { 0, 5, 10, 15, 20, 25 };
    vector<int> v2 { 0, 5, 10, 15, 20, 25 };
    vector<int> v3 { 0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50 };

    // Using range-and-a-half equal:
    bool b = equal(v1.begin(), v1.end(), v2.begin());
    cout << "v1 and v2 are equal: "
       << b << endl; // true, as expected

    b = equal(v1.begin(), v1.end(), v3.begin());
    cout << "v1 and v3 are equal: "
       << b << endl; // true, surprisingly

    // Using dual-range equal:
    b = equal(v1.begin(), v1.end(), v3.begin(), v3.end());
    cout << "v1 and v3 are equal with dual-range overload: "
       << b << endl; // false

    return 0;
}

```

## <a name="equal_range"></a> equal_range

Bei einem sortierten Bereich wird der Unterbereich gesucht, in dem alle Elemente einem angegebenen Wert entsprechen.

```cpp
template<class ForwardIterator, class Type>
pair<ForwardIterator, ForwardIterator> equal_range(
    ForwardIterator first,
    ForwardIterator last,
    const Type& val);

template<class ForwardIterator, class Type, class Predicate>
pair<ForwardIterator, ForwardIterator> equal_range(
    ForwardIterator first,
    ForwardIterator last,
    const Type& val,
    Predicate comp);
```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der die Position des ersten Elements im Bereich, gesucht werden soll.

*letzte* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich, gesucht werden soll.

*Val* den Wert im sortierten Bereich gesucht wird.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das den Sinn definiert, in dem ein Element kleiner als ein anderes ist.

### <a name="return-value"></a>Rückgabewert

Ein paar forward-Iteratoren, die angeben, einen Unterbereich, enthalten, die innerhalb des Bereichs, der durchsucht, in dem alle Elemente dem entsprechen *Val* insofern vom verwendeten binären Prädikat definiert (entweder *Comp* oder den Standardwert, kleiner-als).

Wenn keine Elemente in dem Bereich entsprechen *Val*, das zurückgegebene Paare von forward-Iteratoren sind gleich, und geben Sie den an, in denen *Val* eingefügt werden kann, ohne die Reihenfolge des Bereichs zu beeinträchtigen.

### <a name="remarks"></a>Hinweise

Der erste Iterator des vom Algorithmus zurückgegebenen Paars ist [lower_bound](../standard-library/algorithm-functions.md#lower_bound), der zweite Iterator ist [upper_bound](../standard-library/algorithm-functions.md#upper_bound).

Der Bereich muss dem für `equal_range` bereitgestellten Prädikat entsprechend sortiert werden. Wenn Sie z. B: das Prädikat "größer als" verwenden, muss der Bereich in absteigender Reihenfolge sortiert werden.

Elemente im möglicherweise leeren Unterbereich, definiert durch das Paar von Iteratoren, die vom `equal_range` werden gleich *Val* in dem vom verwendeten Prädikat definierten Sinn.

Die Komplexität dieses Algorithmus ist bei zufallszugriffsiteratoren logarithmisch und andernfalls mit der Anzahl von Schritten proportional zu lineare (*letzten* - *erste*).

### <a name="example"></a>Beispiel

```cpp
// alg_equal_range.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // greater<int>()
#include <iostream>
#include <string>
using namespace std;

template<class T> void dump_vector( const vector<T>& v, pair< typename vector<T>::iterator, typename vector<T>::iterator > range )
{
    // prints vector v with range delimited by [ and ]

    for( typename vector<T>::const_iterator i = v.begin(); i != v.end(); ++i )
    {
        if( i == range.first )
        {
            cout << "[ ";
        }
        if( i == range.second )
        {
            cout << "] ";
        }

        cout << *i << " ";
    }
    cout << endl;
}

template<class T> void equal_range_demo( const vector<T>& original_vector, T val )
{
    vector<T> v(original_vector);

    sort( v.begin(), v.end() );
    cout << "Vector sorted by the default binary predicate <:" << endl << '\t';
    for( vector<T>::const_iterator i = v.begin(); i != v.end(); ++i )
    {
        cout << *i << " ";
    }
    cout << endl << endl;

    pair< vector<T>::iterator, vector<T>::iterator > result
        = equal_range( v.begin(), v.end(), val );

    cout << "Result of equal_range with val = " << val << ":" << endl << '\t';
    dump_vector( v, result );
    cout << endl;
}

template<class T, class F> void equal_range_demo( const vector<T>& original_vector, T val, F pred, string predname )
{
    vector<T> v(original_vector);

    sort( v.begin(), v.end(), pred );
    cout << "Vector sorted by the binary predicate " << predname << ":" << endl << '\t';
    for( typename vector<T>::const_iterator i = v.begin(); i != v.end(); ++i )
    {
        cout << *i << " ";
    }
    cout << endl << endl;

    pair< typename vector<T>::iterator, typename vector<T>::iterator > result
        = equal_range( v.begin(), v.end(), val, pred );

    cout << "Result of equal_range with val = " << val << ":" << endl << '\t';
    dump_vector( v, result );
    cout << endl;
}

// Return whether absolute value of elem1 is less than absolute value of elem2
bool abs_lesser( int elem1, int elem2 )
{
    return abs(elem1) < abs(elem2);
}

// Return whether string l is shorter than string r
bool shorter_than(const string& l, const string& r)
{
    return l.size() < r.size();
}

int main()
{
    vector<int> v1;

    // Constructing vector v1 with default less than ordering
    for( int i = -1; i <= 4; ++i )
    {
        v1.push_back(i);
    }

    for( int i =-3; i <= 0; ++i )
    {
        v1.push_back( i );
    }

    equal_range_demo( v1, 3 );
    equal_range_demo( v1, 3, greater<int>(), "greater" );
    equal_range_demo( v1, 3, abs_lesser, "abs_lesser" );

    vector<string> v2;

    v2.push_back("cute");
    v2.push_back("fluffy");
    v2.push_back("kittens");
    v2.push_back("fun");
    v2.push_back("meowmeowmeow");
    v2.push_back("blah");

    equal_range_demo<string>( v2, "fred" );
    equal_range_demo<string>( v2, "fred", shorter_than, "shorter_than" );
}

```

## <a name="fill"></a> fill

Weist den gleichen neuen Wert jedem Element in einem angegebenen Bereich zu.

```cpp
template<class ForwardIterator, class Type>
void fill(
    ForwardIterator first,
    ForwardIterator last,
    const Type& val);
```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der die Position des ersten Elements im Bereich durchlaufen werden.

*letzte* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich durchlaufen werden.

*Val* den Wert zuzuweisenden Elemente im Bereich [ *erste*, *letzten*).

### <a name="remarks"></a>Hinweise

Der Zielbereich muss gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position ist von der Ersten durch Zunahme erreichbar. Die Komplexität ist mit der Größe des Bereichs linear.

### <a name="example"></a>Beispiel

```cpp
// alg_fill.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   cout << "Vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // Fill the last 5 positions with a value of 2
   fill( v1.begin( ) + 5, v1.end( ), 2 );

   cout << "Modified v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Vector v1 = ( 0 5 10 15 20 25 30 35 40 45 )
Modified v1 = ( 0 5 10 15 20 2 2 2 2 2 )
```

## <a name="fill_n"></a> fill_n

Weist einer angegebenen Anzahl von Elementen in einem Bereich, der mit einem bestimmten Element beginnt, einen neuen Wert zu.

```cpp
template<class OutputIterator, class Size, class Type>
OutputIterator fill_n(
    OutputIterator First,
    Size Count,
    const Type& Val);
```

### <a name="parameters"></a>Parameter

*Erste* ein Ausgabeiterator, der Wert zugewiesen werden, der die Position des ersten Elements im Bereich von *Val*.

*Anzahl* ein signiert oder unsigned Integer-Datentyp, der die Anzahl der Elemente angibt, der Wert zugewiesen werden.

*Val* den Wert zuzuweisenden Elemente im Bereich [ *erste*, *First + Count*).

### <a name="return-value"></a>Rückgabewert

Ein Iterator für das Element, das das letzte Element folgt aufgefüllt, wenn *Anzahl* > null ist, andernfalls das erste Element.

### <a name="remarks"></a>Hinweise

Der Zielbereich muss gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position ist von der Ersten durch Zunahme erreichbar. Die Komplexität ist mit der Größe des Bereichs linear.

### <a name="example"></a>Beispiel

```cpp
// alg_fill_n.cpp
// compile using /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;
    vector <int> v;

    for ( auto i = 0 ; i < 9 ; ++i )
        v.push_back( 0 );

    cout << "  vector v = ( " ;
    for ( const auto &w : v )
        cout << w << " ";
    cout << ")" << endl;

    // Fill the first 3 positions with a value of 1, saving position.
    auto pos = fill_n( v.begin(), 3, 1 );

    cout << "modified v = ( " ;
    for ( const auto &w : v )
        cout << w << " ";
    cout << ")" << endl;

    // Fill the next 3 positions with a value of 2, using last position.
    fill_n( pos, 3, 2 );

    cout << "modified v = ( " ;
    for ( const auto &w : v )
        cout << w << " ";
    cout << ")" << endl;

    // Fill the last 3 positions with a value of 3, using relative math.
    fill_n( v.end()-3, 3, 3 );

    cout << "modified v = ( " ;
    for ( const auto &w : v )
        cout << w << " ";
    cout << ")" << endl;
}

```

## <a name="find"></a> find

Sucht die Position des ersten Vorkommens eines Elements in einem Bereich, der einen angegebenen Wert enthält.

```cpp
template<class InputIterator, class T>
InputIterator find(
    InputIterator first,
    InputIterator last,
    const T& val);
```

### <a name="parameters"></a>Parameter

*erste* ein Eingabe-Iterator, der die Position des ersten Elements im Bereich, für den angegebenen Wert gesucht werden soll.

*letzte* ein eingabeiterator, der die Position hinter dem letzten Element im Bereich adressiert, für den angegebenen Wert gesucht werden soll.

*Val* der Wert, der gesucht werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein Eingabeiterator, der das erste Vorkommen des angegebenen Werts im zu durchsuchenden Bereich adressiert. Gibt zurück, wenn kein Element mit einem äquivalenten Wert gefunden wird, *letzten*.

### <a name="remarks"></a>Hinweise

Der zur Bestimmung des Gleichheitszustands zwischen einem Element und dem angegebenen Wert verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Ein Codebeispiel mit `find()` finden Sie unter [find_if](../standard-library/algorithm-functions.md#find_if).

## <a name="find_end"></a> find_end

Sucht in einem Bereich nach der letzten Untersequenz, die mit einer angegebenen Sequenz identisch ist oder die in durch ein binäres Prädikat angegebenen Sinne äquivalent ist.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
ForwardIterator1 find_end(
    ForwardIterator1 First1,
    ForwardIterator1 Last1,
    ForwardIterator2 First2,
    ForwardIterator2 Last2);

template<class ForwardIterator1, class ForwardIterator2, class Pred>
ForwardIterator1 find_end(
    ForwardIterator1 First1,
    ForwardIterator1 Last1,
    ForwardIterator2 First2,
    ForwardIterator2 Last2,
    Pred Comp);
```

### <a name="parameters"></a>Parameter

*First1* ein forward-Iterator, der die Position des ersten Elements im Bereich, gesucht werden soll.

*Last1* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich, gesucht werden soll.

*First2* ein forward-Iterator, der die Position des ersten Elements im Bereich von zu suchenden.

*Last2* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich von zu suchenden.

*Comp* User-defined Function, Prädikat-Objekt, das definiert die Bedingung erfüllt wird, wenn zwei Elemente enthalten sind, die ausgeführt werden als gleichwertig. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator, der die Position des ersten Elements der letzten Untersequenz in [First1, Last1) adressiert, die der angegebenen Sequenz [First2, Last2) entspricht.

### <a name="remarks"></a>Hinweise

Der zur Bestimmung des Gleichheitszustands zwischen einem Element und dem angegebenen Wert verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Die Bereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

### <a name="example"></a>Beispiel

```cpp
// alg_find_end.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

// Return whether second element is twice the first
bool twice ( int elem1, int elem2 )
{
   return 2 * elem1 == elem2;
}

int main( )
{
   using namespace std;
   vector <int> v1, v2;
   list <int> L1;
   vector <int>::iterator Iter1, Iter2;
   list <int>::iterator L1_Iter, L1_inIter;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   int ii;
   for ( ii = 1 ; ii <= 4 ; ii++ )
   {
      L1.push_back( 5 * ii );
   }

   int iii;
   for ( iii = 2 ; iii <= 4 ; iii++ )
   {
      v2.push_back( 10 * iii );
   }

   cout << "Vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "List L1 = ( " ;
   for ( L1_Iter = L1.begin( ) ; L1_Iter!= L1.end( ) ; L1_Iter++ )
      cout << *L1_Iter << " ";
   cout << ")" << endl;

   cout << "Vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
      cout << ")" << endl;

   // Searching v1 for a match to L1 under identity
   vector <int>::iterator result1;
   result1 = find_end ( v1.begin( ), v1.end( ), L1.begin( ), L1.end( ) );

   if ( result1 == v1.end( ) )
      cout << "There is no match of L1 in v1."
           << endl;
   else
      cout << "There is a match of L1 in v1 that begins at "
           << "position "<< result1 - v1.begin( ) << "." << endl;

   // Searching v1 for a match to L1 under the binary predicate twice
   vector <int>::iterator result2;
   result2 = find_end ( v1.begin( ), v1.end( ), v2.begin( ), v2.end( ), twice );

   if ( result2 == v1.end( ) )
      cout << "There is no match of L1 in v1."
           << endl;
   else
      cout << "There is a sequence of elements in v1 that "
           << "are equivalent to those\n in v2 under the binary "
           << "predicate twice and that begins at position "
           << result2 - v1.begin( ) << "." << endl;
}
```

```Output
Vector v1 = ( 0 5 10 15 20 25 0 5 10 15 20 25 )
List L1 = ( 5 10 15 20 )
Vector v2 = ( 20 30 40 )
There is a match of L1 in v1 that begins at position 7.
There is a sequence of elements in v1 that are equivalent to those
 in v2 under the binary predicate twice and that begins at position 8.
```

## <a name="find_first_of"></a> find_first_of

Sucht das erste Vorkommen mehrerer Werte innerhalb eines Zielbereichs oder das erste Vorkommen mehrerer Elemente, die wie durch ein binäres Prädikat angegeben mit einem angegebenen Satz der Elemente äquivalent sind.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
ForwardIterator1 find_first_of(
    ForwardIterator1  first1,
    ForwardIterator1 Last1,
    ForwardIterator2  first2,
    ForwardIterator2 Last2);

template<class ForwardIterator1, class ForwardIterator2, class BinaryPredicate>
ForwardIterator1 find_first_of(
    ForwardIterator1  first1,
    ForwardIterator1 Last1,
    ForwardIterator2  first2,
    ForwardIterator2 Last2,
    BinaryPredicate  comp);
```

### <a name="parameters"></a>Parameter

*first1* ein forward-Iterator, der die Position des ersten Elements im Bereich, gesucht werden soll.

*Last1* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich, gesucht werden soll.

*first2* ein forward-Iterator, der die Position des ersten Elements im Bereich von abgeglichen wird.

*Last2* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich von abgeglichen wird.

*Comp* User-defined Function, Prädikat-Objekt, das definiert die Bedingung erfüllt wird, wenn zwei Elemente enthalten sind, die ausgeführt werden als gleichwertig. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator, der die Position des ersten Elements der ersten Untersequenz adressiert, die der angegebenen Sequenz entspricht oder die wie von einem binären Prädikat angegeben äquivalent ist.

### <a name="remarks"></a>Hinweise

Der zur Bestimmung des Gleichheitszustands zwischen einem Element und dem angegebenen Wert verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Die Bereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

### <a name="example"></a>Beispiel

```cpp
// alg_find_first_of.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

// Return whether second element is twice the first
bool twice ( int elem1, int elem2 )
{
   return 2 * elem1 == elem2;
}

int main( )
{
   using namespace std;
   vector <int> v1, v2;
   list <int> L1;
   vector <int>::iterator Iter1, Iter2;
   list <int>::iterator L1_Iter, L1_inIter;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   int ii;
   for ( ii = 3 ; ii <= 4 ; ii++ )
   {
      L1.push_back( 5 * ii );
   }

   int iii;
   for ( iii = 2 ; iii <= 4 ; iii++ )
   {
      v2.push_back( 10 * iii );
   }

   cout << "Vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "List L1 = ( " ;
   for ( L1_Iter = L1.begin( ) ; L1_Iter!= L1.end( ) ; L1_Iter++ )
      cout << *L1_Iter << " ";
   cout << ")" << endl;

   cout << "Vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
      cout << ")" << endl;

   // Searching v1 for first match to L1 under identity
   vector <int>::iterator result1;
   result1 = find_first_of ( v1.begin( ), v1.end( ), L1.begin( ), L1.end( ) );

   if ( result1 == v1.end( ) )
      cout << "There is no match of L1 in v1."
           << endl;
   else
      cout << "There is at least one match of L1 in v1"
           << "\n and the first one begins at "
           << "position "<< result1 - v1.begin( ) << "." << endl;

   // Searching v1 for a match to L1 under the binary predicate twice
   vector <int>::iterator result2;
   result2 = find_first_of ( v1.begin( ), v1.end( ), v2.begin( ), v2.end( ), twice );

   if ( result2 == v1.end( ) )
      cout << "There is no match of L1 in v1."
           << endl;
   else
      cout << "There is a sequence of elements in v1 that "
           << "are equivalent\n to those in v2 under the binary "
           << "predicate twice\n and the first one begins at position "
           << result2 - v1.begin( ) << "." << endl;
}
```

```Output
Vector v1 = ( 0 5 10 15 20 25 0 5 10 15 20 25 )
List L1 = ( 15 20 )
Vector v2 = ( 20 30 40 )
There is at least one match of L1 in v1
 and the first one begins at position 3.
There is a sequence of elements in v1 that are equivalent
 to those in v2 under the binary predicate twice
 and the first one begins at position 2.
```

## <a name="find_if"></a> find_if

Sucht die Position des ersten Vorkommens eines Elements in einem Bereich, der eine bestimmte Bedingung erfüllt.

```cpp
template<class InputIterator, class Predicate>
InputIterator find_if(
    InputIterator first,
    InputIterator last,
    Predicate pred);
```

### <a name="parameters"></a>Parameter

*erste* ein eingabeiterator, der die Position des ersten Elements in dem Bereich adressiert, gesucht werden soll.

*letzte* ein eingabeiterator, der die Position hinter dem letzten Element im Bereich adressiert, gesucht werden soll.

*Pred* benutzerdefiniertes prädikatfunktionsobjekt oder [Lambda-Ausdruck](../cpp/lambda-expressions-in-cpp.md) , definiert die Bedingung, die von der zu suchenden Element erfüllt werden. Ein Prädikat akzeptiert einzelnes Argument und gibt **"true"** (erfüllt) oder **"false"** (nicht erfüllt). Die Signatur der *Pred* effektiv sein `bool pred(const T& arg);`, wobei `T` ist ein Typ, der `InputIterator` können beim Dereferenzieren implizit konvertiert werden. Die **const** Schlüsselwort dient nur zu veranschaulichen, dass das Argument nicht zu den Funktions- oder lambdaobjekt ändern sollten.

### <a name="return-value"></a>Rückgabewert

Ein eingabeiterator, der auf das erste Element im Bereich verweist, das vom Prädikat angegebene Bedingung erfüllt (das Prädikat ergibt **"true"**). Gibt zurück, wenn kein Element gefunden wird, um das Prädikat erfüllen, *letzten*.

### <a name="remarks"></a>Hinweise

Diese Vorlagenfunktion ist eine Generalisierung des Algorithmus [find](../standard-library/algorithm-functions.md#find) und ersetzt das Prädikat „entspricht einem bestimmten Wert“ durch ein beliebiges Prädikat. Das logische Gegenstück (Suchen des ersten Elements, das das Prädikat nicht erfüllt) finden Sie unter [find_if_not](../standard-library/algorithm-functions.md#find_if_not).

### <a name="example"></a>Beispiel

```cpp
// cl.exe /W4 /nologo /EHsc /MTd
#include <vector>
#include <algorithm>
#include <iostream>
#include <string>

using namespace std;

template <typename S> void print(const S& s) {
    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }
    cout << endl;
}

// Test std::find()
template <class InputIterator, class T>
void find_print_result(InputIterator first, InputIterator last, const T& value) {

    // call <algorithm> std::find()
    auto p = find(first, last, value);

    cout << "value " << value;
    if (p == last) {
        cout << " not found." << endl;
    } else {
        cout << " found." << endl;
    }
}

// Test std::find_if()
template <class InputIterator, class Predicate>
void find_if_print_result(InputIterator first, InputIterator last,
    Predicate Pred, const string& Str) {

    // call <algorithm> std::find_if()
    auto p = find_if(first, last, Pred);

    if (p == last) {
        cout << Str << " not found." << endl;
    } else {
        cout << "first " << Str << " found: " << *p << endl;
    }
}

// Function to use as the UnaryPredicate argument to find_if() in this example
bool is_odd_int(int i) {
    return ((i % 2) != 0);
}

int main()
{
    // Test using a plain old array.
    const int x[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    cout << "array x[] contents: ";
    print(x);
    // Using non-member std::begin()/std::end() to get input iterators for the plain old array.
    cout << "Test std::find() with array..." << endl;
    find_print_result(begin(x), end(x), 10);
    find_print_result(begin(x), end(x), 42);
    cout << "Test std::find_if() with array..." << endl;
    find_if_print_result(begin(x), end(x), is_odd_int, "odd integer"); // function name
    find_if_print_result(begin(x), end(x), // lambda
        [](int i){ return ((i % 2) == 0); }, "even integer");

    // Test using a vector.
    vector<int> v;
    for (int i = 0; i < 10; ++i) {
        v.push_back((i + 1) * 10);
    }
    cout << endl << "vector v contents: ";
    print(v);
    cout << "Test std::find() with vector..." << endl;
    find_print_result(v.begin(), v.end(), 20);
    find_print_result(v.begin(), v.end(), 12);
    cout << "Test std::find_if() with vector..." << endl;
    find_if_print_result(v.begin(), v.end(), is_odd_int, "odd integer");
    find_if_print_result(v.begin(), v.end(), // lambda
        [](int i){ return ((i % 2) == 0); }, "even integer");
}

```

## <a name="find_if_not"></a> find_if_not

Gibt das erste Element im angegebenen Bereich zurück, der eine Bedingung nicht erfüllt.

```cpp
template<class InputIterator, class Predicate>
InputIterator find_if_not(
    InputIterator first,
    InputIterator last,
    Predicate pred);
```

### <a name="parameters"></a>Parameter

*erste* ein eingabeiterator, der die Position des ersten Elements in dem Bereich adressiert, gesucht werden soll.

*letzte* ein eingabeiterator, der die Position hinter dem letzten Element im Bereich adressiert, gesucht werden soll.

*Pred* benutzerdefiniertes prädikatfunktionsobjekt oder [Lambda-Ausdruck](../cpp/lambda-expressions-in-cpp.md) , definiert die Bedingung nicht erfüllt werden muss, durch das Element gesucht wird. Ein Prädikat akzeptiert einzelnes Argument und gibt **"true"** (erfüllt) oder **"false"** (nicht erfüllt). Die Signatur der *Pred* effektiv sein `bool pred(const T& arg);`, wobei `T` ist ein Typ, der `InputIterator` können beim Dereferenzieren implizit konvertiert werden. Die **const** Schlüsselwort dient nur zu veranschaulichen, dass das Argument nicht zu den Funktions- oder lambdaobjekt ändern sollten.

### <a name="return-value"></a>Rückgabewert

Ein eingabeiterator, der auf das erste Element im Bereich verweist, die die vom Prädikat angegebene Bedingung nicht erfüllt (das Prädikat ergibt **"false"**). Wenn alle Elemente das Prädikat erfüllen (das Prädikat ergibt **"true"** für jedes Element), gibt *letzten*.

### <a name="remarks"></a>Hinweise

Diese Vorlagenfunktion ist eine Generalisierung des Algorithmus [find](../standard-library/algorithm-functions.md#find) und ersetzt das Prädikat „entspricht einem bestimmten Wert“ durch ein beliebiges Prädikat. Das logische Gegenstück (Suchen des ersten Elements, das das Prädikat erfüllt) finden Sie unter [find_if](../standard-library/algorithm-functions.md#find_if).

Ein Codebeispiel, das problemlos für `find_if_not()` angepasst werden kann, finden Sie unter [find_if](../standard-library/algorithm-functions.md#find_if).

## <a name="for_each"></a> for_each

Wendet ein angegebenes Funktionsobjekt auf jedes Element in einer Vorwärtsreihenfolge innerhalb eines Bereichs an und gibt das Funktionsobjekt zurück.

```cpp
template<class InputIterator, class Function>
Function for_each(
    InputIterator first,
    InputIterator last,
    Function _Func);
```

### <a name="parameters"></a>Parameter

*erste* ein eingabeiterator, der die Position des ersten Elements im zu verarbeitenden Bereich adressiert.

*letzte* ein eingabeiterator, der die Position hinter dem letzten Element im Bereich verarbeitet.

*_Func* User-defined Function,-Objekt, das auf jedes Element im Bereich angewendet wird.

### <a name="return-value"></a>Rückgabewert

Eine Kopie des Funktionsobjekts, nachdem es auf alle Elemente im Bereich angewendet wurde.

### <a name="remarks"></a>Hinweise

Der Algorithmus `for_each` ist hoch flexibel, sodass die benutzerdefinierte Änderung jedes einzelnen Elements eines Bereichs möglich sind. Vorlagenbasierte Funktionen, die möglicherweise in veränderter Form erneut verwendet werden, indem sie unterschiedliche Parameter erfüllen. Benutzerdefinierte Funktionen sammeln möglicherweise Informationen innerhalb eines internen Zustands, die der Algorithmus möglicherweise zurückgibt, nachdem er alle Elemente im Bereich verarbeitet hat.

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb der Sequenz muss von der ersten Position aus durch Zunahme erreichbar sein.

Die Komplexität ist linear, wobei höchstens ( *letzten* -  *erste*) vergleichen.

### <a name="example"></a>Beispiel

```cpp
// alg_for_each.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

// The function object multiplies an element by a Factor
template <class Type>
class MultValue
{
private:
   Type Factor;   // The value to multiply by
public:
   // Constructor initializes the value to multiply by
   MultValue ( const Type& val ) : Factor ( val ) {
   }

   // The function call for the element to be multiplied
   void operator ( ) ( Type& elem ) const
   {
      elem *= Factor;
   }
};

// The function object to determine the average
class Average
{
private:
   long num;      // The number of elements
   long sum;      // The sum of the elements
public:
   // Constructor initializes the value to multiply by
   Average ( ) : num ( 0 ) , sum ( 0 )
   {
   }

   // The function call to process the next elment
   void operator ( ) ( int elem ) \
   {
      num++;      // Increment the element count
      sum += elem;   // Add the value to the partial sum
   }

   // return Average
   operator double ( )
   {
      return  static_cast <double> (sum) /
      static_cast <double> (num);
   }
};

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   // Constructing vector v1
   int i;
   for ( i = -4 ; i <= 2 ; i++ )
   {
      v1.push_back(  i );
   }

   cout << "Original vector  v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Using for_each to multiply each element by a Factor
   for_each ( v1.begin ( ) , v1.end ( ) , MultValue<int> ( -2 ) );

   cout << "Multiplying the elements of the vector v1\n "
        <<  "by the factor -2 gives:\n v1mod1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // The function object is templatized and so can be
   // used again on the elements with a different Factor
   for_each (v1.begin ( ) , v1.end ( ) , MultValue<int> (5 ) );

   cout << "Multiplying the elements of the vector v1mod\n "
        <<  "by the factor 5 gives:\n v1mod2 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // The local state of a function object can accumulate
   // information about a sequence of actions that the
   // return value can make available, here the Average
   double avemod2 = for_each ( v1.begin ( ) , v1.end ( ) ,
      Average ( ) );
   cout << "The average of the elements of v1 is:\n Average ( v1mod2 ) = "
        << avemod2 << "." << endl;
}
```

```Output
Original vector  v1 = ( -4 -3 -2 -1 0 1 2 ).
Multiplying the elements of the vector v1
 by the factor -2 gives:
 v1mod1 = ( 8 6 4 2 0 -2 -4 ).
Multiplying the elements of the vector v1mod
 by the factor 5 gives:
 v1mod2 = ( 40 30 20 10 0 -10 -20 ).
The average of the elements of v1 is:
 Average ( v1mod2 ) = 10.
```

## <a name="generate"></a> generate

Weist die Werte, die von einem Funktionsobjekt generiert werden, jedem Element in einem Bereich zu.

```cpp
template<class ForwardIterator, class Generator>
void generate(
    ForwardIterator first,
    ForwardIterator last,
    Generator _Gen);
```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der die Position des ersten Elements im Bereich auf die Werte zugewiesen werden soll.

*letzte* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich auf die Werte zugewiesen werden soll.

*_Gen* ein Funktionsobjekt, das ohne Argumente aufgerufen wird, die verwendet wird, zum Generieren der Werte aller Elemente im Bereich zugewiesen werden.

### <a name="remarks"></a>Hinweise

Das Funktionsobjekt wird jedem Element im Bereich zugeordnet und muss nicht bei jedem Aufruf denselben Wert zurückgeben. Es kann z, B. aus einer Datei lesen oder auf einen lokalen Zustand verweisen und diesen ändern. Der Ergebnistyp des Generators muss in den Wertetyp des Vorwärtsiterators für den Bereich konvertierbar sein.

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb der Sequenz muss von der ersten Position aus durch Zunahme erreichbar sein.

Die Komplexität ist linear, wobei exakt ( `last`  -   `first`) Aufrufe des Generators erforderlich sind.

### <a name="example"></a>Beispiel

```cpp
// alg_generate.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>
#include <ostream>

int main( )
{
   using namespace std;

   // Assigning random values to vector integer elements
   vector <int> v1 ( 5 );
   vector <int>::iterator Iter1;
   deque <int> deq1 ( 5 );
   deque <int>::iterator d1_Iter;

   generate ( v1.begin ( ), v1.end ( ) , rand );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Assigning random values to deque integer elements
   generate ( deq1.begin ( ), deq1.end ( ) , rand );

   cout << "Deque deq1 is ( " ;
   for ( d1_Iter = deq1.begin( ) ; d1_Iter != deq1.end( ) ; d1_Iter++ )
      cout << *d1_Iter << " ";
   cout << ")." << endl;
}
```

```Output
Vector v1 is ( 41 18467 6334 26500 19169 ).
Deque deq1 is ( 15724 11478 29358 26962 24464 ).
```

## <a name="generate_n"></a> generate_n

Weist die Werte, die von einem Funktionsobjekt generiert werden, einer angegebenen Anzahl von Elementen eines Bereichs zu und kehrt zu der Position zurück, die direkt nach dem letzten zugewiesenen Wert liegt.

```cpp
template<class OutputIterator, class Diff, class Generator>
void generate_n(
    OutputIterator First,
    Diff Count,
    Generator Gen);
```

### <a name="parameters"></a>Parameter

*Erste* ein Ausgabeiterator, der die Position des ersten Elements im Bereich auf die Werte zugewiesen werden soll.

*Anzahl* ein signierte oder unsignierte Ganzzahltyp auf die Anzahl der Elemente, einen Wert durch die Generatorfunktion zuzuweisenden.

*Gen* ein Funktionsobjekt, das ohne Argumente aufgerufen wird, die verwendet wird, zum Generieren der Werte aller Elemente im Bereich zugewiesen werden.

### <a name="remarks"></a>Hinweise

Das Funktionsobjekt wird jedem Element im Bereich zugeordnet und muss nicht bei jedem Aufruf denselben Wert zurückgeben. Es kann z, B. aus einer Datei lesen oder auf einen lokalen Zustand verweisen und diesen ändern. Der Ergebnistyp des Generators muss in den Wertetyp des Vorwärtsiterators für den Bereich konvertierbar sein.

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb der Sequenz muss von der ersten Position aus durch Zunahme erreichbar sein.

Die Komplexität ist linear, wobei exakt `Count` Aufrufe des Generators erforderlich sind.

### <a name="example"></a>Beispiel

```cpp
// cl.exe /EHsc /nologo /W4 /MTd
#include <vector>
#include <deque>
#include <iostream>
#include <string>
#include <algorithm>
#include <random>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    const int elemcount = 5;
    vector<int> v(elemcount);
    deque<int> dq(elemcount);

    // Set up random number distribution
    random_device rd;
    mt19937 engine(rd());
    uniform_int_distribution<int> dist(-9, 9);

    // Call generate_n, using a lambda for the third parameter
    generate_n(v.begin(), elemcount, [&](){ return dist(engine); });
    print("vector v is: ", v);

    generate_n(dq.begin(), elemcount, [&](){ return dist(engine); });
    print("deque dq is: ", dq);
}

```

## <a name="includes"></a> includes

Testet, ob ein sortierter Bereich alle Elemente enthält, die in einem zweiten sortierten Bereich enthalten sind, wobei das Sortier- oder Äquivalenzkriterium für die Elemente durch ein binäres Prädikat angegeben werden kann.

```cpp
template<class InputIterator1, class InputIterator2>
bool includes(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2);

template<class InputIterator1, class InputIterator2, class BinaryPredicate>
bool includes(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    BinaryPredicate comp );
```

### <a name="parameters"></a>Parameter

*first1* ein Eingabe-Iterator, der die Position des ersten Elements im ersten der beiden sortierten Quellbereiche geprüft werden soll, ob alle Elemente des zweiten im ersten Bereich enthalten sind.

*Last1* ein Eingabe-Iterator, der die Position hinter dem letzten Element im ersten der beiden sortierten Quellbereiche adressiert, die geprüft werden soll, ob alle Elemente des zweiten im ersten Bereich enthalten sind.

*first2* ein Eingabe-Iterator, der die Position des ersten Elements im zweiten der beiden aufeinanderfolgenden sortierten Quellbereiche adressiert, die geprüft werden soll, ob alle Elemente des zweiten im ersten Bereich enthalten sind.

*Last2* ein eingabeiterator, der die Position hinter dem letzten Element im zweiten der beiden aufeinanderfolgenden sortierten Quellbereiche adressiert, geprüft werden soll, ob alle Elemente des zweiten im ersten Bereich enthalten sind.

*Comp* ermitteln benutzerdefiniertes prädikatfunktionsobjekt, das definiert, in dem ein Element kleiner als ein anderes ist. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der erste sortierte Bereich alle Elemente des zweiten Bereichs enthält; ansonsten **FALSE**.

### <a name="remarks"></a>Hinweise

Anders ausgedrückt bedeutet dies, dass dieser Test feststellt, ob der zweite Quellbereich eine Teilmenge des ersten Quellbereichs ist.

Die sortierten Quellbereiche, auf die verwiesen wird, müssen gültig sein; alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb jeder Sequenz muss von der ersten Position durch Zunahme erreichbar sein.

Die sortierten Quellbereiche müssen als Vorbedingung zur Anwendung des Algorithmus entsprechend der gleichen Reihenfolge sortiert werden, die vom Algorithmus für die Sortierung der kombinierten Bereiche verwendet wird.

Die Quellbereiche werden nicht geändert, durch den Algorithmus `merge`.

Die Werttypen der Eingabeiteratoren müssen mit „kleiner als“ vergleichbar sein, um sortiert zu werden, sodass zwei Elemente möglicherweise als gleichwertig (in dem Sinne, dass keines kleiner als das andere ist) oder eines als kleiner als das andere bestimmt werden können. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen. Dies bedeutet, dass der Algorithmus überprüft, ob alle Elemente im an erster Stelle aufgelisteten Bereich unter einem angegebenen binären Prädikat genauso wie die Elemente des an zweiter Stelle aufgelisteten Bereichs sortiert sind.

Die Komplexität dieses Algorithmus ist höchstens mit 2 linear \* (( *last1 – first1*) – (* last2 – first2 *)) – 1 Vergleiche für nicht leere Quellbereiche.

### <a name="example"></a>Beispiel

```cpp
// alg_includes.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser (int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
}

int main( )
{
   using namespace std;
   vector <int> v1a, v1b;
   vector <int>::iterator Iter1a,  Iter1b;

   // Constructing vectors v1a & v1b with default less-than ordering
   int i;
   for ( i = -2 ; i <= 4 ; i++ )
   {
      v1a.push_back(  i );
   }

   int ii;
   for ( ii =-2 ; ii <= 3 ; ii++ )
   {
      v1b.push_back(  ii  );
   }

   cout << "Original vector v1a with range sorted by the\n "
        << "binary predicate less than is v1a = ( " ;
   for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
      cout << *Iter1a << " ";
   cout << ")." << endl;

   cout << "Original vector v1b with range sorted by the\n "
        <<  "binary predicate less than is v1b = ( " ;
   for ( Iter1b = v1b.begin ( ) ; Iter1b != v1b.end ( ) ; Iter1b++ )
      cout << *Iter1b << " ";
   cout << ")." << endl;

   // Constructing vectors v2a & v2b with ranges sorted by greater
   vector <int> v2a ( v1a ) , v2b ( v1b );
   vector <int>::iterator Iter2a,  Iter2b;
   sort ( v2a.begin ( ) , v2a.end ( ) , greater<int> ( ) );
   sort ( v2b.begin ( ) , v2b.end ( ) , greater<int> ( ) );
   v2a.pop_back ( );

   cout << "Original vector v2a with range sorted by the\n "
        <<  "binary predicate greater is v2a = ( " ;
   for ( Iter2a = v2a.begin ( ) ; Iter2a != v2a.end ( ) ; Iter2a++ )
      cout << *Iter2a << " ";
   cout << ")." << endl;

   cout << "Original vector v2b with range sorted by the\n "
        <<  "binary predicate greater is v2b = ( " ;
   for ( Iter2b = v2b.begin ( ) ; Iter2b != v2b.end ( ) ; Iter2b++ )
      cout << *Iter2b << " ";
   cout << ")." << endl;

   // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
   vector <int> v3a ( v1a ), v3b ( v1b ) ;
   vector <int>::iterator Iter3a, Iter3b;
   reverse (v3a.begin( ), v3a.end( ) );
   v3a.pop_back ( );
   v3a.pop_back ( );
   sort ( v3a.begin ( ) , v3a.end ( ) , mod_lesser );
   sort ( v3b.begin ( ) , v3b.end ( ) , mod_lesser );

   cout << "Original vector v3a with range sorted by the\n "
        <<  "binary predicate mod_lesser is v3a = ( " ;
   for ( Iter3a = v3a.begin ( ) ; Iter3a != v3a.end ( ) ; Iter3a++ )
      cout << *Iter3a << " ";
   cout << ")." << endl;

   cout << "Original vector v3b with range sorted by the\n "
        <<  "binary predicate mod_lesser is v3b = ( " ;
   for ( Iter3b = v3b.begin ( ) ; Iter3b != v3b.end ( ) ; Iter3b++ )
      cout << *Iter3b << " ";
   cout << ")." << endl;

   // To test for inclusion under an asscending order
   // with the default binary predicate less <int> ( )
   bool Result1;
   Result1 = includes ( v1a.begin ( ) , v1a.end ( ) ,
      v1b.begin ( ) , v1b.end ( ) );
   if ( Result1 )
      cout << "All the elements in vector v1b are "
           << "contained in vector v1a." << endl;
   else
      cout << "At least one of the elements in vector v1b "
           << "is not contained in vector v1a." << endl;

   // To test for inclusion under descending
   // order specify binary predicate greater<int>( )
   bool Result2;
   Result2 = includes ( v2a.begin ( ) , v2a.end ( ) ,
      v2b.begin ( ) , v2b.end ( ) , greater <int> ( ) );
   if ( Result2 )
      cout << "All the elements in vector v2b are "
           << "contained in vector v2a." << endl;
   else
      cout << "At least one of the elements in vector v2b "
           << "is not contained in vector v2a." << endl;

   // To test for inclusion under a user
   // defined binary predicate mod_lesser
   bool Result3;
   Result3 = includes ( v3a.begin ( ) , v3a.end ( ) ,
      v3b.begin ( ) , v3b.end ( ) , mod_lesser );
   if ( Result3 )
      cout << "All the elements in vector v3b are "
           << "contained under mod_lesser in vector v3a."
           << endl;
   else
      cout << "At least one of the elements in vector v3b is "
           << " not contained under mod_lesser in vector v3a."
           << endl;
}
```

```Output
Original vector v1a with range sorted by the
 binary predicate less than is v1a = ( -2 -1 0 1 2 3 4 ).
Original vector v1b with range sorted by the
 binary predicate less than is v1b = ( -2 -1 0 1 2 3 ).
Original vector v2a with range sorted by the
 binary predicate greater is v2a = ( 4 3 2 1 0 -1 ).
Original vector v2b with range sorted by the
 binary predicate greater is v2b = ( 3 2 1 0 -1 -2 ).
Original vector v3a with range sorted by the
 binary predicate mod_lesser is v3a = ( 0 1 2 3 4 ).
Original vector v3b with range sorted by the
 binary predicate mod_lesser is v3b = ( 0 -1 1 -2 2 3 ).
All the elements in vector v1b are contained in vector v1a.
At least one of the elements in vector v2b is not contained in vector v2a.
At least one of the elements in vector v3b is  not contained under mod_lesser in vector v3a.
```

## <a name="inplace_merge"></a> inplace_merge

Kombiniert die Elemente von zwei aufeinander folgenden sortierten Bereichen in einen einzelnen sortierten Bereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.

```cpp
template<class BidirectionalIterator>
void inplace_merge(
    BidirectionalIterator first,
    BidirectionalIterator middle,
    BidirectionalIterator last);

template<class BidirectionalIterator, class Predicate>
void inplace_merge(
    BidirectionalIterator first,
    BidirectionalIterator middle,
    BidirectionalIterator last,
    Predicate comp);
```

### <a name="parameters"></a>Parameter

*erste* ein bidirektionaler Iterator, der die Position der ersten im ersten der beiden nacheinander sortierten Elementbereiche kombiniert und zu einem einzelnen Bereich sortiert werden sollen.

*Mittlere* ein bidirektionaler Iterator, der die Position der ersten im zweiten der beiden nacheinander sortierten Elementbereiche kombiniert und zu einem einzelnen Bereich sortiert werden sollen.

*letzte* ein bidirektionaler Iterator, der die Position hinter dem letzten im zweiten der beiden aufeinanderfolgenden sortierten Elementbereiche kombiniert und zu einem einzelnen Bereich sortiert werden sollen.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das den Sinn definiert, in dem ein Element größer als die andere ist. Das binäre Prädikat akzeptiert zwei Argumente und sollte **true** zurückgeben, wenn das erste Element kleiner als das zweite Element ist, andernfalls wird **false** zurückgegeben.

### <a name="remarks"></a>Hinweise

Die sortierten aufeinanderfolgenden Quellbereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb jeder Sequenz muss von der ersten Position aus durch Zunahme erreichbar sein.

Die sortierten aufeinanderfolgenden Bereiche müssen als Vorbedingung zur Anwendung des `inplace_merge`-Algorithmus entsprechend der gleichen Reihenfolge sortiert werden, die vom Algorithmus für die Sortierung der kombinierten Bereiche verwendet wird. Der Vorgang ist stabil, da die relative Reihenfolge der Elemente innerhalb jedes Bereichs beibehalten wird. Wenn in beiden Quellbereichen äquivalente Elemente vorhanden sind, stehen im kombinierten Bereich das Element aus dem ersten Bereich vor dem Element aus dem zweiten Bereich.

Die Komplexität hängt davon ab, wie viel Speicher verfügbar ist, während der Algorithmus dem temporären Puffer Speicher zuweist. Wenn ausreichend Arbeitsspeicher verfügbar ist, ist der beste Fall linear mit (* Nachname - Vorname *) – 1 vergleichen; Wenn kein auxiliary-Speicher verfügbar ist, ist der schlimmste Fall *N* Log *(N)*, wobei  *N* = (* Nachname - Vorname*).

### <a name="example"></a>Beispiel

```cpp
// alg_inplace_merge.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      //For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
}

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1, Iter2, Iter3;

   // Constructing vector v1 with default less-than ordering
   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii =-5 ; ii <= 0 ; ii++ )
   {
      v1.push_back(  ii  );
   }

   cout << "Original vector v1 with subranges sorted by the\n "
        <<  "binary predicate less than is  v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // Constructing vector v2 with ranges sorted by greater
   vector <int> v2 ( v1 );
   vector <int>::iterator break2;
   break2 = find ( v2.begin ( ) , v2.end ( ) , -5 );
   sort ( v2.begin ( ) , break2 , greater<int> ( ) );
   sort ( break2 , v2.end ( ) , greater<int> ( ) );
   cout << "Original vector v2 with subranges sorted by the\n "
        << "binary predicate greater is v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Constructing vector v3 with ranges sorted by mod_lesser
   vector <int> v3 ( v1 );
   vector <int>::iterator break3;
   break3 = find ( v3.begin ( ) , v3.end ( ) , -5 );
   sort ( v3.begin ( ) , break3 , mod_lesser );
   sort ( break3 , v3.end ( ) , mod_lesser );
   cout << "Original vector v3 with subranges sorted by the\n "
        << "binary predicate mod_lesser is v3 = ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;

   vector <int>::iterator break1;
   break1 = find (v1.begin ( ) , v1.end ( ) , -5 );
   inplace_merge ( v1.begin( ), break1, v1.end( ) );
   cout << "Merged inplace with default order,\n vector v1mod = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To merge inplace in descending order, specify binary
   // predicate greater<int>( )
   inplace_merge ( v2.begin( ), break2 , v2.end( ) , greater<int>( ) );
   cout << "Merged inplace with binary predicate greater specified,\n "
        << "vector v2mod = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Applying a user defined (UD) binary predicate mod_lesser
   inplace_merge ( v3.begin( ), break3, v3.end( ), mod_lesser );
   cout << "Merged inplace with binary predicate mod_lesser specified,\n "
        << "vector v3mod = ( " ; ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 with subranges sorted by the
 binary predicate less than is  v1 = ( 0 1 2 3 4 5 -5 -4 -3 -2 -1 0 )
Original vector v2 with subranges sorted by the
 binary predicate greater is v2 = ( 5 4 3 2 1 0 0 -1 -2 -3 -4 -5 )
Original vector v3 with subranges sorted by the
 binary predicate mod_lesser is v3 = ( 0 1 2 3 4 5 0 -1 -2 -3 -4 -5 )
Merged inplace with default order,
 vector v1mod = ( -5 -4 -3 -2 -1 0 0 1 2 3 4 5 )
Merged inplace with binary predicate greater specified,
 vector v2mod = ( 5 4 3 2 1 0 0 -1 -2 -3 -4 -5 )
Merged inplace with binary predicate mod_lesser specified,
 vector v3mod = ( 0 0 1 -1 2 -2 3 -3 4 -4 5 -5 )
```

## <a name="is_heap"></a> is_heap

Gibt **"true"** , wenn die Elemente im angegebenen Bereich ein Heap bilden.

```cpp
template<class RandomAccessIterator>
bool is_heap(
    RandomAccessIterator first,
    RandomAccessIterator last);

template<class RandomAccessIterator, class BinaryPredicate>
bool is_heap(
    RandomAccessIterator first,
    RandomAccessIterator last,
    BinaryPredicate comp);
```

### <a name="parameters"></a>Parameter

*erste* ein zufälliger direkter Iterator, der den Beginn eines Bereichs für einen Heap zu überprüfen angibt.

*letzte* ein zufälliger direkter Iterator, der das Ende eines Bereichs angibt.

*Comp* eine Bedingung zum Sortieren von Elementen zu testen. Ein binäres Prädikat akzeptiert ein einzelnes Argument und gibt **"true"** oder **"false"**.

### <a name="return-value"></a>Rückgabewert

Gibt **"true"** , wenn die Elemente im angegebenen Bereich einen Heap bilden **"false"** ist dies nicht der Fall.

### <a name="remarks"></a>Hinweise

Die erste Vorlagenfunktion gibt [is_heap_until](../standard-library/algorithm-functions.md#is_heap_until)`(` `first ,` `last ) ==` `last` zurück.

Die zweite Vorlagenfunktion gibt Folgendes zurück

`is_heap_until` `(`  `first` `,`  `last` `,`  `comp` `) ==`  `last`.

## <a name="is_heap_until"></a> is_heap_until

Gibt einen Iterator an das erste Element im Bereich positioniert [ `begin`, `end`), der die heapsortierbedingung nicht erfüllt oder *End* Wenn der Bereich einen Heap bildet.

```cpp
template<class RandomAccessIterator>
RandomAccessIterator is_heap_until(
    RandomAccessIterator begin,
    RandomAccessIterator end);

template<class RandomAccessIterator, class BinaryPredicate>
RandomAccessIterator is_heap_until(
    RandomAccessIterator begin,
    RandomAccessIterator end,
    BinaryPredicate compare);
```

### <a name="parameters"></a>Parameter

*Begin* ein zufälliger direkter Iterator, der angibt, das erste Element eines Bereichs für einen Heap zu überprüfen.

*End* ein zufälliger direkter Iterator, der angibt, das Ende des Bereichs, der bei einem Heap zu überprüfen.

*Vergleichen Sie* ein binäres Prädikat, der angibt, die strikten schwachen Sortierung Bedingung, die einen Heap definiert. Das standardmäßige Prädikat, wenn *vergleichen* ist nicht angegeben ist `std::less<>`.

### <a name="return-value"></a>Rückgabewert

Gibt *End* , wenn der angegebene Bereich einen Heap bildet oder ein oder weniger Elemente enthält. Gibt andernfalls einen Iterator für das erste Elemente zurück, das die Heap-Bedingung nicht erfüllt.

### <a name="remarks"></a>Hinweise

Die erste Vorlagenfunktion gibt den letzten Iterator `next` in `[ begin , end ]` , in denen `[ begin , next)` ist ein Heap, sortiert nach dem Funktionsobjekt `std::less<>`. Wenn die Entfernung `end - begin < 2`, die Funktion gibt *End*.

Die zweite Vorlagenfunktion verhält sich wie die erste, mit der Ausnahme, dass sie das Prädikat `compare` anstelle von `std::less<>` als Heapsortierbedingung verwendet.

## <a name="is_partitioned"></a> is_partitioned

Gibt **"true"** , wenn alle Elemente im angegebenen Bereich zu testen, ob **"true"** für eine Bedingung ergeben, vor allen Elementen, die testen **"false"**.

```cpp
template<class InputIterator, class BinaryPredicate>
bool is_partitioned(
    InputIterator first,
    InputIterator last,
    BinaryPredicate comp);
```

### <a name="parameters"></a>Parameter

*erste* ein Eingabe-Iterator, der angibt, in dem Beginn des Bereichs auf eine Bedingung geprüft.

*letzte* ein Eingabe-Iterator, der das Ende eines Bereichs angibt.

*Comp* die Bedingung zu testen. Dies wird von einem benutzerdefinierten Prädikatfunktionsobjekt bereitgestellt, das bzw. der die Bedingung definiert, die vom zu suchenden Element erfüllt wird. Ein Prädikat akzeptiert ein einzelnes Argument und gibt entweder **TRUE** oder **FALSE** zurück.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn alle Elemente im angegebenen Bereich, die testen **"true"** für eine Bedingung ergeben, vor allen Elementen, die testen **"false"**, und andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt **"true"** nur, wenn alle Elemente im `[` `first ,` `last )` sind nach partitioniert *Comp*; d. h. alle Elemente `X` in `[` `first ,` `last )` für die `comp (X)` ist "true" vor allen Elementen auftreten `Y` für die `comp (Y)` ist **"false"**.

## <a name="is_permutation"></a> is_permutation

Gibt „true“ zurück, wenn beide Bereiche dieselben Elemente enthalten, und zwar unabhängig davon, ob sich die Elemente in derselben Reihenfolge befinden. Verwenden Sie die Überladungen mit zwei Bereichen im C++14-Code, da die Überladungen, die nur einen einzigen Iterator für den zweiten Bereich nutzen, keine Unterschiede erkennen, wenn der zweite Bereich länger als der erste Bereich ist. Darüber hinaus führt dies zu einem nicht definierten Verhalten, wenn der zweite Bereich kürzer als der erste Bereich ist.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
bool is_permutation(
    ForwardIterator1 First1,
    ForwardIterator1 Last1,
    ForwardIterator2 First2);

template<class ForwardIterator1, class ForwardIterator2, class Predicate>
bool is_permutation(
    ForwardIterator1 First1,
    ForwardIterator1 Last1,
    ForwardIterator2 First2,
    Predicate Pred);

// C++14
template<class ForwardIterator1, class ForwardIterator2>
bool is_permutation(
    ForwardIterator1 First1,
    ForwardIterator1 Last1,
    ForwardIterator2 First2,
    ForwardIterator2 Last2);

template<class ForwardIterator1, class ForwardIterator2, class Predicate>
bool is_permutation(
    ForwardIterator1 First1,
    ForwardIterator1 Last1,
    ForwardIterator2 First2,
    ForwardIterator2 Last2,
    Predicate Pred);
```

### <a name="parameters"></a>Parameter

*First1* ein forward-Iterator, der auf das erste Element des Bereichs verweist.

*Last1* ein forward-Iterator, der hinter dem letzten Element des Bereichs verweist.

*First2* ein forward-Iterator, der auf das erste Element eines zweiten Bereichs, der für den Vergleich verweist.

*Last2* ein forward-Iterator, der verweist auf eine Stelle hinter dem letzten Element eines zweiten Bereichs, der für den Vergleich verwendet.

*Pred* ein Prädikat, das auf Übereinstimmung überprüft und gibt eine **"bool"**.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Bereiche neu angeordnet werden können, um gemäß dem Vergleichsprädikat identisch ist, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

`is_permutation` verfügt im schlimmsten Fall über die quadratische Komplexität.

Die erste Vorlagenfunktion geht davon aus, dass es so viele Elemente im Bereich beginnend mit *First2* wie es im Bereich [ `First1`, `Last1`). Wenn es weitere Elemente im zweiten Bereich gibt, werden sie ignoriert; wenn es weniger sind, hat das ein undefiniertes Verhalten zur Folge. Die dritte Vorlagenfunktion (C++14 und höher) macht diese Annahme nicht.  Beide zurückgeben **"true"** nur dann für jedes Element X im Bereich von [ `First1`, `Last1`) Es gibt so viele Elemente Y im selben Bereich für die X == Y, wie es im Bereich beginnend mit *First2* oder [ `First2, Last2).` hier `operator==` müssen einen paarweisen Vergleich zwischen zwei Operanden ausführen.

Die zweiten und vierten Vorlagenfunktionen verhalten sich identisch, jedoch mit der Ausnahme, dass sie `operator==(X, Y)` durch `Pred(X, Y)` ersetzen. Für das ordnungsgemäße Verhalten muss das Prädikat symmetrisch, reflexiv und transitiv sein.

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `is_permutation`:

```cpp
#include <vector>
#include <iostream>
#include <algorithm>
#include <string>

using namespace std;

int main()
{
    vector<int> vec_1{ 2, 3, 0, 1, 4, 5 };
    vector<int> vec_2{ 5, 4, 0, 3, 1, 2 };

    vector<int> vec_3{ 4, 9, 13, 3, 6, 5 };
    vector<int> vec_4{ 7, 4, 11, 9, 2, 1 };

    cout << "(1) Compare using built-in == operator: ";
    cout << boolalpha << is_permutation(vec_1.begin(), vec_1.end(),
        vec_2.begin(), vec_2.end()) << endl; // true

    cout << "(2) Compare after modifying vec_2: ";
    vec_2[0] = 6;
    cout << is_permutation(vec_1.begin(), vec_1.end(),
        vec_2.begin(), vec_2.end()) << endl; // false

    // Define equivalence as "both are odd or both are even"
    cout << "(3) vec_3 is a permutation of vec_4: ";
    cout << is_permutation(vec_3.begin(), vec_3.end(),
        vec_4.begin(), vec_4.end(),
        [](int lhs, int rhs) { return lhs % 2 == rhs % 2; }) << endl; // true

    // Initialize a vector using the 's' string literal to specify a std::string
    vector<string> animals_1{ "dog"s, "cat"s, "bird"s, "monkey"s };
    vector<string> animals_2{ "donkey"s, "bird"s, "meerkat"s, "cat"s };

    // Define equivalence as "first letters are equal":
    bool is_perm = is_permutation(animals_1.begin(), animals_1.end(), animals_2.begin(), animals_2.end(),
        [](const string& lhs, const string& rhs)
    {
        return lhs[0] == rhs[0]; //std::string guaranteed to have at least a null terminator
    });

    cout << "animals_2 is a permutation of animals_1: " << is_perm << endl; // true

    cout << "Press a letter" << endl;
    char c;
    cin >> c;

    return 0;
}

```

## <a name="is_sorted"></a> is-sorted

Gibt **"true"** , wenn die Elemente im angegebenen Bereich in sortierter Reihenfolge befinden.

```cpp
template<class ForwardIterator>
bool is_sorted(
    ForwardIterator first,
    ForwardIterator last);

template<class ForwardIterator, class BinaryPredicate>
bool is_sorted(
    ForwardIterator first,
    ForwardIterator last,
    BinaryPredicate comp);
```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der angibt, an dem der zu prüfende Bereich beginnt.

*letzte* ein forward-Iterator, der das Ende eines Bereichs angibt.

*Comp* die Bedingung zu testen, um eine Position zwischen zwei Elementen zu bestimmen. Ein Prädikat akzeptiert ein einzelnes Argument und gibt entweder **TRUE** oder **FALSE** zurück. Dies führt den gleichen Task wie `operator<` aus.

### <a name="remarks"></a>Hinweise

Die erste Vorlagenfunktion gibt [Is_sorted_until](http://msdn.microsoft.com/bbad99d0-deaa-4fe6-ae58-eb5b3e4dded0)`( first, last ) == last`. Die `operator<` Funktion führt den reihenfolgenvergleich.

Die zweite Vorlagenfunktion gibt `is_sorted_until( first, last , comp ) == last`. Die *Comp* Prädikatfunktion führt einen reihenfolgenvergleich.

## <a name="is_sorted_until"></a> is_sorted_until

Gibt ein `ForwardIterator` zurück, das auf das letzte Element festgelegt ist, das in der Sortierreihenfolge eines angegebenen Bereichs ist.

Die zweite Version können Sie bieten eine `BinaryPredicate` -Funktion, die zurückgegeben **"true"** Wenn zwei angegebene Elemente in der Sortierreihenfolge sind und **"false"** andernfalls.

```cpp
template<class ForwardIterator>
    ForwardIterator is_sorted_until(
        ForwardIterator first,
        ForwardIterator last
    );
template<class ForwardIterator, class BinaryPredicate>
    ForwardIterator is_sorted_until(
        ForwardIterator first,
        ForwardIterator last,
        BinaryPredicate comp
    );
```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der angibt, in dem der zu prüfende Bereich beginnt.

*letzte* ein forward-Iterator, der das Ende eines Bereichs angibt.

*Comp* die Bedingung zu testen, um eine Position zwischen zwei Elementen zu bestimmen. Ein Prädikat akzeptiert ein einzelnes Argument und gibt entweder **TRUE** oder **FALSE** zurück.

### <a name="return-value"></a>Rückgabewert

Gibt ein `ForwardIterator` zurück, das auf das letzte Element in der Sortierreihenfolge festgelegt ist. Die sortierte Sequenz beginnt bei *erste*.

### <a name="remarks"></a>Hinweise

Die erste Vorlagenfunktion gibt den letzten Iterator `next` in `[` `first ,` `last ]` zurück, wobei `[` `first , next)` zu einer von `operator<` sortierten Sequenz wird. Wenn `distance()` `< 2` die Funktion gibt *letzten*.

Die zweite Vorlagenfunktion verhält sich genauso; der einzige Unterschied ist, dass sie `operator<(X, Y)` durch `comp (X, Y)` ersetzt.

## <a name="iter_swap"></a> iter_swap

Tauscht zwei Werte aus, auf die durch ein Paar angegebener Iteratoren verwiesen wird.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
void iter_swap( ForwardIterator1 left, ForwardIterator2 right );

```

### <a name="parameters"></a>Parameter

*linken* eines forward-Iteratoren, dessen Wert ausgetauscht werden sollen.

*richtige* das zweite der forward-Iteratoren, dessen Wert ausgetauscht werden sollen.

### <a name="remarks"></a>Hinweise

`swap` sollte **iter_swap** vorgezogen werden; dieses war im C++-Standard für die Abwärtskompatibilität enthalten. Wenn `Fit1` und `Fit2` forward-Iteratoren sind `iter_swap` ( `Fit1`, `Fit2` ), entspricht der `swap` ( \* `Fit1`, \* `Fit2` ).

Die Werttypen der Forward-Eingabeiteratoren müssen den gleichen Wert haben.

### <a name="example"></a>Beispiel

```cpp
// alg_iter_swap.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt
{
public:
   CInt( int n = 0 ) : m_nVal( n ){}
   CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
   CInt&   operator=( const CInt& rhs ) { m_nVal =
   rhs.m_nVal; return *this; }
   bool operator<( const CInt& rhs ) const
      { return ( m_nVal < rhs.m_nVal );}
   friend ostream& operator<<( ostream& osIn, const CInt& rhs );

private:
   int m_nVal;
};

inline ostream& operator<<( ostream& osIn, const CInt& rhs )
{
   osIn << "CInt(" << rhs.m_nVal << ")";
   return osIn;
}

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
};

int main( )
{
   CInt c1 = 5, c2 = 1, c3 = 10;
   deque<CInt> deq1;
   deque<CInt>::iterator d1_Iter;

   deq1.push_back ( c1 );
   deq1.push_back ( c2 );
   deq1.push_back ( c3 );

   cout << "The original deque of CInts is deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl;

   // Exchanging first and last elements with iter_swap
   iter_swap ( deq1.begin ( ) , --deq1.end ( ) );

   cout << "The deque of CInts with first & last elements swapped is:\n deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl;

   // Swapping back first and last elements with swap
   swap ( *deq1.begin ( ) , *(deq1.end ( ) -1 ) );

   cout << "The deque of CInts with first & last elements swapped back is:\n deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl;

   // Swapping a vector element with a deque element
   vector <int> v1;
   vector <int>::iterator Iter1;
   deque <int> deq2;
   deque <int>::iterator d2_Iter;

   int i;
   for ( i = 0 ; i <= 3 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii = 4 ; ii <= 5 ; ii++ )
   {
      deq2.push_back( ii );
   }

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "Deque deq2 is ( " ;
   for ( d2_Iter = deq2.begin( ) ; d2_Iter != deq2.end( ) ; d2_Iter++ )
      cout << *d2_Iter << " ";
   cout << ")." << endl;

   iter_swap ( v1.begin ( ) , deq2.begin ( ) );

   cout << "After exchanging first elements,\n vector v1 is: v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl << " & deque deq2 is: deq2 = ( ";
   for ( d2_Iter = deq2.begin( ) ; d2_Iter != deq2.end( ) ; d2_Iter++ )
      cout << *d2_Iter << " ";
   cout << ")." << endl;
}
```

```Output
The original deque of CInts is deq1 = ( CInt(5), CInt(1), CInt(10) ).
The deque of CInts with first & last elements swapped is:
 deq1 = ( CInt(10), CInt(1), CInt(5) ).
The deque of CInts with first & last elements swapped back is:
 deq1 = ( CInt(5), CInt(1), CInt(10) ).
Vector v1 is ( 0 1 2 3 ).
Deque deq2 is ( 4 5 ).
After exchanging first elements,
 vector v1 is: v1 = ( 4 1 2 3 ).
 & deque deq2 is: deq2 = ( 0 5 ).
```

## <a name="lexicographical_compare"></a> lexicographical_compare

Vergleicht zwei Sequenzen elementweise, um zu bestimmen, welche der beiden kleiner ist.

```cpp
template<class InputIterator1, class InputIterator2>
 bool lexicographical_compare(
     InputIterator1  first1,
     InputIterator1 Last1,
     InputIterator2  first2,
     InputIterator2 Last2  );

template<class InputIterator1, class InputIterator2, class BinaryPredicate>
bool lexicographical_compare(
     InputIterator1  first1,
     InputIterator1 Last1,
     InputIterator2  first2,
     InputIterator2 Last2,
     BinaryPredicate  comp  );

```

### <a name="parameters"></a>Parameter

*first1* ein eingabeiterator, der die Position des ersten Elements im ersten Bereich adressiert, verglichen werden soll.

*Last1* ein Eingabe-Iterator, der die Position hinter dem letzten Element im ersten Bereich adressiert, verglichen werden soll.

*first2* ein Eingabe-Iterator, der die Position des ersten Elements im zweiten Bereich verglichen werden soll.

*Last2* ein Eingabe-Iterator, der die Position hinter dem letzten Element im zweiten Bereich adressiert, verglichen werden soll.

*Comp* ermitteln benutzerdefiniertes prädikatfunktionsobjekt, das definiert, in dem ein Element kleiner als ein anderes ist. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der erste Bereich lexikographisch kleiner als der zweite Bereich ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Ein lexikographischer Vergleich zweier Sequenzen vergleicht diese elementweise bis:

- es zwei korrespondierende ungleiche Elemente findet, und deren Vergleich als Ergebnis des Vergleichs zweier Sequenzen genommen wird.

- keine Ungleichungen gefunden werden, aber eine Sequenz mehr Elemente als eine andere hat, und die kürzere Sequenz als kleiner als die längere Sequenz angesehen wird.

- keine Ungleichungen gefunden werden, und Sequenzen die gleiche Anzahl von Elementen haben. Demnach sind die Sequenzen gleich und das Ergebnis des Vergleichs ist FALSE.

### <a name="example"></a>Beispiel

```cpp
// alg_lex_comp.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

// Return whether second element is twice the first
bool twice ( int elem1, int elem2 )
{
   return 2 * elem1 < elem2;
}

int main( )
{
   using namespace std;
   vector <int> v1, v2;
   list <int> L1;
   vector <int>::iterator Iter1, Iter2;
   list <int>::iterator L1_Iter, L1_inIter;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }
   int ii;
   for ( ii = 0 ; ii <= 6 ; ii++ )
   {
      L1.push_back( 5 * ii );
   }

   int iii;
   for ( iii = 0 ; iii <= 5 ; iii++ )
   {
      v2.push_back( 10 * iii );
   }

   cout << "Vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "List L1 = ( " ;
   for ( L1_Iter = L1.begin( ) ; L1_Iter!= L1.end( ) ; L1_Iter++ )
      cout << *L1_Iter << " ";
   cout << ")" << endl;

   cout << "Vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
      cout << ")" << endl;

   // Self lexicographical_comparison of v1 under identity
   bool result1;
   result1 = lexicographical_compare (v1.begin( ), v1.end( ),
                  v1.begin( ), v1.end( ) );
   if ( result1 )
      cout << "Vector v1 is lexicographically_less than v1." << endl;
   else
      cout << "Vector v1 is not lexicographically_less than v1." << endl;

   // lexicographical_comparison of v1 and L2 under identity
   bool result2;
   result2 = lexicographical_compare (v1.begin( ), v1.end( ),
                  L1.begin( ), L1.end( ) );
   if ( result2 )
      cout << "Vector v1 is lexicographically_less than L1." << endl;
   else
      cout << "Vector v1 is lexicographically_less than L1." << endl;

   bool result3;
   result3 = lexicographical_compare (v1.begin( ), v1.end( ),
                  v2.begin( ), v2.end( ), twice );
   if ( result3 )
      cout << "Vector v1 is lexicographically_less than v2 "
           << "under twice." << endl;
   else
      cout << "Vector v1 is not lexicographically_less than v2 "
           << "under twice." << endl;
}
```

```Output
Vector v1 = ( 0 5 10 15 20 25 )
List L1 = ( 0 5 10 15 20 25 30 )
Vector v2 = ( 0 10 20 30 40 50 )
Vector v1 is not lexicographically_less than v1.
Vector v1 is lexicographically_less than L1.
Vector v1 is not lexicographically_less than v2 under twice.
```

## <a name="lower_bound"></a> lower_bound

Sucht die Position des ersten Elements in einem sortierten Bereich, der über einen Wert größer als oder gleich einem angegebenen Wert verfügt. Dabei wird das Sortierkriterium möglicherweise von einen binären Prädikat bestimmt.

```cpp
template<class ForwardIterator, class Type>
ForwardIterator lower_bound(
     ForwardIterator first,
     ForwardIterator last,
     const Type& value );

template<class ForwardIterator, class Type, class BinaryPredicate>
ForwardIterator lower_bound(
     ForwardIterator first,
     ForwardIterator last,
     const Type& value,
     BinaryPredicate comp );

```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der die Position des ersten Elements im Bereich, gesucht werden soll.

*letzte* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich, gesucht werden soll.

*Wert* der Wert, dessen erste Position oder mögliche erste Position für die im sortierten Bereich gesucht wird ist.

*Comp* ermitteln benutzerdefiniertes prädikatfunktionsobjekt, das definiert, in dem ein Element kleiner als ein anderes ist. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator an der Position des ersten Elements in einem sortierten Bereich mit einem Wert, der größer als oder gleich einem angegebenen Wert ist, wobei die Äquivalenz von einem binären Prädikat angegeben wird.

### <a name="remarks"></a>Hinweise

Der sortierte Quellbereich, auf den verwiesen wird, muss gültig sein. Alle Iteratoren müssen dereferenzierbar sein und die letzte Position muss der innerhalb der Reihenfolge vom ersten von der ersten Position aus durch Zunahme erreichbar sein.

Ein sortierter Bereich ist eine Vorbedingung für die Verwendung von `lower_bound` und wann immer die Reihenfolge mit der vom binärem Prädikat angegebenen identisch ist.

Der Bereich wird vom Algorithmus `lower_bound` nicht geändert.

Die Werttypen der Forward-Iteratoren müssen weniger als vergleichbar sein, um sortiert zu werden, sodass zwei Elemente möglicherweise als gleichwertig bestimmt werden (in dem Sinne, dass keins geringer als das Andere ist), oder dass eins geringer als das Andere ist. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen.

Die Komplexität dieses Algorithmus ist bei Zufallszugriffsiteratoren logarithmisch und andernfalls linear. Dabei ist eine Anzahl von Schritten proportional zu (`last - first`).

### <a name="example"></a>Beispiel

```cpp
// alg_lower_bound.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser( int elem1, int elem2 )
{
    if ( elem1 < 0 )
        elem1 = - elem1;
    if ( elem2 < 0 )
        elem2 = - elem2;
    return elem1 < elem2;
}

int main( )
{
    using namespace std;

    vector<int> v1;
    // Constructing vector v1 with default less-than ordering
    for ( auto i = -1 ; i <= 4 ; ++i )
    {
        v1.push_back(  i );
    }

    for ( auto ii =-3 ; ii <= 0 ; ++ii )
    {
        v1.push_back(  ii  );
    }

    cout << "Starting vector v1 = ( " ;
    for (const auto &Iter : v1)
        cout << Iter << " ";
    cout << ")." << endl;

    sort(v1.begin(), v1.end());
    cout << "Original vector v1 with range sorted by the\n "
        << "binary predicate less than is v1 = ( " ;
    for (const auto &Iter : v1)
        cout << Iter << " ";
    cout << ")." << endl;

    // Constructing vector v2 with range sorted by greater
    vector<int> v2(v1);

    sort(v2.begin(), v2.end(), greater<int>());

    cout << "Original vector v2 with range sorted by the\n "
        << "binary predicate greater is v2 = ( " ;
    for (const auto &Iter : v2)
        cout << Iter << " ";
    cout << ")." << endl;

    // Constructing vectors v3 with range sorted by mod_lesser
    vector<int> v3(v1);
    sort(v3.begin(), v3.end(), mod_lesser);

    cout << "Original vector v3 with range sorted by the\n "
        <<  "binary predicate mod_lesser is v3 = ( " ;
    for (const auto &Iter : v3)
        cout << Iter << " ";
    cout << ")." << endl;

    // Demonstrate lower_bound

    vector<int>::iterator Result;

    // lower_bound of 3 in v1 with default binary predicate less<int>()
    Result = lower_bound(v1.begin(), v1.end(), 3);
    cout << "The lower_bound in v1 for the element with a value of 3 is: "
        << *Result << "." << endl;

    // lower_bound of 3 in v2 with the binary predicate greater<int>( )
    Result = lower_bound(v2.begin(), v2.end(), 3, greater<int>());
    cout << "The lower_bound in v2 for the element with a value of 3 is: "
        << *Result << "." << endl;

    // lower_bound of 3 in v3 with the binary predicate  mod_lesser
    Result = lower_bound(v3.begin(), v3.end(), 3,  mod_lesser);
    cout << "The lower_bound in v3 for the element with a value of 3 is: "
        << *Result << "." << endl;
}

```

## <a name="make_heap"></a> make_heap

Konvertiert Elemente aus einem angegebenen Bereich in einen Heap, in dem das erste Element das größte ist und für den ein Sortierkriterium durch ein binäres Prädikat angegeben werden kann.

```cpp
template<class RandomAccessIterator>
void make_heap(
     RandomAccessIterator first,
     RandomAccessIterator last );

template<class RandomAccessIterator, class BinaryPredicate>
void make_heap(
     RandomAccessIterator first,
     RandomAccessIterator last,
     BinaryPredicate comp );

```

### <a name="parameters"></a>Parameter

*erste* ein zufälliger eingabeiterator, der die Position des ersten Elements im Bereich, in einen Heap konvertiert werden soll.

*letzte* ein zufälliger eingabeiterator, der die Position adressiert, hinter dem letzten Element im Bereich, in einen Heap konvertiert werden soll.

*Comp* ermitteln benutzerdefiniertes prädikatfunktionsobjekt, das definiert, in dem ein Element kleiner als ein anderes ist. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="remarks"></a>Hinweise

Heaps haben zwei Eigenschaften:

- Das erste Element ist immer das größte.

- Elemente können in logarithmischer Zeit hinzugefügt oder entfernt werden.

Heaps sind ideal zum Implementieren von Vorrangwarteschlangen. Sie werden beim Implementieren des C++-Standardbibliothekadapters [priority_queue-Klasse](../standard-library/priority-queue-class.md) verwendet.

Die Komplexität ist linear und erfordert 3 \* (* Nachname - Vorname *) vergleichen.

### <a name="example"></a>Beispiel

```cpp
// alg_make_heap.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   random_shuffle( v1.begin( ), v1.end( ) );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Make v1 a heap with default less than ordering
   make_heap ( v1.begin( ), v1.end( ) );
   cout << "The heaped version of vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Make v1 a heap with greater than ordering
   make_heap ( v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "The greater-than heaped version of v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="max"></a> max

Vergleicht zwei Objekte und gibt das größere der beiden zurück, wobei das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.

```cpp
template<class Type>
    const Type& max(
        const Type& left,
        const Type& right
    );
template<class Type, class Pr>
    const Type& max(
        const Type& left,
        const Type& right,
        BinaryPredicate comp
    );
template<class Type>
    Type& max (
        initializer_list<Type> _Ilist
    );
template<class Type, class Pr>
    Type& max(
        initializer_list<Type> _Ilist,
        BinaryPredicate comp
    );
```

### <a name="parameters"></a>Parameter

*linken* das erste der beiden verglichenen Objekte.

*richtige* das zweite der beiden Objekte mit dem verglichen wird.

*Comp* ein binäres Prädikat, das zum Vergleichen der beiden Objekte verwendet.

*_IList* der Initialisiererliste, die die zu vergleichenden Objekte enthält.

### <a name="return-value"></a>Rückgabewert

Das größere der beiden Objekte, es sei denn, keins ist größer als das andere. In diesem Fall wird das erste der beiden Objekte zurückgegeben. Bei einem initializer_list-Element wird das größere der Objekte in der Liste zurückgegeben.

### <a name="remarks"></a>Hinweise

Der `max`-Algorithmus ist ungewöhnlich, denn er weist Objekte auf, die als Parameter übergeben werden. Die meisten C++-Algorithmen der Standardbibliothek werden auf einem Elementbereich ausgeführt, dessen Position von als Parameter übergebenen Iteratoren angegeben wird. Wenn Sie eine Funktion benötigen, die einen Elementbereich bearbeitet, verwenden Sie stattdessen [max_element](../standard-library/algorithm-functions.md#max_element).

### <a name="example"></a>Beispiel

```cpp
// alg_max.cpp
// compile with: /EHsc
#include <vector>
#include <set>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt
{
public:
   CInt( int n = 0 ) : m_nVal( n ){}
   CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
   CInt&   operator=( const CInt& rhs ) {m_nVal =
   rhs.m_nVal; return *this;}
   bool operator<( const CInt& rhs ) const
      {return ( m_nVal < rhs.m_nVal );}
   friend ostream& operator<<( ostream& osIn, const CInt& rhs );

private:
   int m_nVal;
};

inline ostream& operator<<( ostream& osIn, const CInt& rhs )
{
   osIn << "CInt( " << rhs.m_nVal << " )";
   return osIn;
}

// Return whether absolute value of elem1 is greater than
// absolute value of elem2
bool abs_greater ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = -elem1;
   if ( elem2 < 0 )
      elem2 = -elem2;
   return elem1 < elem2;
};

int main( )
{
   int a = 6, b = -7;
   // Return the integer with the larger absolute value
   const int& result1 = max(a, b, abs_greater);
   // Return the larger integer
   const int& result2 = max(a, b);

   cout << "Using integers 6 and -7..." << endl;
   cout << "The integer with the greater absolute value is: "
        << result1 << "." << endl;
   cout << "The integer with the greater value is: "
        << result2 << "." << endl;
   cout << endl;

// Comparing the members of an initializer_list
const int& result3 = max({ a, b });
const int& result4 = max({ a, b }, abs_greater);

cout << "Comparing the members of an initializer_list..." << endl;
cout << "The member with the greater value is: " << result3 << endl;
cout << "The integer with the greater absolute value is: " << result4 << endl;

   // Comparing set containers with elements of type CInt
   // using the max algorithm
   CInt c1 = 1, c2 = 2, c3 = 3;
   set<CInt> s1, s2, s3;
   set<CInt>::iterator s1_Iter, s2_Iter, s3_Iter;

   s1.insert ( c1 );
   s1.insert ( c2 );
   s2.insert ( c2 );
   s2.insert ( c3 );

   cout << "s1 = (";
   for ( s1_Iter = s1.begin( ); s1_Iter != --s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter << ",";
   s1_Iter = --s1.end( );
   cout << " " << *s1_Iter << " )." << endl;

   cout << "s2 = (";
   for ( s2_Iter = s2.begin( ); s2_Iter != --s2.end( ); s2_Iter++ )
      cout << " " << *s2_Iter << ",";
   s2_Iter = --s2.end( );
   cout << " " << *s2_Iter << " )." << endl;

   s3 = max ( s1, s2 );
   cout << "s3 = max ( s1, s2 ) = (";
   for ( s3_Iter = s3.begin( ); s3_Iter != --s3.end( ); s3_Iter++ )
      cout << " " << *s3_Iter << ",";
   s3_Iter = --s3.end( );
   cout << " " << *s3_Iter << " )." << endl << endl;

   // Comparing vectors with integer elements using the max algorithm
   vector <int> v1, v2, v3, v4, v5;
   vector <int>::iterator Iter1, Iter2, Iter3, Iter4, Iter5;

   int i;
   for ( i = 0 ; i <= 2 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii = 0 ; ii <= 2 ; ii++ )
   {
      v2.push_back( ii );
   }

   int iii;
   for ( iii = 0 ; iii <= 2 ; iii++ )
   {
      v3.push_back( 2 * iii );
   }

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "Vector v2 is ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   cout << "Vector v3 is ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")." << endl;

   v4 = max ( v1, v2 );
   v5 = max ( v1, v3 );

   cout << "Vector v4 = max (v1,v2) is ( " ;
   for ( Iter4 = v4.begin( ) ; Iter4 != v4.end( ) ; Iter4++ )
      cout << *Iter4 << " ";
   cout << ")." << endl;

   cout << "Vector v5 = max (v1,v3) is ( " ;
   for ( Iter5 = v5.begin( ) ; Iter5 != v5.end( ) ; Iter5++ )
      cout << *Iter5 << " ";
   cout << ")." << endl;
}
```

```Output
Using integers 6 and -7...
The integer with the greater absolute value is: -7
The integer with the greater value is: 6.
Comparing the members of an initializer_list...The member with the greater value is: 6The integer wiht the greater absolute value is: -7
s1 = ( CInt( 1 ), CInt( 2 ) ).
s2 = ( CInt( 2 ), CInt( 3 ) ).
s3 = max ( s1, s2 ) = ( CInt( 2 ), CInt( 3 ) ).

Vector v1 is ( 0 1 2 ).
Vector v2 is ( 0 1 2 ).
Vector v3 is ( 0 2 4 ).
Vector v4 = max (v1,v2) is ( 0 1 2 ).
Vector v5 = max (v1,v3) is ( 0 2 4 ).
```

## <a name="max_element"></a> max_element

Sucht das erste Vorkommen des größten Elements in einem angegebenen Bereich, in dem das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.

```cpp
template<class ForwardIterator>
ForwardIterator max_element(ForwardIterator first, ForwardIterator last );

template<class ForwardIterator, class BinaryPredicate>
ForwardIterator max_element(ForwardIterator first, ForwardIterator last, BinaryPredicate comp );

```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der die Position des ersten Elements im Bereich, nach dem größten Element gesucht werden soll.

*letzte* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich, nach dem größten Element gesucht werden soll.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das den Sinn definiert, in dem ein Element größer als die andere ist. Das binäre Prädikat akzeptiert zwei Argumente und sollte **true** zurückgeben, wenn das erste Element kleiner als das zweite Element ist, andernfalls wird **false** zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Ein Vorwärtsiterator, der die Position des ersten Vorkommen des größten Elements im zu durchsuchenden Bereich adressiert.

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Komplexität ist linear: (`last` - `first`) – 1 Vergleiche sind für einen nicht leeren Bereich erforderlich.

### <a name="example"></a>Beispiel

```cpp
// alg_max_element.cpp
// compile with: /EHsc
#include <vector>
#include <set>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt
{
public:
   CInt( int n = 0 ) : m_nVal( n ){}
   CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
   CInt& operator=( const CInt& rhs ) {m_nVal =
   rhs.m_nVal; return *this;}
   bool operator<( const CInt& rhs ) const
      {return ( m_nVal < rhs.m_nVal );}
   friend ostream& operator<<( ostream& osIn, const CInt& rhs );

private:
   int m_nVal;
};

inline ostream& operator<<(ostream& osIn, const CInt& rhs)
{
   osIn << "CInt( " << rhs.m_nVal << " )";
   return osIn;
}

// Return whether modulus of elem1 is greater than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
};

int main( )
{
   // Searching a set container with elements of type CInt
   // for the maximum element
   CInt c1 = 1, c2 = 2, c3 = -3;
   set<CInt> s1;
   set<CInt>::iterator s1_Iter, s1_R1_Iter, s1_R2_Iter;

   s1.insert ( c1 );
   s1.insert ( c2 );
   s1.insert ( c3 );

   cout << "s1 = (";
   for ( s1_Iter = s1.begin( ); s1_Iter != --s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter << ",";
   s1_Iter = --s1.end( );
   cout << " " << *s1_Iter << " )." << endl;

   s1_R1_Iter = max_element ( s1.begin ( ) , s1.end ( ) );

   cout << "The largest element in s1 is: " << *s1_R1_Iter << endl;
   cout << endl;

   // Searching a vector with elements of type int for the maximum
   // element under default less than & mod_lesser binary predicates
   vector <int> v1;
   vector <int>::iterator v1_Iter, v1_R1_Iter, v1_R2_Iter;

   int i;
   for ( i = 0 ; i <= 3 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii = 1 ; ii <= 4 ; ii++ )
   {
      v1.push_back( - 2 * ii );
   }

   cout << "Vector v1 is ( " ;
   for ( v1_Iter = v1.begin( ) ; v1_Iter != v1.end( ) ; v1_Iter++ )
      cout << *v1_Iter << " ";
   cout << ")." << endl;

   v1_R1_Iter = max_element ( v1.begin ( ) , v1.end ( ) );
   v1_R2_Iter = max_element ( v1.begin ( ) , v1.end ( ), mod_lesser);

   cout << "The largest element in v1 is: " << *v1_R1_Iter << endl;
   cout << "The largest element in v1 under the mod_lesser"
        << "\n binary predicate is: " << *v1_R2_Iter << endl;
}
```

## <a name="merge"></a> merge

Kombiniert alle Elemente aus zwei sortierten Quellbereichen zu einem einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
 OutputIterator merge(
     InputIterator1 first1,
     InputIterator1 last1,
     InputIterator2 first2,
     InputIterator2 last2,
     OutputIterator result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class BinaryPredicate>
OutputIterator merge(
     InputIterator1 first1,
     InputIterator1 last1,
     InputIterator2 first2,
     InputIterator2 last2,
     OutputIterator result,
     BinaryPredicate comp );

```

### <a name="parameters"></a>Parameter

*first1* ein Eingabe-Iterator, der die Position des ersten Elements im ersten der beiden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich sortiert werden sollen.

*Last1* ein eingabeiterator, der die Position hinter dem letzten Element im ersten der beiden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich sortiert werden sollen.

*first2* ein eingabeiterator, der die Position des ersten Elements im zweiten der beiden aufeinanderfolgenden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich sortiert werden sollen.

*Last2* ein eingabeiterator, der die Position direkt hinter dem letzten Element im zweiten der beiden aufeinanderfolgenden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich sortiert werden sollen.

*Ergebnis* ein Ausgabeiterator, der die Position des ersten Elements im Zielbereich, in dem die beiden Bereiche Source, sind, die mit einem einzelnen Bereich sortiert kombiniert werden.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das den Sinn definiert, in dem ein Element größer als die andere ist. Das binäre Prädikat akzeptiert zwei Argumente und sollte **true** zurückgeben, wenn das erste Element kleiner als das zweite Element ist, andernfalls wird **false** zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der die Position hinter dem letzten Element im sortierten Zielbereich adressiert.

### <a name="remarks"></a>Hinweise

Die sortierten Quellbereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb jeder Sequenz muss von der ersten Position aus durch Zunahme erreichbar sein.

Der Zielbereich sollte keinen der Quellbereiche überlappen und groß genug sein, um den Zielbereich zu enthalten.

Die sortierten Quellbereiche müssen als Vorbedingung zur Anwendung des `merge` -Algorithmus entsprechend der gleichen Reihenfolge sortiert werden, die vom Algorithmus für die Sortierung der kombinierten Bereiche verwendet wird.

Der Vorgang ist stabil, da die relative Reihenfolge der Elemente innerhalb jedes Bereichs im Zielbereich beibehalten wird. Die Quellbereiche werden nicht geändert, durch den Algorithmus `merge`.

Die Werttypen der Eingabeiteratoren müssen mit „kleiner als“ vergleichbar sein, um sortiert zu werden, sodass zwei Elemente möglicherweise als gleichwertig (in dem Sinne, dass keines kleiner als das andere ist) oder eines als kleiner als das andere bestimmt werden können. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen. Wenn in beiden Quellbereichen äquivalente Elemente vorhanden sind, stehen im Zielbereich die Elemente aus dem ersten Bereich vor den Elementen aus dem zweiten Bereich.

Die Komplexität dieses Algorithmus ist linear, wobei höchstens (* last1 – first1 *) – (* last2 – first2*) – 1 Vergleiche.

Die [-list-Klasse](../standard-library/list-class.md) stellt eine Memberfunktion „merge“ bereit, um die Elemente zweier Listen zusammenzuführen.

### <a name="example"></a>Beispiel

```cpp
// alg_merge.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>   // For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 ) {
   if (elem1 < 0)
      elem1 = - elem1;
   if (elem2 < 0)
      elem2 = - elem2;
   return elem1 < elem2;
}

int main() {
   using namespace std;
   vector <int> v1a, v1b, v1 ( 12 );
   vector <int>::iterator Iter1a,  Iter1b, Iter1;

   // Constructing vector v1a and v1b with default less than ordering
   int i;
   for ( i = 0 ; i <= 5 ; i++ )
      v1a.push_back(  i );

   int ii;
   for ( ii =-5 ; ii <= 0 ; ii++ )
      v1b.push_back(  ii  );

   cout << "Original vector v1a with range sorted by the\n "
        << "binary predicate less than is  v1a = ( " ;
   for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
      cout << *Iter1a << " ";
   cout << ")." << endl;

   cout << "Original vector v1b with range sorted by the\n "
        << "binary predicate less than is  v1b = ( " ;
   for ( Iter1b = v1b.begin ( ) ; Iter1b != v1b.end ( ) ; Iter1b++ )
      cout << *Iter1b << " ";
   cout << ")." << endl;

   // Constructing vector v2 with ranges sorted by greater
   vector <int> v2a ( v1a ) , v2b ( v1b ) ,  v2 ( v1 );
   vector <int>::iterator Iter2a,  Iter2b, Iter2;
   sort ( v2a.begin ( ) , v2a.end ( ) , greater<int> ( ) );
   sort ( v2b.begin ( ) , v2b.end ( ) , greater<int> ( ) );

   cout << "Original vector v2a with range sorted by the\n "
        <<  "binary predicate greater is   v2a =  ( " ;
   for ( Iter2a = v2a.begin ( ) ; Iter2a != v2a.end ( ) ; Iter2a++ )
      cout << *Iter2a << " ";
   cout << ")." << endl;

   cout << "Original vector v2b with range sorted by the\n "
        <<  "binary predicate greater is   v2b =  ( " ;
   for ( Iter2b = v2b.begin ( ) ; Iter2b != v2b.end ( ) ; Iter2b++ )
      cout << *Iter2b << " ";
   cout << ")." << endl;

   // Constructing vector v3 with ranges sorted by mod_lesser
   vector <int> v3a ( v1a ), v3b ( v1b ) ,  v3 ( v1 );
   vector <int>::iterator Iter3a,  Iter3b, Iter3;
   sort ( v3a.begin ( ) , v3a.end ( ) , mod_lesser );
   sort ( v3b.begin ( ) , v3b.end ( ) , mod_lesser );

   cout << "Original vector v3a with range sorted by the\n "
        << "binary predicate mod_lesser is   v3a =  ( " ;
   for ( Iter3a = v3a.begin ( ) ; Iter3a != v3a.end ( ) ; Iter3a++ )
      cout << *Iter3a << " ";
   cout << ")." << endl;

   cout << "Original vector v3b with range sorted by the\n "
        << "binary predicate mod_lesser is   v3b =  ( " ;
   for ( Iter3b = v3b.begin ( ) ; Iter3b != v3b.end ( ) ; Iter3b++ )
      cout << *Iter3b << " ";
   cout << ")." << endl;

   // To merge inplace in ascending order with default binary
   // predicate less <int> ( )
   merge ( v1a.begin ( ) , v1a.end ( ) , v1b.begin ( ) , v1b.end ( ) , v1.begin ( ) );
   cout << "Merged inplace with default order,\n vector v1mod =  ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To merge inplace in descending order, specify binary
   // predicate greater<int>( )
   merge ( v2a.begin ( ) , v2a.end ( ) , v2b.begin ( ) , v2b.end ( ) ,
       v2.begin ( ) ,  greater <int> ( ) );
   cout << "Merged inplace with binary predicate greater specified,\n "
        << "vector v2mod  = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   // Applying A user-defined (UD) binary predicate mod_lesser
   merge ( v3a.begin ( ) , v3a.end ( ) , v3b.begin ( ) , v3b.end ( ) ,
       v3.begin ( ) ,  mod_lesser );
   cout << "Merged inplace with binary predicate mod_lesser specified,\n "
        << "vector v3mod  = ( " ; ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")." << endl;
}
```

## <a name="min"></a> min

Vergleicht zwei Objekte und gibt das kleinere der beiden zurück, wobei das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.

```cpp
template<class Type>
    const Type& min(
        const Type& left,
        const Type& right
    );
template<class Type, class Pr>
    const Type& min(
        const Type& left,
        const Type& right,
        BinaryPredicate comp
    );
template<class Type>
    Type min ( initializer_list<Type> _Ilist
    );
template<class Type, class Pr>    Type min (
        initializer_list<Type> _Ilist,
        BinaryPredicate comp
    );

```

### <a name="parameters"></a>Parameter

*linken* das erste der beiden verglichenen Objekte.

*richtige* das zweite der beiden Objekte mit dem verglichen wird.

*Comp* ein binäres Prädikat, das zum Vergleichen der beiden Objekte verwendet.

*_IList* das initializer_list-Element, das die zu vergleichenden Member enthält.

### <a name="return-value"></a>Rückgabewert

Das kleinere der beiden Objekte, es sei denn, keins ist geringer als das andere. In diesem Fall wird das erste der beiden Objekte zurückgegeben. Bei einem initializer_list-Element wird das geringste der Objekte in der Liste zurückgegeben.

### <a name="remarks"></a>Hinweise

Der `min`-Algorithmus ist ungewöhnlich, denn er weist Objekte auf, die als Parameter übergeben werden. Die meisten C++-Algorithmen der Standardbibliothek werden auf einem Elementbereich ausgeführt, dessen Position von als Parameter übergebenen Iteratoren angegeben wird. Wenn Sie eine Funktion benötigen, die einen Elementbereich nutzt, verwenden Sie [min_element](../standard-library/algorithm-functions.md#min_element).

### <a name="example"></a>Beispiel

```cpp
// alg_min.cpp
// compile with: /EHsc
#include <vector>
#include <set>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt
{
public:
    CInt( int n = 0 ) : m_nVal( n ){}
    CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
    CInt& operator=( const CInt& rhs ) {m_nVal =
    rhs.m_nVal; return *this;}
    bool operator<( const CInt& rhs ) const
        {return ( m_nVal < rhs.m_nVal );}
    friend ostream& operator<<(ostream& osIn, const CInt& rhs);

private:
    int m_nVal;
};

inline ostream& operator<<( ostream& osIn, const CInt& rhs )
{
    osIn << "CInt( " << rhs.m_nVal << " )";
       return osIn;
}

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
    if ( elem1 < 0 )
        elem1 = - elem1;
    if ( elem2 < 0 )
        elem2 = - elem2;
    return elem1 < elem2;
};

int main( )
{
    // Comparing integers directly using the min algorithm with
    // binary predicate mod_lesser & with default less than
    int a = 6, b = -7, c = 7 ;
    const int& result1 = min ( a, b, mod_lesser );
    const int& result2 = min ( b, c );

    cout << "The mod_lesser of the integers 6 & -7 is: "
        << result1 << "." << endl;
     cout << "The lesser of the integers -7 & 7 is: "
        << result2 << "." << endl;
    cout << endl;

// Comparing the members of an initializer_list
    const int& result3 = min({ a, c });
    const int& result4 = min({ a, b }, mod_lesser);

    cout << "The lesser of the integers 6 & 7 is: "
        << result3 << "." << endl;
    cout << "The mod_lesser of the integers 6 & -7 is: "
        << result4 << "." << endl;
    cout << endl;

    // Comparing set containers with elements of type CInt
       // using the min algorithm
    CInt c1 = 1, c2 = 2, c3 = 3;
    set<CInt> s1, s2, s3;
    set<CInt>::iterator s1_Iter, s2_Iter, s3_Iter;

    s1.insert ( c1 );
    s1.insert ( c2 );
    s2.insert ( c2 );
    s2.insert ( c3 );

    cout << "s1 = (";
    for ( s1_Iter = s1.begin( ); s1_Iter != --s1.end( ); s1_Iter++ )
        cout << " " << *s1_Iter << ",";
    s1_Iter = --s1.end( );
        cout << " " << *s1_Iter << " )." << endl;

    cout << "s2 = (";
    for ( s2_Iter = s2.begin( ); s2_Iter != --s2.end( ); s2_Iter++ )
        cout << " " << *s2_Iter << ",";
    s2_Iter = --s2.end( );
    cout << " " << *s2_Iter << " )." << endl;

    s3 = min ( s1, s2 );
    cout << "s3 = min ( s1, s2 ) = (";
    for ( s3_Iter = s3.begin( ); s3_Iter != --s3.end( ); s3_Iter++ )
        cout << " " << *s3_Iter << ",";
    s3_Iter = --s3.end( );
    cout << " " << *s3_Iter << " )." << endl << endl;

    // Comparing vectors with integer elements using min algorithm
    vector <int> v1, v2, v3, v4, v5;
    vector <int>::iterator Iter1, Iter2, Iter3, Iter4, Iter5;

    int i;
    for ( i = 0 ; i <= 2 ; i++ )
    {
        v1.push_back( i );
    }

    int ii;
    for ( ii = 0 ; ii <= 2 ; ii++ )
    {
        v2.push_back( ii );
    }

    int iii;
    for ( iii = 0 ; iii <= 2 ; iii++ )
    {
        v3.push_back( 2 * iii );
    }

    cout << "Vector v1 is ( " ;
    for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
        cout << *Iter1 << " ";
    cout << ")." << endl;

    cout << "Vector v2 is ( " ;
    for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
        cout << *Iter2 << " ";
    cout << ")." << endl;

    cout << "Vector v3 is ( " ;
    for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
        cout << *Iter3 << " ";
    cout << ")." << endl;

    v4 = min ( v1, v2 );
    v5 = min ( v1, v3 );

    cout << "Vector v4 = min ( v1,v2 ) is ( " ;
    for ( Iter4 = v4.begin( ) ; Iter4 != v4.end( ) ; Iter4++ )
        cout << *Iter4 << " ";
    cout << ")." << endl;

    cout << "Vector v5 = min ( v1,v3 ) is ( " ;
    for ( Iter5 = v5.begin( ) ; Iter5 != v5.end( ) ; Iter5++ )
        cout << *Iter5 << " ";
    cout << ")." << endl;
}
```

```Output
The mod_lesser of the integers 6 & -7 is: 6.
The lesser of the integers -7 & 7 is: -7.
The lesser of the integers 6 & 7 is: 6.The mod_lesser of the integers 6 & -7 is: 6.
s1 = ( CInt( 1 ), CInt( 2 ) ).
s2 = ( CInt( 2 ), CInt( 3 ) ).
s3 = min ( s1, s2 ) = ( CInt( 1 ), CInt( 2 ) ).

Vector v1 is ( 0 1 2 ).
Vector v2 is ( 0 1 2 ).
Vector v3 is ( 0 2 4 ).
Vector v4 = min ( v1,v2 ) is ( 0 1 2 ).
Vector v5 = min ( v1,v3 ) is ( 0 1 2 ).
```

## <a name="min_element"></a> min_element

Sucht das erste Vorkommen des kleinsten Elements in einem angegebenen Bereich, in dem das Sortierkriterium von einem binären Prädikat angegeben werden kann.

```cpp
template<class ForwardIterator>
ForwardIterator min_element(ForwardIterator first, ForwardIterator last );

template<class ForwardIterator, class BinaryPredicate>
ForwardIterator min_element(ForwardIterator first, ForwardIterator last, BinaryPredicate comp);

```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der die Position des ersten Elements im Bereich, nach dem kleinsten Element gesucht werden soll.

*letzte* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich, nach dem kleinsten Element gesucht werden soll.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das den Sinn definiert, in dem ein Element größer als die andere ist. Das binäre Prädikat akzeptiert zwei Argumente und sollte **true** zurückgeben, wenn das erste Element kleiner als das zweite Element ist, andernfalls wird **false** zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator, der die Position des ersten Vorkommen des kleinsten Elements im zu durchsuchenden Bereich adressiert.

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Komplexität ist linear: (`last` - `first`) – 1 Vergleiche sind für einen nicht leeren Bereich erforderlich.

### <a name="example"></a>Beispiel

```cpp
// alg_min_element.cpp
// compile with: /EHsc
#include <vector>
#include <set>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt
{
public:
   CInt( int n = 0 ) : m_nVal( n ){}
   CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
   CInt& operator=( const CInt& rhs ) {m_nVal =
   rhs.m_nVal; return *this;}
   bool operator<( const CInt& rhs ) const
      {return ( m_nVal < rhs.m_nVal );}
   friend ostream& operator<<( ostream& osIn, const CInt& rhs );

private:
   int m_nVal;
};

inline ostream& operator<<( ostream& osIn, const CInt& rhs )
{
   osIn << "CInt( " << rhs.m_nVal << " )";
   return osIn;
}

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
};

int main()
{
   // Searching a set container with elements of type CInt
   // for the minimum element
   CInt c1 = 1, c2 = 2, c3 = -3;
   set<CInt> s1;
   set<CInt>::iterator s1_Iter, s1_R1_Iter, s1_R2_Iter;

   s1.insert ( c1 );
   s1.insert ( c2 );
   s1.insert ( c3 );

   cout << "s1 = (";
   for ( s1_Iter = s1.begin( ); s1_Iter != --s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter << ",";
   s1_Iter = --s1.end( );
   cout << " " << *s1_Iter << " )." << endl;

   s1_R1_Iter = min_element ( s1.begin ( ) , s1.end ( ) );

   cout << "The smallest element in s1 is: " << *s1_R1_Iter << endl;
   cout << endl;

   // Searching a vector with elements of type int for the maximum
   // element under default less than & mod_lesser binary predicates
   vector <int> v1;
   vector <int>::iterator v1_Iter, v1_R1_Iter, v1_R2_Iter;

   int i;
   for ( i = 0 ; i <= 3 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii = 1 ; ii <= 4 ; ii++ )
   {
      v1.push_back( - 2 * ii );
   }

   cout << "Vector v1 is ( " ;
   for ( v1_Iter = v1.begin( ) ; v1_Iter != v1.end( ) ; v1_Iter++ )
      cout << *v1_Iter << " ";
   cout << ")." << endl;

   v1_R1_Iter = min_element ( v1.begin ( ) , v1.end ( ) );
   v1_R2_Iter = min_element ( v1.begin ( ) , v1.end ( ), mod_lesser);

   cout << "The smallest element in v1 is: " << *v1_R1_Iter << endl;
   cout << "The smallest element in v1 under the mod_lesser"
        << "\n binary predicate is: " << *v1_R2_Iter << endl;
}
```

```Output
s1 = ( CInt( -3 ), CInt( 1 ), CInt( 2 ) ).
The smallest element in s1 is: CInt( -3 )

Vector v1 is ( 0 1 2 3 -2 -4 -6 -8 ).
The smallest element in v1 is: -8
The smallest element in v1 under the mod_lesser
 binary predicate is: 0
```

## <a name="minmax_element"></a> minmax_element

Führt die Aufgaben aus, die von `min_element` und `max_element` in einem Aufruf erledigt werden.

```cpp
template<class ForwardIterator>
    pair< ForwardIterator, ForwardIterator >
        minmax_element(
            ForwardIterator  first,
            ForwardIterator Last
                 );
template<class ForwardIterator, class BinaryPredicate>
    pair< ForwardIterator, ForwardIterator >
        minmax_element(
            ForwardIterator  first,
            ForwardIterator Last,
            BinaryPredicate  comp
                );
```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der den Beginn eines Bereichs angibt.

*letzte* ein forward-Iterator, der das Ende eines Bereichs angibt.

*Comp* ein optionaler Test, der zum Sortieren von Elementen verwendet.

### <a name="return-value"></a>Rückgabewert

Rückgabe

`pair<ForwardIterator, ForwardIterator>`

`(` [Min_element](../standard-library/algorithm-functions.md#min_element)`(first, last), `[Max_element](../standard-library/algorithm-functions.md#max_element)`(first, last))`.

### <a name="remarks"></a>Hinweise

Die erste Vorlagenfunktion gibt Folgendes zurück:

`pair<ForwardIterator,ForwardIterator>`

`(min_element(_First,Last), max_element(_First,Last))`

Die zweite Vorlagenfunktion verhält sich genauso; der einzige Unterschied ist, dass sie `operator<(X, Y)` durch `comp (X, Y)` ersetzt.

Wenn die Sequenz nicht leer ist, führt die Funktion höchstens `3 * (last - first - 1) / 2` Vergleiche.

## <a name="minmax"></a> minmax

Vergleicht zwei Eingabeparameter und gibt diese als Paar, in der Reihenfolge "kleiner zu größer" zurück.

```cpp
template<class Type>
    pair<const Type&, const Type&>
        minmax(
            const Type& left,
            const Type& right
        );
template<class Type, class BinaryPredicate>
    pair<const Type&, const Type&>
        minmax(
            const Type& left,
            const Type& right,
            BinaryPredicate comp
        );
template<class Type>     pair<Type&, Type&>         minmax(
            initializer_list<Type> _Ilist
        );
template<class Type, class BinaryPredicate>
    pair<Type&, Type&>         minmax(
            initializer_list<Type> _Ilist,
            BinaryPredicate comp
        );

```

### <a name="parameters"></a>Parameter

*linken* das erste der beiden verglichenen Objekte.

*richtige* das zweite der beiden Objekte mit dem verglichen wird.

*Comp* ein binäres Prädikat, das zum Vergleichen der beiden Objekte verwendet.

*_IList* das initializer_list-Element, das die zu vergleichenden Member enthält.

### <a name="remarks"></a>Hinweise

Die erste Vorlagenfunktion gibt `pair<const Type&, const Type&>( right , left )` Wenn *rechten* ist kleiner als *linken*. Andernfalls wird `pair<const Type&, const Type&>( left , right )` zurückgegeben.

Die zweite Memberfunktion gibt ein zurück, wobei das erste Element ist kleiner als und die zweite größer ist, wenn durch das Prädikat verglichen *Comp*.

Die verbleibenden Vorlagenfunktionen Verhalten sich identisch, außer dass sie ersetzen die *linken* und *rechten* Parameter mit *_IList*.

Die Funktion führt genau einen Vergleich aus.

## <a name="mismatch"></a> mismatch

Vergleicht zwei Bereiche elementweise und findet die e erste Position mit einem Unterschied.

Verwenden Sie die Überladungen mit zwei Bereichen im C++14-Code, da die Überladungen, die nur einen einzigen Iterator für den zweiten Bereich nutzen, keine Unterschiede erkennen, wenn der zweite Bereich länger als der erste Bereich ist. Darüber hinaus führt dies zu einem nicht definierten Verhalten, wenn der zweite Bereich kürzer als der erste Bereich ist.

```cpp
template<class InputIterator1, class InputIterator2>
pair<InputIterator1, InputIterator2>>
mismatch(
     InputIterator1 First1,
     InputIterator1 Last1,
     InputIterator2 First2 );

template<class InputIterator1, class InputIterator2, class BinaryPredicate> pair<InputIterator1, InputIterator2>>
mismatch(
     InputIterator1 First1,
     InputIterator1 Last1,
     InputIterator2 First2,
     BinaryPredicate Comp );

//C++14
template<class InputIterator1, class InputIterator2>
pair<InputIterator1, InputIterator2>>
mismatch(
    InputIterator1 First1,
     InputIterator1 Last1,
     InputIterator2 First2,
     InputIterator2 Last2 );

template<class InputIterator1, class InputIterator2, class BinaryPredicate> pair<InputIterator1, InputIterator2>>
mismatch(
     InputIterator1 First1,
     InputIterator1 Last1,
     InputIterator2 First2,
     InputIterator2 Last2,
     BinaryPredicate Comp);
```

### <a name="parameters"></a>Parameter

*First1* ein Eingabe-Iterator, der die Position des ersten Elements im ersten Bereich getestet werden.

*Last1* ein Eingabe-Iterator, der die Position hinter dem letzten Element im ersten Bereich adressiert, die getestet werden.

*First2* ein Eingabe-Iterator, der die Position des ersten Elements im zweiten Bereich getestet werden.

*Last2* ein Eingabe-Iterator, der die Position hinter dem letzten Element im zweiten Bereich getestet werden.

*Comp* User-defined Function, Prädikat-Objekt, vergleicht die aktuellen Elemente in jedem Bereich und bestimmt, ob sie gleich sind. Gibt **TRUE** zurück, wenn erfüllt und **FALSE**, wenn nicht erfüllt.

### <a name="return-value"></a>Rückgabewert

Ein Paar von Iteratoren zu den Positionen des Konflikts in zwei Bereichen, der erste Komponenteniterator an die Position im ersten Bereich und der zweite Komponenteniterator an die Position im zweiten Bereich. Wenn es im Vergleich zwischen den Elementen keinen Unterschied gibt oder das binäre Prädikat in der zweiten Version durch alle Elementpaare aus den beiden Bereichen erfüllt wird, verweist der erste Komponenteniterator auf die erste Position hinter dem letzten Element in den ersten Bereich und der zweite Komponenteniterator auf die Position eine Stelle nach dem letzten Element im zweiten Bereich.

### <a name="remarks"></a>Hinweise

Die erste Vorlagenfunktion geht davon aus, dass im Bereich beginnend mit beginnend mit first2 so viele Elemente vorhanden sind, wie es im Bereich [first1, last1) der Fall ist. Wenn es mehr im zweiten Bereich gibt, werden sie ignoriert; wenn es weniger sind, hat das ein undefiniertes Verhalten zur Folge.

Der zu durchsuchende Bereich muss gültig sein. Alle Iteratoren müssen dereferenzierbar sein, und die letzte Position ist von der Ersten durch Zunahme erreichbar.

Die Zeitkomplexität des Algorithmus ist linear zur Anzahl der im kürzeren Bereich enthaltenen Elemente.

Das benutzerdefinierte Prädikat ist nicht erforderlich, um eine Äquivalenzbeziehung vorzugeben, die zwischen den dazugehörigen Operanden symmetrisch, reflexiv und transitiv ist.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird dein Konflikt verwendet werden kann. Die C ++ 03 Überlastung wird nur zum Veranschaulichen des Erzeugens eines unerwarteten Ergebnisses dargestellt.

```cpp
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>
#include <string>
#include <utility>

using namespace std;

// Return whether first element is twice the second
// Note that this is not a symmetric, reflexive and transitive equivalence.
// mismatch and equal accept such predicates, but is_permutation does not.
bool twice(int elem1, int elem2)
{
    return elem1 == elem2 * 2;
}

void PrintResult(const string& msg, const pair<vector<int>::iterator, vector<int>::iterator>& result,
    const vector<int>& left, const vector<int>& right)
{
    // If either iterator stops before reaching the end of its container,
    // it means a mismatch was detected.
    if (result.first != left.end() || result.second != right.end())
    {
        string leftpos(result.first == left.end() ? "end" : to_string(*result.first));
        string rightpos(result.second == right.end() ? "end" : to_string(*result.second));
        cout << msg << "mismatch. Left iterator at " << leftpos
            << " right iterator at " << rightpos << endl;
    }
    else
    {
        cout << msg << " match." << endl;
    }
}

int main()
{

    vector<int> vec_1{ 0, 5, 10, 15, 20, 25 };
    vector<int> vec_2{ 0, 5, 10, 15, 20, 25, 30 };

    // Testing different length vectors for mismatch (C++03)
    auto match_vecs = mismatch(vec_1.begin(), vec_1.end(), vec_2.begin());
    bool is_mismatch = match_vecs.first != vec_1.end();
    cout << "C++03: vec_1 and vec_2 are a mismatch: " << boolalpha << is_mismatch << endl;

    // Using dual-range overloads:

    // Testing different length vectors for mismatch (C++14)
    match_vecs = mismatch(vec_1.begin(), vec_1.end(), vec_2.begin(), vec_2.end());
    PrintResult("C++14: vec_1 and vec_2: ", match_vecs, vec_1, vec_2);

    // Identify point of mismatch between vec_1 and modified vec_2.
    vec_2[3] = 42;
    match_vecs = mismatch(vec_1.begin(), vec_1.end(), vec_2.begin(), vec_2.end());
    PrintResult("C++14 vec_1 v. vec_2 modified: ", match_vecs, vec_1, vec_2);

    // Test vec_3 and vec_4 for mismatch under the binary predicate twice (C++14)
    vector<int> vec_3{ 10, 20, 30, 40, 50, 60 };
    vector<int> vec_4{ 5, 10, 15, 20, 25, 30 };
    match_vecs = mismatch(vec_3.begin(), vec_3.end(), vec_4.begin(), vec_4.end(), twice);
    PrintResult("vec_3 v. vec_4 with pred: ", match_vecs, vec_3, vec_4);

    vec_4[5] = 31;
    match_vecs = mismatch(vec_3.begin(), vec_3.end(), vec_4.begin(), vec_4.end(), twice);
    PrintResult("vec_3 v. modified vec_4 with pred: ", match_vecs, vec_3, vec_4);

    // Compare a vector<int> to a list<int>
    list<int> list_1{ 0, 5, 10, 15, 20, 25 };
    auto match_vec_list = mismatch(vec_1.begin(), vec_1.end(), list_1.begin(), list_1.end());
    is_mismatch = match_vec_list.first != vec_1.end() || match_vec_list.second != list_1.end();
    cout << "vec_1 and list_1 are a mismatch: " << boolalpha << is_mismatch << endl;

    char c;
    cout << "Press a key" << endl;
    cin >> c;

}

/*
Output:
C++03: vec_1 and vec_2 are a mismatch: false
C++14: vec_1 and vec_2: mismatch. Left iterator at end right iterator at 30
C++14 vec_1 v. vec_2 modified: mismatch. Left iterator at 15 right iterator at 42
C++14 vec_3 v. vec_4 with pred:  match.
C++14 vec_3 v. modified vec_4 with pred: mismatch. Left iterator at 60 right iterator at 31
C++14: vec_1 and list_1 are a mismatch: false
Press a key
*/

```

## <a name="alg_move"></a> &lt;alg&gt; move

Verschiebt Elemente, die einem angegebenen Bereich zugeordnet sind.

```cpp
template<class InputIterator, class OutputIterator>
    OutputIterator move(
        InputIterator first,
        InputIterator last,
        OutputIterator dest
                  );
```

### <a name="parameters"></a>Parameter

*erste* ein Eingabe-Iterator, der angibt, wo Sie anfangen des Bereichs von Elementen zu verschieben.

*letzte* ein Eingabe-Iterator, der das Ende eines Bereichs von Elementen, verschieben angibt.

*Dest* Ausgabeiterator, der zu verschiebenden Elemente enthalten ist.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion wertet `*(dest + N) = move(*(first + N))` einmal für jedes `N` im Bereich von `[0, last - first)`, bei strikt ansteigenden Werten von `N` beginnend mit dem niedrigsten Wert. Dann wird `dest + N` zurückgegeben. Wenn `dest` und *erste* Bereiche des Speichers, bestimmt *Dest* darf nicht in den Bereich sein `[first, last)`.

## <a name="move_backward"></a> move_backward

Verschiebt die Elemente eines Iterators in einen anderen. Die Verschiebung beginnt mit dem letzten Element in einem angegebenen Bereich und endet mit dem ersten Element in diesem Bereich.

```cpp
template<class BidirectionalIterator1, class BidirectionalIterator2>
   BidirectionalIterator2 move_backward(
       BidirectionalIterator1 first,
       BidirectionalIterator1 last,
       BidirectionalIterator2 destEnd);

```

### <a name="parameters"></a>Parameter

*erste* ein Iterator, der den Beginn eines Bereichs Elemente verschoben angibt.

*letzte* ein Iterator, der zeigt, an das Ende eines Bereichs Elemente verschoben. Dieses Element wird nicht verschoben.

*DestEnd* ein bidirektionaler Iterator, der die Position hinter dem letzten Element im Zielbereich.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion wertet `*(destEnd - N - 1) = move(*(last - N - 1))` einmal für jedes `N` im Bereich von `[0, last - first)`, bei strikt ansteigenden Werten von `N` beginnend mit dem niedrigsten Wert. Dann wird `destEnd - (last - first)` zurückgegeben. Wenn *DestEnd* und *erste* Bereiche des Speichers, bestimmt *DestEnd* darf nicht in den Bereich sein `[first, last)`.

`move` und `move_backward` entsprechen funktional der Verwendung von `copy` und `copy_backward` mit einem Verschiebeiterator.

## <a name="next_permutation"></a> next_permutation

Ordnet die Elemente in einem Bereich neu, damit die ursprüngliche Reihenfolge von der lexikografisch nächsthöheren Permutation ersetzt wird, falls vorhanden, wobei die Bedeutung von „nächsthöher“ durch ein binäres Prädikat angegeben werden kann.

```cpp
template<class BidirectionalIterator>
bool next_permutation(BidirectionalIterator first, BidirectionalIterator last);

template<class BidirectionalIterator, class BinaryPredicate>
bool next_permutation(BidirectionalIterator first, BidirectionalIterator last, BinaryPredicate comp);

```

### <a name="parameters"></a>Parameter

*erste* ein bidirektionaler Iterator, die Position des ersten Elements im Bereich zu permutierenden.

*letzte* ein bidirektionaler Iterator, die Position hinter dem letzten Element im Bereich zu permutierenden.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das das Vergleichskriterium erfüllt werden muss, indem aufeinander folgende Elemente in der Reihenfolge definiert. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die lexikographisch nächste Permutation beendet wird und die ursprüngliche Reihenfolge des Bereichs ersetzt hat; andernfalls **FALSE**. In diesem Fall wird die Reihenfolge in die lexikographisch kleinste Permutation umgewandelt.

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Das standardmäßige binäre Prädikat ist weniger als vergleichbar und die Elemente im Bereich müssen weniger als vergleichbar sein, um sicherzustellen, dass die nächste Permutation gut definiert ist.

Die Komplexität ist linear, wobei höchstens (* Nachname - Vorname *) / 2 getauscht.

### <a name="example"></a>Beispiel

```cpp
// alg_next_perm.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt
{
public:
   CInt( int n = 0 ) : m_nVal( n ){}
   CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
   CInt&   operator=( const CInt& rhs ) {m_nVal =
   rhs.m_nVal; return *this;}
   bool operator<( const CInt& rhs ) const
      { return ( m_nVal < rhs.m_nVal );}
   friend   ostream& operator<<( ostream& osIn, const CInt& rhs );

private:
   int m_nVal;
};

inline ostream& operator<<( ostream& osIn, const CInt& rhs )
{
   osIn << "CInt( " << rhs.m_nVal << " )";
   return osIn;
}

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
};

int main( )
{
   // Reordering the elements of type CInt in a deque
   // using the prev_permutation algorithm
   CInt c1 = 5, c2 = 1, c3 = 10;
   bool deq1Result;
   deque<CInt> deq1, deq2, deq3;
   deque<CInt>::iterator d1_Iter;

   deq1.push_back ( c1 );
   deq1.push_back ( c2 );
   deq1.push_back ( c3 );

   cout << "The original deque of CInts is deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl;

   deq1Result = next_permutation ( deq1.begin ( ) , deq1.end ( ) );

   if ( deq1Result )
      cout << "The lexicographically next permutation "
           << "exists and has\nreplaced the original "
           << "ordering of the sequence in deq1." << endl;
   else
      cout << "The lexicographically next permutation doesn't "
           << "exist\n and the lexicographically "
           << "smallest permutation\n has replaced the "
           << "original ordering of the sequence in deq1." << endl;

   cout << "After one application of next_permutation,\n deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl << endl;

   // Permuting vector elements with binary function mod_lesser
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = -3 ; i <= 3 ; i++ )
   {
      v1.push_back( i );
   }

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   next_permutation ( v1.begin ( ) , v1.end ( ) , mod_lesser );

   cout << "After the first next_permutation, vector v1 is:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   int iii = 1;
   while ( iii <= 5 ) {
      next_permutation ( v1.begin ( ) , v1.end ( ) , mod_lesser );
      cout << "After another next_permutation of vector v1,\n v1 =   ( " ;
      for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ;Iter1 ++ )
         cout << *Iter1  << " ";
      cout << ")." << endl;
      iii++;
   }
}
```

```Output
The original deque of CInts is deq1 = ( CInt( 5 ), CInt( 1 ), CInt( 10 ) ).
The lexicographically next permutation exists and has
replaced the original ordering of the sequence in deq1.
After one application of next_permutation,
 deq1 = ( CInt( 5 ), CInt( 10 ), CInt( 1 ) ).

Vector v1 is ( -3 -2 -1 0 1 2 3 ).
After the first next_permutation, vector v1 is:
 v1 = ( -3 -2 -1 0 1 3 2 ).
After another next_permutation of vector v1,
 v1 =   ( -3 -2 -1 0 2 1 3 ).
After another next_permutation of vector v1,
 v1 =   ( -3 -2 -1 0 2 3 1 ).
After another next_permutation of vector v1,
 v1 =   ( -3 -2 -1 0 3 1 2 ).
After another next_permutation of vector v1,
 v1 =   ( -3 -2 -1 0 3 2 1 ).
After another next_permutation of vector v1,
 v1 =   ( -3 -2 -1 1 0 2 3 ).
```

## <a name="nth_element"></a> nth_element

Partitioniert einen Bereich von Elementen und ermittelt das *n*-te-Element der Sequenz im Bereich, sodass alle Elemente davor kleiner oder gleich sind und alle Elemente, die in der Sequenz folgen, größer oder gleich sind.

```cpp
template<class RandomAccessIterator>
void nth_element( RandomAccessIterator first, RandomAccessIterator _Nth, RandomAccessIterator last);

template<class RandomAccessIterator, class BinaryPredicate>
 void nth_element( RandomAccessIterator first, RandomAccessIterator _Nth, RandomAccessIterator last, BinaryPredicate comp);

```

### <a name="parameters"></a>Parameter

*erste* ein random-Access-Iterator, der die Position des ersten Elements im Bereich partitioniert werden soll.

*_Nth* ein zufälliger eingabeiterator, der die Position des Elements, an der Grenze der Partition korrekt sortiert werden.

*letzte* ein zufälliger eingabeiterator, der die Position hinter dem letzten Element im Bereich adressiert partitioniert werden soll.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das das Vergleichskriterium erfüllt werden muss, indem aufeinander folgende Elemente in der Reihenfolge definiert. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Der `nth_element`-Algorithmus stellt nicht sicher, dass Elemente in Unterbereichen, die sich auf beiden Seiten des *n*-ten Elements befinden, sortiert werden. Deshalb gibt es weniger Garantien als `partial_sort`, das Elemente in einem Bereich unter ausgewählten Elementen ordnet, und das möglicherweise als schnellere Alternative zu `partial_sort` verwendet werden kann, wenn eine Sortierung des niedrigeren Bereichs nicht erforderlich ist.

Wenn keins kleiner als das andere ist, sind Elemente äquivalent, aber nicht unbedingt gleich.

Der Durchschnitt einer sortierungskomplexität ist bezüglich linear * Nachname - Vorname *.

### <a name="example"></a>Beispiel

```cpp
// alg_nth_elem.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether first element is greater than the second
bool UDgreater ( int elem1, int elem2 ) {
   return elem1 > elem2;
}

int main() {
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
      v1.push_back( 3 * i );

   int ii;
   for ( ii = 0 ; ii <= 5 ; ii++ )
      v1.push_back( 3 * ii + 1 );

   int iii;
   for ( iii = 0 ; iii <= 5 ; iii++ )
      v1.push_back( 3 * iii +2 );

   cout << "Original vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   nth_element(v1.begin( ), v1.begin( ) + 3, v1.end( ) );
   cout << "Position 3 partitioned vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order, specify binary predicate
   nth_element( v1.begin( ), v1.begin( ) + 4, v1.end( ),
          greater<int>( ) );
   cout << "Position 4 partitioned (greater) vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   random_shuffle( v1.begin( ), v1.end( ) );
   cout << "Shuffled vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // A user-defined (UD) binary predicate can also be used
   nth_element( v1.begin( ), v1.begin( ) + 5, v1.end( ), UDgreater );
   cout << "Position 5 partitioned (UDgreater) vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

## <a name="none_of"></a> none_of

Gibt **"true"** Wenn niemals eine Bedingung zwischen Elementen im angegebenen Bereich vorhanden ist.

```cpp
template<class InputIterator, class BinaryPredicate>
bool none_of(InputIterator first, InputIterator last, BinaryPredicate comp);
```

### <a name="parameters"></a>Parameter

*erste* ein Eingabe-Iterator, der angibt, wo Sie anfangen, um einen Bereich von Elementen für eine Bedingung zu überprüfen.

*letzte* ein Eingabe-Iterator, der das Ende eines Bereichs von Elementen angibt.

*Comp* die Bedingung zu testen. Diese Bedingung wird von einem benutzerdefinierten Prädikatfunktionsobjekt bereitgestellt. Ein Prädikat akzeptiert ein einzelnes Argument und gibt entweder **TRUE** oder **FALSE** zurück.

### <a name="return-value"></a>Rückgabewert

Gibt **"true"** , wenn die Bedingung nicht mindestens einmal im angegebenen Bereich erkannt wird und **"false"** , wenn die Bedingung erkannt wird.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt **"true"** nur dann für einige `N` im Bereich von `[0, last - first)`, das Prädikat `comp(*(first + N))` ist immer **"false"**.

## <a name="partial_sort"></a> partial_sort

Ordnet eine bestimmte Anzahl von kleineren Elementen in einem Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird.

```cpp
template<class RandomAccessIterator>
   void partial_sort(
      RandomAccessIterator first,
      RandomAccessIterator sortEnd,
      RandomAccessIterator last);

template<class RandomAccessIterator, class BinaryPredicate>
   void partial_sort(
      RandomAccessIterator first,
      RandomAccessIterator sortEnd,
      RandomAccessIterator last
      BinaryPredicate comp);

```

### <a name="parameters"></a>Parameter

*erste* ein zufälliger eingabeiterator, der die Position des ersten Elements im Bereich sortiert werden soll.

*SortEnd* ein zufälliger eingabeiterator, der die Position hinter dem letzten Element in dem Unterbereich adressiert sortiert werden soll.

*letzte* ein zufälliger eingabeiterator, der die Position hinter dem letzten Element im Bereich adressiert teilweise sortiert werden soll.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das das Vergleichskriterium erfüllt werden muss, indem aufeinander folgende Elemente in der Reihenfolge definiert. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Wenn keins kleiner als das andere ist, sind Elemente äquivalent, aber nicht unbedingt gleich. Die `sort` Algorithmus ist nicht stabil und garantiert nicht, dass die relative Sortierung equivalenter Elemente beibehalten wird. Der Algorithmus `stable_sort` behält diese ursprüngliche Sortierung bei.

Die durchschnittliche teilsortierungskomplexität ist *O*((`last`- `first`) Log (`sortEnd`- `first`)).

### <a name="example"></a>Beispiel

```cpp
// alg_partial_sort.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether first element is greater than the second
bool UDgreater ( int elem1, int elem2 )
{
   return elem1 > elem2;
}

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   int ii;
   for ( ii = 0 ; ii <= 5 ; ii++ )
   {
      v1.push_back( 2 * ii +1 );
   }

   cout << "Original vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   partial_sort(v1.begin( ), v1.begin( ) + 6, v1.end( ) );
   cout << "Partially sorted vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To partially sort in descending order, specify binary predicate
   partial_sort(v1.begin( ), v1.begin( ) + 4, v1.end( ), greater<int>( ) );
   cout << "Partially resorted (greater) vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // A user-defined (UD) binary predicate can also be used
   partial_sort(v1.begin( ), v1.begin( ) + 8, v1.end( ),
 UDgreater );
   cout << "Partially resorted (UDgreater) vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector:
 v1 = ( 0 2 4 6 8 10 1 3 5 7 9 11 )
Partially sorted vector:
 v1 = ( 0 1 2 3 4 5 10 8 6 7 9 11 )
Partially resorted (greater) vector:
 v1 = ( 11 10 9 8 0 1 2 3 4 5 6 7 )
Partially resorted (UDgreater) vector:
 v1 = ( 11 10 9 8 7 6 5 4 0 1 2 3 )
```

## <a name="partial_sort_copy"></a> partial_sort_copy

Kopiert Elemente aus einem Quellbereich in einen Zielbereich, in dem die Quellelemente entweder durch kleiner als oder durch ein anderes festgelegtes binäres Prädikat sortiert werden.

```cpp
template<class InputIterator, class RandomAccessIterator>
RandomAccessIterator partial_sort_copy(
    InputIterator first1,
    InputIterator last1,
    RandomAccessIterator first2,
    RandomAccessIterator last2 );

template<class InputIterator, class RandomAccessIterator, class BinaryPredicate>
RandomAccessIterator partial_sort_copy(
     InputIterator first1,
     InputIterator last1,
     RandomAccessIterator first2,
     RandomAccessIterator last2,
     BinaryPredicate comp);
```

### <a name="parameters"></a>Parameter

*first1* ein eingabeiterator, der die Position des ersten Elements im Quellbereich adressiert.

*Last1* ein eingabeiterator, der die Position hinter dem letzten Element im Quellbereich adressiert.

*first2* ein zufälliger eingabeiterator, der die Position des ersten Elements im sortierten Zielbereich adressiert.

*Last2* ein zufälliger eingabeiterator, der die Position hinter dem letzten Element im sortierten Zielbereich adressiert.

*Comp* User-defined Function, Prädikat-Objekt, das definiert die Bedingung erfüllt wird, wenn zwei Elemente enthalten sind, die ausgeführt werden als gleichwertig. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

Ein zufälliger Eingabeiterator, der Elemente im Zielbereich, die direkt hinter dem letzten aus dem Quellbereich eingefügten Element liegen, adressiert.

### <a name="remarks"></a>Hinweise

Die Quell- und Zielbereiche dürfen sich nicht überlappen und müssen gültig sein: Alle Zeiger müssen dereferenzierbar sein; die letzte Position innerhalb jeder Sequenz muss von der ersten Position aus durch Zunahme erreichbar sein.

Das binäre Prädikat muss eine strikte schwache Sortierung bereitstellen, sodass Elemente, die nicht äquivalent sind, sortiert werden, aber Elemente, die äquivalent sind, nicht sortiert werden. Wenn keins kleiner als das andere ist, sind Elemente äquivalent, aber nicht unbedingt gleich.

### <a name="example"></a>Beispiel

```cpp
// alg_partial_sort_copy.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <functional>
#include <iostream>

int main() {
    using namespace std;
    vector<int> v1, v2;
    list<int> list1;
    vector<int>::iterator iter1, iter2;
    list<int>::iterator list1_Iter, list1_inIter;

    int i;
    for (i = 0; i <= 9; i++)
        v1.push_back(i);

    random_shuffle(v1.begin(), v1.end());

    list1.push_back(60);
    list1.push_back(50);
    list1.push_back(20);
    list1.push_back(30);
    list1.push_back(40);
    list1.push_back(10);

    cout << "Vector v1 = ( " ;
    for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
        cout << *iter1 << " ";
    cout << ")" << endl;

    cout << "List list1 = ( " ;
    for (list1_Iter = list1.begin();
         list1_Iter!= list1.end();
         list1_Iter++)
        cout << *list1_Iter << " ";
    cout << ")" << endl;

    // Copying a partially sorted copy of list1 into v1
    vector<int>::iterator result1;
    result1 = partial_sort_copy(list1.begin(), list1.end(),
             v1.begin(), v1.begin() + 3);

    cout << "List list1 Vector v1 = ( " ;
    for (iter1 = v1.begin() ; iter1 != v1.end() ; iter1++)
        cout << *iter1 << " ";
    cout << ")" << endl;
    cout << "The first v1 element one position beyond"
         << "\n the last L 1 element inserted was " << *result1
         << "." << endl;

    // Copying a partially sorted copy of list1 into v2
    int ii;
    for (ii = 0; ii <= 9; ii++)
        v2.push_back(ii);

    random_shuffle(v2.begin(), v2.end());
    vector<int>::iterator result2;
    result2 = partial_sort_copy(list1.begin(), list1.end(),
             v2.begin(), v2.begin() + 6);

    cout << "List list1 into Vector v2 = ( " ;
    for (iter2 = v2.begin() ; iter2 != v2.end(); iter2++)
        cout << *iter2 << " ";
    cout << ")" << endl;
    cout << "The first v2 element one position beyond"
         << "\n the last L 1 element inserted was " << *result2
         << "." << endl;
}
```

## <a name="partition"></a> partition

Klassifiziert Elemente in einem Bereich in zwei zusammenhanglose Sätze, wenn diese Elemente ein unäres Prädikat erfüllen, das denen direkt vorausgeht, die es nicht erfüllen können.

```cpp
template<class BidirectionalIterator, class Predicate>
   BidirectionalIterator partition(
      BidirectionalIterator first,
      BidirectionalIterator last,
      Predicate comp);

```

### <a name="parameters"></a>Parameter

*erste* ein bidirektionaler Iterator, der die Position des ersten Elements im Bereich von partitioniert werden soll.

*letzte* ein bidirektionaler Iterator, der die Position hinter dem letzten Element im Bereich adressiert, die partitioniert werden.

*Comp* User-defined Function, Prädikat-Objekt, das definiert die Bedingung erfüllt wird, wenn ein Element ist klassifiziert werden sollen. Ein Prädikat akzeptiert ein einzelnes Argument und gibt entweder **TRUE** oder **FALSE** zurück.

### <a name="return-value"></a>Rückgabewert

Ein bidirektionaler Iterator, der die Position des ersten Elements in dem Bereich adressiert, das die Prädikatbedingung nicht erfüllt.

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Elemente *a* und *b* sind äquivalent, aber nicht unbedingt gleich, wenn sowohl *Pr* (*a*, *b*) als auch *Pr* (*b*, *a*) dort FALSE sind, wo *Pr* das parameterspezifische Prädikat ist. Die `partition` Algorithmus ist nicht stabil und garantiert nicht, dass die relative Sortierung equivalenter Elemente beibehalten wird. Der Algorithmus `stable_ partition` behält diese ursprüngliche Sortierung bei.

Die Komplexität ist linear: Es gibt (`last` - `first`) Anwendungen *Comp* und höchstens (`last` - `first`) / 2 getauscht.

### <a name="example"></a>Beispiel

```cpp
// alg_partition.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater5 ( int value ) {
   return value >5;
}

int main( ) {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 0 ; i <= 10 ; i++ )
   {
      v1.push_back( i );
   }
   random_shuffle( v1.begin( ), v1.end( ) );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Partition the range with predicate greater10
   partition ( v1.begin( ), v1.end( ), greater5 );
   cout << "The partitioned set of elements in v1 is: ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="partition_copy"></a> partition_copy

Kopiert Elemente, die für die eine Bedingung ist **"true"** an ein Ziel, und für den die Bedingung **"false"** in einen anderen. Die Elemente müssen von einem angegebenen Bereich stammen.

```cpp
template<class InputIterator, class OutputIterator1, class OutputIterator2, class Predicate>
    pair<OutputIterator1, OutputIterator2>
        partition_copy(
            InputIterator first,
            InputIterator last,
            OutputIterator1 dest1,
            OutputIterator2 dest2,
            Predicate pred
        );
```

### <a name="parameters"></a>Parameter

*erste* ein Eingabe-Iterator, der den Beginn eines Bereichs zu prüfen, bis eine Bedingung angibt.

*letzte* ein Eingabe-Iterator, der das Ende eines Bereichs angibt.

*dest1* ein Ausgabeiterator, der verwendet wird, um Elemente zu kopieren, die für eine Bedingung "true" zurückgeben getestet mit *_Pred*.

*dest2* ein Ausgabeiterator, der verwendet wird, um Elemente zu kopieren, die eine Bedingung "false" zurückgeben getestet mit *_Pred*.

*_Pred* die Bedingung zu testen. Diese Bedingung wird von einem benutzerdefinierten Prädikatfunktionsobjekt bereitgestellt, das die zu prüfende Bedingung definiert. Ein Prädikat akzeptiert ein einzelnes Argument und gibt entweder **TRUE** oder **FALSE** zurück.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion kopiert jedes Element `X` in `[first,last)` zu `*dest1++` Wenn `_Pred(X)` ist "true" oder `*dest2++` Wenn nicht. Er gibt `pair<OutputIterator1, OutputIterator2>(dest1, dest2)` zurück.

## <a name="partition_point"></a> partition_point

Gibt das erste Element im angegebenen Bereich zurück, der die Bedingung nicht erfüllt. Die Elemente werden so sortiert, dass die, die die Bedingung erfüllen, vor denen angeordnet werden, die die Bedingung nicht erfüllen.

```cpp
template<class ForwardIterator, class Predicate>
    ForwardIterator partition_point(
        ForwardIterator first,
        ForwardIterator last,
        Predicate comp
    );
```

### <a name="parameters"></a>Parameter

*erste* ein `ForwardIterator` , der den Beginn eines Bereichs zu prüfen, bis eine Bedingung angibt.

*letzte* ein `ForwardIterator` , der das Ende eines Bereichs angibt.

*Comp* die Bedingung zu testen. Dies wird von einem benutzerdefinierten Prädikatfunktionsobjekt bereitgestellt, das bzw. der die Bedingung definiert, die vom zu suchenden Element erfüllt wird. Ein Prädikat akzeptiert ein einzelnes Argument und gibt entweder **TRUE** oder **FALSE** zurück.

### <a name="return-value"></a>Rückgabewert

Gibt eine `ForwardIterator` , verweist auf das erste Element, das die Bedingung geprüft nicht erfüllt *Comp*, oder gibt *letzten* Wenn keiner gefunden wird.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion findet den ersten Iterator `it` in `[first, last)` für die `comp(*it)` ist **"false"**. Die Sequenz muss sortiert werden, indem *Comp*.

## <a name="pop_heap"></a> pop_heap

Entfernt das größte Element von der Vorderseite eines Heaps und fügt es in die vorletzte Position des Bereichs ein und bildet dann einen neuen Heap aus den übrigen Elementen.

```cpp
template<class RandomAccessIterator>
void pop_heap( RandomAccessIterator first, RandomAccessIterator last);

template<class RandomAccessIterator, class BinaryPredicate>
void pop_heap(RandomAccessIterator first, RandomAccessIterator last, BinaryPredicate comp);

```

### <a name="parameters"></a>Parameter

*erste* ein zufälliger eingabeiterator, der die Position des ersten Elements im Heap adressiert.

*letzte* ein zufälliger eingabeiterator, der die Position hinter dem letzten Element im Heap adressiert.

*Comp* ermitteln benutzerdefiniertes prädikatfunktionsobjekt, das definiert, in dem ein Element kleiner als ein anderes ist. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="remarks"></a>Hinweise

Der Algorithmus `pop_heap` ist die Umkehrung des Vorgangs, der vom push_heap-Algorithmus durchgeführt wird. In diesem Vorgang wird das vorletzte Element eines Bereichs einem Heap hinzugefügt, der aus den vorherigen Elementen des Bereichs besteht, wenn das hinzuzufügende Element größer als alle anderen Elemente des Heaps sind.

Heaps haben zwei Eigenschaften:

- Das erste Element ist immer das größte.

- Elemente können in logarithmischer Zeit hinzugefügt oder entfernt werden.

Heaps sind ideal zum Implementieren von Vorrangwarteschlangen. Sie werden beim Implementieren des C++-Standardbibliothekadapters [priority_queue-Klasse](../standard-library/priority-queue-class.md) verwendet.

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Der Bereich, ohne das neu am Ende hinzugefügte Element, muss ein Heap sein.

Die Komplexität ist logarithmisch ist, dass höchstens Log (* Nachname - Vorname *) vergleichen.

### <a name="example"></a>Beispiel

```cpp
// alg_pop_heap.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

int main( )  {
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 1 ; i <= 9 ; i++ )
      v1.push_back( i );

   // Make v1 a heap with default less than ordering
   random_shuffle( v1.begin( ), v1.end( ) );
   make_heap ( v1.begin( ), v1.end( ) );
   cout << "The heaped version of vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Add an element to the back of the heap
   v1.push_back( 10 );
   push_heap( v1.begin( ), v1.end( ) );
   cout << "The reheaped v1 with 10 added is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Remove the largest element from the heap
   pop_heap( v1.begin( ), v1.end( ) );
   cout << "The heap v1 with 10 removed is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl << endl;

   // Make v1 a heap with greater-than ordering with a 0 element
   make_heap ( v1.begin( ), v1.end( ), greater<int>( ) );
   v1.push_back( 0 );
   push_heap( v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "The 'greater than' reheaped v1 puts the smallest "
        << "element first:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Application of pop_heap to remove the smallest element
   pop_heap( v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "The 'greater than' heaped v1 with the smallest element\n "
        << "removed from the heap is: ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="prev_permutation"></a> prev_permutation

Ordnet die Elemente in einem Bereich neu, damit die ursprüngliche Reihenfolge von der lexikografisch vorherigen höheren Permutation ersetzt wird, falls vorhanden, wobei die Bedeutung von „vorherige“ durch ein binäres Prädikat angegeben werden kann.

```cpp
template<class BidirectionalIterator>
   bool prev_permutation(
      BidirectionalIterator first,
      BidirectionalIterator last);

template<class BidirectionalIterator, class BinaryPredicate>
   bool prev_permutation(
      BidirectionalIterator first,
      BidirectionalIterator last,
      BinaryPredicate comp);

```

### <a name="parameters"></a>Parameter

*erste* ein bidirektionaler Iterator, die Position des ersten Elements im Bereich zu permutierenden.

*letzte* ein bidirektionaler Iterator, die Position hinter dem letzten Element im Bereich zu permutierenden.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das das Vergleichskriterium erfüllt werden muss, indem aufeinander folgende Elemente in der Reihenfolge definiert. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die lexikographisch vorherige Permutation vorhanden ist und ersetzt die ursprüngliche Reihenfolge des Bereichs; andernfalls **"false"**, in diesem Fall wird die Reihenfolge in die lexikographisch größte umgewandelt Permutation.

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Das standardmäßige binäre Prädikat ist weniger und die Elemente des Bereichs müssen weniger als vergleichbar sein, um sicherzustellen, dass die vorherige Permutation gut definiert ist.

Die Komplexität ist linear, wobei höchstens (`last` -  `first`) / 2 getauscht.

### <a name="example"></a>Beispiel

```cpp
// alg_prev_perm.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt {
public:
   CInt( int n = 0 ) : m_nVal( n ){}
   CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
   CInt&   operator=( const CInt& rhs ) {m_nVal =
   rhs.m_nVal; return *this;}
   bool operator<( const CInt& rhs ) const
      {return ( m_nVal < rhs.m_nVal );}
   friend ostream& operator<<( ostream& osIn, const CInt& rhs );

private:
   int m_nVal;
};

inline ostream& operator<<( ostream& osIn, const CInt& rhs ) {
   osIn << "CInt( " << rhs.m_nVal << " )";
   return osIn;
}

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser (int elem1, int elem2 ) {
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
};

int main() {
   // Reordering the elements of type CInt in a deque
   // using the prev_permutation algorithm
   CInt c1 = 1, c2 = 5, c3 = 10;
   bool deq1Result;
   deque<CInt> deq1, deq2, deq3;
   deque<CInt>::iterator d1_Iter;

   deq1.push_back ( c1 );
   deq1.push_back ( c2 );
   deq1.push_back ( c3 );

   cout << "The original deque of CInts is deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl;

   deq1Result = prev_permutation ( deq1.begin ( ) , deq1.end ( ) );

   if ( deq1Result )
      cout << "The lexicographically previous permutation "
           << "exists and has \nreplaced the original "
           << "ordering of the sequence in deq1." << endl;
   else
      cout << "The lexicographically previous permutation doesn't "
           << "exist\n and the lexicographically "
           << "smallest permutation\n has replaced the "
           << "original ordering of the sequence in deq1." << endl;

   cout << "After one application of prev_permutation,\n deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl << endl;

   // Permutating vector elements with binary function mod_lesser
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = -3 ; i <= 3 ; i++ )
      v1.push_back( i );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   prev_permutation ( v1.begin ( ) , v1.end ( ) , mod_lesser );

   cout << "After the first prev_permutation, vector v1 is:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   int iii = 1;
   while ( iii <= 5 ) {
      prev_permutation ( v1.begin ( ) , v1.end ( ) , mod_lesser );
      cout << "After another prev_permutation of vector v1,\n v1 =   ( " ;
      for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ;Iter1 ++ )
         cout << *Iter1  << " ";
      cout << ")." << endl;
      iii++;
   }
}
```

```Output
The original deque of CInts is deq1 = ( CInt( 1 ), CInt( 5 ), CInt( 10 ) ).
The lexicographically previous permutation doesn't exist
 and the lexicographically smallest permutation
 has replaced the original ordering of the sequence in deq1.
After one application of prev_permutation,
 deq1 = ( CInt( 10 ), CInt( 5 ), CInt( 1 ) ).

Vector v1 is ( -3 -2 -1 0 1 2 3 ).
After the first prev_permutation, vector v1 is:
 v1 = ( -3 -2 0 3 2 1 -1 ).
After another prev_permutation of vector v1,
 v1 =   ( -3 -2 0 3 -1 2 1 ).
After another prev_permutation of vector v1,
 v1 =   ( -3 -2 0 3 -1 1 2 ).
After another prev_permutation of vector v1,
 v1 =   ( -3 -2 0 2 3 1 -1 ).
After another prev_permutation of vector v1,
 v1 =   ( -3 -2 0 2 -1 3 1 ).
After another prev_permutation of vector v1,
 v1 =   ( -3 -2 0 2 -1 1 3 ).
```

## <a name="push_heap"></a> push_heap

Fügt ein Element hinzu, das sich am Ende eines Bereichs in einem vorhandenen Heap befindet, der aus den vorherigen Elementen im Bereich besteht.

```cpp
template<class RandomAccessIterator>
void push_heap( RandomAccessIterator first, RandomAccessIterator last );

template<class RandomAccessIterator, class BinaryPredicate>
void push_heap( RandomAccessIterator first, RandomAccessIterator last, BinaryPredicate comp);

```

### <a name="parameters"></a>Parameter

*erste* ein zufälliger eingabeiterator, der die Position des ersten Elements im Heap adressiert.

*letzte* ein zufälliger eingabeiterator, der die Position adressiert, hinter dem letzten Element im Bereich, in einen Heap konvertiert werden soll.

*Comp* ermitteln benutzerdefiniertes prädikatfunktionsobjekt, das definiert, in dem ein Element kleiner als ein anderes ist. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="remarks"></a>Hinweise

Zunächst muss das Element ans Ende eines vorhandenen Heaps bewegt werden; danach kann der Algorithmus verwendet werden, um das Element dem vorhanden Heap hinzuzufügen.

Heaps haben zwei Eigenschaften:

- Das erste Element ist immer das größte.

- Elemente können in logarithmischer Zeit hinzugefügt oder entfernt werden.

Heaps sind ideal zum Implementieren von Vorrangwarteschlangen. Sie werden beim Implementieren des C++-Standardbibliothekadapters [priority_queue-Klasse](../standard-library/priority-queue-class.md) verwendet.

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Der Bereich, ohne das neu am Ende hinzugefügte Element, muss ein Heap sein.

Die Komplexität ist logarithmisch ist, dass höchstens Log ( *Nachname - Vorname*) vergleichen.

### <a name="example"></a>Beispiel

```cpp
// alg_push_heap.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

int main( ) {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 1 ; i <= 9 ; i++ )
      v1.push_back( i );

   random_shuffle( v1.begin( ), v1.end( ) );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Make v1 a heap with default less than ordering
   make_heap ( v1.begin( ), v1.end( ) );
   cout << "The heaped version of vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Add an element to the heap
   v1.push_back( 10 );
   cout << "The heap v1 with 10 pushed back is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   push_heap( v1.begin( ), v1.end( ) );
   cout << "The reheaped v1 with 10 added is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl << endl;

   // Make v1 a heap with greater than ordering
   make_heap ( v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "The greater-than heaped version of v1 is\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   v1.push_back(0);
   cout << "The greater-than heap v1 with 11 pushed back is\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   push_heap( v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "The greater than reheaped v1 with 11 added is\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="random_shuffle"></a> random_shuffle

Die Funktion Std::random_shuffle() ist veraltet, ersetzt durch [Std:: Shuffle](../standard-library/algorithm-functions.md#shuffle). Ein Codebeispiel und Weitere Informationen finden Sie unter [ \<random >](../standard-library/random.md) und im Stackoverflow-Posting [Warum werden Std:: random_shuffle Methods eingestellt in C ++ 14?](http://go.microsoft.com/fwlink/p/?linkid=397954).

## <a name="remove"></a>  remove

Eliminiert einen angegebenen Wert von einem angegebenen Bereich, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Bereichs zurückzugeben, der den angegebenen Wert nicht enthält.

```cpp
template<class ForwardIterator, class Type>
 ForwardIterator remove(ForwardIterator first, ForwardIterator last, const Type& val);

```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der die Position des ersten Elements im Bereich von aus dem Elemente entfernt werden.

*letzte* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich von aus dem Elemente entfernt werden.

*Val* der Wert, der aus dem Bereich entfernt werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Vorwärtsiterator für die neue Endposition des veränderten Bereichs, eine Position hinter dem letzten Element der verbleibenden Sequenz, die den angegebenen Wert nicht enthält.

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Reihenfolge der nicht entfernten Elemente bleibt bestehen.

Der zur Bestimmung des Gleichheitszustands zwischen Elementen verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Die Komplexität ist linear; Es gibt (`last` - `first`) Vergleiche auf Gleichheit.

Die [list-Klasse](../standard-library/list-class.md) hat eine effizientere Memberfunktion von `remove`, die auch Zeiger neu verlinkt.

### <a name="example"></a>Beispiel

```cpp
// alg_remove.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main( ) {
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1, Iter2, new_end;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle ( v1.begin( ), v1.end( ) );
   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Remove elements with a value of 7
   new_end = remove ( v1.begin( ), v1.end( ), 7 );

   cout << "Vector v1 with value 7 removed is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To change the sequence size, use erase
   v1.erase (new_end, v1.end( ) );

   cout << "Vector v1 resized with value 7 removed is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="remove_copy"></a> remove_copy

Kopiert Elemente aus einem Quellbereich in einen Zielbereich, ohne dass Elemente eines angegebenen Werts kopiert werden und ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Zielbereichs zurückzugeben.

```cpp
template<class InputIterator, class OutputIterator, class Type>
 OutputIterator remove_copy(InputIterator first, InputIterator last, OutputIterator result, const Type& val);

```

### <a name="parameters"></a>Parameter

*erste* ein Eingabe-Iterator, der die Position des ersten Elements im Bereich von aus dem Elemente entfernt werden.

*letzte* ein eingabeiterator, der die Position hinter dem letzten Element im Bereich von aus dem Elemente entfernt werden.

*Ergebnis* ein Ausgabeiterator, der die Position des ersten Elements im Zielbereich, aus dem Elemente entfernt werden.

*Val* der Wert, der aus dem Bereich entfernt werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator, der die neue Endposition des Zielbereichs adressiert, sprich eine Position hinter dem letzten Element der Kopie der verbleibenden Sequenz, die den angegebenen Wert nicht enthält.

### <a name="remarks"></a>Hinweise

Die Quell- und Zielbereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Der Zielbereich muss über ausreichend Platz verfügen, um die verbleibenden Elemente zu enthalten, die nach dem Entfernen von Elementen des angegebenen Werts kopiert werden.

Die Reihenfolge der nicht entfernten Elemente bleibt bestehen.

Der zur Bestimmung des Gleichheitszustands zwischen Elementen verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Die Komplexität ist linear; Es gibt (`last` - `first`) Vergleiche auf Gleichheit und höchstens (`last` - `first`) Zuweisungen.

### <a name="example"></a>Beispiel

```cpp
// alg_remove_copy.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1, v2(10);
   vector <int>::iterator Iter1, Iter2, new_end;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle (v1.begin( ), v1.end( ) );
   cout << "The original vector v1 is:     ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Remove elements with a value of 7
   new_end = remove_copy ( v1.begin( ), v1.end( ), v2.begin( ), 7 );

   cout << "Vector v1 is left unchanged as ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "Vector v2 is a copy of v1 with the value 7 removed:\n ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;
}
```

## <a name="remove_copy_if"></a> remove_copy_if

Kopiert Elemente aus einem Quellbereich in einen Zielbereich, ohne dass Elemente, die ein Prädikat erfüllen, kopiert werden und ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Zielbereichs zurückzugeben.

```cpp
template<class InputIterator, class OutputIterator, class Predicate>
OutputIterator remove_copy_if(InputIterator first, InputIterator Last, OutputIterator result, Predicate pred);

```

### <a name="parameters"></a>Parameter

*erste* ein Eingabe-Iterator, der die Position des ersten Elements im Bereich von aus dem Elemente entfernt werden.

*letzte* ein eingabeiterator, der die Position hinter dem letzten Element im Bereich von aus dem Elemente entfernt werden.

*Ergebnis* ein Ausgabeiterator, der die Position des ersten Elements im Zielbereich, aus dem Elemente entfernt werden.

*_Pred* das unäre Prädikat, das erfüllt sein muss, ist der Wert eines Elements ersetzt werden.

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator, der die neue Endposition des Zielbereichs adressiert, sprich eine Position hinter dem letzten Element der verbleibenden Sequenz, die die Elemente nicht enthält, die das Prädikat erfüllen.

### <a name="remarks"></a>Hinweise

Der Quellbereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Der Zielbereich muss über ausreichend Platz verfügen, um die verbleibenden Elemente zu enthalten, die nach dem Entfernen von Elementen des angegebenen Werts kopiert werden.

Die Reihenfolge der nicht entfernten Elemente bleibt bestehen.

Der zur Bestimmung des Gleichheitszustands zwischen Elementen verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Die Komplexität ist linear: Es gibt (`last` - `first`) Vergleiche auf Gleichheit und höchstens (`last` - `first`) Zuweisungen.

Informationen über das Verhalten dieser Funktionen finden Sie unter [Überprüfte Iteratoren ](../standard-library/checked-iterators.md).

### <a name="example"></a>Beispiel

```cpp
// alg_remove_copy_if.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater6 ( int value ) {
   return value >6;
}

int main() {
   using namespace std;
   vector <int> v1, v2(10);
   vector <int>::iterator Iter1, Iter2, new_end;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle ( v1.begin( ), v1.end( ) );
   cout << "The original vector v1 is:      ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Remove elements with a value greater than 6
   new_end = remove_copy_if ( v1.begin( ), v1.end( ),
      v2.begin( ), greater6 );

   cout << "After the appliation of remove_copy_if to v1,\n "
        << "vector v1 is left unchanged as ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "Vector v2 is a copy of v1 with values greater "
        << "than 6 removed:\n ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != new_end ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;
}
```

## <a name="remove_if"></a> remove_if

Eliminiert Elemente, die ein Prädikat aus einem angegebenen Bereich erfüllen, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Bereichs zurückzugeben, der den angegebenen Wert nicht enthält.

```cpp
template<class ForwardIterator, class Predicate>
 ForwardIterator remove_if(ForwardIterator first, ForwardIterator last, Predicate pred);

```

### <a name="parameters"></a>Parameter

*erste* ein vorwärtsiterator, der auf die Position des ersten Elements im Bereich von aus dem Elemente entfernt werden.

*letzte* ein forward-Iterator auf die Position hinter dem letzten Element im Bereich von aus dem Elemente entfernt werden.

*_Pred* das unäre Prädikat, das erfüllt sein muss, ist der Wert eines Elements ersetzt werden.

### <a name="return-value"></a>Rückgabewert

Ein Vorwärtsiterator für die neue Endposition des veränderten Bereichs, eine Position hinter dem letzten Element der verbleibenden Sequenz, die den angegebenen Wert nicht enthält.

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Reihenfolge der nicht entfernten Elemente bleibt bestehen.

Der zur Bestimmung des Gleichheitszustands zwischen Elementen verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Die Komplexität ist linear: Es gibt (`last` - `first`) Vergleiche auf Gleichheit.

List hat eine effizientere Memberfunktion von remove, durch die Zeiger neu verlinkt werden.

### <a name="example"></a>Beispiel

```cpp
// alg_remove_if.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater6 ( int value ) {
   return value >6;
}

int main( ) {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2, new_end;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle ( v1.begin( ), v1.end( ) );
   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Remove elements satisfying predicate greater6
   new_end = remove_if (v1.begin( ), v1.end( ), greater6 );

   cout << "Vector v1 with elements satisfying greater6 removed is\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To change the sequence size, use erase
   v1.erase (new_end, v1.end( ) );

   cout << "Vector v1 resized elements satisfying greater6 removed is\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="replace"></a> replace

Überprüft jedes Element in einem Bereich und ersetzt es, sofern es einem angegebenen Wert entspricht.

```cpp
template<class ForwardIterator, class Type>
void replace(ForwardIterator first, ForwardIterator last, const Type& _OldVal, const Type& _NewVal);
```

### <a name="parameters"></a>Parameter

*erste* ein vorwärtsiterator, der auf die Position des ersten Elements im Bereich von aus dem Elemente ersetzt werden.

*letzte* ein forward-Iterator auf die Position hinter dem letzten Element im Bereich von aus dem Elemente ersetzt werden.

*_OldVal* der alte Wert der ersetzten Elemente.

*_NewVal* der neue Wert, der die Elemente mit dem alten Wert zugewiesen wird.

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Reihenfolge der nicht ersetzten Elemente bleibt bestehen.

Der zur Bestimmung des Gleichheitszustands zwischen Elementen verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Die Komplexität ist linear; Es gibt (`last` - `first`) Vergleiche auf Gleichheit und höchstens (`last` - `first`) Zuweisungen von neuen Werten.

### <a name="example"></a>Beispiel

```cpp
// alg_replace.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main( ) {
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle (v1.begin( ), v1.end( ) );
   cout << "The original vector v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Replace elements with a value of 7 with a value of 700
   replace (v1.begin( ), v1.end( ), 7 , 700);

   cout << "The vector v1 with a value 700 replacing that of 7 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="replace_copy"> </a> replace_copy

Überprüft jedes Element in einem Quellbereich und ersetzt es, sofern es einem angegebenen Wert entspricht, während das Ergebnis in einen neuen Zielbereich kopiert wird.

```cpp
template<class InputIterator, class OutputIterator, class Type>
OutputIterator replace_copy(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    const Type& _OldVal,
    const Type& _NewVal);
```

### <a name="parameters"></a>Parameter

*erste* ein eingabeiterator, der auf die Position des ersten Elements im Bereich von aus dem Elemente ersetzt werden.

*letzte* ein eingabeiterator, der auf die Position hinter dem letzten Element im Bereich von aus dem Elemente ersetzt werden.

*Ergebnis* ein Ausgabeiterator verweist auf das erste Element im Zielbereich, in dem die geänderte Sequenz von Elementen kopiert wird.

*_OldVal* der alte Wert der ersetzten Elemente.

*_NewVal* der neue Wert, der die Elemente mit dem alten Wert zugewiesen wird.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der auf die Position hinter dem letzten Element im Zielbereich verweist, in den die geänderte Sequenz von Elementen kopiert wird.

### <a name="remarks"></a>Hinweise

Die Quell- und Zielbereiche, auf die verwiesen wird, dürfen sich nicht überlappen und müssen gültig sein: Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Reihenfolge der nicht ersetzten Elemente bleibt bestehen.

Der zur Bestimmung des Gleichheitszustands zwischen Elementen verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Die Komplexität ist linear: Es gibt (`last` - `first`) Vergleiche auf Gleichheit und höchstens (`last` - `first`) Zuweisungen von neuen Werten.

### <a name="example"></a>Beispiel

```cpp
// alg_replace_copy.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

int main( ) {
   using namespace std;
   vector <int> v1;
   list <int> L1 (15);
   vector <int>::iterator Iter1;
   list <int>::iterator L_Iter1;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle ( v1.begin( ), v1.end( ) );

   int iii;
   for ( iii = 0 ; iii <= 15 ; iii++ )
      v1.push_back( 1 );

   cout << "The original vector v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Replace elements in one part of a vector with a value of 7
   // with a value of 70 and copy into another part of the vector
   replace_copy ( v1.begin( ), v1.begin( ) + 14,v1.end( ) -15, 7 , 70);

   cout << "The vector v1 with a value 70 replacing that of 7 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Replace elements in a vector with a value of 70
   // with a value of 1 and copy into a list
   replace_copy ( v1.begin( ), v1.begin( ) + 14,L1.begin( ), 7 , 1);

   cout << "The list copy L1 of v1 with the value 0 replacing "
        << "that of 7 is:\n ( " ;
   for ( L_Iter1 = L1.begin( ) ; L_Iter1 != L1.end( ) ; L_Iter1++ )
      cout << *L_Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="replace_copy_if"></a> replace_copy_if

Überprüft jedes Element in einem Quellbereich und ersetzt es, sofern es ein angegebenes Prädikat erfüllt, während das Ergebnis in einen neuen Zielbereich kopiert wird.

```cpp
template<class InputIterator, class OutputIterator, class Predicate, class Type>
OutputIterator replace_copy_if(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    Predicate pred,
    const Type& val);

```

### <a name="parameters"></a>Parameter

*erste* ein eingabeiterator, der auf die Position des ersten Elements im Bereich von aus dem Elemente ersetzt werden.

*letzte* ein eingabeiterator, der auf die Position hinter dem letzten Element im Bereich von aus dem Elemente ersetzt werden.

*Ergebnis* ein Ausgabeiterator, der auf die Position des ersten Elements im Zielbereich, in das Elemente kopiert werden.

*_Pred* das unäre Prädikat, das erfüllt sein muss, ist der Wert eines Elements ersetzt werden.

*Val* der neue Wert wird zugewiesen, auf die Elemente, deren Alter Wert das Prädikat erfüllt.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der auf die Position hinter dem letzten Element im Zielbereich verweist, in den die geänderte Sequenz von Elementen kopiert wird.

### <a name="remarks"></a>Hinweise

Die Quell- und Zielbereiche, auf die verwiesen wird, dürfen sich nicht überlappen und müssen gültig sein: Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Reihenfolge der nicht ersetzten Elemente bleibt bestehen.

Der zur Bestimmung des Gleichheitszustands zwischen Elementen verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Die Komplexität ist linear; Es gibt (`last` - `first`) Vergleiche auf Gleichheit und höchstens (`last` - `first`) Zuweisungen von neuen Werten.

### <a name="example"></a>Beispiel

```cpp
// alg_replace_copy_if.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

bool greater6 ( int value ) {
   return value >6;
}

int main( ) {
   using namespace std;
   vector <int> v1;
   list <int> L1 (13);
   vector <int>::iterator Iter1;
   list <int>::iterator L_Iter1;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle ( v1.begin( ), v1.end( ) );

   int iii;
   for ( iii = 0 ; iii <= 13 ; iii++ )
      v1.push_back( 1 );

   cout << "The original vector v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Replace elements with a value of 7 in the 1st half of a vector
   // with a value of 70 and copy it into the 2nd half of the vector
   replace_copy_if ( v1.begin( ), v1.begin( ) + 14,v1.end( ) -14,
      greater6 , 70);

   cout << "The vector v1 with values of 70 replacing those greater"
        << "\n than 6 in the 1st half & copied into the 2nd half is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Replace elements in a vector with a value of 70
   // with a value of 1 and copy into a list
   replace_copy_if ( v1.begin( ), v1.begin( ) + 13,L1.begin( ),
      greater6 , -1 );

   cout << "A list copy of vector v1 with the value -1\n replacing "
        << "those greater than 6 is:\n ( " ;
   for ( L_Iter1 = L1.begin( ) ; L_Iter1 != L1.end( ) ; L_Iter1++ )
      cout << *L_Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="replace_if"></a> replace_if

Überprüft jedes Element in einem Bereich und ersetzt es, sofern es das angegebene Prädikat erfüllt.

```cpp
template<class ForwardIterator, class Predicate, class Type>
void replace_if(ForwardIterator first, ForwardIterator last, Predicate pred, const Type& val);

```

### <a name="parameters"></a>Parameter

*erste* ein vorwärtsiterator, der auf die Position des ersten Elements im Bereich von aus dem Elemente ersetzt werden.

*letzte* ein Iterator, der auf die Position hinter dem letzten Element im Bereich von aus dem Elemente ersetzt werden.

*_Pred* das unäre Prädikat, das erfüllt sein muss, ist der Wert eines Elements ersetzt werden.

*Val* der neue Wert wird zugewiesen, auf die Elemente, deren Alter Wert das Prädikat erfüllt.

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Reihenfolge der nicht ersetzten Elemente bleibt bestehen.

Der Algorithmus `replace_if` ist eine Generalisierung des Algorithmus `replace`, sodass beliebige Prädikate angegeben werden, anstatt auf Gleichheit mit einem angegebenen konstanten Wert.

Der zur Bestimmung des Gleichheitszustands zwischen Elementen verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Die Komplexität ist linear: Es gibt (`last` - `first`) Vergleiche auf Gleichheit und höchstens (`last` - `first`) Zuweisungen von neuen Werten.

### <a name="example"></a>Beispiel

```cpp
// alg_replace_if.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater6 ( int value ) {
   return value >6;
}

int main( ) {
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle ( v1.begin( ), v1.end( ) );
   cout << "The original vector v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Replace elements satisfying the predicate greater6
   // with a value of 70
   replace_if ( v1.begin( ), v1.end( ), greater6 , 70);

   cout << "The vector v1 with a value 70 replacing those\n "
        << "elements satisfying the greater6 predicate is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="reverse"></a> reverse

Kehrt die Reihenfolge der Elemente innerhalb eines Bereichs um.

```cpp
template<class BidirectionalIterator>
 void reverse(BidirectionalIterator first, BidirectionalIterator last);

```

### <a name="parameters"></a>Parameter

*erste* ein bidirektionaler Iterator, auf die Position des ersten Elements im Bereich verweist in dem die Elemente sind wird permutiert verweist.

*letzte* ein bidirektionaler Iterator, auf die Position hinter dem letzten Element im Bereich verweist in dem die Elemente sind wird permutiert verweist.

### <a name="remarks"></a>Hinweise

Der Quellbereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

### <a name="example"></a>Beispiel

```cpp
// alg_reverse.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main( ) {
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
   {
      v1.push_back( i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Reverse the elements in the vector
   reverse (v1.begin( ), v1.end( ) );

   cout << "The modified vector v1 with values reversed is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
 ( 0 1 2 3 4 5 6 7 8 9 ).
The modified vector v1 with values reversed is:
 ( 9 8 7 6 5 4 3 2 1 0 ).
```

## <a name="reverse_copy"> </a> reverse_copy

Kehrt die Reihenfolge der Elemente in einem Quellbereich beim Kopieren in einen Zielbereich um.

```cpp
template<class BidirectionalIterator, class OutputIterator>
OutputIterator reverse_copy(
    BidirectionalIterator  first,
    BidirectionalIterator Last,
    OutputIterator  result);

```

### <a name="parameters"></a>Parameter

*erste* ein bidirektionaler Iterator, der an die Position des ersten Elements im Quellbereich verweist in dem die Elemente sind wird permutiert.

*letzte* ein bidirektionaler Iterator, auf die Position hinter dem letzten Element im Quellbereich verweist in dem die Elemente sind wird permutiert verweist.

*Ergebnis* ein Ausgabeiterator, der auf die Position des ersten Elements im Zielbereich, in das Elemente kopiert werden.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der auf die Position hinter dem letzten Element im Zielbereich verweist, in den die geänderte Sequenz von Elementen kopiert wird.

### <a name="remarks"></a>Hinweise

Die Quell- und Zielbereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

### <a name="example"></a>Beispiel

```cpp
// alg_reverse_copy.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main( ) {
   using namespace std;
   vector <int> v1, v2( 10 );
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
   {
      v1.push_back( i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Reverse the elements in the vector
   reverse_copy (v1.begin( ), v1.end( ), v2.begin( ) );

   cout << "The copy v2 of the reversed vector v1 is:\n ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   cout << "The original vector v1 remains unmodified as:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="rotate"></a> rotate

Vertauscht die Elemente in zwei benachbarten Bereichen.

```cpp
template<class ForwardIterator>
 void rotate(ForwardIterator first, ForwardIterator middle, ForwardIterator last);

```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der die Position des ersten Elements im Bereich von rotiert werden soll.

*Mittlere* ein forward-Iterator definieren die Grenzen innerhalb des Bereichs, der die Position des ersten Elements im zweiten Teil des Bereichs adressiert, dessen Elemente sind mit denen im ersten Teil des Bereichs ausgetauscht werden.

*Letzte* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich von rotiert werden soll.

### <a name="remarks"></a>Hinweise

Die Bereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Komplexität ist linear, wobei höchstens (`last` - `first`) vertauscht.

### <a name="example"></a>Beispiel

```cpp
// alg_rotate.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>

int main( ) {
   using namespace std;
   vector <int> v1;
   deque <int> d1;
   vector <int>::iterator v1Iter1;
   deque<int>::iterator d1Iter1;

   int i;
   for ( i = -3 ; i <= 5 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii =0 ; ii <= 5 ; ii++ )
   {
      d1.push_back( ii );
   }

   cout << "Vector v1 is ( " ;
   for ( v1Iter1 = v1.begin( ) ; v1Iter1 != v1.end( ) ;v1Iter1 ++ )
      cout << *v1Iter1  << " ";
   cout << ")." << endl;

   rotate ( v1.begin ( ) , v1.begin ( ) + 3 , v1.end ( ) );
   cout << "After rotating, vector v1 is ( " ;
   for ( v1Iter1 = v1.begin( ) ; v1Iter1 != v1.end( ) ;v1Iter1 ++ )
      cout << *v1Iter1  << " ";
   cout << ")." << endl;

   cout << "The original deque d1 is ( " ;
   for ( d1Iter1 = d1.begin( ) ; d1Iter1 != d1.end( ) ;d1Iter1 ++ )
      cout << *d1Iter1  << " ";
   cout << ")." << endl;

   int iii = 1;
   while ( iii <= d1.end ( ) - d1.begin ( ) ) {
      rotate ( d1.begin ( ) , d1.begin ( ) + 1 , d1.end ( ) );
      cout << "After the rotation of a single deque element to the back,\n d1 is   ( " ;
      for ( d1Iter1 = d1.begin( ) ; d1Iter1 != d1.end( ) ;d1Iter1 ++ )
         cout << *d1Iter1  << " ";
      cout << ")." << endl;
      iii++;
   }
}
```

```Output
Vector v1 is ( -3 -2 -1 0 1 2 3 4 5 ).
After rotating, vector v1 is ( 0 1 2 3 4 5 -3 -2 -1 ).
The original deque d1 is ( 0 1 2 3 4 5 ).
After the rotation of a single deque element to the back,
 d1 is   ( 1 2 3 4 5 0 ).
After the rotation of a single deque element to the back,
 d1 is   ( 2 3 4 5 0 1 ).
After the rotation of a single deque element to the back,
 d1 is   ( 3 4 5 0 1 2 ).
After the rotation of a single deque element to the back,
 d1 is   ( 4 5 0 1 2 3 ).
After the rotation of a single deque element to the back,
 d1 is   ( 5 0 1 2 3 4 ).
After the rotation of a single deque element to the back,
 d1 is   ( 0 1 2 3 4 5 ).
```

## <a name="rotate_copy"></a> rotate_copy

Vertauscht die Elemente in zwei benachbarten Bereiche innerhalb eines Quellbereichs und kopiert das Ergebnis in einen Zielbereich.

```cpp
template<class ForwardIterator, class OutputIterator>
OutputIterator rotate_copy(
    ForwardIterator first,
    ForwardIterator middle,
    ForwardIterator last,
    OutputIterator result );

```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der die Position des ersten Elements im Bereich von rotiert werden soll.

*Mittlere* ein forward-Iterator definieren die Grenzen innerhalb des Bereichs, der die Position des ersten Elements im zweiten Teil des Bereichs adressiert, dessen Elemente sind mit denen im ersten Teil des Bereichs ausgetauscht werden.

_ *Letzten* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich von rotiert werden soll.

*Ergebnis* ein Ausgabeiterator, der die Position des ersten Elements im Zielbereich adressiert.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der die Position hinter dem letzten Element im Zielbereich adressiert.

### <a name="remarks"></a>Hinweise

Die Bereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Komplexität ist linear, wobei höchstens (`last` - `first`) vertauscht.

### <a name="example"></a>Beispiel

```cpp
// alg_rotate_copy.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1 , v2 ( 9 );
   deque <int> d1 , d2 ( 6 );
   vector <int>::iterator v1Iter , v2Iter;
   deque<int>::iterator d1Iter , d2Iter;

   int i;
   for ( i = -3 ; i <= 5 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii =0 ; ii <= 5 ; ii++ )
      d1.push_back( ii );

   cout << "Vector v1 is ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ;v1Iter ++ )
      cout << *v1Iter  << " ";
   cout << ")." << endl;

   rotate_copy ( v1.begin ( ) , v1.begin ( ) + 3 , v1.end ( ) , v2.begin ( ) );
   cout << "After rotating, the vector v1 remains unchanged as:\n v1 = ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ;v1Iter ++ )
      cout << *v1Iter  << " ";
   cout << ")." << endl;

   cout << "After rotating, the copy of vector v1 in v2 is:\n v2 = ( " ;
   for ( v2Iter = v2.begin( ) ; v2Iter != v2.end( ) ;v2Iter ++ )
      cout << *v2Iter  << " ";
   cout << ")." << endl;

   cout << "The original deque d1 is ( " ;
   for ( d1Iter = d1.begin( ) ; d1Iter != d1.end( ) ;d1Iter ++ )
      cout << *d1Iter  << " ";
   cout << ")." << endl;

   int iii = 1;
   while ( iii <= d1.end ( ) - d1.begin ( ) )
   {
      rotate_copy ( d1.begin ( ) , d1.begin ( ) + iii , d1.end ( ) , d2.begin ( ) );
      cout << "After the rotation of a single deque element to the back,\n d2 is   ( " ;
      for ( d2Iter = d2.begin( ) ; d2Iter != d2.end( ) ;d2Iter ++ )
         cout << *d2Iter  << " ";
      cout << ")." << endl;
      iii++;
   }
}
```

## <a name="search"></a> search

Sucht das erste Vorkommen einer Sequenz in einem Zielbereich, dessen Elemente gleich den Elementen in einer bestimmten Elementsequenz sind oder dessen Elemente äquivalent sind mit den Elementen in der angegebenen Sequenz, wie durch ein binäres Prädikat festgelegt.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
   ForwardIterator1 search(
      ForwardIterator1 first1,
      ForwardIterator1 last1,
      ForwardIterator2 first2,
      ForwardIterator2 last2);

template<class ForwardIterator1, class ForwardIterator2, class Predicate>
   ForwardIterator1 search(
      ForwardIterator1 first1,
      ForwardIterator1 last1,
      ForwardIterator2 first2,
      ForwardIterator2 last2
      Predicate comp);

```

### <a name="parameters"></a>Parameter

*first1* ein forward-Iterator, der die Position des ersten Elements im Bereich, gesucht werden soll.

*Last1* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich, gesucht werden soll.

*first2* ein forward-Iterator, der die Position des ersten Elements im Bereich von abgeglichen wird.

*Last2* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich von abgeglichen wird.

*Comp* User-defined Function, Prädikat-Objekt, das definiert die Bedingung erfüllt wird, wenn zwei Elemente enthalten sind, die ausgeführt werden als gleichwertig. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator, der die Position des ersten Elements der ersten Untersequenz adressiert, die der angegebenen Sequenz entspricht oder die wie von einem binären Prädikat angegeben äquivalent ist.

### <a name="remarks"></a>Hinweise

Der zur Bestimmung des Gleichheitszustands zwischen einem Element und dem angegebenen Wert verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Die Bereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die durchschnittliche Komplexität ist bezüglich der Größe des durchsuchten Bereichs linear; im schlimmsten Fall ist die Komplexität auch bezüglich der Größe der zu suchenden Sequenz linear.

### <a name="example"></a>Beispiel

```cpp
// alg_search.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

// Return whether second element is twice the first
bool twice (int elem1, int elem2 )
{
   return 2 * elem1 == elem2;
}

int main( ) {
   using namespace std;
   vector <int> v1, v2;
   list <int> L1;
   vector <int>::iterator Iter1, Iter2;
   list <int>::iterator L1_Iter, L1_inIter;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   int ii;
   for ( ii = 4 ; ii <= 5 ; ii++ )
   {
      L1.push_back( 5 * ii );
   }

   int iii;
   for ( iii = 2 ; iii <= 4 ; iii++ )
   {
      v2.push_back( 10 * iii );
   }

   cout << "Vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "List L1 = ( " ;
   for ( L1_Iter = L1.begin( ) ; L1_Iter!= L1.end( ) ; L1_Iter++ )
      cout << *L1_Iter << " ";
   cout << ")" << endl;

   cout << "Vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
      cout << ")" << endl;

   // Searching v1 for first match to L1 under identity
   vector <int>::iterator result1;
   result1 = search (v1.begin( ), v1.end( ), L1.begin( ), L1.end( ) );

   if ( result1 == v1.end( ) )
      cout << "There is no match of L1 in v1."
           << endl;
   else
      cout << "There is at least one match of L1 in v1"
           << "\n and the first one begins at "
           << "position "<< result1 - v1.begin( ) << "." << endl;

   // Searching v1 for a match to L1 under the binary predicate twice
   vector <int>::iterator result2;
   result2 = search  (v1.begin( ), v1.end( ), v2.begin( ), v2.end( ), twice );

   if ( result2 == v1.end( ) )
      cout << "There is no match of L1 in v1."
           << endl;
   else
      cout << "There is a sequence of elements in v1 that "
           << "are equivalent\n to those in v2 under the binary "
           << "predicate twice\n and the first one begins at position "
           << result2 - v1.begin( ) << "." << endl;
}
```

```Output
Vector v1 = ( 0 5 10 15 20 25 0 5 10 15 20 25 )
List L1 = ( 20 25 )
Vector v2 = ( 20 30 40 )
There is at least one match of L1 in v1
 and the first one begins at position 4.
There is a sequence of elements in v1 that are equivalent
 to those in v2 under the binary predicate twice
 and the first one begins at position 2.
```

## <a name="search_n"></a> search_n

Sucht nach der ersten Untersequenz in einem Bereich, der aus einer angegebenen Anzahl von Elementen besteht, die einen bestimmten Wert oder eine Beziehung zu diesem durch ein binäres Prädikat angegebenen Wert haben.

```cpp
template<class ForwardIterator1, class Diff2, class Type>
   ForwardIterator1 search_n(
      ForwardIterator1 first1,
      ForwardIterator1 last1,
      Diff2 count,
      const Type& val);

template<class ForwardIterator1, class Diff2, class Type, class BinaryPredicate>
   ForwardIterator1 search_n(
      ForwardIterator1 first1,
      ForwardIterator1 last1,
      Diff2 count,
      const Type& val,
      BinaryPredicate comp);

```

### <a name="parameters"></a>Parameter

*first1* ein forward-Iterator, der die Position des ersten Elements im Bereich, gesucht werden soll.

*Last1* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich, gesucht werden soll.

*Anzahl* die Größe der zu suchenden Untersequenz.

*Val* den Wert der Elemente in der Sequenz gesucht wird.

*Comp* User-defined Function, Prädikat-Objekt, das definiert die Bedingung erfüllt wird, wenn zwei Elemente enthalten sind, die ausgeführt werden als gleichwertig. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator, der die Position des ersten Elements der ersten Untersequenz adressiert, die der angegebenen Sequenz entspricht oder die wie von einem binären Prädikat angegeben äquivalent ist.

### <a name="remarks"></a>Hinweise

Der zur Bestimmung des Gleichheitszustands zwischen einem Element und dem angegebenen Wert verwendete `operator==` muss eine Äquivalenzrelation zwischen zwei Operanden vorgeben.

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Komplexität ist bezüglich der Größe des Gesuchten linear.

### <a name="example"></a>Beispiel

```cpp
// alg_search_n.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

// Return whether second element is 1/2 of the first
bool one_half ( int elem1, int elem2 )
{
   return elem1 == 2 * elem2;
}

int main( )
{
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   for ( i = 0 ; i <= 2 ; i++ )
   {
      v1.push_back( 5  );
   }

   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   for ( i = 0 ; i <= 2 ; i++ )
   {
      v1.push_back( 10  );
   }

   cout << "Vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // Searching v1 for first match to (5 5 5) under identity
   vector <int>::iterator result1;
   result1 = search_n ( v1.begin( ), v1.end( ), 3, 5 );

   if ( result1 == v1.end( ) )
      cout << "There is no match for a sequence ( 5 5 5 ) in v1."
           << endl;
   else
      cout << "There is at least one match of a sequence ( 5 5 5 )"
           << "\n in v1 and the first one begins at "
           << "position "<< result1 - v1.begin( ) << "." << endl;

   // Searching v1 for first match to (5 5 5) under one_half
   vector <int>::iterator result2;
   result2 = search_n (v1.begin( ), v1.end( ), 3, 5, one_half );

   if ( result2 == v1.end( ) )
      cout << "There is no match for a sequence ( 5 5 5 ) in v1"
           << " under the equivalence predicate one_half." << endl;
   else
      cout << "There is a match of a sequence ( 5 5 5 ) "
           << "under the equivalence\n predicate one_half "
           << "in v1 and the first one begins at "
           << "position "<< result2 - v1.begin( ) << "." << endl;
}
```

```Output
Vector v1 = ( 0 5 10 15 20 25 5 5 5 0 5 10 15 20 25 10 10 10 )
There is at least one match of a sequence ( 5 5 5 )
 in v1 and the first one begins at position 6.
There is a match of a sequence ( 5 5 5 ) under the equivalence
 predicate one_half in v1 and the first one begins at position 15.
```

## <a name="set_difference"></a> set_difference

Vereinigt alle Elemente, die zu dem einen, jedoch nicht zu einem anderen sortierten Quellbereich gehören, in einen einzelnen, sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
OutputIterator set_difference(
     InputIterator1  first1,
     InputIterator1  last1,
     InputIterator2  first2,
     InputIterator2  last2,
     OutputIterator  result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class BinaryPredicate>
OutputIterator set_difference(
    InputIterator1  first1,
    InputIterator1  last1,
    InputIterator2  first2,
    InputIterator2  last2,
    OutputIterator  result,
    BinaryPredicate  comp );
```

### <a name="parameters"></a>Parameter

*first1* ein Eingabe-Iterator, der die Position des ersten Elements im ersten der beiden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich repräsentiert den Unterschied der beiden Quellbereiche sortiert werden sollen.

*Last1* ein Eingabe-Iterator, der die Position hinter dem letzten Element im ersten der beiden sortierten Quellbereiche adressiert, die kombiniert und zu einem einzelnen Bereich repräsentiert den Unterschied der beiden Quellbereiche sortiert werden sollen.

*first2* ein eingabeiterator, der die Position des ersten Elements im zweiten der beiden aufeinanderfolgenden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich repräsentiert den Unterschied der beiden Quellbereiche sortiert werden sollen.

*Last2* ein eingabeiterator, der die Position hinter dem letzten Element im zweiten der beiden aufeinanderfolgenden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich repräsentiert den Unterschied der beiden Quellbereiche sortiert werden sollen.

*Ergebnis* ein Ausgabeiterator, der die Position des ersten Elements im Zielbereich, in dem die beiden Bereiche Datenquelle, auf einem einzelnen Bereich sortiert repräsentiert den Unterschied der beiden Quellbereiche kombiniert werden.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das den Sinn definiert, in dem ein Element größer als die andere ist. Das binäre Prädikat akzeptiert zwei Argumente und sollte **true** zurückgeben, wenn das erste Element kleiner als das zweite Element ist, andernfalls wird **false** zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der die Position hinter dem letzten Element im sortierten Zielbereich adressiert, der den Unterschied der beiden Quellbereiche repräsentiert.

### <a name="remarks"></a>Hinweise

Die sortierten Quellbereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb jeder Sequenz muss von der ersten Position aus durch Zunahme erreichbar sein.

Der Zielbereich sollte keinen der Quellbereiche überlappen und groß genug sein, um den ersten Quellbereich zu enthalten.

Die sortierten Quellbereiche müssen als Vorbedingung zur Anwendung des `set_difference` -Algorithmus entsprechend der gleichen Reihenfolge sortiert werden, die vom Algorithmus für die Sortierung der kombinierten Bereiche verwendet wird.

Der Vorgang ist stabil, da die relative Reihenfolge der Elemente innerhalb jedes Bereichs im Zielbereich beibehalten wird. Die Quellbereiche werden durch den merge-Algorithmus nicht geändert.

Die Werttypen der Eingabeiteratoren müssen mit „kleiner als“ vergleichbar sein, um sortiert zu werden, sodass zwei Elemente möglicherweise als gleichwertig (in dem Sinne, dass keines kleiner als das andere ist) oder eines als kleiner als das andere bestimmt werden können. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen. Wenn in beiden Quellbereichen äquivalente Elemente vorhanden sind, stehen im Zielbereich die Elemente aus dem ersten Bereich vor den Elementen aus dem zweiten Bereich. Wenn die Quellbereiche Duplikate eines Elements enthalten, sodass sich im ersten Quellbereich mehr Elemente befinden als im zweiten, enthält der Zielbereich die Zahl, um die die Vorkommen dieser Elemente im ersten Quellbereich die Vorkommen dieser Elemente im zweiten Quellbereich übersteigen.

Die Komplexität dieses Algorithmus ist höchstens mit 2 linear \* (( *last1 – first1*) – ( *last2 – first2*)) – 1 Vergleiche für nicht leere Quellbereiche.

### <a name="example"></a>Beispiel

```cpp
// alg_set_diff.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser (int elem1, int elem2 )
{
   if (elem1 < 0)
      elem1 = - elem1;
   if (elem2 < 0)
      elem2 = - elem2;
   return elem1 < elem2;
}

int main( )
{
   using namespace std;
   vector <int> v1a, v1b, v1 ( 12 );
   vector <int>::iterator Iter1a,  Iter1b, Iter1, Result1;

   // Constructing vectors v1a & v1b with default less-than ordering
   int i;
   for ( i = -1 ; i <= 4 ; i++ )
   {
      v1a.push_back(  i );
   }

   int ii;
   for ( ii =-3 ; ii <= 0 ; ii++ )
   {
      v1b.push_back(  ii  );
   }

   cout << "Original vector v1a with range sorted by the\n "
        <<  "binary predicate less than is  v1a = ( " ;
   for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
      cout << *Iter1a << " ";
   cout << ")." << endl;

   cout << "Original vector v1b with range sorted by the\n "
        <<  "binary predicate less than is  v1b = ( " ;
   for ( Iter1b = v1b.begin ( ) ; Iter1b != v1b.end ( ) ; Iter1b++ )
      cout << *Iter1b << " ";
   cout << ")." << endl;

   // Constructing vectors v2a & v2b with ranges sorted by greater
   vector <int> v2a ( v1a ) , v2b ( v1b ) ,  v2 ( v1 );
   vector <int>::iterator Iter2a, Iter2b, Iter2, Result2;
   sort ( v2a.begin ( ) , v2a.end ( ) , greater<int> ( ) );
   sort ( v2b.begin ( ) , v2b.end ( ) , greater<int> ( ) );

   cout << "Original vector v2a with range sorted by the\n "
        <<  "binary predicate greater is   v2a =  ( " ;
   for ( Iter2a = v2a.begin ( ) ; Iter2a != v2a.end ( ) ; Iter2a++ )
      cout << *Iter2a << " ";
   cout << ")." << endl;

   cout << "Original vector v2b with range sorted by the\n "
        <<  "binary predicate greater is   v2b =  ( " ;
   for ( Iter2b = v2b.begin ( ) ; Iter2b != v2b.end ( ) ; Iter2b++ )
      cout << *Iter2b << " ";
   cout << ")." << endl;

   // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
   vector <int> v3a ( v1a ), v3b ( v1b ) ,  v3 ( v1 );
   vector <int>::iterator Iter3a,  Iter3b, Iter3, Result3;
   sort ( v3a.begin ( ) , v3a.end ( ) , mod_lesser );
   sort ( v3b.begin ( ) , v3b.end ( ) , mod_lesser  );

   cout << "Original vector v3a with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3a =  ( " ;
   for ( Iter3a = v3a.begin ( ) ; Iter3a != v3a.end ( ) ; Iter3a++ )
      cout << *Iter3a << " ";
   cout << ")." << endl;

   cout << "Original vector v3b with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3b =  ( " ;
   for ( Iter3b = v3b.begin ( ) ; Iter3b != v3b.end ( ) ; Iter3b++ )
      cout << *Iter3b << " ";
   cout << ")." << endl;

   // To combine into a difference in asscending
   // order with the default binary predicate less <int> ( )
   Result1 = set_difference ( v1a.begin ( ) , v1a.end ( ) ,
      v1b.begin ( ) , v1b.end ( ) , v1.begin ( ) );
   cout << "Set_difference of source ranges with default order,"
        << "\n vector v1mod =  ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != Result1 ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To combine into a difference in descending
   // order specify binary predicate greater<int>( )
   Result2 = set_difference ( v2a.begin ( ) , v2a.end ( ) ,
      v2b.begin ( ) , v2b.end ( ) ,v2.begin ( ) , greater <int> ( ) );
   cout << "Set_difference of source ranges with binary"
        << "predicate greater specified,\n vector v2mod  = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != Result2 ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   // To combine into a difference applying a user
   // defined binary predicate mod_lesser
   Result3 = set_difference (  v3a.begin ( ) , v3a.end ( ) ,
      v3b.begin ( ) , v3b.end ( ) , v3.begin ( ) , mod_lesser );
   cout << "Set_difference of source ranges with binary "
        << "predicate mod_lesser specified,\n vector v3mod  = ( " ; ;
   for ( Iter3 = v3.begin( ) ; Iter3 != Result3 ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")." << endl;
}
```

## <a name="set_intersection"></a> set_intersection

Vereinigt alle Elemente, die zu beiden sortierten Quellbereichen gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
OutputIterator set_intersection(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class BinaryPredicate>
OutputIterator set_intersection(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result,
    BinaryPredicate comp );
```

### <a name="parameters"></a>Parameter

*first1* ein Eingabe-Iterator, der die Position des ersten Elements im ersten der beiden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich repräsentiert die Schnittmenge der beiden Quellbereiche sortiert werden sollen.

*Last1* ein Eingabe-Iterator, der die Position hinter dem letzten Element im ersten der beiden sortierten Quellbereiche adressiert, die kombiniert und zu einem einzelnen Bereich repräsentiert die Schnittmenge der beiden Quellbereiche sortiert werden sollen.

*first2* ein eingabeiterator, der die Position des ersten Elements im zweiten der beiden aufeinanderfolgenden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich repräsentiert die Schnittmenge der beiden Quellbereiche sortiert werden sollen.

*Last2* ein eingabeiterator, der die Position hinter dem letzten Element im zweiten der beiden aufeinanderfolgenden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich repräsentiert die Schnittmenge der beiden Quellbereiche sortiert werden sollen.

**_** *Ergebnis* ein Ausgabeiterator, der die Position des ersten Elements im Zielbereich, in dem die beiden Bereiche Datenquelle, kombiniert werden sollen in einem einzelnen Bereich sortiert, die die Schnittmenge der beiden Quelle darstellt. Bereiche.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das den Sinn definiert, in dem ein Element größer als die andere ist. Das binäre Prädikat akzeptiert zwei Argumente und sollte **true** zurückgeben, wenn das erste Element kleiner als das zweite Element ist, andernfalls wird **false** zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der die Position hinter dem letzten Element im sortierten Zielbereich adressiert, der die Schnittmenge der beiden Quellbereiche repräsentiert.

### <a name="remarks"></a>Hinweise

Die sortierten Quellbereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb jeder Sequenz muss von der ersten Position aus durch Zunahme erreichbar sein.

Der Zielbereich sollte keinen der Quellbereiche überlappen und groß genug sein, um den Zielbereich zu enthalten.

Die sortierten Quellbereiche müssen als Vorbedingung zur Anwendung des merge-Algorithmus entsprechend der gleichen Reihenfolge sortiert werden, die vom Algorithmus für die Sortierung der kombinierten Bereiche verwendet wird.

Der Vorgang ist stabil, da die relative Reihenfolge der Elemente innerhalb jedes Bereichs im Zielbereich beibehalten wird. Die Quellbereiche werden durch den Algorithmus nicht geändert.

Die Werttypen der Eingabeiteratoren müssen mit „kleiner als“ vergleichbar sein, um sortiert zu werden, sodass zwei Elemente möglicherweise als gleichwertig (in dem Sinne, dass keines kleiner als das andere ist) oder eines als kleiner als das andere bestimmt werden können. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen. Wenn in beiden Quellbereichen äquivalente Elemente vorhanden sind, stehen im Zielbereich die Elemente aus dem ersten Bereich vor den Elementen aus dem zweiten Bereich. Wenn die Quellbereiche Duplikate eines Element enthalten, wird der Zielbereich die maximale Anzahl dieser Elemente enthalten, die in beiden Quellbereichen auftreten.

Die Komplexität dieses Algorithmus ist höchstens mit 2 linear \* (( *last1 – first1*) + ( *last2 – first2*)) – 1 Vergleiche für nicht leere Quellbereiche.

### <a name="example"></a>Beispiel

```cpp
// alg_set_intersection.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>   // For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser (int elem1, int elem2 ) {
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
}

int main() {
   using namespace std;
   vector <int> v1a, v1b, v1 ( 12 );
   vector <int>::iterator Iter1a,  Iter1b, Iter1, Result1;

   // Constructing vectors v1a & v1b with default less than ordering
   int i;
   for ( i = -1 ; i <= 3 ; i++ )
      v1a.push_back( i );

   int ii;
   for ( ii =-3 ; ii <= 1 ; ii++ )
      v1b.push_back( ii );

   cout << "Original vector v1a with range sorted by the\n "
        <<  "binary predicate less than is  v1a = ( " ;
   for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
      cout << *Iter1a << " ";
   cout << ")." << endl;

   cout << "Original vector v1b with range sorted by the\n "
        <<  "binary predicate less than is  v1b = ( " ;
   for ( Iter1b = v1b.begin ( ) ; Iter1b != v1b.end ( ) ; Iter1b++ )
      cout << *Iter1b << " ";
   cout << ")." << endl;

   // Constructing vectors v2a & v2b with ranges sorted by greater
   vector <int> v2a ( v1a ) , v2b ( v1b ) , v2 ( v1 );
   vector <int>::iterator Iter2a, Iter2b, Iter2, Result2;
   sort ( v2a.begin ( ) , v2a.end ( ) , greater<int> ( ) );
   sort ( v2b.begin ( ) , v2b.end ( ) , greater<int> ( ) );

   cout << "Original vector v2a with range sorted by the\n "
        << "binary predicate greater is   v2a =  ( " ;
   for ( Iter2a = v2a.begin ( ) ; Iter2a != v2a.end ( ) ; Iter2a++ )
      cout << *Iter2a << " ";
   cout << ")." << endl;

   cout << "Original vector v2b with range sorted by the\n "
        << "binary predicate greater is   v2b =  ( " ;
   for ( Iter2b = v2b.begin ( ) ; Iter2b != v2b.end ( ) ; Iter2b++ )
      cout << *Iter2b << " ";
   cout << ")." << endl;

   // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
   vector <int> v3a ( v1a ), v3b ( v1b ) , v3 ( v1 );
   vector <int>::iterator Iter3a,  Iter3b, Iter3, Result3;
   sort ( v3a.begin ( ) , v3a.end ( ) , mod_lesser );
   sort ( v3b.begin ( ) , v3b.end ( ) , mod_lesser );

   cout << "Original vector v3a with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3a =  ( " ;
   for ( Iter3a = v3a.begin ( ) ; Iter3a != v3a.end ( ) ; Iter3a++ )
      cout << *Iter3a << " ";
   cout << ")." << endl;

   cout << "Original vector v3b with range sorted by the\n "
           <<  "binary predicate mod_lesser is   v3b =  ( " ;
   for ( Iter3b = v3b.begin ( ) ; Iter3b != v3b.end ( ) ; Iter3b++ )
      cout << *Iter3b << " ";
   cout << ")." << endl;

   // To combine into an intersection in asscending order with the
   // default binary predicate less <int> ( )
   Result1 = set_intersection ( v1a.begin ( ) , v1a.end ( ) ,
      v1b.begin ( ) , v1b.end ( ) , v1.begin ( ) );
   cout << "Intersection of source ranges with default order,"
        << "\n vector v1mod =  ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != Result1 ; ++Iter1 )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To combine into an intersection in descending order, specify
   // binary predicate greater<int>( )
   Result2 = set_intersection ( v2a.begin ( ) , v2a.end ( ) ,
      v2b.begin ( ) , v2b.end ( ) ,v2.begin ( ) , greater <int> ( ) );
   cout << "Intersection of source ranges with binary predicate"
        << " greater specified,\n vector v2mod  = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != Result2 ; ++Iter2 )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   // To combine into an intersection applying a user-defined
   // binary predicate mod_lesser
   Result3 = set_intersection ( v3a.begin ( ) , v3a.end ( ) ,
      v3b.begin ( ) , v3b.end ( ) , v3.begin ( ) , mod_lesser );
   cout << "Intersection of source ranges with binary predicate "
        << "mod_lesser specified,\n vector v3mod  = ( " ; ;
   for ( Iter3 = v3.begin( ) ; Iter3 != Result3 ; ++Iter3 )
      cout << *Iter3 << " ";
   cout << ")." << endl;
}
```

## <a name="set_symmetric_difference"></a> set_symmetric_difference

Vereinigt alle Elemente, die zu einem, jedoch nicht zu beiden sortierten Quellbereichen gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
 OutputIterator set_symmetric_difference(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class BinaryPredicate>
OutputIterator set_symmetric_difference(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result,
    BinaryPredicate comp );

```

### <a name="parameters"></a>Parameter

*first1* ein Eingabe-Iterator, der die Position des ersten Elements im ersten der beiden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich repräsentiert den symmetrischen Unterschied der beiden Quellbereiche sortiert werden sollen.

*Last1* ein Eingabe-Iterator, der die Position hinter dem letzten Element im ersten der beiden sortierten Quellbereiche adressiert, die kombiniert und zu einem einzelnen Bereich repräsentiert den symmetrischen Unterschied der beiden Quellbereiche sortiert werden sollen.

*first2* ein eingabeiterator, der die Position des ersten Elements im zweiten der beiden aufeinanderfolgenden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich repräsentiert den symmetrischen Unterschied der beiden Quellbereiche sortiert werden sollen.

*Last2* ein eingabeiterator, der die Position hinter dem letzten Element im zweiten der beiden aufeinanderfolgenden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich repräsentiert den symmetrischen Unterschied der beiden Quellbereiche sortiert werden sollen.

**_** *Ergebnis* ein Ausgabeiterator, der die Position des ersten Elements im Zielbereich, in dem die beiden Bereiche Datenquelle, kombiniert werden sollen in einem einzelnen Bereich sortiert, die den symmetrischen Unterschied der beiden darstellt. Die Quellbereiche.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das den Sinn definiert, in dem ein Element größer als die andere ist. Das binäre Prädikat akzeptiert zwei Argumente und sollte **true** zurückgeben, wenn das erste Element kleiner als das zweite Element ist, andernfalls wird **false** zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der die Position hinter dem letzten Element im sortierten Zielbereich adressiert, der den symmetrischen Unterschied der beiden Quellbereiche repräsentiert.

### <a name="remarks"></a>Hinweise

Die sortierten Quellbereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb jeder Sequenz muss von der ersten Position aus durch Zunahme erreichbar sein.

Der Zielbereich sollte keinen der Quellbereiche überlappen und groß genug sein, um den Zielbereich zu enthalten.

Die sortierten Quellbereiche müssen als Vorbedingung zur Anwendung des `merge*` -Algorithmus entsprechend der gleichen Reihenfolge sortiert werden, die vom Algorithmus für die Sortierung der kombinierten Bereiche verwendet wird.

Der Vorgang ist stabil, da die relative Reihenfolge der Elemente innerhalb jedes Bereichs im Zielbereich beibehalten wird. Die Quellbereiche werden durch den merge-Algorithmus nicht geändert.

Die Werttypen der Eingabeiteratoren müssen mit „kleiner als“ vergleichbar sein, um sortiert zu werden, sodass zwei Elemente möglicherweise als gleichwertig (in dem Sinne, dass keines kleiner als das andere ist) oder eines als kleiner als das andere bestimmt werden können. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen. Wenn in beiden Quellbereichen äquivalente Elemente vorhanden sind, stehen im Zielbereich die Elemente aus dem ersten Bereich vor den Elementen aus dem zweiten Bereich. Wenn die Quellbereiche Duplikate eines Elements enthalten, enthält der Zielbereich den absoluten Wert der Zahl, um die die Vorkommen jener Elemente in einem der Quellbereich die Vorkommen dieser Elemente im zweiten Quellbereich übersteigen.

Die Komplexität dieses Algorithmus ist höchstens mit 2 linear \* ((*last1 – first1*) – (*last2 – first2*)) – 1 Vergleiche für nicht leere Quellbereiche.

### <a name="example"></a>Beispiel

```cpp
// alg_set_sym_diff.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser (int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
}

int main( )
{
   using namespace std;
   vector <int> v1a, v1b, v1 ( 12 );
   vector <int>::iterator Iter1a,  Iter1b, Iter1, Result1;

   // Constructing vectors v1a & v1b with default less-than ordering
   int i;
   for ( i = -1 ; i <= 4 ; i++ )
   {
      v1a.push_back(  i );
   }

   int ii;
   for ( ii =-3 ; ii <= 0 ; ii++ )
   {
      v1b.push_back(  ii  );
   }

   cout << "Original vector v1a with range sorted by the\n "
        <<  "binary predicate less than is  v1a = ( " ;
   for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
      cout << *Iter1a << " ";
   cout << ")." << endl;

   cout << "Original vector v1b with range sorted by the\n "
        <<  "binary predicate less than is  v1b = ( " ;
   for ( Iter1b = v1b.begin ( ) ; Iter1b != v1b.end ( ) ; Iter1b++ )
      cout << *Iter1b << " ";
   cout << ")." << endl;

   // Constructing vectors v2a & v2b with ranges sorted by greater
   vector <int> v2a ( v1a ) , v2b ( v1b ) ,  v2 ( v1 );
   vector <int>::iterator Iter2a, Iter2b, Iter2, Result2;
   sort ( v2a.begin ( ) , v2a.end ( ) , greater<int> ( ) );
   sort ( v2b.begin ( ) , v2b.end ( ) , greater<int> ( ) );

   cout << "Original vector v2a with range sorted by the\n "
        <<  "binary predicate greater is   v2a =  ( " ;
   for ( Iter2a = v2a.begin ( ) ; Iter2a != v2a.end ( ) ; Iter2a++ )
      cout << *Iter2a << " ";
   cout << ")." << endl;

   cout << "Original vector v2b with range sorted by the\n "
        <<  "binary predicate greater is   v2b =  ( " ;
   for ( Iter2b = v2b.begin ( ) ; Iter2b != v2b.end ( ) ; Iter2b++ )
      cout << *Iter2b << " ";
   cout << ")." << endl;

   // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
   vector <int> v3a ( v1a ), v3b ( v1b ) ,  v3 ( v1 );
   vector <int>::iterator Iter3a, Iter3b, Iter3, Result3;
   sort ( v3a.begin ( ) , v3a.end ( ) , mod_lesser );
   sort ( v3b.begin ( ) , v3b.end ( ) , mod_lesser  );

   cout << "Original vector v3a with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3a =  ( " ;
   for ( Iter3a = v3a.begin ( ) ; Iter3a != v3a.end ( ) ; Iter3a++ )
      cout << *Iter3a << " ";
   cout << ")." << endl;

   cout << "Original vector v3b with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3b =  ( " ;
   for ( Iter3b = v3b.begin ( ) ; Iter3b != v3b.end ( ) ; Iter3b++ )
      cout << *Iter3b << " ";
   cout << ")." << endl;

   // To combine into a symmetric difference in ascending
   // order with the default binary predicate less <int> ( )
   Result1 = set_symmetric_difference ( v1a.begin ( ) , v1a.end ( ) ,
      v1b.begin ( ) , v1b.end ( ) , v1.begin ( ) );
   cout << "Set_symmetric_difference of source ranges with default order,"
        << "\n vector v1mod =  ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != Result1 ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To combine into a symmetric difference in descending
   // order, specify binary predicate greater<int>( )
   Result2 = set_symmetric_difference ( v2a.begin ( ) , v2a.end ( ) ,
      v2b.begin ( ) , v2b.end ( ) ,v2.begin ( ) , greater <int> ( ) );
   cout << "Set_symmetric_difference of source ranges with binary"
        << "predicate greater specified,\n vector v2mod  = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != Result2 ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   // To combine into a symmetric difference applying a user
   // defined binary predicate mod_lesser
   Result3 = set_symmetric_difference ( v3a.begin ( ) , v3a.end ( ) ,
      v3b.begin ( ) , v3b.end ( ) , v3.begin ( ) , mod_lesser );
   cout << "Set_symmetric_difference of source ranges with binary "
        << "predicate mod_lesser specified,\n vector v3mod  = ( " ; ;
   for ( Iter3 = v3.begin( ) ; Iter3 != Result3 ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")." << endl;
}
```

## <a name="set_union"></a> set_union

Vereinigt alle Elemente, die mindestens zu einem der beiden sortierten Quellbereiche gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
OutputIterator set_union(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class BinaryPredicate>
OutputIterator set_union(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result,
    BinaryPredicate comp );
```

### <a name="parameters"></a>Parameter

*first1* ein Eingabe-Iterator, der die Position des ersten Elements im ersten der beiden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich repräsentiert die Verbindung der beiden Quellbereiche sortiert werden sollen.

*Last1* ein Eingabe-Iterator, der die Position hinter dem letzten Element im ersten der beiden sortierten Quellbereiche adressiert, die kombiniert und zu einem einzelnen Bereich repräsentiert die Verbindung der beiden Quellbereiche sortiert werden sollen.

*first2* ein eingabeiterator, der die Position des ersten Elements im zweiten der beiden aufeinanderfolgenden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich repräsentiert die Verbindung der beiden Quellbereiche sortiert werden sollen.

*Last2* ein eingabeiterator, der die Position hinter dem letzten Element im zweiten der beiden aufeinanderfolgenden sortierten Quellbereiche kombiniert und zu einem einzelnen Bereich repräsentiert die Verbindung der beiden Quellbereiche sortiert werden sollen.

**_** *Ergebnis* ein Ausgabeiterator, der die Position des ersten Elements im Zielbereich, in dem die beiden Bereiche Datenquelle, auf einem einzelnen Bereich sortiert repräsentiert die Verbindung der beiden Quellbereiche kombiniert werden.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das den Sinn definiert, in dem ein Element größer als die andere ist. Das binäre Prädikat akzeptiert zwei Argumente und sollte **true** zurückgeben, wenn das erste Element kleiner als das zweite Element ist, andernfalls wird **false** zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der die Position hinter dem letzten Element im sortierten Zielbereich adressiert, der die Verbindung der beiden Quellbereiche repräsentiert.

### <a name="remarks"></a>Hinweise

Die sortierten Quellbereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb jeder Sequenz muss von der ersten Position aus durch Zunahme erreichbar sein.

Der Zielbereich sollte keinen der Quellbereiche überlappen und groß genug sein, um den Zielbereich zu enthalten.

Die sortierten Quellbereiche müssen als Vorbedingung zur Anwendung des `merge` -Algorithmus entsprechend der gleichen Reihenfolge sortiert werden, die vom Algorithmus für die Sortierung der kombinierten Bereiche verwendet wird.

Der Vorgang ist stabil, da die relative Reihenfolge der Elemente innerhalb jedes Bereichs im Zielbereich beibehalten wird. Die Quellbereiche werden nicht geändert, durch den Algorithmus `merge`.

Die Werttypen der Eingabeiteratoren müssen mit „kleiner als“ vergleichbar sein, um sortiert zu werden, sodass zwei Elemente möglicherweise als gleichwertig (in dem Sinne, dass keines kleiner als das andere ist) oder eines als kleiner als das andere bestimmt werden können. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen. Wenn in beiden Quellbereichen äquivalente Elemente vorhanden sind, stehen im Zielbereich die Elemente aus dem ersten Bereich vor den Elementen aus dem zweiten Bereich. Wenn die Quellbereiche Duplikate eines Element enthalten, wird der Zielbereich die maximale Anzahl dieser Elemente enthalten, die in beiden Quellbereichen auftreten.

Die Komplexität dieses Algorithmus ist höchstens mit 2 linear \* (( *last1 – first1*) – ( *last2 – first2*)) – 1 Vergleiche.

### <a name="example"></a>Beispiel

```cpp
// alg_set_union.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
}

int main( )
{
   using namespace std;
   vector <int> v1a, v1b, v1 ( 12 );
   vector <int>::iterator Iter1a, Iter1b, Iter1, Result1;

   // Constructing vectors v1a & v1b with default less than ordering
   int i;
   for ( i = -1 ; i <= 3 ; i++ )
   {
      v1a.push_back(  i );
   }

   int ii;
   for ( ii =-3 ; ii <= 1 ; ii++ )
   {
      v1b.push_back(  ii  );
   }

   cout << "Original vector v1a with range sorted by the\n "
        <<  "binary predicate less than is  v1a = ( " ;
   for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
      cout << *Iter1a << " ";
   cout << ")." << endl;

   cout << "Original vector v1b with range sorted by the\n "
        <<  "binary predicate less than is  v1b = ( " ;
   for ( Iter1b = v1b.begin ( ) ; Iter1b != v1b.end ( ) ; Iter1b++ )
      cout << *Iter1b << " ";
   cout << ")." << endl;

   // Constructing vectors v2a & v2b with ranges sorted by greater
   vector <int> v2a ( v1a ) , v2b ( v1b ) , v2 ( v1 );
   vector <int>::iterator Iter2a,  Iter2b, Iter2, Result2;
   sort ( v2a.begin ( ) , v2a.end ( ) , greater<int> ( ) );
   sort ( v2b.begin ( ) , v2b.end ( ) , greater<int> ( ) );

   cout << "Original vector v2a with range sorted by the\n "
        <<  "binary predicate greater is   v2a =  ( " ;
   for ( Iter2a = v2a.begin ( ) ; Iter2a != v2a.end ( ) ; Iter2a++ )
      cout << *Iter2a << " ";
   cout << ")." << endl;

   cout << "Original vector v2b with range sorted by the\n "
        <<  "binary predicate greater is   v2b =  ( " ;
   for ( Iter2b = v2b.begin ( ) ; Iter2b != v2b.end ( ) ; Iter2b++ )
      cout << *Iter2b << " ";
   cout << ")." << endl;

   // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
   vector <int> v3a ( v1a ), v3b ( v1b ) ,  v3 ( v1 );
   vector <int>::iterator Iter3a, Iter3b, Iter3, Result3;
   sort ( v3a.begin ( ) , v3a.end ( ) , mod_lesser );
   sort ( v3b.begin ( ) , v3b.end ( ) , mod_lesser  );

   cout << "Original vector v3a with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3a =  ( " ;
   for ( Iter3a = v3a.begin ( ) ; Iter3a != v3a.end ( ) ; Iter3a++ )
      cout << *Iter3a << " ";
   cout << ")." << endl;

   cout << "Original vector v3b with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3b =  ( " ;
   for ( Iter3b = v3b.begin ( ) ; Iter3b != v3b.end ( ) ; Iter3b++ )
      cout << *Iter3b << " ";
   cout << ")." << endl;

   // To combine into a union in ascending order with the default
    // binary predicate less <int> ( )
   Result1 = set_union ( v1a.begin ( ) , v1a.end ( ) ,
      v1b.begin ( ) , v1b.end ( ) , v1.begin ( ) );
   cout << "Union of source ranges with default order,"
        << "\n vector v1mod =  ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != Result1 ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To combine into a union in descending order, specify binary
   // predicate greater<int>( )
   Result2 = set_union (  v2a.begin ( ) , v2a.end ( ) ,
      v2b.begin ( ) , v2b.end ( ) ,v2.begin ( ) , greater <int> ( ) );
   cout << "Union of source ranges with binary predicate greater "
        << "specified,\n vector v2mod  = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != Result2 ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   // To combine into a union applying a user-defined
   // binary predicate mod_lesser
   Result3 = set_union ( v3a.begin ( ) , v3a.end ( ) ,
      v3b.begin ( ) , v3b.end ( ) , v3.begin ( ) , mod_lesser );
   cout << "Union of source ranges with binary predicate "
        << "mod_lesser specified,\n vector v3mod  = ( " ; ;
   for ( Iter3 = v3.begin( ) ; Iter3 != Result3 ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")." << endl;
}
```

## <a name="shuffle"></a> std::shuffle

Mischt (ordnet) Elemente für einen gegebenen Bereich mithilfe eines Zufallszahlengenerators.

```cpp
template<class RandomAccessIterator, class UniformRandomNumberGenerator>
void shuffle(RandomAccessIterator first,
    RandomAccessIterator last,
    UniformRandomNumberGenerator&& gen);
```

### <a name="parameters"></a>Parameter

*erste* ein Iterator zum ersten Element im Bereich zu mischenden (inklusiv) enthalten. Muss die Anforderungen von `RandomAccessIterator` und `ValueSwappable` erfüllen.

*letzte* ein Iterator auf das letzte Element im Bereich zu mischenden, exklusiv. Muss die Anforderungen von `RandomAccessIterator` und `ValueSwappable` erfüllen.

*Gen* den Zufallszahlengenerator, der die `shuffle()` für den Vorgang verwendet wird. Muss die Anforderungen eines `UniformRandomNumberGenerator` erfüllen.

### <a name="remarks"></a>Hinweise

Weitere Informationen und ein Codebeispiel mit `shuffle()` finden Sie unter [\<random>](../standard-library/random.md).

## <a name="sort"></a> sort

Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird.

```cpp
template<class RandomAccessIterator>
   void sort(
      RandomAccessIterator first,
      RandomAccessIterator last);

template<class RandomAccessIterator, class Predicate>
   void sort(
      RandomAccessIterator first,
      RandomAccessIterator last,
      Predicate comp);

```

### <a name="parameters"></a>Parameter

*erste* ein zufälliger eingabeiterator, der die Position des ersten Elements im Bereich sortiert werden soll.

*letzte* ein zufälliger eingabeiterator, der die Position adressiert, hinter dem letzten Element im Bereich sortiert werden soll.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das das Vergleichskriterium erfüllt werden muss, indem aufeinander folgende Elemente in der Reihenfolge definiert. Das binäre Prädikat akzeptiert zwei Argumente und gibt **"true"** , wenn die zwei Argumente sortiert sind und **"false"** andernfalls. Diese Vergleichoperatorfunktion muss eine strikte schwache Sortierung auf Elementenpaare der Sequenz anwenden. Weitere Informationen finden Sie unter [Algorithmen](../standard-library/algorithms.md).

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Wenn keins kleiner als das andere ist, sind Elemente äquivalent, aber nicht unbedingt gleich. Der Algorithmus `sort` ist nicht stabil und stellt deshalb nicht sicher, dass die relative Sortierung equivalenter Elemente beibehalten wird. Der Algorithmus `stable_sort` behält diese ursprüngliche Sortierung bei.

Der Durchschnitt einer sortierungskomplexität ist *O*( *N* Log *N*), wobei *N* =  *Nachname - Vorname*.

### <a name="example"></a>Beispiel

```cpp
// alg_sort.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether first element is greater than the second
bool UDgreater ( int elem1, int elem2 )
{
   return elem1 > elem2;
}

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   int ii;
   for ( ii = 0 ; ii <= 5 ; ii++ )
   {
      v1.push_back( 2 * ii + 1 );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   sort( v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order. specify binary predicate
   sort( v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "Resorted (greater) vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // A user-defined (UD) binary predicate can also be used
   sort( v1.begin( ), v1.end( ), UDgreater );
   cout << "Resorted (UDgreater) vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = ( 0 2 4 6 8 10 1 3 5 7 9 11 )
Sorted vector v1 = ( 0 1 2 3 4 5 6 7 8 9 10 11 )
Resorted (greater) vector v1 = ( 11 10 9 8 7 6 5 4 3 2 1 0 )
Resorted (UDgreater) vector v1 = ( 11 10 9 8 7 6 5 4 3 2 1 0 )
```

## <a name="sort_heap"></a> sort_heap

Konvertiert einen Heap in einen sortierten Bereich.

```cpp
template<class RandomAccessIterator>
   void sort_heap(
      RandomAccessIterator first,
      RandomAccessIterator last);

template<class RandomAccessIterator, class Predicate>
   void sort_heap(
      RandomAccessIterator first,
      RandomAccessIterator last,
      Predicate comp);
```

### <a name="parameters"></a>Parameter

*erste* ein zufälliger eingabeiterator, der die Position des ersten Elements im Zielheap adressiert.

*letzte* ein zufälliger eingabeiterator, der die Position hinter dem letzten Element im Zielheap adressiert.

*Comp* ermitteln benutzerdefiniertes prädikatfunktionsobjekt, das definiert, in dem ein Element kleiner als ein anderes ist. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="remarks"></a>Hinweise

Heaps haben zwei Eigenschaften:

- Das erste Element ist immer das größte.

- Elemente können in logarithmischer Zeit hinzugefügt oder entfernt werden.

Nach der Anwendung dieses Logarithmus ist der Bereich, auf den er angewendet wurde, kein Heap mehr.

Dies ist keine stabile Sortierung, da die relative Reihenfolge äquivalenter Elemente nicht unbedingt beibehalten wird.

Heaps sind ideal zum Implementieren von Vorrangwarteschlangen. Sie werden beim Implementieren des C++-Standardbibliothekadapters [priority_queue-Klasse](../standard-library/priority-queue-class.md) verwendet.

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Komplexität ist höchstens *N* Log *N*, wobei *N* = ( *Nachname - Vorname*).

### <a name="example"></a>Beispiel

```cpp
// alg_sort_heap.cpp
// compile with: /EHsc
#include <algorithm>
#include <functional>
#include <iostream>
#include <ostream>
#include <string>
#include <vector>
using namespace std;

void print(const string& s, const vector<int>& v) {
    cout << s << ": ( ";

    for (auto i = v.begin(); i != v.end(); ++i) {
        cout << *i << " ";
    }

    cout << ")" << endl;
}

int main() {
    vector<int> v;
    for (int i = 1; i <= 9; ++i) {
        v.push_back(i);
    }
    print("Initially", v);

    random_shuffle(v.begin(), v.end());
    print("After random_shuffle", v);

    make_heap(v.begin(), v.end());
    print("     After make_heap", v);

    sort_heap(v.begin(), v.end());
    print("     After sort_heap", v);

    random_shuffle(v.begin(), v.end());
    print("             After random_shuffle", v);

    make_heap(v.begin(), v.end(), greater<int>());
    print("After make_heap with greater<int>", v);

    sort_heap(v.begin(), v.end(), greater<int>());
    print("After sort_heap with greater<int>", v);
}
```

## <a name="stable_partition"></a> stable_partition

Klassifiziert Elemente in einem Bereich in zwei zusammenhanglose Sätze, wobei die Elemente, die ein unäres Prädikat erfüllen, direkt den Elementen vorausgehen, die es nicht erfüllen können. Die relative Reihenfolge der äquivalenten Elemente wird dabei beibehalten.

```cpp
template<class BidirectionalIterator, class Predicate>
BidirectionalIterator stable_partition(
    BidirectionalIterator first,
    BidirectionalIterator last,
    Predicate pred );

```

### <a name="parameters"></a>Parameter

*erste* ein bidirektionaler Iterator, der die Position des ersten Elements im Bereich von partitioniert werden soll.

*letzte* ein bidirektionaler Iterator, der die Position hinter dem letzten Element im Bereich adressiert, die partitioniert werden.

*_Pred* User-defined Function, Prädikat-Objekt, das definiert die Bedingung erfüllt wird, wenn ein Element ist klassifiziert werden sollen. Ein Prädikat akzeptiert ein einzelnes Argument und gibt entweder **TRUE** oder **FALSE** zurück.

### <a name="return-value"></a>Rückgabewert

Ein bidirektionaler Iterator, der die Position des ersten Elements in dem Bereich adressiert, das die Prädikatbedingung nicht erfüllt.

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Die Elemente *a* und *b* sind äquivalent, aber nicht unbedingt gleich, wenn sowohl *Pr* (*a*, *b*) als auch *Pr* (*b*, *a*) dort FALSE sind, wo *Pr* das parameterspezifische Prädikat ist. Die `stable_ partition` Algorithmus ist stabil und stellt sicher, dass die relative Sortierung equivalenter Elemente beibehalten wird. Der Algorithmus `partition` werden nicht unbedingt beibehalten diese ursprüngliche Sortierung.

### <a name="example"></a>Beispiel

```cpp
// alg_stable_partition.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater5 ( int value ) {
   return value >5;
}

int main( ) {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2, result;

   int i;
   for ( i = 0 ; i <= 10 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 4 ; ii++ )
      v1.push_back( 5 );

   random_shuffle(v1.begin( ), v1.end( ) );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Partition the range with predicate greater10
   result = stable_partition (v1.begin( ), v1.end( ), greater5 );
   cout << "The partitioned set of elements in v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "The first element in v1 to fail to satisfy the"
        << "\n predicate greater5 is: " << *result << "." << endl;
}
```

## <a name="stable_sort"></a> stable_sort

Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird, und behält die relative Reihenfolge der äquivalenten Elemente bei.

```cpp
template<class BidirectionalIterator>
 void stable_sort( BidirectionalIterator first, BidirectionalIterator last );

template<class BidirectionalIterator, class BinaryPredicate>
void stable_sort(
    BidirectionalIterator first,
    BidirectionalIterator last,
    BinaryPredicate comp );

```

### <a name="parameters"></a>Parameter

*erste* ein bidirektionaler Iterator, der die Position des ersten Elements im Bereich sortiert werden soll.

*letzte* ein bidirektionaler Iterator, der die Position adressiert, hinter dem letzten Element im Bereich sortiert werden soll.

*Comp* benutzerdefiniertes prädikatfunktionsobjekt, das das Vergleichskriterium erfüllt werden muss, indem aufeinander folgende Elemente in der Reihenfolge definiert. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="remarks"></a>Hinweise

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar.

Wenn keins kleiner als das andere ist, sind Elemente äquivalent, aber nicht unbedingt gleich. Die `sort` Algorithmus ist stabil und stellt sicher, dass die relative Sortierung equivalenter Elemente beibehalten wird.

Die laufzeitkomplexität von `stable_sort` hängt die Menge an Arbeitsspeicher verfügbar ist, aber der beste Fall (wenn über genügend Arbeitsspeicher) *O*( *N* Log *N*) und im schlimmsten Fall ist *O*( *N* (Protokoll *N* ) 2), wobei *N* =  *last – First.* In der Regel die `sort` Algorithmus ist bedeutend schneller als `stable_sort`.

### <a name="example"></a>Beispiel

```cpp
// alg_stable_sort.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether first element is greater than the second
bool UDgreater (int elem1, int elem2 )
{
   return elem1 > elem2;
}

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 2 * i  );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   stable_sort(v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order, specify binary predicate
   stable_sort(v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "Resorted (greater) vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // A user-defined (UD) binary predicate can also be used
   stable_sort(v1.begin( ), v1.end( ), UDgreater );
   cout << "Resorted (UDgreater) vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = ( 0 2 4 6 8 10 0 2 4 6 8 10 )
Sorted vector v1 = ( 0 0 2 2 4 4 6 6 8 8 10 10 )
Resorted (greater) vector v1 = ( 10 10 8 8 6 6 4 4 2 2 0 0 )
Resorted (UDgreater) vector v1 = ( 10 10 8 8 6 6 4 4 2 2 0 0 )
```

## <a name="swap"></a>  swap

Das erste Überschreiben tauscht die Werte zweier Objekte aus. Das zweite Überschreiben tauscht die Werte zwischen zwei Arrays von Objekten aus.

```cpp
template<class Type>
   void swap(
      Type& left,
      Type& right);
template<class Type, size_t N>
   void swap(
      Type (& left)[N],
      Type (& right)[N]);\r

```

### <a name="parameters"></a>Parameter

*linken* beim ersten überschreiben, das erste Objekt, dessen Inhalt ausgetauscht haben. Das erste Array von Objekten, dessen Inhalte beim zweiten Überschreiben ausgetauscht werden soll.

*richtige* beim ersten überschreiben, das zweite Objekt, dessen Inhalt ausgetauscht haben. Das zweite Array von Objekten, dessen Inhalte beim zweiten Überschreiben ausgetauscht werden soll.

### <a name="remarks"></a>Hinweise

Die erste Überladung wurde dafür entwickelt, einzelne Objekte zu verarbeiten. Die zweite Überladung tauscht die Inhalte von Objekten zwischen zwei Arrays aus.

### <a name="example"></a>Beispiel

```cpp
// alg_swap.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2, result;

   for ( int i = 0 ; i <= 10 ; i++ )
   {
      v1.push_back( i );
   }

   for ( int ii = 0 ; ii <= 4 ; ii++ )
   {
      v2.push_back( 5 );
   }

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "Vector v2 is ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   swap( v1, v2 );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "Vector v2 is ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;
}
```

```Output
Vector v1 is ( 0 1 2 3 4 5 6 7 8 9 10 ).
Vector v2 is ( 5 5 5 5 5 ).
Vector v1 is ( 5 5 5 5 5 ).
Vector v2 is ( 0 1 2 3 4 5 6 7 8 9 10 ).
```

## <a name="swap_ranges"></a> swap_ranges

Vertauscht die Elemente eines Bereichs mit den Elementen eines anderen gleich großen Bereichs.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 swap_ranges(
   ForwardIterator1 first1,
   ForwardIterator1 last1,
   ForwardIterator2 first2 );

```

### <a name="parameters"></a>Parameter

*first1* ein forward-Iterator zeigt, an die erste Position des ersten Bereichs, dessen Elemente ausgetauscht werden sollen.

*Last1* ein forward-Iterator verweist auf eine Stelle hinter der letzten Position des ersten Bereichs, dessen Elemente ausgetauscht werden sollen.

*first2* ein forward-Iterator verweist, die erste Position des zweiten Bereichs anzeigt, dessen Elemente ausgetauscht werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator, der die erste Position direkt hinter der letzten Position des zweiten Bereichs anzeigt, dessen Elemente ausgetauscht werden sollen.

### <a name="remarks"></a>Hinweise

Die Bereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar. Der zweite Bereich muss so groß wie der erste Bereich sein.

Die Komplexität ist linear, wobei *last1* - *first1* ausgetauscht. Wenn Elemente von Containern des selben Typen ausgetauscht werden, sollte die `swap`-Memberfunktion dieses Containers verwendet werden, da die Memberfunktion typischerweise eine konstante Komplexität hat.

### <a name="example"></a>Beispiel

```cpp
// alg_swap_ranges.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   deque <int> d1;
   vector <int>::iterator v1Iter1;
   deque<int>::iterator d1Iter1;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii =4 ; ii <= 9 ; ii++ )
   {
      d1.push_back( 6 );
   }

   cout << "Vector v1 is ( " ;
   for ( v1Iter1 = v1.begin( ) ; v1Iter1 != v1.end( ) ;v1Iter1 ++ )
      cout << *v1Iter1  << " ";
   cout << ")." << endl;

   cout << "Deque d1 is  ( " ;
   for ( d1Iter1 = d1.begin( ) ; d1Iter1 != d1.end( ) ;d1Iter1 ++ )
      cout << *d1Iter1  << " ";
   cout << ")." << endl;

   swap_ranges ( v1.begin ( ) , v1.end ( ) , d1.begin ( ) );

   cout << "After the swap_range, vector v1 is ( " ;
   for ( v1Iter1 = v1.begin( ) ; v1Iter1 != v1.end( ) ;v1Iter1 ++ )
      cout << *v1Iter1 << " ";
   cout << ")." << endl;

   cout << "After the swap_range deque d1 is   ( " ;
   for ( d1Iter1 = d1.begin( ) ; d1Iter1 != d1.end( ) ;d1Iter1 ++ )
      cout << *d1Iter1 << " ";
   cout << ")." << endl;
}
```

```Output
Vector v1 is ( 0 1 2 3 4 5 ).
Deque d1 is  ( 6 6 6 6 6 6 ).
After the swap_range, vector v1 is ( 6 6 6 6 6 6 ).
After the swap_range deque d1 is   ( 0 1 2 3 4 5 ).
```

## <a name="transform"></a> transform

Wendet ein angegebenes Funktionsobjekt auf jedes Element in einem Quellbereich oder auf ein Elementpaar aus zwei Quellbereichen an und kopiert die Rückgabewerte des Funktionsobjekts in einen Zielbereich.

```cpp
template<class InputIterator, class OutputIterator, class UnaryFunction>
OutputIterator transform(
    InputIterator first1,
    InputIterator last1,
    OutputIterator result,
    UnaryFunction _Func );

template<class InputIterator1, class InputIterator2, class OutputIterator, class BinaryFunction>
OutputIterator transform(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    OutputIterator result,
    BinaryFunction _Func );
```

### <a name="parameters"></a>Parameter

*first1* ein Eingabe-Iterator, der die Position des ersten Elements im ersten Quellbereich verarbeitet werden sollen.

*Last1* ein eingabeiterator, der die Position hinter dem letzten Element im ersten Quellbereich verarbeitet.

*first2* ein Eingabe-Iterator, der die Position des ersten Elements im zweiten Quellbereich verarbeitet werden sollen.

*Ergebnis* ein Ausgabeiterator, der die Position des ersten Elements im Zielbereich adressiert.

*_Func* ein benutzerdefiniertes unäres Funktionsobjekt verwendet, in der ersten Version des Algorithmus, der angewendet wird, um jedes Element in der ersten Quellbereich oder eine benutzerdefinierte (UD) binäres Funktionsobjekt verwendet, in der zweiten Version des Algorithmus, der angewendet wird paarweise in aufsteigender Reihenfolge, um die beiden Quellbereiche.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der die Position direkt hinter dem letzten Element im Zielbereich adressiert, der die vom Funktionsobjekt umgewandelten Ausgabeelemente erhält.

### <a name="remarks"></a>Hinweise

Die Bereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb jeder Sequenz muss von der ersten Position aus durch Zunahme erreichbar sein. Der Zielbereich muss groß genug sein, damit er den umgewandelten Quellbereich aufnehmen kann.

Wenn *Ergebnis* gleich festgelegt *first1* in der ersten Version des Algorithmus, klicken Sie dann die Quell- und Zielbereiche werden übereinstimmen und die Sequenz wird direkt bearbeitet werden. Aber die *Ergebnis* kann eine Position innerhalb des Bereichs nicht betreffen [`first1` + 1, `last1`).

Die Komplexität ist linear, wobei höchstens (`last1` - `first1`) vergleichen.

### <a name="example"></a>Beispiel

```cpp
// alg_transform.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

// The function object multiplies an element by a Factor
template <class Type>
class MultValue
{
   private:
      Type Factor;   // The value to multiply by
   public:
      // Constructor initializes the value to multiply by
      MultValue ( const Type& val ) : Factor ( val ) {
      }

      // The function call for the element to be multiplied
      Type operator ( ) ( Type& elem ) const
      {
         return elem * Factor;
      }
};

int main( )
{
   using namespace std;
   vector <int> v1, v2 ( 7 ), v3 ( 7 );
   vector <int>::iterator Iter1, Iter2 , Iter3;

   // Constructing vector v1
   int i;
   for ( i = -4 ; i <= 2 ; i++ )
   {
      v1.push_back(  i );
   }

   cout << "Original vector  v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Modifying the vector v1 in place
   transform (v1.begin ( ) , v1.end ( ) , v1.begin ( ) , MultValue<int> ( 2 ) );
   cout << "The elements of the vector v1 multiplied by 2 in place gives:"
        << "\n v1mod = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Using transform to multiply each element by a factor of 5
   transform ( v1.begin ( ) , v1.end ( ) , v2.begin ( ) , MultValue<int> ( 5 ) );

   cout << "Multiplying the elements of the vector v1mod\n "
        <<  "by the factor 5 & copying to v2 gives:\n v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   // The second version of transform used to multiply the
   // elements of the vectors v1mod & v2 pairwise
   transform ( v1.begin ( ) , v1.end ( ) ,  v2.begin ( ) , v3.begin ( ) ,
      multiplies <int> ( ) );

   cout << "Multiplying elements of the vectors v1mod and v2 pairwise "
        <<  "gives:\n v3 = ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")." << endl;
}
```

```Output
Original vector  v1 = ( -4 -3 -2 -1 0 1 2 ).
The elements of the vector v1 multiplied by 2 in place gives:
 v1mod = ( -8 -6 -4 -2 0 2 4 ).
Multiplying the elements of the vector v1mod
 by the factor 5 & copying to v2 gives:
 v2 = ( -40 -30 -20 -10 0 10 20 ).
Multiplying elements of the vectors v1mod and v2 pairwise gives:
 v3 = ( 320 180 80 20 0 20 80 ).
```

## <a name="unique"></a> unique

Entfernt doppelte Elemente, die in einem angegebenen Bereich nebeneinander angeordnet sind.

```cpp
template<class ForwardIterator>
   ForwardIterator unique(
      ForwardIterator first,
      ForwardIterator last);

template<class ForwardIterator, class Predicate>
   ForwardIterator unique(
      ForwardIterator first,
      ForwardIterator last,
      Predicate comp);

```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der die Position des ersten Elements im Bereich zum Entfernen von doppelten Elementen durchsucht werden soll.

*letzte* ein vorwärtsiterator, der die Position hinter dem letzten Element im Bereich zum Entfernen von doppelten Elementen durchsucht werden soll.

*Comp* User-defined Function, Prädikat-Objekt, das definiert die Bedingung erfüllt wird, wenn zwei Elemente enthalten sind, die ausgeführt werden als gleichwertig. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator am neuen Ende der veränderten Sequenz, die keine aufeinanderfolgenden doppelten Elemente enthält, adressiert die Position direkt hinter dem letzten Element, das nicht entfernt wurde.

### <a name="remarks"></a>Hinweise

Beide Formen des Algorithmus entfernen das zweite Duplikat eines aufeinanderfolgenden Paars gleicher Elemente.

Der Vorgang des Algorithmus ist stabil, sodass die relative Reihenfolge der nicht gelöschten Elemente nicht geändert wird.

Der Bereich, auf den verwiesen wird, muss gültig sein. Alle Zeiger müssen dereferenzierbar sein und die letzte Position innerhalb der Sequenz ist von der ersten Position aus durch Zunahme erreichbar. die Anzahl von Elementen in der Sequenz wird nicht geändert, durch den Algorithmus `unique` und die Elemente hinter dem Ende der veränderten Sequenz sind dereferenzierbar, aber nicht angegeben.

Die Komplexität ist linear und erfordert (`last` - `first`) – 1 Vergleiche.

List stellt die effizientere Memberfunktion „unique“ bereit, die möglicherweise besser funktioniert.

Diese Algorithmen können nicht auf einen assoziativen Container angewendet werden.

### <a name="example"></a>Beispiel

```cpp
// alg_unique.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>
#include <ostream>

using namespace std;

// Return whether modulus of elem1 is equal to modulus of elem2
bool mod_equal ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 == elem2;
};

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1_Iter1, v1_Iter2, v1_Iter3,
         v1_NewEnd1, v1_NewEnd2, v1_NewEnd3;

   int i;
   for ( i = 0 ; i <= 3 ; i++ )
   {
      v1.push_back( 5 );
      v1.push_back( -5 );
   }

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
   {
      v1.push_back( 4 );
   }
   v1.push_back( 7 );

   cout << "Vector v1 is ( " ;
   for ( v1_Iter1 = v1.begin( ) ; v1_Iter1 != v1.end( ) ; v1_Iter1++ )
      cout << *v1_Iter1 << " ";
   cout << ")." << endl;

   // Remove consecutive duplicates
   v1_NewEnd1 = unique ( v1.begin ( ) , v1.end ( ) );

   cout << "Removing adjacent duplicates from vector v1 gives\n ( " ;
   for ( v1_Iter1 = v1.begin( ) ; v1_Iter1 != v1_NewEnd1 ; v1_Iter1++ )
      cout << *v1_Iter1 << " ";
   cout << ")." << endl;

   // Remove consecutive duplicates under the binary prediate mod_equals
   v1_NewEnd2 = unique ( v1.begin ( ) , v1_NewEnd1 , mod_equal );

   cout << "Removing adjacent duplicates from vector v1 under the\n "
        << " binary predicate mod_equal gives\n ( " ;
   for ( v1_Iter2 = v1.begin( ) ; v1_Iter2 != v1_NewEnd2 ; v1_Iter2++ )
      cout << *v1_Iter2 << " ";
   cout << ")." << endl;

   // Remove elements if preceded by an element that was greater
   v1_NewEnd3 = unique ( v1.begin ( ) , v1_NewEnd2, greater<int>( ) );

   cout << "Removing adjacent elements satisfying the binary\n "
        << " predicate mod_equal from vector v1 gives ( " ;
   for ( v1_Iter3 = v1.begin( ) ; v1_Iter3 != v1_NewEnd3 ; v1_Iter3++ )
      cout << *v1_Iter3 << " ";
   cout << ")." << endl;
}
```

```Output
Vector v1 is ( 5 -5 5 -5 5 -5 5 -5 4 4 4 4 7 ).
Removing adjacent duplicates from vector v1 gives
 ( 5 -5 5 -5 5 -5 5 -5 4 7 ).
Removing adjacent duplicates from vector v1 under the
  binary predicate mod_equal gives
 ( 5 4 7 ).
Removing adjacent elements satisfying the binary
  predicate mod_equal from vector v1 gives ( 5 7 ).
```

## <a name="unique_copy"></a> nique_copy

Kopiert Elemente aus einem Quellbereich in einen Zielbereich mit Ausnahmen von doppelten Elementen, die nebeneinander angeordnet sind.

```cpp
template<class InputIterator, class OutputIterator>
OutputIterator unique_copy( InputIterator first,
    InputIterator last,
    OutputIterator result );

template<class InputIterator, class OutputIterator, class BinaryPredicate>
OutputIterator unique_copy( InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryPredicate comp );
```

### <a name="parameters"></a>Parameter

*erste* ein forward-Iterator, der die Position des ersten Elements im Quellbereich kopiert werden soll.

*letzte* ein forward-Iterator, der die Position hinter dem letzten Element im Quellbereich adressiert kopiert werden soll.

*Ergebnis* ein Ausgabeiterator, der die Position des ersten Elements im Zielbereich, die empfängt die Kopie der aufeinanderfolgende Duplikate entfernt.

*Comp* User-defined Function, Prädikat-Objekt, das definiert die Bedingung erfüllt wird, wenn zwei Elemente enthalten sind, die ausgeführt werden als gleichwertig. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der die Position hinter dem letzten Elements im Zielbereich adressiert, der die Kopie erhält, aus der aufeinanderfolgende Duplikate entfernt wurden.

### <a name="remarks"></a>Hinweise

Beide Formen des Algorithmus entfernen das zweite Duplikat eines aufeinanderfolgenden Paars gleicher Elemente.

Der Vorgang des Algorithmus ist stabil, sodass die relative Reihenfolge der nicht gelöschten Elemente nicht geändert wird.

Die Bereiche, auf die verwiesen wird, müssen gültig sein. Alle Zeiger müssen dereferenzierbar sein, und die letzte Position innerhalb einer Sequenz muss von der ersten Position aus durch Zunahme erreichbar sein.

Die Komplexität ist linear und erfordert (`last` - `first`) vergleichen.

### <a name="example"></a>Beispiel

```cpp
// alg_unique_copy.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>
#include <ostream>

using namespace std;

// Return whether modulus of elem1 is equal to modulus of elem2
bool mod_equal ( int elem1, int elem2 ) {
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 == elem2;
};

int main() {
   vector <int> v1;
   vector <int>::iterator v1_Iter1, v1_Iter2,
         v1_NewEnd1, v1_NewEnd2;

   int i;
   for ( i = 0 ; i <= 1 ; i++ ) {
      v1.push_back( 5 );
      v1.push_back( -5 );
   }

   int ii;
   for ( ii = 0 ; ii <= 2 ; ii++ )
      v1.push_back( 4 );
   v1.push_back( 7 );

   int iii;
   for ( iii = 0 ; iii <= 5 ; iii++ )
      v1.push_back( 10 );

   cout << "Vector v1 is\n ( " ;
   for ( v1_Iter1 = v1.begin( ) ; v1_Iter1 != v1.end( ) ; v1_Iter1++ )
      cout << *v1_Iter1 << " ";
   cout << ")." << endl;

   // Copy first half to second, removing consecutive duplicates
   v1_NewEnd1 = unique_copy ( v1.begin ( ) , v1.begin ( ) + 8, v1.begin ( ) + 8 );

   cout << "Copying the first half of the vector to the second half\n "
        << "while removing adjacent duplicates gives\n ( " ;
   for ( v1_Iter1 = v1.begin( ) ; v1_Iter1 != v1_NewEnd1 ; v1_Iter1++ )
      cout << *v1_Iter1 << " ";
   cout << ")." << endl;

   int iv;
   for ( iv = 0 ; iv <= 7 ; iv++ )
      v1.push_back( 10 );

   // Remove consecutive duplicates under the binary prediate mod_equals
   v1_NewEnd2 = unique_copy ( v1.begin ( ) , v1.begin ( ) + 14,
      v1.begin ( ) + 14 , mod_equal );

   cout << "Copying the first half of the vector to the second half\n "
        << " removing adjacent duplicates under mod_equals gives\n ( " ;
   for ( v1_Iter2 = v1.begin( ) ; v1_Iter2 != v1_NewEnd2 ; v1_Iter2++ )
      cout << *v1_Iter2 << " ";
   cout << ")." << endl;
}
```

## <a name="upper_bound"></a> upper_bound

Sucht die Position des ersten Elements in einem sortierten Bereich, der über einen Wert größer als einen angegebenen Wert verfügt. Dabei wird das Sortierkriterium möglicherweise von einen binären Prädikat bestimmt.

```cpp
template<class ForwardIterator, class Type>
   ForwardIterator upper_bound(
      ForwardIterator first,
      ForwardIterator last,
      const Type& value);

template<class ForwardIterator, class Type, class Predicate>
   ForwardIterator upper_bound(
      ForwardIterator first,
      ForwardIterator last,
      const Type& value,
      Predicate comp);

```

### <a name="parameters"></a>Parameter

*erste* die Position des ersten Elements im zu durchsuchenden Bereich.

*letzte* die Position hinter dem letzten Element im zu durchsuchenden Bereichs.

*Wert* zurückgegebene Wert im sortierten Bereich, der durch den Wert der vom Iterator adressierten Elements überschritten werden muss.

*Comp* ermitteln benutzerdefiniertes prädikatfunktionsobjekt, das definiert, in dem ein Element kleiner als ein anderes ist. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück.

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator zur Position des ersten Elements, das über einen Wert größer als den angegebenen Wert verfügt.

### <a name="remarks"></a>Hinweise

Der sortierte Quellbereich, auf den verwiesen wird, muss gültig sein. Alle Iteratoren müssen dereferenzierbar sein und die letzte Position muss der innerhalb der Reihenfolge vom ersten von der ersten Position aus durch Zunahme erreichbar sein.

Ein sortierter Bereich ist eine Vorbedingung für die Verwendung von `upper_bound` und wann immer das Sortierkriterium mit vom binären Prädikat angegebenen identisch ist.

Der Bereich wird von `upper_bound` nicht geändert.

Die Werttypen der Forward-Iteratoren müssen weniger als vergleichbar sein, um sortiert zu werden, sodass zwei Elemente möglicherweise als gleichwertig bestimmt werden (in dem Sinne, dass keins geringer als das Andere ist), oder dass eins geringer als das Andere ist. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen.

Die Komplexität dieses Algorithmus ist bei Zufallszugriffsiteratoren logarithmisch und andernfalls linear. Dabei ist eine Anzahl von Schritten proportional zu (`last - first`).

### <a name="example"></a>Beispiel

```cpp
// alg_upper_bound.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser( int elem1, int elem2 )
{
    if ( elem1 < 0 )
        elem1 = - elem1;
    if ( elem2 < 0 )
        elem2 = - elem2;
    return elem1 < elem2;
}

int main( )
{
    using namespace std;

    vector<int> v1;
    // Constructing vector v1 with default less-than ordering
    for ( auto i = -1 ; i <= 4 ; ++i )
    {
        v1.push_back(  i );
    }

    for ( auto ii =-3 ; ii <= 0 ; ++ii )
    {
        v1.push_back(  ii  );
    }

    cout << "Starting vector v1 = ( " ;
    for (const auto &Iter : v1)
        cout << Iter << " ";
    cout << ")." << endl;

    sort(v1.begin(), v1.end());
    cout << "Original vector v1 with range sorted by the\n "
        << "binary predicate less than is v1 = ( " ;
    for (const auto &Iter : v1)
        cout << Iter << " ";
    cout << ")." << endl;

    // Constructing vector v2 with range sorted by greater
    vector<int> v2(v1);

    sort(v2.begin(), v2.end(), greater<int>());

    cout << "Original vector v2 with range sorted by the\n "
        << "binary predicate greater is v2 = ( " ;
    for (const auto &Iter : v2)
        cout << Iter << " ";
    cout << ")." << endl;

    // Constructing vectors v3 with range sorted by mod_lesser
    vector<int> v3(v1);
    sort(v3.begin(), v3.end(), mod_lesser);

    cout << "Original vector v3 with range sorted by the\n "
        <<  "binary predicate mod_lesser is v3 = ( " ;
    for (const auto &Iter : v3)
        cout << Iter << " ";
    cout << ")." << endl;

    // Demonstrate upper_bound

    vector<int>::iterator Result;

    // upper_bound of 3 in v1 with default binary predicate less<int>()
    Result = upper_bound(v1.begin(), v1.end(), 3);
    cout << "The upper_bound in v1 for the element with a value of 3 is: "
        << *Result << "." << endl;

    // upper_bound of 3 in v2 with the binary predicate greater<int>( )
    Result = upper_bound(v2.begin(), v2.end(), 3, greater<int>());
    cout << "The upper_bound in v2 for the element with a value of 3 is: "
        << *Result << "." << endl;

    // upper_bound of 3 in v3 with the binary predicate  mod_lesser
    Result = upper_bound(v3.begin(), v3.end(), 3,  mod_lesser);
    cout << "The upper_bound in v3 for the element with a value of 3 is: "
        << *Result << "." << endl;
}

```
## <a name="see-also"></a>Siehe auch

[\<algorithm>](../standard-library/algorithm.md)<br/>