---
title: hash_map-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- hash_map/stdext::hash_map
- hash_map/stdext::hash_map::allocator_type
- hash_map/stdext::hash_map::const_iterator
- hash_map/stdext::hash_map::const_pointer
- hash_map/stdext::hash_map::const_reference
- hash_map/stdext::hash_map::const_reverse_iterator
- hash_map/stdext::hash_map::difference_type
- hash_map/stdext::hash_map::iterator
- hash_map/stdext::hash_map::key_compare
- hash_map/stdext::hash_map::key_type
- hash_map/stdext::hash_map::mapped_type
- hash_map/stdext::hash_map::pointer
- hash_map/stdext::hash_map::reference
- hash_map/stdext::hash_map::reverse_iterator
- hash_map/stdext::hash_map::size_type
- hash_map/stdext::hash_map::value_type
- hash_map/stdext::hash_map::at
- hash_map/stdext::hash_map::begin
- hash_map/stdext::hash_map::cbegin
- hash_map/stdext::hash_map::cend
- hash_map/stdext::hash_map::clear
- hash_map/stdext::hash_map::count
- hash_map/stdext::hash_map::crbegin
- hash_map/stdext::hash_map::crend
- hash_map/stdext::hash_map::emplace
- hash_map/stdext::hash_map::emplace_hint
- hash_map/stdext::hash_map::empty
- hash_map/stdext::hash_map::end
- hash_map/stdext::hash_map::equal_range
- hash_map/stdext::hash_map::erase
- hash_map/stdext::hash_map::find
- hash_map/stdext::hash_map::get_allocator
- hash_map/stdext::hash_map::insert
- hash_map/stdext::hash_map::key_comp
- hash_map/stdext::hash_map::lower_bound
- hash_map/stdext::hash_map::max_size
- hash_map/stdext::hash_map::rbegin
- hash_map/stdext::hash_map::rend
- hash_map/stdext::hash_map::size
- hash_map/stdext::hash_map::swap
- hash_map/stdext::hash_map::upper_bound
- hash_map/stdext::hash_map::value_comp
dev_langs:
- C++
helpviewer_keywords:
- stdext::hash_map
- stdext::hash_map::allocator_type
- stdext::hash_map::const_iterator
- stdext::hash_map::const_pointer
- stdext::hash_map::const_reference
- stdext::hash_map::const_reverse_iterator
- stdext::hash_map::difference_type
- stdext::hash_map::iterator
- stdext::hash_map::key_compare
- stdext::hash_map::key_type
- stdext::hash_map::mapped_type
- stdext::hash_map::pointer
- stdext::hash_map::reference
- stdext::hash_map::reverse_iterator
- stdext::hash_map::size_type
- stdext::hash_map::value_type
- stdext::hash_map::at
- stdext::hash_map::begin
- stdext::hash_map::cbegin
- stdext::hash_map::cend
- stdext::hash_map::clear
- stdext::hash_map::count
- stdext::hash_map::crbegin
- stdext::hash_map::crend
- stdext::hash_map::emplace
- stdext::hash_map::emplace_hint
- stdext::hash_map::empty
- stdext::hash_map::end
- stdext::hash_map::equal_range
- stdext::hash_map::erase
- stdext::hash_map::find
- stdext::hash_map::get_allocator
- stdext::hash_map::insert
- stdext::hash_map::key_comp
- stdext::hash_map::lower_bound
- stdext::hash_map::max_size
- stdext::hash_map::rbegin
- stdext::hash_map::rend
- stdext::hash_map::size
- stdext::hash_map::swap
- stdext::hash_map::upper_bound
- stdext::hash_map::value_comp
ms.assetid: 40879dfc-51ba-4a59-9f9e-26208de568a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68d3ed6e9274fdfad38ad7ed8cdd9f8e83e0630a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849079"
---
# <a name="hashmap-class"></a>hash_map-Klasse

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Speichert Daten und ruft sie schnell aus einer Auflistung ab, in der jedes Element ein Paar ist, das einen Sortierschlüssel aufweist, dessen Wert eindeutig und ein zugeordneter Datenwert ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Key,
    class Type,
    class Traits=hash_compare<Key, less<Key>>,
    class Allocator=allocator<pair <const Key, Type>>>
class hash_map
```

### <a name="parameters"></a>Parameter

`Key` Geben Sie die Schlüsseldaten im hash_map-Element gespeichert werden.

`Type` Der im hash_map-Element zu speichernde Elementdatentyp.

`Traits` Der Typ, der zwei Funktionsobjekte enthält: eines der zwei Elementwerte als Sortierschlüssel, um zu bestimmen, deren relative Reihenfolge und eine Hashfunktion, die vergleichen kann Compare-Klasse ist ein unäres Prädikat Schlüsselwerte der Elemente zu vorzeichenlosen ganzen Zahlen des Typs `size_t`. Dieses Argument ist optional, und der Standardwert ist hash_compare<`Key`, less<`Key`> >.

`Allocator` Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zum Belegen und Freigeben des Arbeitsspeichers des hash_map Elements kapselt. Dieses Argument ist optional, und der Standardwert ist allocator<pair <const `Key`, `Type`>>.

## <a name="remarks"></a>Hinweise

Das hash_map-Element ist:

- Ein assoziativer Container, der ein Container variabler Größe ist, der den effizienten Abruf von Elementwerten auf Grundlage eines zugeordneten Schlüsselwert unterstützt.

- Umkehrbar, da ein bidirektionaler Iterator für den Zugriff auf die Elemente bereitgestellt wird.

- Gehasht, da die Elemente auf Grundlage des Werts einer Hashfunktion, die auf die Schlüsselwerte der Elemente angewendet wird, in Buckets gruppiert werden.

- Insofern eindeutig, da jedes der Elemente einen eindeutigen Schlüssel aufweisen muss.

- Ein Paar assoziativer Container, da sich die Elementdatenwerte von den Schlüsselwerten unterscheiden.

- Eine Vorlagenklasse, da die bereitgestellten Funktionen generisch ist und daher unabhängig vom angegebenen Datentyp, der als Elemente oder Schlüssel enthalten ist. Die für Elemente und Schlüssel zu verwendenden Datentypen werden stattdessen in der Klassenvorlage zusammen mit der Vergleichsfunktion und der Zuweisung als Parameter angegeben.

Der Hauptvorteil des Hashverfahrens gegenüber der Sortierung ist die größere Effizienz. Bei einem erfolgreichen Hashverfahren werden Einfüge-, Lösch- und Suchvorgänge, verglichen mit einer Zeit, die zum Logarithmus der Anzahl von Elementen im Container für Sortiertechniken proportional ist, in einer konstanten Durchschnittszeit durchgeführt. Der Wert eines Elements in einem hash_map-Element, aber nicht der zugehörige Schlüsselwert, werden möglicherweise direkt geändert. Stattdessen müssen die Schlüsselwerte, die alten Elementen zugeordnet sind, gelöscht, und stattdessen neuen Schlüsselwerten für neue Elemente zugeordnet werden.

Die Auswahl des Containertyps sollte im Allgemeinen auf Grundlage des für die Anwendung erforderlichen Suchen und Einfügetyps erfolgen. Gehashte assoziative Container sind für Such-, Einfüge- und Entfernvorgänge optimiert. Die Memberfunktionen, die diese Vorgänge explizit unterstützen, sind effizient, wenn sie mit einer gut entworfenen Hashfunktion verwendet werden. Dann werden sie in einer Zeit ausgeführt, die im Durchschnitt konstant und nicht von der Anzahl von Elementen im Container abhängig ist. Eine ausgereifte Hashfunktion erzeugt eine vereinheitlichte Verteilung gehashter Werte und minimiert die Anzahl von Konflikten, bei denen ein Konflikt vorhergesagt wird, wenn unterschiedliche Schlüsselwerte dem gleichen gehashten Wert zugeordnet werden. Im schlimmsten Fall ist die Anzahl von Vorgängen bei der schlimmstmöglichen Hashfunktion zu der Anzahl von Elementen in der Sequenz proportional (lineare Zeit).

Das hash_map-Element sollte der ausgewählte assoziative Container sein, wenn die Bedingungen, mit denen die Werte von der Anwendung den Schlüsseln zugeordnet werden, erfüllt werden. Ein Modell für diesen Strukturtyp ist eine geordnete Liste eindeutig auftretender Schlüsselwörter mit zugeordneten Zeichenfolgewerten, die etwa Definitionen bereitstellen. Wenn stattdessen die Wörter mehrere genaue Definition aufweisen, sodass die Schlüssel nicht eindeutig sind, ist ein hash_multimap-Element der ausgewählte Container. Wenn hingegen nur die Wortliste gespeichert wurden, ist ein hash_set-Element der richtige Container. Wenn mehrfaches Vorkommen der Wörter zugelassen wird, ist ein hash_multiset-Element die geeignete Containerstruktur.

Das hash_map-Element sortiert die gesteuerte Sequenz, indem ein gespeichertes `Traits`-Hashobjekt der Klasse [value_compare](../standard-library/value-compare-class.md) aufgerufen wird. Auf das gespeicherte Objekt kann zugegriffen werden, indem die Memberfunktion [key_comp](#key_comp) aufrufen wird. Ein solches Funktionsobjekt muss sich wie ein Objekt der Klasse [hash_compare](../standard-library/hash-compare-class.md)<Key, less\<Key>> verhalten. Insbesondere für alle `Key`-Werte des Typs `Key` erreicht der `Traits`-Aufruf ( `Key` ) eine Verteilung der Werte vom Typ `size_t`.

Im Allgemeinen müssen die Elemente der Vorwärtsiteratoren etwas weniger als vergleichbar sein, um diese Sortierung zu erstellen, sodass beliebige zwei Elemente möglicherweise als gleichwertig bestimmt werden (in dem Sinne, dass keins geringer als das Andere ist), oder dass eins geringer als das Andere ist. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen. Etwas technischer betrachtet ist die Vergleichsfunktion ein binäres Prädikat, das eine strenge schwache Sortierung im mathematischen Sinn verursacht. Bei einem binären f(x y)--Prädikat handelt es sich um ein Funktionsobjekt, das die zwei Argumentobjekte `x` und `y` aufweist sowie einen Rückgabewert von `true` oder `false`. Eine Sortierung, die auf ein hash_map-Element angewendet wird, ist eine strenge schwache Sortierung, wenn das binäre Prädikat irreflexiv, antisymmetrisch und transitiv ist, und wenn die Äquivalenz transitiv ist, wobei die beiden Objekte x und y als äquivalent definiert werden, wenn sowohl f (x, y) als auch f (x, y) falsch sind. Wenn der stärkere Gleichheitszustand zwischen Schlüsseln die Äquivalenz ersetzt, erfolgt die Sortierung total (d. h., alle Elemente werden zueinander sortiert), und die verglichenen Schlüssel sind von den einander nicht mehr zu unterscheiden.

Die tatsächliche Reihenfolge der Elemente in der gesteuerten Sequenz hängt von der Hashfunktion, der Sortierfunktion und der aktuellen Größe der Hashtabelle ab, die im Containerobjekt gespeichert wird. Die aktuelle Größe der Hashtabelle kann nicht bestimmt werden. Deshalb kann die Reihenfolge der Elemente in der gesteuerten Sequenz im Allgemeinen nicht vorhergesagt werden. Das Einfügen von Elementen führt nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen von Elementen werden nur solche Iteratoren ungültig, die speziell auf die entfernten Elemente gezeigt haben.

Der von einer hash_map-Klasse bereitgestellte Iterator ist ein bidirektionaler Iterator. Die Klassenmemberfunktionen [insert](#insert) und [hash_map](#hash_map) weisen allerdings Versionen auf, die einen abgeschwächten Eingabeiterator als Vorlagenparameter akzeptieren, dessen Funktionalitätsanforderungen weniger umfangreich sind, als die von der Klasse bidirektionaler Iteratoren garantierten. Die verschiedenen Iteratorkonzepte bilden eine Family, die durch Verfeinerungen in ihrer Funktionen verknüpft ist. Jedes Iteratorkonzept weist einen eigenen Satz von Anforderungen auf, und die damit funktionierenden Algorithmen müssen die Annahmen hinsichtlich der von diesem Iteratortyp bereitgestellten Anforderungen begrenzen. Es kann davon ausgegangen werden, dass ein Eingabeiterator möglicherweise so dereferenziert wird, dass er auf ein Objekt verweist und dieses möglicherweise zum folgenden Iterator in der Sequenz erhöht. Das ist ein minimaler Funktionssatz, allerdings genügt er, um sinnvoll über einen Bereich von `[First, Last)`-Iteratoren im Kontext der Klassenmemberfunktionen zu sprechen.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[hash_map](#hash_map)|Erstellt ein `hash_map`-Element, das leer oder die Kopie eines ganzen anderen `hash_map`-Elements oder eines Teils davon ist.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[allocator_type](#allocator_type)|Ein Typ, der die `allocator`-Klassentyp für das `hash_map`-Objekt darstellt.|
|[const_iterator](#const_iterator)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, der im `const`-Element ein `hash_map`-Element lesen kann.|
|[const_pointer](#const_pointer)|Ein Typ, der einen Zeiger auf ein `const`-Element in einem `hash_map`-Element bereitstellt.|
|[const_reference](#const_reference)|Ein Typ, der einen Verweis auf ein `const`-Element bereitstellt, das in einem `hash_map`-Element zum Lesen und Ausführen von `const`-Vorgängen gespeichert ist.|
|[const_reverse_iterator](#const_reverse_iterator)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, der im `const`-Element jedes `hash_map`-Element lesen kann.|
|[difference_type](#difference_type)|Ein Ganzzahltyp mit Vorzeichen, der dazu verwendet werden kann, die Anzahl von Elementen eines `hash_map`-Elements in einen Bereich zwischen Elementen darzustellen, auf die von Iteratoren gezeigt wird.|
|[Iterator](#iterator)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem jedes Element in einer `hash_map` gelesen oder geändert werden kann.|
|[key_compare](#key_compare)|Eine Typ, der ein Funktionsobjekt bereitstellt, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen im `hash_map`-Element zu bestimmen.|
|[key_type](#key_type)|Ein Typ beschreibt das Sortierschlüsselobjekt, das jedes Element von `hash_map` bildet.|
|[mapped_type](#mapped_type)|Ein Typ, der den in einer `hash_map` gespeicherten Datentyp darstellt.|
|[Zeiger](#pointer)|Ein Typ, der einen Zeiger auf ein Element in einer `hash_map` bereitstellt.|
|[reference](#reference)|Ein Typ, der einen Verweis auf ein in einer `hash_map` gespeichertes Element bereitstellt.|
|[reverse_iterator](#reverse_iterator)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem ein Element in einem umgekehrten `hash_map`-Element gelesen oder geändert werden kann.|
|[size_type](#size_type)|Eine Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in `hash_map` darstellen kann.|
|[value_type](#value_type)|Eine Typ, der ein Funktionsobjekt bereitstellt, das zwei Elemente als Sortierschlüssel vergleichen kann, um die relative Position im `hash_map`-Element zu bestimmen.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[at](#at)|Sucht ein Element in der `hash_map` mit einem angegebenen Schlüsselwert.|
|[begin](#begin)|Gibt ein Iterator zurück, der das erste Element im `hash_map`-Element adressiert.|
|[cbegin](#cbegin)|Gibt einen konstanten Iterator zurück, der das erste Element im `hash_map`-Element adressiert.|
|[cend](#cend)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines `hash_map`-Elements nachfolgt.|
|[clear](#clear)|Löscht alle Elemente einer `hash_map` auf.|
|[count](#count)|Gibt die Anzahl von Elementen in einem `hash_map`-Element zurück, dessen Schlüssel dem von einem Parameter angegebenen Schlüssel entspricht.|
|[crbegin](#crbegin)|Gibt einen konstanten Iterator zurück, der das erste Element im umgekehrten `hash_map`-Element adressiert.|
|[crend](#crend)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten `hash_map`-Elements nachfolgt.|
|[emplace](#emplace)|Fügt ein Element ein, das vor Ort in ein `hash_map`-Element erstellt wird.|
|[emplace_hint](#emplace_hint)|Fügt ein Element ein, das vor Ort mit einem Platzierungshinweis in ein `hash_map`-Element erstellt wird.|
|[empty](#empty)|Testet, ob ein `hash_map`-Element leer ist.|
|[end](#end)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einem `hash_map`-Element nachfolgt.|
|[equal_range](#equal_range)|Gibt ein Iteratorpaar jeweils zum ersten Element in einem `hash_map`-Element mit einem Schlüssel zurück, der größer als ein bestimmter Schlüssel ist, bzw. zum ersten Element im `hash_map`-Element mit einem Schlüssel, der größer oder gleich dem Schlüssel ist.|
|[erase](#erase)|Entfernt ein Element oder eine Reihe von Elementen in einer `hash_map` aus angegebenen Speicherorten.|
|[find](#find)|Gibt einen Iterator zurück, der die Position eines Elements in einem `hash_map`-Element adressiert, das einen Schlüssel aufweist, der einen angegebenen Schlüssel entspricht.|
|[get_allocator](#get_allocator)|Gibt eine Kopie des zum Erstellen von `allocator` verwendeten `hash_map`-Objekts zurück.|
|[insert](#insert)|Fügt ein Element oder einen Elementbereich in ein `hash_map`-Element ein.|
|[key_comp](#key_comp)|Gibt einen Iterator zum ersten Element in einem `hash_map`-Element mit einem Schlüsselwert zurück, der gleich oder größer ist, als ein angegebener Schlüssel.|
|[lower_bound](#lower_bound)|Gibt einen Iterator zum ersten Element in einem `hash_map`-Element mit einem Schlüsselwert zurück, der gleich oder größer ist, als ein angegebener Schlüssel.|
|[max_size](#max_size)|Gibt die Maximallänge der `hash_map` zurück.|
|[rbegin](#rbegin)|Gibt einen Iterator zurück, der das erste Element in einem umgekehrten `hash_map`-Element adressiert.|
|[rend](#rend)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten `hash_map`-Elements nachfolgt.|
|[size](#size)|Gibt die Anzahl von Elementen in der `hash_map` zurück.|
|[swap](#swap)|Tauscht die Elemente zweier `hash_map`n.|
|[upper_bound](#upper_bound)|Gibt einen Iterator zum ersten Element in einem `hash_map`-Element mit einem Schlüsselwert zurück, der größer ist, als ein angegebener Schlüssel.|
|[value_comp](#value_comp)|Ruft eine Kopie des Vergleichsobjekts ab, das zum Sortieren der Elementwerte in `hash_map` verwendet wird.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator&#91;&#93;](#op_at)|Fügt ein Element in ein `hash_map`-Element mit einem angegebenen Schlüsselwert ein.|
|[hash_map::operator=](#op_eq)|Ersetzt die Elemente eines `hash_map`-Elements durch eine Kopie eines anderen `hash_map`-Elements.|

## <a name="requirements"></a>Anforderungen

**Header:** \<hash_map>

**Namespace:** stdext

## <a name="allocator_type"></a> hash_map::allocator_type

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Typ, der die Zuweisungsklasse für das hash_map-Objekt darstellt.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="example"></a>Beispiel

In dem Beispiel für [get_allocator](#get_allocator) finden Sie ein Beispiel, das `allocator_type` verwendet.

## <a name="at"></a> hash_map::at

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Verwendet einen angegebenen Schlüsselwert, um in einem hash_map-Element nach einem Element zu suchen.

```cpp
Type& at(const Key& key);

const Type& at(const Key& key) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`key`|Der Schlüsselwert des zu suchenden Elements.|

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf den Datenwert des gefundenen Elements.

### <a name="remarks"></a>Hinweise

Wird der als Argument angegebene Schlüsselwert nicht gefunden, löst die Funktion ein Objekt der [out_of_range](../standard-library/out-of-range-class.md)-Klasse aus.


### <a name="example"></a>Beispiel

```cpp
// hash_map_at.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef pair <const int, int> cInt2Int;
   hash_map <int, int> hm1;

   // Insert data values
   hm1.insert ( cInt2Int ( 1, 10 ) );
   hm1.insert ( cInt2Int ( 2, 20 ) );
   hm1.insert ( cInt2Int ( 3, 30 ) );

   cout  << "The values of the mapped elements are:";
   for ( int i = 1 ; i <= hm1.size() ; i++ )
      cout << " " << hm1.at(i);
   cout << "." << endl;
}
```

## <a name="begin"></a> hash_map::begin

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt einen Iterator zurück, der das erste Element im hash_map-Element adressiert.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Rückgabewert

Ein bidirektionaler Iterator, der das erste Element in der hash_map adressiert oder auf den Speicherort hinweist, der auf eine leere hash_map folgt.

### <a name="example"></a>Beispiel

```cpp
// hash_map_begin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: iterator hm1_Iter;
   hash_map <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 0, 0 ) );
   hm1.insert ( Int_Pair ( 1, 1 ) );
   hm1.insert ( Int_Pair ( 2, 4 ) );

   hm1_cIter = hm1.begin ( );
   cout << "The first element of hm1 is "
        << hm1_cIter -> first << "." << endl;

   hm1_Iter = hm1.begin ( );
   hm1.erase ( hm1_Iter );

   // The following 2 lines would err because the iterator is const
   // hm1_cIter = hm1.begin ( );
   // hm1.erase ( hm1_cIter );

   hm1_cIter = hm1.begin( );
   cout << "The first element of hm1 is now "
        << hm1_cIter -> first << "." << endl;
}
```

```Output
The first element of hm1 is 0.
The first element of hm1 is now 1.
```

## <a name="cbegin"></a> hash_map::cbegin

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt einen const-Iterator zurück, der das erste Element in der hash_map adressiert.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein konstanter bidirektionaler Iterator, der das erste Element in der [hash_map](../standard-library/hash-map-class.md) adressiert oder auf den Speicherort hinweist, der auf eine leere `hash_map` folgt.

### <a name="example"></a>Beispiel

```cpp
// hash_map_cbegin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 2, 4 ) );

   hm1_cIter = hm1.cbegin ( );
   cout << "The first element of hm1 is "
        << hm1_cIter -> first << "." << endl;
   }
```

```Output
The first element of hm1 is 2.
```

## <a name="cend"></a> hash_map::cend

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der auf das letzte Element einer hash_map folgt.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Rückgabewert

Ein konstanter bidirektionaler Iterator, der den Speicherort adressiert, der auf das letzte Element einer [hash_map](../standard-library/hash-map-class.md) folgt. Wenn `hash_map` leer ist, dann gilt `hash_map::cend == hash_map::begin`.

### <a name="remarks"></a>Hinweise

`cend` wird verwendet, um zu testen, ob ein Iterator das Ende seines `hash_map` erreicht hat.

Der von `cend` zurückgegebene Wert darf nicht dereferenziert werden.

### <a name="example"></a>Beispiel

```cpp
// hash_map_cend.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_cIter = hm1.cend( );
   hm1_cIter--;
   cout << "The value of last element of hm1 is "
        << hm1_cIter -> second << "." << endl;
   }
```

```Output
The value of last element of hm1 is 30.
```

## <a name="clear"></a> hash_map::clear

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Löscht alle Elemente einer hash_map.

```cpp
void clear();
```

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Verwendung der Memberfunktion "hash_map::clear" gezeigt.

```cpp
// hash_map_clear.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int> hm1;
    hash_map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 1));
    hm1.insert(Int_Pair(2, 4));

    i = hm1.size();
    cout << "The size of the hash_map is initially "
         << i << "." << endl;

    hm1.clear();
    i = hm1.size();
    cout << "The size of the hash_map after clearing is "
         << i << "." << endl;
}
```

```Output
The size of the hash_map is initially 2.
The size of the hash_map after clearing is 0.
```

## <a name="const_iterator"></a> hash_map::const_iterator

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem ein **const**-Element in der hash_map gelesen werden kann.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Hinweise

Ein `const_iterator`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden.

Die `const_iterator` durch hash_map-Element verweist auf Elemente, die Objekte des definierten [Value_type](#value_type), d. h. vom Typ `pair` *\< ***const Key, Type*** >*, dessen erste Member ist der Schlüssel, der dem Element und, deren zweite Element ist der zugeordnete Bezug frei, die für das Element.

Dereferenziert einen `const_iterator` `cIter` verweist auf ein Element in einer Hash_map, verwenden Sie die **->** Operator.

Um auf den Wert des Schlüssels für das Element zuzugreifen, verwenden Sie `cIter` **-> first**, das (\* `cIter`) **.first** entspricht. Um auf den Wert des zugeordneten Datums für das Element zuzugreifen, verwenden Sie `cIter` **-> second**, das (\* `cIter`) **.second** entspricht.

### <a name="example"></a>Beispiel

Im Beispiel für [begin](#begin) finden Sie ein Beispiel, das `const_iterator` verwendet.

## <a name="const_pointer"></a> hash_map::const_pointer

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Typ, der einen Zeiger auf ein **const**-Element in einer hash_map bereitstellt.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Hinweise

Ein `const_pointer`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden.

In den meisten Fällen sollte ein [iterator](#iterator) für den Zugriff auf Elemente in einem Listenobjekt verwendet werden.

## <a name="const_reference"></a> hash_map::const_reference

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Typ, der einen Verweis auf ein **const**-Element bereitstellt, das in einer hash_map zum Lesen und Ausführen von **const**-Vorgängen gespeichert ist.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_reference const_reference;
```

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

```cpp
// hash_map_const_ref.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map<int, int> hm1;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( hm1.begin( ) -> first );

   // The following line would cause an error because the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( hm1.begin( ) -> first );

   cout << "The key of the first element in the hash_map is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( hm1.begin( ) -> second );

   cout << "The data value of the first element in the hash_map is "
        << Ref2 << "." << endl;
}
```

```Output
The key of the first element in the hash_map is 1.
The data value of the first element in the hash_map is 10.
```

## <a name="const_reverse_iterator"></a> hash_map::const_reverse_iterator

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem jedes **const**-Element in der hash_map gelesen werden kann.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse)iterator const_reverse_iterator;
```

### <a name="remarks"></a>Hinweise

Ein `const_reverse_iterator`-Typ kann nicht den Wert eines Elements ändern und wird verwendet, um die hash_map in umgekehrter Reihenfolge zu durchlaufen.

Der `const_reverse_iterator`, der durch hash_map definiert wird, zeigt auf Elemente, die Objekte eines [value_type](#value_type) sind, das von Typ `pair`\< **const Key, Type**> ist. Dessen erster Member ist der Schlüssel zum Element, und dessen zweiter Member ist das zugeordnete Datum, das vom Element gehalten wird.

Dereferenziert einen `const_reverse_iterator` `crIter` verweist auf ein Element in einer Hash_map, verwenden Sie die **->** Operator.

Verwenden Sie `crIter` -> **first**, das (\*`crIter`) **.first** entspricht, um auf den Wert des Schlüssels für das Element zuzugreifen. Verwenden Sie `crIter` -> **second**, das (\* `crIter`). **first** entspricht, um auf den Wert des zugeordneten Datums für das Element zuzugreifen.

### <a name="example"></a>Beispiel

Im Beispiel für [rend](#rend) wird verdeutlicht, wie `const_reverse_iterator` deklariert und verwendet wird.

## <a name="count"></a> hash_map::count

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt die Anzahl von Elementen in einer hash_map-Klasse zurück, dessen Schlüssel dem von einem Parameter angegebenen Schlüssel entspricht.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parameter

`key` Der Schlüsselwert der aus der Hash_map zu entfernenden Elemente.

### <a name="return-value"></a>Rückgabewert

1, wenn die hash_map-Klasse ein Element enthält, dessen Sortierungsschlüssel dem Parameterschlüssel entspricht; 0, wenn die hash_map-Klasse kein Element mit einem übereinstimmenden Schlüssel enthält.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Anzahl der Elemente *x* im Bereich zurück

(`lower_bound` (_ *Key* ), `upper_bound` (\_ *Key* ))

0 oder 1 für hash_map, was einem eindeutigen assoziativen Container entspricht.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Verwendung der Memberfunktion "hash_map::count" gezeigt.

```cpp
// hash_map_count.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int> hm1;
    hash_map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair (1, 1));
    hm1.insert(Int_Pair (2, 1));
    hm1.insert(Int_Pair (1, 4));
    hm1.insert(Int_Pair (2, 1));

    // Keys must be unique in hash_map, so duplicates are ignored
    i = hm1.count(1);
    cout << "The number of elements in hm1 with a sort key of 1 is: "
         << i << "." << endl;

    i = hm1.count(2);
    cout << "The number of elements in hm1 with a sort key of 2 is: "
         << i << "." << endl;

    i = hm1.count(3);
    cout << "The number of elements in hm1 with a sort key of 3 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in hm1 with a sort key of 1 is: 1.
The number of elements in hm1 with a sort key of 2 is: 1.
The number of elements in hm1 with a sort key of 3 is: 0.
```

## <a name="crbegin"></a> hash_map::crbegin

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt einen const-Iterator zurück, der das erste Element in einer umgekehrten hash_map adressiert.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein umgekehrter bidirektionaler const-Iterator, mit dem das erste Element in einer umgekehrten [hash_map](../standard-library/hash-map-class.md) adressiert wird (bzw. mit dem das ehemals letzte Element in der nicht umgekehrten `hash_map` adressiert wird).

### <a name="remarks"></a>Hinweise

`crbegin` wird bei einer umgekehrten hash_map auf die gleiche Weise verwendet, wie [begin](#begin) bei einer `hash_map` verwendet wird.

Bei dem Rückgabewert von `crbegin` kann das `hash_map`-Objekt nicht geändert werden.

Mit `crbegin` lässt sich eine `hash_map` rückwärts durchlaufen.

### <a name="example"></a>Beispiel

```cpp
// hash_map_crbegin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_crIter = hm1.crbegin( );
   cout << "The first element of the reversed hash_map hm1 is "
        << hm1_crIter -> first << "." << endl;
}
```

```Output
The first element of the reversed hash_map hm1 is 3.
```

## <a name="crend"></a> hash_map::crend

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt einen const-Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer umgekehrten hash_map nachfolgt.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Rückgabewert

Ein bidirektionaler const_reverse-Iterator, der den Standort anspricht, der dem letzten Element in einer umgekehrten[hash_map](../standard-library/hash-map-class.md) nachfolgt (der Speicherort, der dem ersten Element in der nicht umgekehrten `hash_map` vorangegangen war).

### <a name="remarks"></a>Hinweise

`crend` wird bei einer umgekehrten `hash_map` auf die gleiche Weise verwendet, wie [hash_map::end](#end) bei einer `hash_map` verwendet wird.

Bei dem Rückgabewert von `crend` kann das `hash_map`-Objekt nicht geändert werden.

`crend` kann verwendet werden, um zu testen, ob das Ende der `hash_map` von einem umgekehrten Iterator erreicht wurde.

Der von `crend` zurückgegebene Wert darf nicht dereferenziert werden.

### <a name="example"></a>Beispiel

```cpp
// hash_map_crend.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_crIter = hm1.crend( );
   hm1_crIter--;
   cout << "The last element of the reversed hash_map hm1 is "
        << hm1_crIter -> first << "." << endl;
}
```

```Output
The last element of the reversed hash_map hm1 is 3.
```

## <a name="difference_type"></a> hash_map::difference_type

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Ganzzahltyp mit Vorzeichen, der dazu verwendet werden kann, die Anzahl von Elementen einer hash_map in einem Bereich zwischen Elementen darzustellen, auf die von Iteratoren gezeigt wird.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;
```

### <a name="example"></a>Beispiel

```cpp
// hash_map_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <hash_map>
#include <algorithm>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 3, 20 ) );

   // The following won't insert, because map keys are unique
   hm1.insert ( Int_Pair ( 2, 30 ) );

   hash_map <int, int>::iterator hm1_Iter, hm1_bIter, hm1_eIter;
   hm1_bIter = hm1.begin( );
   hm1_eIter = hm1.end( );

   // Count the number of elements in a hash_map
   hash_map <int, int>::difference_type  df_count = 0;
   hm1_Iter = hm1.begin( );
   while ( hm1_Iter != hm1_eIter)
   {
      df_count++;
      hm1_Iter++;
   }

   cout << "The number of elements in the hash_map hm1 is: "
        << df_count << "." << endl;

   cout  << "The keys of the mapped elements are:";
   for ( hm1_Iter= hm1.begin( ) ; hm1_Iter!= hm1.end( ) ;
         hm1_Iter++)
      cout << " " << hm1_Iter-> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( hm1_Iter= hm1.begin( ) ; hm1_Iter!= hm1.end( ) ;
         hm1_Iter++)
      cout << " " << hm1_Iter-> second;
   cout << "." << endl;
}
```

```Output
The number of elements in the hash_map hm1 is: 3.
The keys of the mapped elements are: 1 2 3.
The values of the mapped elements are: 10 20 20.
```

## <a name="emplace"></a> hash_map::emplace

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Fügt ein Element, das vor Ort erstellt wird, in einer hash_map ein.

```cpp
template <class ValTy>
pair <iterator, bool>
emplace(
    ValTy&& val);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`val`|Der Wert verwendet normalerweise ein Bewegungskonstrukt, um ein Element in eine [hash_map](../standard-library/hash-map-class.md) einzufügen, außer die `hash_map` hat bereits das Element (oder, üblicher, ein Element, dessen Schlüssel gleichwertig sortiert wird).|

### <a name="return-value"></a>Rückgabewert

Die erste `emplace`-Memberfunktion gibt ein Paar zurück, dessen boolesche Komponente „TRUE“ zurückgibt, wenn eine Einfügung erfolgte und „FALSE“, wenn `hash_map` bereits ein Element enthielt, dessen Schlüssel einen entsprechenden Wert in der Reihenfolge aufwies und dessen Iteratorkomponente die Adresse zurückgibt, an der ein neues Element eingefügt wurde oder an der das Element bereits gefunden wurde.

Um auf die Iteratorkomponente eines `pr`-Paares zuzugreifen, das von dieser Memberfunktion zurückgegeben wird, verwenden Sie `pr.first` und `*(pr.first)`, um es zu dereferenzieren. Um auf die `bool`-Komponente eines `pr`-Paares zuzugreifen, das von dieser Memberfunktion zurückgegeben wird, verwenden Sie `pr.second` und `*(pr.second)`, um es zu dereferenzieren.

### <a name="remarks"></a>Hinweise

Der [hash_map::value_type](#value_type) eines Elements wird paarweise angegeben, sodass der Wert eines Elements ein geordnetes Paar ist, bei dem die erste Komponente gleich dem Schlüsselwert und die zweite Komponente gleich dem Datenwert des Elements ist.

### <a name="example"></a>Beispiel

```cpp
// hash_map_emplace.cpp
// compile with: /EHsc
#include<hash_map>
#include<iostream>
#include <string>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, string> hm1;
    typedef pair<int, string> is1(1, "a");

    hm1.emplace(move(is1));
    cout << "After the emplace insertion, hm1 contains:" << endl
      << " " << hm1.begin()->first
      << " => " << hm1.begin()->second
      << endl;
}
```

```Output
After the emplace insertion, hm1 contains:
 1 => a
```

## <a name="emplace_hint"></a> hash_map::emplace_hint

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Fügt ein Element ein, das vor Ort mit einem Platzierungshinweis in einer hash_map erstellt wird.

```cpp
template <class ValTy>
iterator emplace_hint(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`val`|Der Wert verwendet normalerweise ein Bewegungskonstrukt, um ein Element in eine [hash_map](../standard-library/hash-map-class.md) einzufügen, außer die `hash_map` hat bereits das Element (oder, üblicher, ein Element, dessen Schlüssel gleichwertig sortiert wird).|
|`_Where`|Ein Hinweis bezüglich des Platzes, an dem mit der Suche nach dem richtigen Einfügepunkt begonnen wird.|

### <a name="return-value"></a>Rückgabewert

Die [hash_multimap::emplace](../standard-library/hash-multimap-class.md#emplace) Memberfunktion gibt einen Iterator zurück, der auf die Position zeigt, an der das neue Element in die `hash_map` eingefügt wurde, oder, in dem sich das vorhandene Element mit entsprechender Sortierung befindet.

### <a name="remarks"></a>Hinweise

Der [hash_map::value_type](#value_type) eines Elements wird paarweise angegeben, sodass der Wert eines Elements ein geordnetes Paar ist, bei dem die erste Komponente gleich dem Schlüsselwert und die zweite Komponente gleich dem Datenwert des Elements ist.

Das Einfügen kann in amortisierter konstanter Zeit anstelle von logarithmischer Zeit erfolgen, wenn die Einfügemarke direkt auf `_Where` folgt.

### <a name="example"></a>Beispiel

```cpp
// hash_map_emplace_hint.cpp
// compile with: /EHsc
#include<hash_map>
#include<iostream>
#include <string>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, string> hm1;
    typedef pair<int, string> is1(1, "a");

    hm1.emplace(hm1.begin(), move(is1));
    cout << "After the emplace, hm1 contains:" << endl
      << " " << hm1.begin()->first
      << " => " << hm1.begin()->second
      << endl;
}
```

```Output
After the emplace insertion, hm1 contains:
 1 => a
```

## <a name="empty"></a> hash_map::empty

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Testet, ob ein hash_map-Element leer ist.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das hash_map-Element leer ist; **FALSE**, wenn es nicht leer ist.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

```cpp
// hash_map_empty.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2;

   typedef pair <int, int> Int_Pair;
   hm1.insert ( Int_Pair ( 1, 1 ) );

   if ( hm1.empty( ) )
      cout << "The hash_map hm1 is empty." << endl;
   else
      cout << "The hash_map hm1 is not empty." << endl;

   if ( hm2.empty( ) )
      cout << "The hash_map hm2 is empty." << endl;
   else
      cout << "The hash_map hm2 is not empty." << endl;
}
```

```Output
The hash_map hm1 is not empty.
The hash_map hm2 is empty.
```

## <a name="end"></a> hash_map::end

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt einen Iterator zurück, der den Speicherort adressiert, der auf das letzte Element einer hash_map folgt.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Rückgabewert

Ein bidirektionaler Iterator, der den Speicherort adressiert, der dem letzten Element einer hash_map nachfolgt. Wenn die hash_map leer ist, folgt anschließend „hash_map::end == hash_map::begin“.

### <a name="remarks"></a>Hinweise

**end** wird verwendet, um zu testen, ob ein Iterator das Ende seiner hash_map erreicht hat.

Der von **end** zurückgegebene Wert darf nicht dereferenziert werden.

### <a name="example"></a>Beispiel

```cpp
// hash_map_end.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: iterator hm1_Iter;
   hash_map <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_cIter = hm1.end( );
   hm1_cIter--;
   cout << "The value of last element of hm1 is "
        << hm1_cIter -> second << "." << endl;

   hm1_Iter = hm1.end( );
   hm1_Iter--;
   hm1.erase ( hm1_Iter );

   // The following 2 lines would err because the iterator is const
   // hm1_cIter = hm1.end ( );
   // hm1_cIter--;
   // hm1.erase ( hm1_cIter );

   hm1_cIter = hm1.end( );
   hm1_cIter--;
   cout << "The value of last element of hm1 is now "
        << hm1_cIter -> second << "." << endl;
}
```

```Output
The value of last element of hm1 is 30.
The value of last element of hm1 is now 20.
```

## <a name="equal_range"></a> hash_map::equal_range

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt ein Iteratorpaar jeweils zum ersten Element in einer hash_map mit einem Schlüssel zurück, der größer als ein angegebener Schlüssel ist, bzw. zum ersten Element in einer hash_map mit einem Schlüssel, der größer oder gleich dem Schlüssel ist.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parameter

`key` Das Argument angegebene Schlüsselwert mit dem Sortierschlüssel eines Elements aus der Hash_map zu durchsuchenden verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Iteratorenpaar, bei dem der erste Iterator der [lower_bound](#lower_bound) des Schlüssels und der zweite Iterator der [upper_bound](#upper_bound) des Schlüssels ist.

Sie können auf den ersten Iterator eines von einer Memberfunktion zurückgegebenen Paars `pr` zugreifen, indem Sie `pr`. **first** verwenden, und Sie können einen lower_bound-Iterator dereferenzieren, indem Sie \*( `pr`. **first**) verwenden. Sie können auf den zweiten Iterator eines von einer Memberfunktion zurückgegebenen Paars `pr` zugreifen, indem Sie `pr`. **second** verwenden, und Sie können einen upper_bound-Iterator dereferenzieren, indem Sie \*( `pr`. **second**) verwenden.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

```cpp
// hash_map_equal_range.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef hash_map <int, int> IntMap;
   IntMap hm1;
   hash_map <int, int> :: const_iterator hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   pair <IntMap::const_iterator, IntMap::const_iterator> p1, p2;
   p1 = hm1.equal_range( 2 );

   cout << "The lower bound of the element with "
        << "a key of 2 in the hash_map hm1 is: "
        << p1.first -> second << "." << endl;

   cout << "The upper bound of the element with "
        << "a key of 2 in the hash_map hm1 is: "
        << p1.second -> second << "." << endl;

   // Compare the upper_bound called directly
   hm1_RcIter = hm1.upper_bound( 2 );

   cout << "A direct call of upper_bound( 2 ) gives "
        << hm1_RcIter -> second << "," << endl
        << " matching the 2nd element of the pair"
        << " returned by equal_range( 2 )." << endl;

   p2 = hm1.equal_range( 4 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == hm1.end( ) ) && ( p2.second == hm1.end( ) ) )
      cout << "The hash_map hm1 doesn't have an element "
             << "with a key less than 40." << endl;
   else
      cout << "The element of hash_map hm1 with a key >= 40 is: "
           << p1.first -> first << "." << endl;
}
```

```Output
The lower bound of the element with a key of 2 in the hash_map hm1 is: 20.
The upper bound of the element with a key of 2 in the hash_map hm1 is: 30.
A direct call of upper_bound( 2 ) gives 30,
 matching the 2nd element of the pair returned by equal_range( 2 ).
The hash_map hm1 doesn't have an element with a key less than 40.
```

## <a name="erase"></a> hash_map::erase

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Es wird ein Element oder ein Bereich von Elementen in einer hash_map von angegebenen Speicherorten entfernt oder es werden die einem angegebenen Schlüssel entsprechenden Elemente entfernt.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Parameter

`_Where` Die Position des Elements aus der Hash_map entfernt werden soll.

`first` Die Position des ersten Elements aus der Hash_map entfernt.

`last` Die Position direkt hinter dem letzten Element aus der Hash_map entfernt.

`key` Der Schlüsselwert der aus der Hash_map zu entfernenden Elemente.

### <a name="return-value"></a>Rückgabewert

Bei den ersten beiden Memberfunktionen ist es ein bidirektionaler Iterator, der das erste über die entfernten Elemente hinaus verbliebene Element festlegt, oder ein Zeiger auf das das Ende der hash_map, wenn kein solches Element vorhanden ist.

Für die dritte Memberfunktion wird die Anzahl der von der hash_map entfernten Elemente zurückgegeben.

### <a name="remarks"></a>Hinweise

Von der Memberfunktionen wird nie eine Ausnahme ausgelöst.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Verwendung der Memberfunktion "hash_map::erase" gezeigt.

```cpp
// hash_map_erase.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int> hm1, hm2, hm3;
    hash_map<int, int> :: iterator pIter, Iter1, Iter2;
    int i;
    hash_map<int, int>::size_type n;
    typedef pair<int, int> Int_Pair;

    for (i = 1; i < 5; i++)
    {
        hm1.insert(Int_Pair (i, i));
        hm2.insert(Int_Pair (i, i*i));
        hm3.insert(Int_Pair (i, i-1));
    }

    // The 1st member function removes an element at a given position
    Iter1 = ++hm1.begin();
    hm1.erase(Iter1);

    cout << "After the 2nd element is deleted, the hash_map hm1 is:";
    for (pIter = hm1.begin(); pIter != hm1.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 2nd member function removes elements
    // in the range [ first,  last)
    Iter1 = ++hm2.begin();
    Iter2 = --hm2.end();
    hm2.erase(Iter1, Iter2);

    cout << "After the middle two elements are deleted, "
         << "the hash_map hm2 is:";
    for (pIter = hm2.begin(); pIter != hm2.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 3rd member function removes elements with a given  key
    n = hm3.erase(2);

    cout << "After the element with a key of 2 is deleted,\n"
         << "the hash_map hm3 is:";
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 3rd member function returns the number of elements removed
    cout << "The number of elements removed from hm3 is: "
         << n << "." << endl;

    // The dereferenced iterator can also be used to specify a key
    Iter1 = ++hm3.begin();
    hm3.erase(Iter1);

    cout << "After another element with a key equal to that"
         << endl;
    cout  << "of the 2nd element is deleted, "
          << "the hash_map hm3 is:";
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;
}
```

```Output
After the 2nd element is deleted, the hash_map hm1 is: 1 3 4.
After the middle two elements are deleted, the hash_map hm2 is: 1 16.
After the element with a key of 2 is deleted,
the hash_map hm3 is: 0 2 3.
The number of elements removed from hm3 is: 1.
After another element with a key equal to that
of the 2nd element is deleted, the hash_map hm3 is: 0 3.
```

## <a name="find"></a> hash_map::find

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt einen Iterator zurück, der die Position eines Elements in einer hash_map adressiert, das einen Schlüssel aufweist, der einem angegebenen Schlüssel entspricht.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parameter

`key` Der Schlüsselwert, der mit dem Sortierschlüssel eines Elements aus der Hash_map zu durchsuchenden übereinstimmt.

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der den Speicherort eines Elements mit einem angegebenen Schlüssel adressiert, oder den Speicherort, der dem letzten Element in der hash_map nachfolgt, wenn keine Übereinstimmung für den Schlüssel gefunden wird.

### <a name="remarks"></a>Hinweise

**find** gibt einen Iterator zurück, der ein Element in der hash_map adressiert, dessen Sortierschlüssel dem Argumentschlüssel unter einem binären Prädikat entspricht, das eine Reihenfolge basierend auf der Beziehung „Less than comparability“ auslöst.

Wenn der Rückgabewert von**find** [const_iterator](#const_iterator) zugewiesen wird, kann das hash_map-Objekt nicht geändert werden. Wenn der Rückgabewert von **find** einem [Iterator](#iterator) zugewiesen wird, kann die hash_map geändert werden

### <a name="example"></a>Beispiel

```cpp
// hash_map_find.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   hash_map <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_RcIter = hm1.find( 2 );
   cout << "The element of hash_map hm1 with a key of 2 is: "
        << hm1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   hm1_RcIter = hm1.find( 4 );

   if ( hm1_RcIter == hm1.end( ) )
      cout << "The hash_map hm1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of hash_map hm1 with a key of 4 is: "
           << hm1_RcIter -> second << "." << endl;

   // The element at a specific location in the hash_map can be found
   // using a dereferenced iterator addressing the location
   hm1_AcIter = hm1.end( );
   hm1_AcIter--;
   hm1_RcIter = hm1.find( hm1_AcIter -> first );
   cout << "The element of hm1 with a key matching "
        << "that of the last element is: "
        << hm1_RcIter -> second << "." << endl;
}
```

```Output
The element of hash_map hm1 with a key of 2 is: 20.
The hash_map hm1 doesn't have an element with a key of 4.
The element of hm1 with a key matching that of the last element is: 30.
```

## <a name="get_allocator"></a> hash_map::get_allocator

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt eine Kopie des Zuweisungsobjekts zurück, das zum Erstellen der hash_map verwendet wird.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Rückgabewert

Die von der hash_map verwendete Zuweisung.

### <a name="remarks"></a>Hinweise

Zuweisungen für die hash_map-Klasse geben an, wie die Klasse einen Speicher verwaltet. Für die meisten Programmieranforderungen reichen die Standardzuweisungen mit C++-Standardbibliothek-Container-Klassen aus. Schreiben und Verwenden Ihrer eigener Zuweisungsklasse ist ein C++ -Thema für Fortgeschrittene.

### <a name="example"></a>Beispiel

```cpp
// hash_map_get_allocator.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int>::allocator_type hm1_Alloc;
   hash_map <int, int>::allocator_type hm2_Alloc;
   hash_map <int, double>::allocator_type hm3_Alloc;
   hash_map <int, int>::allocator_type hm4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   hash_map <int, int> hm1;
   hash_map <int, int> hm2;
   hash_map <int, double> hm3;

   hm1_Alloc = hm1.get_allocator( );
   hm2_Alloc = hm2.get_allocator( );
   hm3_Alloc = hm3.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << hm2.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << hm3.max_size( ) <<  "." << endl;

   // The following line creates a hash_map hm4
   // with the allocator of hash_map hm1.
   hash_map <int, int> hm4( less<int>( ), hm1_Alloc );

   hm4_Alloc = hm4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated with the other
   if( hm1_Alloc == hm4_Alloc )
   {
      cout << "The allocators are interchangeable."
           << endl;
   }
   else
   {
      cout << "The allocators are not interchangeable."
           << endl;
   }
}
```

## <a name="hash_map"></a> hash_map::hash_map

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Erstellt ein hash_map-Element, das leer oder eine Kopie eines anderen vollständigen hash_map-Elements oder eines Teils davon ist.

```cpp
hash_map();

explicit hash_map(
    const Traits& Comp);

hash_map(
    const Traits& Comp,
    const Allocator& Al);

hash_map(
    const hash_map& Right);

hash_map(
    hash_map&& Right);

hash_map(
    initializer_list<Type> IList);hash_map(initializer_list<Type> IList,
    const key_compare& Comp);

hash_map(
    initializer_list<Type> IList,
    const key_compare& Comp,
    const allocator_type& Al);

template <class InputIterator>
hash_map(
 InputIterator First,
    InputIterator Last);

template <class InputIterator>
hash_map(
 InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
hash_map(
 InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`Al`|Die für dieses hash_map-Objekt zu verwendende Speicherreservierungsklasse, deren Standard **Allocator** ist.|
|`Comp`|Die Vergleichsfunktion des Typs const-`Traits`, die verwendet wird, um Elemente im hash_map-Element zu sortieren, dessen Standard `hash_compare` ist.|
|`Right`|Das hash_map-Element , dessen Kopie die erstellte Zuordnung sein soll.|
|`First`|Die Position des ersten Elements in dem zu kopierenden Elementbereich.|
|`Last`|Die Position des ersten Elements nach dem zu kopierenden Elementbereich.|
|`IList`|Das initializer_list-Element.|

### <a name="remarks"></a>Hinweise

In allen Konstruktoren wird ein Zuweisungsobjekttyp gespeichert, mit dem der Arbeitsspeicher für das hash_map-Element verwaltet wird, und das später zurückgegeben werden kann, indem [get_allocator](#get_allocator) aufgerufen wird. Der Zuweisungsparameter wird häufig aus den Klassendeklarationen und den Vorverarbeitungsmakros weggelassen, die zum Ersetzen alternativer Zuweisungen verwendet werden.

Alle Konstruktoren initialisieren das hash_map-Element.

In allen Konstruktoren wird ein Funktionsobjekt vom Typ `Traits` gespeichert, der verwendet wird, um unter den Schlüsseln des hash_map-Elements eine Sortierung vorzunehmen, und das später zurückgegeben werden kann, indem [key_comp](#key_comp) aufgerufen wird.

Die ersten drei Konstruktoren legen ein leeres erstes hash_map-Element fest. Zusätzlich gibt der zweite den Typ der Vergleichsfunktion (`Comp`) an, die zum Angeben der Reihenfolge der Elemente verwendet wird, und der Dritte gibt explizit den zu verwendenden Zuweisungstyp (`Al`) an. Mit dem Schlüsselwort `explicit` werden bestimmte Arten automatischer Typumwandlung unterdrückt.

Der vierte Konstruktor gibt eine Kopie des `Right`-hash_map-Elements an.

Mit den nächsten drei Konstruktoren wird der `[First, Last)`-Bereich eines hash_map-Elements kopiert, wobei sich die Explizitheit bei Angabe des Typs der Vergleichsfunktion der Klasse `Traits` und "Allocator" erhöht.

Der letzte Konstruktor verschiebt das `Right`-hash_map-Element.

## <a name="insert"></a> hash_map::insert

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Fügt ein Element oder einen Elementbereich in ein hash_map-Element ein.

```cpp
pair <iterator, bool> insert(
    const value_type& val);

iterator insert(
    const_iterator _Where,
    const value_type& val);

template <class InputIterator>
void insert(
    InputIterator first,
    InputIterator last);

template <class ValTy>
pair <iterator, bool>
insert(
    ValTy&& val);

template <class ValTy>
iterator insert(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`val`|Der Wert eines in das hash_map-Element einzufügenden Elements, es sei denn, das hash_map-Element enthält dieses Element bereits (oder, allgemeiner gesagt, enthält ein Element, dessen Schlüssel gleichwertig sortiert wird).|
|`_Where`|Ein Hinweis bezüglich des Platzes, an dem mit der Suche nach dem richtigen Einfügepunkt begonnen wird.|
|`first`|Die Position des ersten Elements, das aus einem hash_map-Element kopiert werden soll.|
|`last`|Die Position direkt hinter dem letzten Element, das aus einem hash_map-Element kopiert werden soll.|

### <a name="return-value"></a>Rückgabewert

Die erste **insert**-Memberfunktion gibt ein Paar zurück, dessen boolesche Komponente „TRUE“ zurückgibt, wenn eine Einfügung vorgenommen wurde, und „FALSE“, wenn die hash_map bereits ein Element enthielt, dessen Schlüssel einen entsprechenden Wert in der Reihenfolge aufweist und dessen Iteratorkomponente die Adresse zurückgibt, an der ein neues Element eingefügt wurde oder an der das Element bereits gefunden wurde.

Auf die iteratorkomponente eines Paars `pr` von dieser Memberfunktion zurückgegeben wird, verwenden Sie `pr`. **erste**, und verwenden, um es zu dereferenzieren, \*( `pr`. **first**) verwenden. Um auf die `bool`-Komponente eines `pr`-Paares zuzugreifen, das von dieser Memberfunktion zurückgegeben wird, verwenden Sie `pr`. **zweite**, und verwenden, um es zu dereferenzieren, \*( `pr`. **second**) verwenden.

Die zweite **insert**-Memberfunktion, die Hinweisversion, gibt einen Iterator zurück, der auf den Speicherort zeigt, an dem das neue Element in die hash_map eingefügt wurde.

Die letzten zwei **insert**-Memberfunktionen verhalten sich identisch zu den ersten beiden, außer dass der eingefügte Wert durch Verschiebung erstellt wird.

### <a name="remarks"></a>Hinweise

Der [value_type](../standard-library/map-class.md#value_type) eines Elements wird paarweise angegeben, sodass der Wert eines Elements ein geordnetes Paar ist, bei dem die erste Komponente gleich dem Schlüsselwert und die zweite Komponente gleich dem Datenwert des Elements ist.

Einfügung kann in amortisierter konstanter Zeit anstelle von logarithmischer Zeit für die Hinweisversion von "insert" erfolgen, wenn die Einfügemarke `_Where` direkt folgt.

Die dritte Memberfunktion fügt die Sequenz von Elementwerten in ein hash_map-Element jedem Element entsprechend ein, das von einem Iterator im Bereich *[First, Last]* einer bestimmten Gruppe adressiert wird.

### <a name="example"></a>Beispiel

```cpp
// hash_map_insert.cpp
// compile with: /EHsc
#include<hash_map>
#include<iostream>
#include <string>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int>::iterator hm1_pIter, hm2_pIter;

    hash_map<int, int> hm1, hm2;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 10));
    hm1.insert(Int_Pair(2, 20));
    hm1.insert(Int_Pair(3, 30));
    hm1.insert(Int_Pair(4, 40));

    cout<< "The original elements (Key => Value) of hm1 are:";
    for (hm1_pIter = hm1.begin(); hm1_pIter != hm1.end(); hm1_pIter++)
        cout << endl << " " << hm1_pIter -> first << " => "
             << hm1_pIter->second;
    cout << endl;

    pair< hash_map<int,int>::iterator, bool > pr;
    pr = hm1.insert(Int_Pair(1, 10));

    if (pr.second == true)
    {
        cout<< "The element 10 was inserted in hm1 successfully."
            << endl;
    }
    else
    {
        cout<< "The element 10 already exists in hm1\n with a key value of"
            << "((pr.first) -> first)= "<<(pr.first)-> first
            << "."<< endl;
    }

    // The hint version of insert
    hm1.insert(--hm1.end(), Int_Pair(5, 50));

    cout<< "After the insertions, the elements of hm1 are:";
    for (hm1_pIter = hm1.begin(); hm1_pIter != hm1.end(); hm1_pIter++)
        cout << endl << " " << hm1_pIter -> first << " => "
             << hm1_pIter->second;
    cout << endl;

    hm2.insert(Int_Pair(10, 100));

    // The templatized version inserting a range
    hm2.insert( ++hm1.begin(), --hm1.end() );

    cout<< "After the insertions, the elements of hm2 are:";
    for (hm2_pIter = hm2.begin(); hm2_pIter != hm2.end(); hm2_pIter++)
        cout << endl << " " << hm2_pIter -> first << " => "
             << hm2_pIter->second;
    cout << endl;

    // The templatized versions move constructing elements
    hash_map<int, string> hm3, hm4;
    pair<int, string> is1(1, "a"), is2(2, "b");

    hm3.insert(move(is1));
    cout << "After the move insertion, hm3 contains:" << endl
      << " " << hm3.begin()->first
      << " => " << hm3.begin()->second
      << endl;

    hm4.insert(hm4.begin(), move(is2));
    cout << "After the move insertion, hm4 contains:" << endl
      << " " << hm4.begin()->first
      << " => " << hm4.begin()->second
      << endl;
}
```

```Output
The original elements (Key => Value) of hm1 are:
 1 => 10
 2 => 20
 3 => 30
 4 => 40
The element 10 already exists in hm1
 with a key value of((pr.first) -> first)= 1.
After the insertions, the elements of hm1 are:
 1 => 10
 2 => 20
 3 => 30
 4 => 40
 5 => 50
After the insertions, the elements of hm2 are:
 2 => 20
 10 => 100
 3 => 30
 4 => 40
After the move insertion, hm3 contains:
 1 => a
After the move insertion, hm4 contains:
 2 => b
```

## <a name="iterator"></a> hash_map::iterator

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem jedes Element in einer hash_map gelesen oder geändert werden kann.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Hinweise

Der **Iterator**, der durch hash_map definiert wird, zeigt auf Elemente, die Objekte eines [value_type](#value_type) sind, das vom Typ **pair\<const Key, Type> ist,** , dessen erster Member ist der Schlüssel zum Element, und dessen zweiter Member ist das zugeordnete Datum, das vom Element gehalten wird.

Verwenden Sie den Operator **->**, um einen **iterator**`Iter`-Typ zu dereferenzieren, der auf ein Element in einer Mehrfachzuordnung zeigt.

Verwenden Sie `Iter` -> **first**, das (\* `Iter`). **first** entspricht, um auf den Wert des Schlüssels für das Element zuzugreifen. Verwenden Sie `Iter` -> **second**, das (\* `Iter`). **second** entspricht, um auf den Wert des zugeordneten Datums für das Element zuzugreifen.

Ein **iterator**-Typ kann zum Ändern des Werts eines Elements verwendet werden.

### <a name="example"></a>Beispiel

Im Beispiel für [begin](#begin) wird verdeutlicht, wie ein **Iterator** deklariert und verwendet wird.

## <a name="key_comp"></a> hash_map::key_comp

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ruft eine Kopie des Vergleichsobjekts ab, das zum Sortieren der Schlüssel in einer hash_map verwendet wird.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt das Funktionsobjekt zurück, das ein hash_map-Element zum Sortieren seiner Elemente verwendet.

### <a name="remarks"></a>Hinweise

Das gespeicherte Objekt definiert die Memberfunktion

**bool operator**( **const Key&** `left`**, const Key&** `right`);

die **TRUE** zurückgibt, wenn `left` vorangestellt ist und nicht gleich `right` in der Sortierreihenfolge ist.

### <a name="example"></a>Beispiel

```cpp
// hash_map_key_comp.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_map <int, int, hash_compare<int, less<int> > > hm1;
   hash_map <int, int, hash_compare<int, less<int> > >::key_compare
      kc1 = hm1.key_comp( ) ;

   // Operator stored in kc1 tests order & returns bool value
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true,"
           << "\n where kc1 is the function object of hm1"
           << " of type key_compare." << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false"
           << "\n where kc1 is the function object of hm1"
           << " of type key_compare." << endl;
   }

   hash_map <int, int, hash_compare<int, greater<int> > > hm2;
   hash_map <int, int, hash_compare<int, greater<int> > >
      ::key_compare kc2 = hm2.key_comp( );

   // Operator stored in kc2 tests order & returns bool value
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true,"
           << "\n where kc2 is the function object of hm2"
           << " of type key_compare." << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false,"
           << "\n where kc2 is the function object of hm2"
           << " of type key_compare." << endl;
   }
}
```

## <a name="key_compare"></a> hash_map::key_compare

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Eine Typ, der ein Funktionsobjekt bereitstellt, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen in der hash_map zu bestimmen.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Hinweise

`key_compare` ist ein Synonym für den Vorlagenparameter `Traits`.

Weitere Informationen zu `Traits` finden Sie im Thema [hash_map-Klasse](../standard-library/hash-map-class.md).

### <a name="example"></a>Beispiel

Im Beispiel für [key_comp](#key_comp) wird verdeutlicht, wie ein `key_compare` deklariert und verwendet wird.

## <a name="key_type"></a> hash_map::key_type

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Typ beschreibt das Sortierschlüsselobjekt, das jedes Element der hash_map bildet.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Hinweise

`key_type` ist ein Synonym für den Vorlagenparameter `Key`.

Weitere Informationen zu `Key` finden Sie im Abschnitt „Hinweise“ des Themas [hash_map-Klasse](../standard-library/hash-map-class.md).

### <a name="example"></a>Beispiel

Im Beispiel für [value_type](#value_type) wird verdeutlicht, wie ein `key_type` deklariert und verwendet wird.

## <a name="lower_bound"></a> hash_map::lower_bound

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt einen Iterator zum ersten Element in einer hash_map mit einem Schlüsselwert zurück, der gleich oder größer ist, als ein angegebener Schlüssel.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Parameter

`key` Das Argument angegebene Schlüsselwert mit dem Sortierschlüssel eines Elements aus der Hash_map zu durchsuchenden verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein [Iterator](#iterator) oder [const_iterator](#const_iterator), der den Speicherort eines Elements in einem hash_map-Element mit einem Schlüssel adressiert, der gleich oder größer als der Argumentschlüssel ist, oder der den Speicherort des folgenden letzten Elements in der hash_map adressiert, wenn kein Treffer für den Schlüssen gefunden wird.

Wenn dem Rückgabewert `lower_bound` `const_iterator` zugewiesen wird, kann das hash_map-Objekt nicht geändert werden. Wenn dem Rückgabewert `lower_bound` einem **iterator** zugewiesen wird, kann das hash_map-Objekt geändert werden.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

```cpp
// hash_map_lower_bound.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   hash_map <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_RcIter = hm1.lower_bound( 2 );
   cout << "The first element of hash_map hm1 with a key of 2 is: "
        << hm1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   hm1_RcIter = hm1. lower_bound ( 4 );

   if ( hm1_RcIter == hm1.end( ) )
      cout << "The hash_map hm1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of hash_map hm1 with a key of 4 is: "
           << hm1_RcIter -> second << "." << endl;

   // An element at a specific location in the hash_map can be
   // found using a dereferenced iterator addressing the location
   hm1_AcIter = hm1.end( );
   hm1_AcIter--;
   hm1_RcIter = hm1. lower_bound ( hm1_AcIter -> first );
   cout << "The element of hm1 with a key matching "
        << "that of the last element is: "
        << hm1_RcIter -> second << "." << endl;
}
```

```Output
The first element of hash_map hm1 with a key of 2 is: 20.
The hash_map hm1 doesn't have an element with a key of 4.
The element of hm1 with a key matching that of the last element is: 30.
```

## <a name="mapped_type"></a> hash_map::mapped_type

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Typ, der den in einer hash_map gespeicherten Datentyp darstellt.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Hinweise

Der Typ `mapped_type` stellt ein Synonym für den Vorlagenparameter `Type` dar.

Weitere Informationen zu `Type` finden Sie im Thema [hash_map-Klasse](../standard-library/hash-map-class.md).

### <a name="example"></a>Beispiel

Im Beispiel für [value_type](#value_type) wird verdeutlicht, wie ein `key_type` deklariert und verwendet wird.

## <a name="max_size"></a> hash_map::max_size

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt die Maximallänge der hash_map zurück.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Rückgabewert

Die mögliche Maximallänge der hash_map.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

```cpp
// hash_map_max_size.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   hash_map <int, int> :: size_type i;

   i = hm1.max_size( );
   cout << "The maximum possible length "
        << "of the hash_map is " << i << "."
        << endl << "(Magnitude is machine specific.)";
}
```

## <a name="op_at"></a> hash_map::operator[]

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Fügt ein Element in ein `hash_map`-Element mit einem angegebenen Schlüsselwert ein.

```cpp
Type& operator[](const Key& key);

Type& operator[](Key&& key);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`key`|Der Schlüsselwert des einzufügenden Elements.|

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf den Datenwert des eingefügten Elements.

### <a name="remarks"></a>Hinweise

Wenn der Argumentschlüsselwert nicht gefunden wird, wird er zusammen mit dem Standardwert des Datentyps eingefügt.

`operator[]` kann auch zum Einfügen von Elementen in einem `hash_map m` verwendet werden, unter Verwendung von

`m[ key] = DataValue`;

dort wo der DataValue der Wert des `mapped_type` des Elements mit einem Schlüsselwert von `key` ist.

Wenn `operator[]` zum Einfügen von Elementen verwendet wird, gibt der zurückgegebene Verweis nicht an, ob eine Einfügung ein bereits vorhandenes Element ändert oder ein neues erstellt. Die Memberfunktionen [find](../standard-library/map-class.md#find) und [insert](../standard-library/map-class.md#insert) können verwendet werden, um zu bestimmen, ob ein Element mit einem bestimmten Schlüssel vor einer Einfügung bereits vorhanden ist.

### <a name="example"></a>Beispiel

```cpp
// hash_map_op_ref.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef pair <const int, int> cInt2Int;
   hash_map <int, int> hm1;
   hash_map <int, int> :: iterator pIter;

   // Insert a data value of 10 with a key of 1
   // into a hash_map using the operator[] member function
   hm1[ 1 ] = 10;

   // Compare other ways to insert objects into a hash_map
   hm1.insert ( hash_map <int, int> :: value_type ( 2, 20 ) );
   hm1.insert ( cInt2Int ( 3, 30 ) );

   cout  << "The keys of the mapped elements are:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;

   // If the key already exists, operator[]
   // changes the value of the datum in the element
   hm1[ 2 ] = 40;

   // operator[] will also insert the value of the data
   // type's default constructor if the value is unspecified
   hm1[5];

   cout  << "The keys of the mapped elements are now:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are now:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;

   // opperator[] will also insert by moving a key
   hash_map <string, int> hm2;
   string str("a");
   hm2[move(str)] = 1;
   cout << "The moved key is " << hm2.begin()->first
      << ", with value " << hm2.begin()->second << endl;
}
```

## <a name="op_eq"></a> hash_map::operator=

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ersetzt die Elemente der hash_map durch eine Kopie einer anderen hash_map.

```cpp
hash_map& operator=(const hash_map& right);

hash_map& operator=(hash_map&& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`right`|Die [hash_map-Klasse](../standard-library/hash-map-class.md), die in die `hash_map` kopiert wird.|

### <a name="remarks"></a>Hinweise

Nachdem ein vorhandenes Element in einem `hash_map` gelöscht wurde, kopiert oder verschiebt `operator=` den Inhalt von `right` in den `hash_map`.

### <a name="example"></a>Beispiel

```cpp
// hash_map_operator_as.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map<int, int> v1, v2, v3;
   hash_map<int, int>::iterator iter;

   v1.insert(pair<int, int>(1, 10));

   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << iter->second << " ";
   cout << endl;

   v2 = v1;
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter->second << " ";
   cout << endl;

// move v1 into v2
   v2.clear();
   v2 = move(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter->second << " ";
   cout << endl;
}
```

## <a name="pointer"></a> hash_map::pointer

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Typ, der einen Zeiger auf ein Element in einer hash_map bereitstellt.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Hinweise

Ein **pointer**-Typ kann zum Ändern des Werts eines Elements verwendet werden.

In den meisten Fällen sollte ein [iterator](#iterator) für den Zugriff auf Elemente in einem Listenobjekt verwendet werden.

## <a name="rbegin"></a> hash_map::rbegin

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt einen Iterator zurück, der das erste Element in einer umgekehrten hash_map adressiert.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Rückgabewert

Ein umgekehrter bidirektionaler const-Iterator, mit dem das erste Element in einer umgekehrten hash_map adressiert wird bzw. mit dem das ehemals letzte Element in der nicht umgekehrten hash_map adressiert wird.

### <a name="remarks"></a>Hinweise

`rbegin` wird bei einer umgekehrten hash_map auf die gleiche Weise wie [begin](#begin) mit einer hash_map verwendet.

Wenn der Rückgabewert von `rbegin` einem [const_reverse_iterator](#const_reverse_iterator) zugewiesen wird, kann das hash_map-Objekt anschließend nicht geändert werden. Wenn der Rückgabewert von `rbegin` einem [reverse_iterator](#reverse_iterator) zugewiesen wird, kann das hash_map-Objekt anschließend geändert werden.

`rbegin` kann verwendet werden, um eine hash_map rückwärts zu durchlaufen.

### <a name="example"></a>Beispiel

```cpp
// hash_map_rbegin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: iterator hm1_Iter;
   hash_map <int, int> :: reverse_iterator hm1_rIter;
   hash_map <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_rIter = hm1.rbegin( );
   cout << "The first element of the reversed hash_map hm1 is "
        << hm1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a hash_map in a forward order
   cout << "The hash_map is: ";
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( ); hm1_Iter++)
      cout << hm1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a hash_map in a reverse order
   cout << "The reversed hash_map is: ";
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( ); hm1_rIter++)
      cout << hm1_rIter -> first << " ";
      cout << "." << endl;

   // A hash_map element can be erased by dereferencing to its key
   hm1_rIter = hm1.rbegin( );
   hm1.erase ( hm1_rIter -> first );

   hm1_rIter = hm1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed hash_map is "
        << hm1_rIter -> first << "." << endl;
}
```

```Output
The first element of the reversed hash_map hm1 is 3.
The hash_map is: 1 2 3 .
The reversed hash_map is: 3 2 1 .
After the erasure, the first element in the reversed hash_map is 2.
```

## <a name="reference"></a> hash_map::reference

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Typ, der einen Verweis auf einer hash_map gespeichertes Element bereitstellt.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::reference reference;
```

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

```cpp
// hash_map_reference.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( hm1.begin( ) -> first );

   // The following line would cause an error as the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( hm1.begin( ) -> first );

   cout << "The key of first element in the hash_map is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( hm1.begin( ) -> second );

   cout << "The data value of first element in the hash_map is "
        << Ref2 << "." << endl;

   // The non-const_reference can be used to modify the
   // data value of the first element
   Ref2 = Ref2 + 5;
   cout << "The modified data value of first element is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the hash_map is 1.
The data value of first element in the hash_map is 10.
The modified data value of first element is 15.
```

## <a name="rend"></a> hash_map::rend

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer umgekehrten hash_map nachfolgt.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Rückgabewert

Ein umgekehrter bidirektionaler Iterator, der den Standort anspricht, der dem letzten Element in einer umgekehrten hash_map nachfolgt (der Speicherort, der dem ersten Element in der nicht umgekehrten hash_map vorangegangen war).

### <a name="remarks"></a>Hinweise

`rend` wird bei einer umgekehrten hash_map auf die gleiche Weise wie [end](#end) mit einer hash_map verwendet.

Wenn der Rückgabewert von `rend` einem [const_reverse_iterator](#const_reverse_iterator) zugewiesen wird, kann das hash_map-Objekt anschließend nicht geändert werden. Wenn der Rückgabewert von `rend` einem [reverse_iterator](#reverse_iterator) zugewiesen wird, kann das hash_map-Objekt anschließend geändert werden.

`rend` kann verwendet werden, um zu testen, ob ein umgekehrter Iterator das Ende seiner hash_map erreicht hat.

Der von `rend` zurückgegebene Wert darf nicht dereferenziert werden.

### <a name="example"></a>Beispiel

```cpp
// hash_map_rend.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: iterator hm1_Iter;
   hash_map <int, int> :: reverse_iterator hm1_rIter;
   hash_map <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_rIter = hm1.rend( );
   hm1_rIter--;
   cout << "The last element of the reversed hash_map hm1 is "
        << hm1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a hash_map in a forward order
   cout << "The hash_map is: ";
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( );
   hm1_Iter++)
      cout << hm1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a hash_map in a reverse order
   cout << "The reversed hash_map is: ";
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( );
      hm1_rIter++)
      cout << hm1_rIter -> first << " ";
      cout << "." << endl;

   // A hash_map element can be erased by dereferencing to its key
   hm1_rIter = --hm1.rend( );
   hm1.erase ( hm1_rIter -> first );

   hm1_rIter = hm1.rend( );
   hm1_rIter--;
   cout << "After the erasure, the last element "
        << "in the reversed hash_map is "
        << hm1_rIter -> first << "." << endl;
}
```

```Output
The last element of the reversed hash_map hm1 is 1.
The hash_map is: 1 2 3 .
The reversed hash_map is: 3 2 1 .
After the erasure, the last element in the reversed hash_map is 2.
```

## <a name="reverse_iterator"></a> hash_map::reverse_iterator

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem ein Element in einer umgekehrten hash_map gelesen oder geändert werden kann.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Hinweise

Ein `reverse_iterator`-Typ kann nicht den Wert eines Elements ändern und wird verwendet, um die hash_map in umgekehrter Reihenfolge zu durchlaufen.

Der `reverse_iterator`, der durch hash_map definiert wird, zeigt auf Elemente, die Objekte eines [value_type](#value_type) sind, das von Typ **pair\<const Key, Type>** ist. Dessen erster Member ist der Schlüssel zum Element, und dessen zweiter Member das zugeordnete Datum, das vom Element gehalten wird.

Dereferenziert eine `reverse_iterator` `rIter` verweist auf ein Element in einer Hash_map, verwenden Sie die Operator ->.

Verwenden Sie `rIter` -> **first**, das (\* `rIter`). **first** entspricht, um auf den Wert des Schlüssels für das Element zuzugreifen. Verwenden Sie `rIter` -> **second**, das (\* `rIter`). **first** entspricht, um auf den Wert des zugeordneten Datums für das Element zuzugreifen.

### <a name="example"></a>Beispiel

Im Beispiel für [rbegin](#rbegin) wird verdeutlicht, wie `reverse_iterator` deklariert und verwendet wird.

## <a name="size"></a> hash_map::size

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt die Anzahl von Elementen in der hash_map zurück.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Länge der hash_map.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Verwendung der Memberfunktion „map::size“ gezeigt.

```cpp
// hash_map_size.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int> hm1, hm2;
    hash_map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 1));
    i = hm1.size();
    cout << "The hash_map length is " << i << "." << endl;

    hm1.insert(Int_Pair(2, 4));
    i = hm1.size();
    cout << "The hash_map length is now " << i << "." << endl;
}
```

```Output
The hash_map length is 1.
The hash_map length is now 2.
```

## <a name="size_type"></a> hash_map::size_type

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in einer hash_map darstellen kann.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

Im Beispiel für [size](#size) wird verdeutlicht, wie ein `size_type` deklariert und verwendet wird

## <a name="swap"></a> hash_map::swap

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Tauscht die Elemente zweier hash_maps aus.

```cpp
void swap(hash_map& right);
```

### <a name="parameters"></a>Parameter

`right` Das Argument Hash_map Elemente mit dem Ziel Hash_map ausgetauscht werden sollen.

### <a name="remarks"></a>Hinweise

Die Memberfunktion macht keine Verweise, Zeiger oder Iteratoren ungültig, die Elemente in zwei hash_maps bezeichnet, dessen Elemente ausgetauscht werden.

### <a name="example"></a>Beispiel

```cpp
// hash_map_swap.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2, hm3;
   hash_map <int, int>::iterator hm1_Iter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );
   hm2.insert ( Int_Pair ( 10, 100 ) );
   hm2.insert ( Int_Pair ( 20, 200 ) );
   hm3.insert ( Int_Pair ( 30, 300 ) );

   cout << "The original hash_map hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout   << "." << endl;

   // This is the member function version of swap
   // hm2 is said to be the argument hash_map;
   // hm1 is said to be the target hash_map
   hm1.swap( hm2 );

   cout << "After swapping with hm2, hash_map hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( hm1, hm3 );

   cout << "After swapping with hm3, hash_map hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout   << "." << endl;
}
```

```Output
The original hash_map hm1 is: 10 20 30.
After swapping with hm2, hash_map hm1 is: 100 200.
After swapping with hm3, hash_map hm1 is: 300.
```

## <a name="upper_bound"></a> hash_map::upper_bound

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt einen Iterator zum ersten Element in einer hash_map mit einem Schlüsselwert zurück, der größer ist, als ein angegebener Schlüssel.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Parameter

`key` Das Argument angegebene Schlüsselwert mit der Sortierschlüsselwert eines Elements aus der Hash_map zu durchsuchenden verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein [Iterator](#iterator) oder [const_iterator](#const_iterator), der den Speicherort eines Elements in einem hash_map-Element mit einem Schlüssel adressiert, der größer als der Argumentschlüssel ist, oder der den Speicherort des folgenden letzten Elements in der hash_map adressiert, wenn kein Treffer für den Schlüssen gefunden wird.

Wenn der Rückgabewert einem `const_iterator` zugewiesen wird, kann das hash_map-Objekt nicht geändert werden. Wenn der Rückgabewert einem **Iterator** zugewiesen wird, kann das hash_map-Objekt nicht geändert werden.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

```cpp
// hash_map_upper_bound.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   hash_map <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_RcIter = hm1.upper_bound( 2 );
   cout << "The first element of hash_map hm1 with a key "
        << "greater than 2 is: "
        << hm1_RcIter -> second << "." << endl;

   // If no match is found for the key, end is returned
   hm1_RcIter = hm1. upper_bound ( 4 );

   if ( hm1_RcIter == hm1.end( ) )
      cout << "The hash_map hm1 doesn't have an element "
           << "with a key greater than 4." << endl;
   else
      cout << "The element of hash_map hm1 with a key > 4 is: "
           << hm1_RcIter -> second << "." << endl;

   // The element at a specific location in the hash_map can be found
   // using a dereferenced iterator addressing the location
   hm1_AcIter = hm1.begin( );
   hm1_RcIter = hm1. upper_bound ( hm1_AcIter -> first );
   cout << "The 1st element of hm1 with a key greater than "
        << "that\n of the initial element of hm1 is: "
        << hm1_RcIter -> second << "." << endl;
}
```

```Output
The first element of hash_map hm1 with a key greater than 2 is: 30.
The hash_map hm1 doesn't have an element with a key greater than 4.
The 1st element of hm1 with a key greater than that
 of the initial element of hm1 is: 20.
```

## <a name="value_comp"></a> hash_map::value_comp

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Gibt ein Funktionsobjekt zurück, das die Reihenfolge der Elemente in einer hash_map bestimmt, indem ihre Schlüsselwerte verglichen werden.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt das Vergleichsfunktionsobjekt zurück, das ein hash_map-Element zum Sortieren seiner Elemente verwendet.

### <a name="remarks"></a>Hinweise

Wenn zwei Elemente, *e*1 *(k*1 *, d*1 *)* und *e*2 *(k*2 *, d*2 *)*, für eine hash_map *m* Objekte eines [value_type](#value_type)-Typs sind, bei dem *k*1 und *k*2 deren Schlüssel des [key_type](#key_type)-Typs sind, und `d`1 und`d`2 deren Daten des [mapped_type](#mapped_type)-Typs sind, entspricht *m.*`value_comp`*( )(e*1 *, e*2 *)* anschließend *m.*`key_comp`*( ) (k*1 *, k*2 *)*. Ein gespeichertes Objekt definiert die Memberfunktion

**bool operator**(**value_type&** `left`, **value_type&** `right`) **;**,

die **TRUE** zurückgibt, wenn der Schlüsselwert von `left` vorangestellt ist und nicht dem Schüsselwert von `right` in der Sortierreihenfolge entspricht.

### <a name="example"></a>Beispiel

```cpp
// hash_map_value_comp.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_map <int, int, hash_compare<int, less<int> > > hm1;
   hash_map <int, int, hash_compare<int, less<int> > >
   ::value_compare vc1 = hm1.value_comp( );
   pair< hash_map<int,int>::iterator, bool > pr1, pr2;

   pr1= hm1.insert ( hash_map <int, int> :: value_type ( 1, 10 ) );
   pr2= hm1.insert ( hash_map <int, int> :: value_type ( 2, 5 ) );

   if( vc1( *pr1.first, *pr2.first ) == true )
   {
      cout << "The element ( 1,10 ) precedes the element ( 2,5 )."
           << endl;
   }
   else
   {
      cout << "The element ( 1,10 ) does not precede the element ( 2,5 )."
           << endl;
   }

   if( vc1 ( *pr2.first, *pr1.first ) == true )
   {
      cout << "The element ( 2,5 ) precedes the element ( 1,10 )."
           << endl;
   }
   else
   {
      cout << "The element ( 2,5 ) does not precede the element ( 1,10 )."
           << endl;
   }
}
```

## <a name="value_type"></a> hash_map::value_type

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Ein Typ, der den Typ des Objekts angibt, das in einer hash_map gespeichert wird.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="remarks"></a>Hinweise

`value_type` wird als deklariert `pair`  *\< * **const**[Key_type](#key_type), [Mapped_type](#mapped_type)*> * und nicht `pair`  **\<Key_type Mapped_type >** , da die Schlüssel des ein assoziativer Container nicht geändert werden können, mit einem nicht Konstanten Iterator oder Verweis.

### <a name="example"></a>Beispiel

```cpp
// hash_map_value_type.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef pair <const int, int> cInt2Int;
   hash_map <int, int> hm1;
   hash_map <int, int> :: key_type key1;
   hash_map <int, int> :: mapped_type mapped1;
   hash_map <int, int> :: value_type value1;
   hash_map <int, int> :: iterator pIter;

   // value_type can be used to pass the correct type
   // explicitely to avoid implicit type conversion
   hm1.insert ( hash_map <int, int> :: value_type ( 1, 10 ) );

   // Compare other ways to insert objects into a hash_map
   hm1.insert ( cInt2Int ( 2, 20 ) );
   hm1[ 3 ] = 30;

   // Initializing key1 and mapped1
   key1 = ( hm1.begin( ) -> first );
   mapped1 = ( hm1.begin( ) -> second );

   cout << "The key of first element in the hash_map is "
        << key1 << "." << endl;

   cout << "The data value of first element in the hash_map is "
        << mapped1 << "." << endl;

   // The following line would cause an error because
   // the value_type is not assignable
   // value1 = cInt2Int ( 4, 40 );

   cout  << "The keys of the mapped elements are:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;
}
```

```Output
The key of first element in the hash_map is 1.
The data value of first element in the hash_map is 10.
The keys of the mapped elements are: 1 2 3.
The values of the mapped elements are: 10 20 30.
```

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
