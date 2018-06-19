---
title: multiset-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- set/std::multiset
- set/std::multiset::allocator_type
- set/std::multiset::const_iterator
- set/std::multiset::const_pointer
- set/std::multiset::const_reference
- set/std::multiset::const_reverse_iterator
- set/std::multiset::difference_type
- set/std::multiset::iterator
- set/std::multiset::key_compare
- set/std::multiset::key_type
- set/std::multiset::pointer
- set/std::multiset::reference
- set/std::multiset::reverse_iterator
- set/std::multiset::size_type
- set/std::multiset::value_compare
- set/std::multiset::value_type
- set/std::multiset::begin
- set/std::multiset::cbegin
- set/std::multiset::cend
- set/std::multiset::clear
- set/std::multiset::count
- set/std::multiset::crbegin
- set/std::multiset::crend
- set/std::multiset::emplace
- set/std::multiset::emplace_hint
- set/std::multiset::empty
- set/std::multiset::end
- set/std::multiset::equal_range
- set/std::multiset::erase
- set/std::multiset::find
- set/std::multiset::get_allocator
- set/std::multiset::insert
- set/std::multiset::key_comp
- set/std::multiset::lower_bound
- set/std::multiset::max_size
- set/std::multiset::rbegin
- set/std::multiset::rend
- set/std::multiset::size
- set/std::multiset::swap
- set/std::multiset::upper_bound
- set/std::multiset::value_comp
dev_langs:
- C++
helpviewer_keywords:
- std::multiset [C++]
- std::multiset [C++], allocator_type
- std::multiset [C++], const_iterator
- std::multiset [C++], const_pointer
- std::multiset [C++], const_reference
- std::multiset [C++], const_reverse_iterator
- std::multiset [C++], difference_type
- std::multiset [C++], iterator
- std::multiset [C++], key_compare
- std::multiset [C++], key_type
- std::multiset [C++], pointer
- std::multiset [C++], reference
- std::multiset [C++], reverse_iterator
- std::multiset [C++], size_type
- std::multiset [C++], value_compare
- std::multiset [C++], value_type
- std::multiset [C++], begin
- std::multiset [C++], cbegin
- std::multiset [C++], cend
- std::multiset [C++], clear
- std::multiset [C++], count
- std::multiset [C++], crbegin
- std::multiset [C++], crend
- std::multiset [C++], emplace
- std::multiset [C++], emplace_hint
- std::multiset [C++], empty
- std::multiset [C++], end
- std::multiset [C++], equal_range
- std::multiset [C++], erase
- std::multiset [C++], find
- std::multiset [C++], get_allocator
- std::multiset [C++], insert
- std::multiset [C++], key_comp
- std::multiset [C++], lower_bound
- std::multiset [C++], max_size
- std::multiset [C++], rbegin
- std::multiset [C++], rend
- std::multiset [C++], size
- std::multiset [C++], swap
- std::multiset [C++], upper_bound
- std::multiset [C++], value_comp
ms.assetid: 630e8c10-0ce9-4ad9-8d79-9e91a600713f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 994e97f126796db9725cdccb629f01a0f22dc962
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863438"
---
# <a name="multiset-class"></a>multiset-Klasse

Die multiset-Klasse der C++-Standardbibliothek wird zum Speichern und Abrufen von Daten aus Auflistungen verwendet, in denen die Werte der jeweiligen Elemente nicht eindeutig sein müssen und in denen sie als die Schlüsselwerte dienen, nach denen die Daten automatisch sortiert werden. Der Schlüsselwert eines Elements in einer Multimenge darf nicht direkt geändert werden. Stattdessen müssen alte Werte gelöscht und Elemente mit neuen Werten eingefügt werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Key, class Compare =less <Key>, class Allocator =allocator <Key>>
class multiset
```

### <a name="parameters"></a>Parameter

*Schlüssel* Elementdatentyp um in die Multimenge zu speichernde Elementdatentyp.

*Vergleichen Sie* der Typ, der ein Funktionsobjekt bereitstellt, das zwei Elementwerte als Sortierschlüssel, um deren relative Reihenfolge in der Multimenge zu bestimmen, vergleichen können. Das binäre Prädikat **less**\<Key> ist der Standardwert.

In C ++ 14 können Sie heterogenes Nachschlagen durch Angabe des `std::less<>` oder `std::greater<>` Prädikats, das keine Typparameter aufweist, aktivieren. Weitere Informationen finden Sie unter [Heterogenes Nachschlagen in assoziativen Containern](../standard-library/stl-containers.md#sequence_containers)

`Allocator` Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zum Belegen und Freigeben des Arbeitsspeichers der Multimenge gekapselt. Der Standardwert ist **Allocator ***\<Key >.*

## <a name="remarks"></a>Hinweise

Auf die multiset-Klasse der C++-Standardbibliothek treffen die folgenden Punkte zu:

- Ein assoziativer Container, der ein Container variabler Größe ist, der den effizienten Abruf von Elementwerten auf Grundlage eines zugeordneten Schlüsselwerts unterstützt.

- Umkehrbar, da bidirektionale Iteratoren für den Zugriff auf die Elemente bereitgestellt werden.

- Sortiert, da die Elemente anhand von Schlüsselwerten innerhalb des Containers mit einer angegebenen Vergleichsfunktion sortiert werden.

- Mehrfach insofern, als die Elemente keine eindeutigen Schlüssel aufweisen müssen, damit ein Schlüsselwert über viele zugeordnete Elementdatenwerte verfügen kann.

- Ein einfacher assoziativer Container, da die Elementwerte den Schlüsselwerten entsprechen.

- Eine Vorlagenklasse, da die bereitgestellten Funktionen generisch und daher unabhängig vom angegebenen Datentyp sind, der als Elemente enthalten ist. Der zu verwendende Datentyp wird stattdessen in der Klassenvorlage zusammen mit der Vergleichsfunktion und der Zuweisung als Parameter angegeben.

Der von der multiset-Klasse bereitgestellte Iterator ist bidirektional. Die Klassenmemberfunktionen [insert](#insert) and [multiset](#multiset) weisen jedoch Versionen auf, die einen abgeschwächten Eingabeiterator als Vorlagenparameter akzeptieren. Die Funktionalitätsanforderungen dieses Eingabeiterators sind weniger umfangreich als die Anforderungen, die von der Klasse bidirektionaler Iteratoren gewährleistet werden. Die verschiedenen Iteratorkonzepte bilden eine Family, die durch Verfeinerungen in ihrer Funktionen verknüpft ist. Jedes Iteratorkonzept weist einen eigenen Satz von Anforderungen auf, und die damit funktionierenden Algorithmen müssen die Annahmen hinsichtlich der von diesem Iteratortyp bereitgestellten Anforderungen begrenzen. Es kann davon ausgegangen werden, dass ein Eingabeiterator möglicherweise so dereferenziert wird, dass er auf ein Objekt verweist und dieses möglicherweise zum folgenden Iterator in der Sequenz erhöht. Obwohl es sich dabei nur um eine Mindestmenge von Funktionen handelt, reichen sie aus, um auf sinnvolle Weise über einen Bereich von Iteratoren [ `First`, `Last`) im Zusammenhang mit den Klassenmemberfunktionen zu sprechen.

Die Auswahl des Containertyps sollte im Allgemeinen auf Grundlage des für die Anwendung erforderlichen Suchen und Einfügetyps erfolgen. Assoziative Container sind für Such-, Einfüge- und Entfernvorgänge optimiert. Die Memberfunktionen, die diese Vorgänge explizit unterstützen, sind effizient und führen sie in einer Zeit aus, die zum Logarithmus der Elementanzahl im Container im Durchschnitt proportional ist. Das Einfügen von Elementen führt nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen von Elementen werden nur solche Iteratoren ungültig, die speziell auf die entfernten Elemente gezeigt haben.

Die Multimenge sollte der ausgewählte assoziative Container sein, wenn die Bedingungen, mit denen die Werte von der Anwendung den Schlüsseln zugeordnet werden, erfüllt werden. Die Elemente einer Multimenge können Mehrfache sein und als eigene Sortierschlüssel dienen, sodass Schlüssel nicht eindeutig sind. Ein Modell für diesen Typ der Struktur ist eine geordnete Liste von z. B. Wörtern, in denen die Wörter möglicherweise mehrmals auftreten. Wenn mehrfaches Vorkommen der Wörter nicht zugelassen wurde, ist eine Menge die geeignete Containerstruktur. Wenn eindeutige Definitionen als Werte zur Liste von eindeutigen Schlüsselwörtern angefügt wurden, ist eine Zuordnung eine äquivalente Struktur, um diese Daten zu enthalten. Wenn stattdessen die Definitionen nicht eindeutig sind, ist eine Mehrfachzuordnung der geeignete Container.

Die Multimenge sortiert die von ihr gesteuerten Elemente, indem ein gespeichertes Funktionsobjekt vom Typ `Compare` aufgerufen wird. Bei diesem gespeicherten Objekt handelt es sich um eine Vergleichsfunktion, auf die durch Aufrufen der Memberfunktion [key_comp](#key_comp) zugegriffen werden kann. Im Allgemeinen müssen die Elemente der Vorwärtsiteratoren etwas weniger als vergleichbar sein, um diese Sortierung zu erstellen, sodass beliebige zwei Elemente möglicherweise als gleichwertig bestimmt werden (in dem Sinne, dass keins geringer als das Andere ist), oder dass eins geringer als das Andere ist. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen. Etwas technischer betrachtet ist die Vergleichsfunktion ein binäres Prädikat, das eine strenge schwache Sortierung im mathematischen Sinn verursacht. Bei einem binären *f*( *x*, *y*)-Prädikat handelt es sich um ein Funktionsobjekt mit den beiden Argumentobjekten *x* und *y* sowie dem Rückgabewert **TRUE** oder **FALSE**. Eine Sortierung, die auf eine Multimenge angewendet wird, ist eine strenge schwache Sortierung, wenn das binäre Prädikat irreflexiv, antisymmetrisch sowie transitiv ist und wenn die Äquivalenz bei zwei Objekten „x“ und „y“ transitiv ist, die als äquivalent definiert werden, wenn sowohl *f*( *x,y*) als auch *f*( *y,x*) FALSE sind. Wenn der stärkere Gleichheitszustand zwischen Schlüsseln die Äquivalenz ersetzt, erfolgt die Sortierung total (d. h., alle Elemente werden zueinander sortiert), und die verglichenen Schlüssel sind von den einander nicht mehr zu unterscheiden.

In C ++ 14 können Sie heterogenes Nachschlagen durch Angabe des `std::less<>` oder `std::greater<>` Prädikats, das keine Typparameter aufweist, aktivieren. Weitere Informationen finden Sie unter [Heterogenes Nachschlagen in assoziativen Containern](../standard-library/stl-containers.md#sequence_containers)

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[multiset](#multiset)|Erstellt ein `multiset`-Element, das leer oder die Kopie eines ganzen angegebenen `multiset`-Elements oder eines Teils davon ist.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[allocator_type](#allocator_type)|Eine Typedef für die `allocator`-Klasse für das `multiset`-Objekt.|
|[const_iterator](#const_iterator)|Eine Typedef für einen bidirektionalen Iterator, der ein `const`-Element in der `multiset` lesen kann.|
|[const_pointer](#const_pointer)|Eine Typedef für einen Zeiger auf ein `const`-Element in einer `multiset`.|
|[const_reference](#const_reference)|Eine Typedef für einen Verweis auf ein `const`-Element, das in einer `multiset` zum Lesen und Ausführen von `const`-Vorgängen gespeichert ist.|
|[const_reverse_iterator](#const_reverse_iterator)|Eine Typedef für einen bidirektionalen Iterator, der ein beliebiges `const`-Element in der `multiset` lesen kann.|
|[difference_type](#difference_type)|Ein Ganzzahltyp mit Vorzeichen für die Anzahl von Elementen einer `multiset` in einem Bereich zwischen Elementen, auf die von Iteratoren gezeigt wird.|
|[Iterator](#iterator)|Eine Typedef für einen bidirektionalen Iterator, der ein beliebiges Element in einer `multiset` lesen oder ändern kann.|
|[key_compare](#key_compare)|Eine Typedef für ein Funktionsobjekt, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen in der `multiset` zu bestimmen.|
|[key_type](#key_type)|Eine Typedef für ein Funktionsobjekt, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen in der `multiset` zu bestimmen.|
|[Zeiger](#pointer)|Eine Typedef für einen Zeiger auf ein Element in einer `multiset`.|
|[Verweis](#reference)|Eine Typedef für einen Verweis auf ein in einer `multiset` gespeichertes Element.|
|[reverse_iterator](#reverse_iterator)|Eine Typedef für einen bidirektionalen Iterator, der ein Element in einer umgekehrten `multiset` lesen oder ändern kann.|
|[size_type](#size_type)|Eine Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in `multiset` darstellen kann.|
|[value_compare](#value_compare)|Die Typedef für ein Funktionsobjekt, das zwei Elemente als Sortierschlüssel vergleichen kann, um ihre relative Position in der `multiset` zu bestimmen.|
|[value_type](#value_type)|Eine Typedef, die ein Objekt beschreibt, das als Element und `multiset` in seiner Kapazität als Wert gespeichert wird.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[begin](#begin)|Gibt einen Iterator zurück, der auf das erste Element in der `multiset` zeigt.|
|[cbegin](#cbegin)|Gibt einen konstanten Iterator zurück, der das erste Element in der `multiset` adressiert.|
|[cend](#cend)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines `multiset`-Elements nachfolgt.|
|[clear](#clear)|Löscht alle Elemente einer `multiset` auf.|
|[count](#count)|Gibt die Anzahl von Elementen in einer `multiset` zurück, deren Schlüssel dem als Parameter angegebenen Schlüssel entspricht.|
|[crbegin](#crbegin)|Gibt einen const-Iterator zurück, der das erste Element in einer umgekehrten Menge adressiert.|
|[crend](#crend)|Gibt einen const-Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer umgekehrten Menge nachfolgt.|
|[emplace](#emplace)|Fügt ein Element ein, das vor Ort in ein `multiset`-Element erstellt wird.|
|[emplace_hint](#emplace_hint)|Fügt ein Element ein, das vor Ort mit einem Platzierungshinweis in ein `multiset`-Element erstellt wird.|
|[empty](#empty)|Testet, ob ein `multiset`-Element leer ist.|
|[end](#end)|Gibt einen Iterator zurück, der auf den Speicherort zeigt, der hinter dem letzten Element einer `multiset` liegt.|
|[equal_range](#equal_range)|Gibt ein Paar von Iteratoren zurück. Der erste Iterator im Paar zeigt auf das erste Element in `multiset` mit einem Schlüssel, der größer ist, als ein bestimmter Schlüssel. Der zweite Iterator im Paar zeigt auf das erste Element in der `multiset` mit einem Schlüssel, der größer oder gleich dem Schlüssel ist.|
|[erase](#erase)|Es wird ein Element oder ein Bereich von Elementen in einem `multiset` von angegebenen Speicherorten entfernt, oder es werden die einem angegebenen Schlüssel entsprechenden Elemente entfernt.|
|[find](#find)|Gibt einen Iterator zurück, der auf den ersten Speicherort eines Elements in einer `multiset` zeigt, der einen Schlüssel gleich einem angegebenen Schlüssel aufweist.|
|[get_allocator](#get_allocator)|Gibt eine Kopie des zum Erstellen der `allocator` verwendeten `multiset`-Objekts zurück.|
|[insert](#insert)|Fügt ein Element oder einen Elementbereich in ein `multiset`-Element ein.|
|[key_comp](#key_comp)|Stellt ein Funktionsobjekt bereit, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen in der `multiset` zu bestimmen.|
|[lower_bound](#lower_bound)|Gibt einen Iterator zum ersten Element in einem `multiset`-Element mit einem Schlüssel zurück, der gleich oder größer ist, als ein angegebener Schlüssel.|
|[max_size](#max_size)|Gibt die Maximallänge der `multiset` zurück.|
|[rbegin](#rbegin)|Gibt einen Iterator zurück, der auf das erste Element in einer umgekehrten `multiset` zeigt.|
|[rend](#rend)|Gibt einen Iterator zurück, der auf den Speicherort zeigt, der auf das letzte Element einer umgekehrten `multiset` folgt.|
|[size](#size)|Gibt die Anzahl von Elementen in einer `multiset` zurück.|
|[swap](#swap)|Tauscht die Elemente zweier `multiset`n.|
|[upper_bound](#upper_bound)|Gibt einen Iterator zum ersten Element in einem `multiset`-Element mit einem Schlüssel zurück, der größer als ein angegebener Schlüssel ist.|
|[value_comp](#value_comp)|Ruft eine Kopie des Vergleichsobjekts ab, das verwendet wird, um Elementwerte in einer `multiset` zu sortieren.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_eq)|Ersetzt die Elemente eines `multiset`-Elements durch eine Kopie eines anderen `multiset`-Elements.|

## <a name="requirements"></a>Anforderungen

**Header:** \<set>

**Namespace:** std

## <a name="allocator_type"></a> multiset::allocator_type

Ein Typ, der die Zuweisungsklasse für das Multiset-Objekt darstellt.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Hinweise

`allocator_type` ist ein Synonym für den Vorlagenparameter `Allocator`.

Weitere Informationen zu `Allocator` finden Sie im Abschnitt „Hinweise“ unter [multiset-Klasse](../standard-library/multiset-class.md).

### <a name="example"></a>Beispiel

Im Beispiel für [get_allocator](#get_allocator) finden Sie ein Beispiel mit `allocator_type`.

## <a name="begin"></a> multiset::begin

Gibt einen Iterator zurück, der das erste Element in der Multimenge adressiert.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Rückgabewert

Ein bidirektionaler Iterator, der das erste Element in der Multimenge oder den auf eine leere Multimenge folgenden Speicherort adressiert.

### <a name="example"></a>Beispiel

```cpp
// multiset_begin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;
   multiset <int>::const_iterator ms1_cIter;

   ms1.insert( 1 );
   ms1.insert( 2 );
   ms1.insert( 3 );

   ms1_Iter = ms1.begin( );
   cout << "The first element of ms1 is " << *ms1_Iter << endl;

   ms1_Iter = ms1.begin( );
   ms1.erase( ms1_Iter );

   // The following 2 lines would err as the iterator is const
   // ms1_cIter = ms1.begin( );
   // ms1.erase( ms1_cIter );

   ms1_cIter = ms1.begin( );
   cout << "The first element of ms1 is now " << *ms1_cIter << endl;
}
```

```Output
The first element of ms1 is 1
The first element of ms1 is now 2
```

## <a name="cbegin"></a> multiset::cbegin

Gibt einen `const`-Iterator zurück, mit dem das erste Element im Bereich behandelt wird.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein bidirektionaler `const`-Access-Iterator, der auf das erste Element des Bereichs zeigt oder auf die Position direkt hinter dem Ende eines leeren Bereichs (für einen leeren Bereich gilt `cbegin() == cend()`).

### <a name="remarks"></a>Hinweise

Bei dem Rückgabewert `cbegin` können die Elemente im Bereich nicht geändert werden.

Sie können diese Memberfunktion anstelle der `begin()`-Memberfunktion verwenden, um sicherzustellen, dass der Rückgabewert `const_iterator` ist. Normalerweise wird sie zusammen mit dem [auto](../cpp/auto-cpp.md)-Typableitungs-Schlüsselwort verwendet, wie im folgenden Beispiel gezeigt. Im folgenden Beispiel ist `Container` ein beliebiger änderbarer Container (ohne `const`), der `begin()` und `cbegin()` unterstützt.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a> multiset::cend

Gibt einen `const`-Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines Bereichs unmittelbar nachfolgt.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Rückgabewert

Ein bidirektionaler `const`-Access-Iterator, der auf eine Position unmittelbar nach dem Ende des Bereichs verweist.

### <a name="remarks"></a>Hinweise

`cend` wird verwendet, um zu testen, ob ein Iterator das Ende seines Bereichs übergeben hat.

Sie können diese Memberfunktion anstelle der `end()`-Memberfunktion verwenden, um sicherzustellen, dass der Rückgabewert `const_iterator` ist. Normalerweise wird sie zusammen mit dem [auto](../cpp/auto-cpp.md)-Typableitungs-Schlüsselwort verwendet, wie im folgenden Beispiel gezeigt. Im folgenden Beispiel ist `Container` ein beliebiger änderbarer (Nicht-`const`-)Container, der `end()` und `cend()` unterstützt.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Der von `cend` zurückgegebene Wert darf nicht dereferenziert werden.

## <a name="clear"></a> multiset::clear

Löscht alle Elemente einer Multimenge.

```cpp
void clear();
```

### <a name="example"></a>Beispiel

```cpp
// multiset_clear.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;

   ms1.insert( 1 );
   ms1.insert( 2 );

   cout << "The size of the multiset is initially "
        << ms1.size( ) << "." << endl;

   ms1.clear( );
   cout << "The size of the multiset after clearing is "
        << ms1.size( ) << "." << endl;
}
```

```Output
The size of the multiset is initially 2.
The size of the multiset after clearing is 0.
```

## <a name="const_iterator"></a> multiset::const_iterator

Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem ein **const**-Element in der Multimenge gelesen werden kann.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Hinweise

Ein `const_iterator`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden.

### <a name="example"></a>Beispiel

Im Beispiel für [begin](#begin) finden Sie ein Beispiel mit `const_iterator`.

## <a name="const_pointer"></a> multiset::const_pointer

Ein Typ, der einen Zeiger auf ein **const**-Element in einer Multimenge bereitstellt.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Hinweise

Ein `const_pointer`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden.

In den meisten Fällen sollte ein [iterator](#iterator)-Typ für den Zugriff auf Elemente in einem Multiset-Objekt verwendet werden.

## <a name="const_reference"></a> multiset::const_reference

Ein Typ, der einen Verweis auf ein **const**-Element bereitstellt, das in einer Multimenge zum Lesen und Ausführen von **const**-Operationen gespeichert ist.

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="example"></a>Beispiel

```cpp
// multiset_const_ref.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;

   ms1.insert( 10 );
   ms1.insert( 20 );

   // Declare and initialize a const_reference &Ref1
   // to the 1st element
   const int &Ref1 = *ms1.begin( );

   cout << "The first element in the multiset is "
        << Ref1 << "." << endl;

   // The following line would cause an error because the
   // const_reference cannot be used to modify the multiset
   // Ref1 = Ref1 + 5;
}
```

```Output
The first element in the multiset is 10.
```

## <a name="const_reverse_iterator"></a> multiset::const_reverse_iterator

Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem alle **const**-Elemente in einer Multimenge gelesen werden können.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Hinweise

Ein `const_reverse_iterator`-Typ kann nicht den Wert eines Elements ändern. Er wird verwendet, um die Multimenge in umgekehrter Reihenfolge zu durchlaufen.

### <a name="example"></a>Beispiel

Im Beispiel für [rend](#rend) wird verdeutlicht, wie `const_reverse_iterator` deklariert und verwendet wird.

## <a name="count"></a> multiset::count

Gibt die Anzahl von Elementen in einer multiset-Klasse zurück, dessen Schlüssel dem von einem Parameter angegebenen Schlüssel entspricht.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Parameter

`key` Der Schlüssel der Elemente, die von der Multimenge abgeglichen werden.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im „multiset“, deren Sortierschlüssel mit dem Parameterschlüssel übereinstimmt.

### <a name="remarks"></a>Hinweise

Die Memberfunktion ermöglicht die Rückgabe der Anzahl von Elementen *x* im Bereich

[ `lower_bound` (_ *Key* ), `upper_bound` (\_ *Key* ) ).

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Verwendung der Memberfunktion „multiset::count“ gezeigt.

```cpp
// multiset_count.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
{
    using namespace std;
    multiset<int> ms1;
    multiset<int>::size_type i;

    ms1.insert(1);
    ms1.insert(1);
    ms1.insert(2);

    // Elements do not need to be unique in multiset,
    // so duplicates are allowed and counted.
    i = ms1.count(1);
    cout << "The number of elements in ms1 with a sort key of 1 is: "
         << i << "." << endl;

    i = ms1.count(2);
    cout << "The number of elements in ms1 with a sort key of 2 is: "
         << i << "." << endl;

    i = ms1.count(3);
    cout << "The number of elements in ms1 with a sort key of 3 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in ms1 with a sort key of 1 is: 2.
The number of elements in ms1 with a sort key of 2 is: 1.
The number of elements in ms1 with a sort key of 3 is: 0.
```

## <a name="crbegin"></a> multiset::crbegin

Gibt einen const-Iterator zurück, der das erste Element in einem umgekehrten Multiset adressiert.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein umgekehrter bidirektionaler const-Iterator, mit dem das erste Element in einem umgekehrten Multiset adressiert wird bzw. mit dem das ehemals letzte Element in dem nicht umgekehrten Multiset adressiert wird.

### <a name="remarks"></a>Hinweise

`crbegin` wird bei einer umgekehrten Multimenge auf dieselbe Weise wie „begin“ bei einer Multimenge verwendet.

Bei dem Rückgabewert von `crbegin`kann das Multisetobjekt nicht geändert werden.

Mit `crbegin` lässt sich eine Multimenge rückwärts durchlaufen.

### <a name="example"></a>Beispiel

```cpp
// multiset_crbegin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::const_reverse_iterator ms1_crIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_crIter = ms1.crbegin( );
   cout << "The first element in the reversed multiset is "
        << *ms1_crIter << "." << endl;
}
```

```Output
The first element in the reversed multiset is 30.
```

## <a name="crend"></a> multiset::crend

Gibt einen const-Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer umgekehrten Multimenge folgt.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Rückgabewert

Ein bidirektionaler const_reverse-Iterator, der den Speicherort adressiert, der dem letzten Element in einer umgekehrten Multimenge folgt (d.h. den Speicherort, der dem ersten Element in der nicht umgekehrten Multimenge vorangegangen war).

### <a name="remarks"></a>Hinweise

`crend` wird bei einer umgekehrten Multimenge auf dieselbe Weise wie [end](#end) bei einer Multimenge verwendet.

Bei einem Rückgabewert von `crend` kann das Multiset-Objekt nicht geändert werden.

Mit `crend` lässt sich überprüfen, ob ein umgekehrter Iterator das Ende seiner Multimenge erreicht hat.

Der von `crend` zurückgegebene Wert darf nicht dereferenziert werden.

### <a name="example"></a>Beispiel

```cpp
// multiset_crend.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main() {
   using namespace std;
   multiset <int> ms1;
   multiset <int>::const_reverse_iterator ms1_crIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_crIter = ms1.crend( ) ;
   ms1_crIter--;
   cout << "The last element in the reversed multiset is "
        << *ms1_crIter << "." << endl;
}
```

## <a name="difference_type"></a> multiset::difference_type

Ein Ganzzahltyp mit Vorzeichen, mit dem sich die Anzahl von Elementen einer Multimenge in einem Bereich zwischen Elementen darstellen lässt, auf die Iteratoren zeigen.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Hinweise

`difference_type` ist der Typ, der beim Subtrahieren oder Inkrementieren über Iteratoren des Containers zurückgegeben wird. `difference_type` wird normalerweise verwendet, um die Anzahl von Elementen im Bereich [ `first`, `last`) zwischen den Iteratoren `first` und `last` darzustellen. Dazu gehört das Element, auf das durch `first` gezeigt wird sowie der Bereich von Elementen bis zu (aber nicht einschließlich) dem Element, auf das durch `last` gezeigt wird.

Bitte beachten Sie, dass `difference_type` einerseits zwar für alle Iteratoren verfügbar ist, die die Anforderungen für einen Eingabeiterator erfüllen (gilt auch für die Klasse bidirektionaler Iteratoren, die von umkehrbaren Containern wie „set“ unterstützt werden), die Subtraktion zwischen Iteratoren andererseits jedoch nur von denjenigen Iteratoren mit zufälligem Zugriff unterstützt wird, die durch einen Container mit zufälligem Zugriff wie z.B. „vector“ bereitgestellt werden.

### <a name="example"></a>Beispiel

```cpp
// multiset_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <set>
#include <algorithm>

int main( )
{
   using namespace std;

   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter, ms1_bIter, ms1_eIter;

   ms1.insert( 20 );
   ms1.insert( 10 );
   ms1.insert( 20 );

   ms1_bIter = ms1.begin( );
   ms1_eIter = ms1.end( );

   multiset <int>::difference_type   df_typ5, df_typ10, df_typ20;

   df_typ5 = count( ms1_bIter, ms1_eIter, 5 );
   df_typ10 = count( ms1_bIter, ms1_eIter, 10 );
   df_typ20 = count( ms1_bIter, ms1_eIter, 20 );

   // The keys, and hence the elements, of a multiset are not unique
   cout << "The number '5' occurs " << df_typ5
        << " times in multiset ms1.\n";
   cout << "The number '10' occurs " << df_typ10
        << " times in multiset ms1.\n";
   cout << "The number '20' occurs " << df_typ20
        << " times in multiset ms1.\n";

   // Count the number of elements in a multiset
   multiset <int>::difference_type  df_count = 0;
   ms1_Iter = ms1.begin( );
   while ( ms1_Iter != ms1_eIter)
   {
      df_count++;
      ms1_Iter++;
   }

   cout << "The number of elements in the multiset ms1 is: "
        << df_count << "." << endl;
}
```

```Output
The number '5' occurs 0 times in multiset ms1.
The number '10' occurs 1 times in multiset ms1.
The number '20' occurs 2 times in multiset ms1.
The number of elements in the multiset ms1 is: 3.
```

## <a name="emplace"></a> multiset::emplace

Fügt ein Element mit einem Platzierungshinweis ein, das vor Ort erstellt wird (Es werden keine Kopier- oder Verschiebevorgänge ausgeführt).

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`args`|Die weitergeleiteten Argumente zur Konstruktion eines Elements, dass in die Multimenge eingefügt werden soll.|

### <a name="return-value"></a>Rückgabewert

Ein Iterator zum neu eingefügten Element.

### <a name="remarks"></a>Hinweise

Von dieser Funktion werden keine Verweise auf Containerelemente für ungültig erklärt, aber möglicherweise werden alle Iteratoren für den Containers für ungültig erklärt.

Wird während des Einbaus eine Ausnahme ausgelöst, wird der Zustand des Containers nicht geändert.

### <a name="example"></a>Beispiel

```cpp
// multiset_emplace.cpp
// compile with: /EHsc
#include <set>
#include <string>
#include <iostream>

using namespace std;

template <typename S> void print(const S& s) {
    cout << s.size() << " elements: ";

    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }

    cout << endl;
}

int main()
{
    multiset<string> s1;

    s1.emplace("Anna");
    s1.emplace("Bob");
    s1.emplace("Carmine");

    cout << "multiset modified, now contains ";
    print(s1);
    cout << endl;

    s1.emplace("Bob");

    cout << "multiset modified, now contains ";
    print(s1);
    cout << endl;
}

```

## <a name="emplace_hint"></a> multiset::emplace_hint

Fügt ein Element mit einem Platzierungshinweis ein, das vor Ort erstellt wird (Es werden keine Kopier- oder Verschiebevorgänge ausgeführt).

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`args`|Die weitergeleiteten Argumente zur Konstruktion eines Elements, dass in die Multimenge eingefügt werden soll.|
|`where`|Die Position, an dem mit der Suche nach dem richtigen Einfügepunkt begonnen wird. (Wenn dieser Punkt `where` direkt vorausgeht, kann die Einfügung in amortisierter konstanter Zeit anstelle von logarithmischer Zeit eintreten.)|

### <a name="return-value"></a>Rückgabewert

Ein Iterator zum neu eingefügten Element.

### <a name="remarks"></a>Hinweise

Von dieser Funktion werden keine Verweise auf Containerelemente für ungültig erklärt, aber möglicherweise werden alle Iteratoren für den Containers für ungültig erklärt.

Wird während des Einbaus eine Ausnahme ausgelöst, wird der Zustand des Containers nicht geändert.

Ein Codebeispiel finden Sie unter [set::emplace_hint](../standard-library/set-class.md#emplace_hint).

## <a name="empty"></a> multiset::empty

Überprüft, ob eine Multimenge leer ist.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Multimenge leer ist, und **FALSE**, wenn sie nicht leer ist.

### <a name="example"></a>Beispiel

```cpp
// multiset_empty.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1, ms2;
   ms1.insert ( 1 );

   if ( ms1.empty( ) )
      cout << "The multiset ms1 is empty." << endl;
   else
      cout << "The multiset ms1 is not empty." << endl;

   if ( ms2.empty( ) )
      cout << "The multiset ms2 is empty." << endl;
   else
      cout << "The multiset ms2 is not empty." << endl;
}
```

```Output
The multiset ms1 is not empty.
The multiset ms2 is empty.
```

## <a name="end"></a> multiset::end

Gibt den "past-the-end"-Iterator zurück.

```cpp
const_iterator end() const;


iterator end();
```

### <a name="return-value"></a>Rückgabewert

Der "past-the-end"-Iterator. Wenn die Multimenge leer ist, dann gilt `multiset::end() == multiset::begin()`.

### <a name="remarks"></a>Hinweise

**end** wird verwendet, um zu überprüfen, ob ein Iterator das Ende seiner Multimenge übergeben hat.

Der von **end** zurückgegebene Wert darf nicht dereferenziert werden.

Ein Codebeispiel finden Sie unter [multiset::find](#find).

## <a name="equal_range"></a> multiset::equal_range

Gibt ein Iteratorenpaar an das erste Element in einer Multimenge entweder mit einem Schlüssel zurück, der größer als ein benutzerdefinierter Schlüssel ist, oder mit einem Schlüssel, der mindestens so groß wie dieser Schlüssel ist.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Parameter

`key` Der Argumentschlüssel mit dem Sortierschlüssel eines Elements aus dem durchsuchten Multiset verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Iteratorenpaar, bei dem der erste Iterator der [lower_bound](#lower_bound) des Schlüssels und der zweite Iterator der [upper_bound](#upper_bound) des Schlüssels ist.

Sie können auf den ersten Iterator eines von einer Memberfunktion zurückgegebenen Paars `pr` zugreifen, indem Sie `pr`. **first** verwenden, und Sie können einen lower_bound-Iterator dereferenzieren, indem Sie \*( `pr`. **first**) verwenden. Sie können auf den zweiten Iterator eines von einer Memberfunktion zurückgegebenen Paars `pr` zugreifen, indem Sie `pr`. **second** verwenden, und Sie können einen upper_bound-Iterator dereferenzieren, indem Sie \*( `pr`. **second**) verwenden.

### <a name="example"></a>Beispiel

```cpp
// multiset_equal_range.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   typedef multiset<int, less<int> > IntSet;
   IntSet ms1;
   multiset <int> :: const_iterator ms1_RcIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   pair <IntSet::const_iterator, IntSet::const_iterator> p1, p2;
   p1 = ms1.equal_range( 20 );

   cout << "The upper bound of the element with "
        << "a key of 20 in the multiset ms1 is: "
        << *( p1.second ) << "." << endl;

   cout << "The lower bound of the element with "
        << "a key of 20 in the multiset ms1 is: "
        << *( p1.first ) << "." << endl;

   // Compare the upper_bound called directly
   ms1_RcIter = ms1.upper_bound( 20 );
   cout << "A direct call of upper_bound( 20 ) gives "
        << *ms1_RcIter << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 20 )." << endl;

   p2 = ms1.equal_range( 40 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == ms1.end( ) ) && ( p2.second == ms1.end( ) ) )
      cout << "The multiset ms1 doesn't have an element "
              << "with a key less than 40." << endl;
   else
      cout << "The element of multiset ms1 with a key >= 40 is: "
                << *( p1.first ) << "." << endl;
}
```

```Output
The upper bound of the element with a key of 20 in the multiset ms1 is: 30.
The lower bound of the element with a key of 20 in the multiset ms1 is: 20.
A direct call of upper_bound( 20 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 20 ).
The multiset ms1 doesn't have an element with a key less than 40.
```

## <a name="erase"></a> multiset::erase

Es wird ein Element oder ein Bereich von Elementen in einer Multimenge von angegebenen Speicherorten entfernt oder es werden die einem angegebenen Schlüssel entsprechenden Elemente entfernt.

```cpp
iterator erase(
    const_iterator Where);

iterator erase(
    const_iterator First,
    const_iterator Last);

size_type erase(
    const key_type& Key);
```

### <a name="parameters"></a>Parameter

`Where` Die Position des zu entfernenden Elements.

`First` Die Position des ersten Elements entfernt werden soll.

`Last` Die Position direkt hinter dem letzten Element entfernt werden soll.

`Key` Der Schlüsselwert der zu entfernenden Elemente.

### <a name="return-value"></a>Rückgabewert

Bei den ersten beiden Memberfunktionen ist es ein bidirektionaler Iterator, der das erste über die entfernten Elemente hinaus verbliebe Element festlegt, oder ein Element, das das Ende der Multimenge darstellt, wenn kein solches Element vorhanden ist.

Für die dritte Memberfunktion wird die Anzahl der von der Multimenge entfernten Elemente zurückgegeben.

### <a name="remarks"></a>Hinweise

Ein Codebeispiel finden Sie unter [set::erase](../standard-library/set-class.md#erase).

## <a name="find"></a> multiset::find

Gibt einen Iterator zurück, der sich auf den Speicherort eines Elements in einer Zuordnung bezieht, der einen Schlüssel entsprechend einem angegebenen Schlüssel aufweist.

```cpp
iterator find(const Key& key);


const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Parameter

`key` Der Schlüsselwert mit dem Sortierschlüssel eines Elements aus dem durchsuchten Multiset verglichen werden.

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der entweder auf den Speicherort eines Elements mit einem benutzerdefinierten Schlüssel oder, wenn für den Schlüssel keine Übereinstimmung gefunden wird, auf den Speicherort verweist, der dem letzten Element in der Multimenge ( `multiset::end()`) folgt.

### <a name="remarks"></a>Hinweise

Die Mitgliedsfunktion gibt ein Iterator zurück, der sich auf ein Element im Multiset bezieht, dessen Schlüssel dem Argument `key` unter einem binären Prädikat entspricht, das eine Sortierung basierend auf einer kleiner-als-Vergleichbarkeitsbeziehung einleitet.

Wird der Rückgabewert von **find** einem **const_iterator** zugewiesen, kann das Multiset-Objekt nicht geändert werden. Wird der Rückgabewert von **find** einem **Iterator** zugewiesen, kann das Multiset-Objekt geändert werden.

### <a name="example"></a>Beispiel

```cpp
// compile with: /EHsc /W4 /MTd
#include <set>
#include <iostream>
#include <vector>
#include <string>

using namespace std;

template <typename T> void print_elem(const T& t) {
    cout << "(" << t << ") ";
}

template <typename T> void print_collection(const T& t) {
    cout << t.size() << " elements: ";

    for (const auto& p : t) {
        print_elem(p);
    }
    cout << endl;
}

template <typename C, class T> void findit(const C& c, T val) {
    cout << "Trying find() on value " << val << endl;
    auto result = c.find(val);
    if (result != c.end()) {
        cout << "Element found: "; print_elem(*result); cout << endl;
    } else {
        cout << "Element not found." << endl;
    }
}

int main()
{
    multiset<int> s1({ 40, 45 });
    cout << "The starting multiset s1 is: " << endl;
    print_collection(s1);

    vector<int> v;
    v.push_back(43);
    v.push_back(41);
    v.push_back(46);
    v.push_back(42);
    v.push_back(44);
    v.push_back(44); // attempt a duplicate

    cout << "Inserting the following vector data into s1: " << endl;
    print_collection(v);

    s1.insert(v.begin(), v.end());

    cout << "The modified multiset s1 is: " << endl;
    print_collection(s1);
    cout << endl;
    findit(s1, 45);
    findit(s1, 6);
}
```

## <a name="get_allocator"></a> multiset::get_allocator

Gibt eine Kopie des Zuweisungsobjekts zurück, das zum Erstellen der Multimenge verwendet wird.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Rückgabewert

Die von der Multimenge verwendete Zuweisung.

### <a name="remarks"></a>Hinweise

Zuweisungen für die Multiset-Klasse geben an, wie die Klasse Speicherplatz verwaltet. Für die meisten Programmieranforderungen reichen die Standardzuweisungen mit C++-Standardbibliothek-Container-Klassen aus. Schreiben und Verwenden Ihrer eigener Zuweisungsklasse ist ein C++ -Thema für Fortgeschrittene.

### <a name="example"></a>Beispiel

```cpp
// multiset_get_allocator.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int>::allocator_type ms1_Alloc;
   multiset <int>::allocator_type ms2_Alloc;
   multiset <double>::allocator_type ms3_Alloc;
   multiset <int>::allocator_type ms4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   multiset <int> ms1;
   multiset <int, allocator<int> > ms2;
   multiset <double, allocator<double> > ms3;

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << ms2.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << ms3.max_size( ) <<  "." << endl;

   // The following lines create a multiset ms4
   // with the allocator of multiset ms1
   ms1_Alloc = ms1.get_allocator( );
   multiset <int> ms4( less<int>( ), ms1_Alloc );
   ms4_Alloc = ms4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated with the other
   if( ms1_Alloc == ms4_Alloc )
   {
      cout << "Allocators are interchangeable."
           << endl;
   }
   else
   {
      cout << "Allocators are not interchangeable."
           << endl;
   }
}
```

## <a name="insert"></a> multiset::insert

Fügt ein Element oder einen Elementbereich in eine Multimenge ein.

```cpp
// (1) single element
pair<iterator, bool> insert(
    const value_type& Val);


// (2) single element, perfect forwarded
template <class ValTy>
pair<iterator, bool>
insert(
    ValTy&& Val);


// (3) single element with hint
iterator insert(
    const_iterator Where,
    const value_type& Val);


// (4) single element, perfect forwarded, with hint
template <class ValTy>
iterator insert(
    const_iterator Where,
    ValTy&& Val);


// (5) range
template <class InputIterator>
void insert(
    InputIterator First,
    InputIterator Last);


// (6) initializer list
void insert(
    initializer_list<value_type>
IList);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`Val`|Der Wert eines in die Multimenge einzufügenden Elements.|
|`Where`|Die Position, an dem mit der Suche nach dem richtigen Einfügepunkt begonnen wird. (Wenn dieser Punkt `Where` direkt vorausgeht, kann die Einfügung in amortisierter konstanter Zeit anstelle von logarithmischer Zeit eintreten.)|
|`ValTy`|Der Vorlagenparameter, mit dem der Argumenttyp angegeben wird, der von der Multimenge verwendet werden kann, um ein Element von [value_type](../standard-library/map-class.md#value_type) zu erstellen und `Val` perfekt als Argument weiterzuleiten.|
|`First`|Die Position des ersten zu kopierenden Elements.|
|`Last`|Die Position direkt über den letzten zu kopierenden Elements.|
|`InputIterator`|Das Vorlagenfunktionsargument, das den Anforderungen eines [Eingabeiterators](../standard-library/input-iterator-tag-struct.md) erfüllt, der auf Elemente eines Typs zeigt, der zum Erstellen von [value_type](../standard-library/map-class.md#value_type)-Objekten verwendet werden kann.|
|`IList`|Das [initializer_list](../standard-library/initializer-list.md)-Element, aus dem die Elemente kopiert werden sollen.|

### <a name="return-value"></a>Rückgabewert

Die Einzelelement-Memberfunktionen (1) und (2) geben einen Iterator an die Position zurück, an der das neue Element in die Multimenge eingefügt wurde.

Die Einzelelement-Memberfunktionen mit Hinweis (3) und (4) geben einen Iterator zurück, der auf die Position zeigt, an der das neue Element in die Multimenge eingefügt wurde.

### <a name="remarks"></a>Hinweise

Von dieser Funktion werden keine Zeiger oder Verweise für ungültig erklärt, aber möglicherweise werden alle Iteratoren für den Containers für ungültig erklärt.

Wird beim Einfügen von nur einem Element eine Ausnahme ausgelöst, wird der Zustand des Containers nicht geändert. Wird beim Einfügen mehrerer Elementen eine Ausnahme ausgelöst, wird der Container in einem nicht angegebenen doch gültigen Zustand belassen.

Das [value_type](../standard-library/map-class.md#value_type)-Element eines Containers ist eine Typedef, die dem Container angehört. Bei einer Menge ist `multiset<V>::value_type` Typ `const V`.

Die Bereichsmemberfunktion (5) fügt die Sequenz von Elementwerten in eine Multimenge ein, die jedem Element entspricht, das von einem Iterator im Bereich `[First, Last)` adressiert wird. Daher wird `Last` nicht eingefügt. Die Containermemberfunktion `end()` bezieht sich auf die Position direkt hinter dem letzten Element im Container. Z. B fügt die Anweisung `s.insert(v.begin(), v.end());` alle Elemente von `v` in `s` ein.

Die Memberfunktion (6) der Initialisiererliste verwendet ein [initializer_list](../standard-library/initializer-list.md)-Element, um Elemente in die Zuordnung zu kopieren.

Informationen zum Einfügen eines lokal erstellten Elements (d.h. wenn keine Kopier- oder Verschiebevorgänge ausgeführt werden) finden Sie unter [multiset::emplace](#emplace) und [multiset::emplace_hint](#emplace_hint).

### <a name="example"></a>Beispiel

```cpp
// multiset_insert.cpp
// compile with: /EHsc
#include <set>
#include <iostream>
#include <string>
#include <vector>

using namespace std;

template <typename S> void print(const S& s) {
    cout << s.size() << " elements: ";

    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }

    cout << endl;
}

int main()
{

    // insert single values
    multiset<int> s1;
    // call insert(const value_type&) version
    s1.insert({ 1, 10 });
    // call insert(ValTy&&) version
    s1.insert(20);

    cout << "The original multiset values of s1 are:" << endl;
    print(s1);

    // intentionally attempt a duplicate, single element
    s1.insert(1);
    cout << "The modified multiset values of s1 are:" << endl;
    print(s1);
    cout << endl;

    // single element, with hint
    s1.insert(s1.end(), 30);
    cout << "The modified multiset values of s1 are:" << endl;
    print(s1);
    cout << endl;

    // The templatized version inserting a jumbled range
    multiset<int> s2;
    vector<int> v;
    v.push_back(43);
    v.push_back(294);
    v.push_back(41);
    v.push_back(330);
    v.push_back(42);
    v.push_back(45);

    cout << "Inserting the following vector data into s2:" << endl;
    print(v);

    s2.insert(v.begin(), v.end());

    cout << "The modified multiset values of s2 are:" << endl;
    print(s2);
    cout << endl;

    // The templatized versions move-constructing elements
    multiset<string>  s3;
    string str1("blue"), str2("green");

    // single element
    s3.insert(move(str1));
    cout << "After the first move insertion, s3 contains:" << endl;
    print(s3);

    // single element with hint
    s3.insert(s3.end(), move(str2));
    cout << "After the second move insertion, s3 contains:" << endl;
    print(s3);
    cout << endl;

    multiset<int> s4;
    // Insert the elements from an initializer_list
    s4.insert({ 4, 44, 2, 22, 3, 33, 1, 11, 5, 55 });
    cout << "After initializer_list insertion, s4 contains:" << endl;
    print(s4);
    cout << endl;
}

```

## <a name="iterator"></a> multiset::iterator

Ein Typ, der einen konstanten [bidirektionalen Iterator](../standard-library/bidirectional-iterator-tag-struct.md) bereitstellt, mit dem alle Elemente in einer Multimenge gelesen oder geändert werden können.

```cpp
typedef implementation-defined iterator;
```

### <a name="example"></a>Beispiel

Im Beispiel für [begin](#begin) wird verdeutlicht, wie ein **iterator**-Element deklariert und verwendet wird.

## <a name="key_comp"></a> multiset::key_comp

Ruft eine Kopie des Vergleichsobjekts ab, das zum Sortieren der Schlüssel in einer Multimenge verwendet wird.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt das Funktionsobjekt zurück, das dem Vorlagenparameter `Compare` entspricht und von einer Multimenge verwendet wird, um die jeweiligen Elemente zu sortieren.

Weitere Informationen zu `Compare` finden Sie im Abschnitt „Hinweise“ unter [multiset-Klasse](../standard-library/multiset-class.md).

### <a name="remarks"></a>Hinweise

Das gespeicherte Objekt definiert die Memberfunktion

**bool operator**( **const Key&** *x*, **const Key&** *y*);

Sie gibt nur dann TRUE zurück, wenn *x* in der Sortierreihenfolge *y* vorausgeht.

[key_compare](#key_compare) und [value_compare](#value_compare) sind Synonyme für den Vorlagenparameter `Compare`. Beide Typen werden für die Klassen „set“ und „multiset“ bereitgestellt, in denen sie identisch sind. Dies geschieht zum Zweck der Kompatibilität mit den Klassen „map“ und „multimap“, in denen sie sich unterscheiden.

### <a name="example"></a>Beispiel

```cpp
// multiset_key_comp.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;

   multiset <int, less<int> > ms1;
   multiset <int, less<int> >::key_compare kc1 = ms1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of s1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of ms1."
           << endl;
   }

   multiset <int, greater<int> > ms2;
   multiset <int, greater<int> >::key_compare kc2 = ms2.key_comp( ) ;
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of ms2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of ms2."
           << endl;
   }
}
```

```Output
kc1( 2,3 ) returns value of true, where kc1 is the function object of s1.
kc2( 2,3 ) returns value of false, where kc2 is the function object of ms2.
```

## <a name="key_compare"></a> multiset::key_compare

Ein Typ, der ein Funktionsobjekt bereitstellt, das zwei Sortierschlüssel vergleichen kann, um die relative Reihenfolge zweier Elemente in der Multimenge zu bestimmen.

```cpp
typedef Compare key_compare;
```

### <a name="remarks"></a>Hinweise

**key_compare** ist ein Synonym für den Vorlagenparameter `Compare`.

Weitere Informationen zu `Compare` finden Sie im Abschnitt „Hinweise“ unter [multiset-Klasse](../standard-library/multiset-class.md).

### <a name="example"></a>Beispiel

Im Beispiel für [key_comp](#key_comp) wird verdeutlicht, wie `key_compare` deklariert und verwendet wird.

## <a name="key_type"></a> multiset::key_type

Ein Typ, der ein Funktionsobjekt bereitstellt, das zwei Sortierschlüssel vergleichen kann, um die relative Reihenfolge zweier Elemente in der Multimenge zu bestimmen.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Hinweise

`key_type` ist ein Synonym für den Vorlagenparameter `Key`.

Weitere Informationen zu `Key` finden Sie im Abschnitt „Hinweise“ unter [multiset-Klasse](../standard-library/multiset-class.md).

### <a name="example"></a>Beispiel

Im Beispiel für [value_type](#value_type) wird verdeutlicht, wie `key_type` deklariert und verwendet wird.

## <a name="lower_bound"></a> multiset::lower_bound

Gibt einen Iterator an das erste Element in einer Multimenge mit einem Schlüssel zurück, der mindestens so groß wie ein benutzerdefinierter Schlüssel ist.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Parameter

`key` Der Argumentschlüssel mit dem Sortierschlüssel eines Elements aus dem durchsuchten Multiset verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein **Iterator** oder ein `const_iterator`, der entweder den Speicherort eines Elements in einer Multimenge mit einem Schlüssel adressiert, der mindestens so groß ist wie der Argumentschlüssel, oder der, wenn für den Schlüssel keine Übereinstimmung gefunden wird, den Speicherort adressiert, der dem letzten Element in der Multimenge folgt.

### <a name="example"></a>Beispiel

```cpp
// multiset_lower_bound.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int> :: const_iterator ms1_AcIter, ms1_RcIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_RcIter = ms1.lower_bound( 20 );
   cout << "The element of multiset ms1 with a key of 20 is: "
        << *ms1_RcIter << "." << endl;

   ms1_RcIter = ms1.lower_bound( 40 );

   // If no match is found for the key, end( ) is returned
   if ( ms1_RcIter == ms1.end( ) )
      cout << "The multiset ms1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of multiset ms1 with a key of 40 is: "
           << *ms1_RcIter << "." << endl;

   // The element at a specific location in the multiset can be
   // found using a derefenced iterator addressing the location
   ms1_AcIter = ms1.end( );
   ms1_AcIter--;
   ms1_RcIter = ms1.lower_bound( *ms1_AcIter );
   cout << "The element of ms1 with a key matching "
        << "that of the last element is: "
        << *ms1_RcIter << "." << endl;
}
```

```Output
The element of multiset ms1 with a key of 20 is: 20.
The multiset ms1 doesn't have an element with a key of 40.
The element of ms1 with a key matching that of the last element is: 30.
```

## <a name="max_size"></a> multiset::max_size

Gibt die Maximallänge der Multimenge zurück.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Rückgabewert

Die maximal mögliche Länge der Multimenge.

### <a name="example"></a>Beispiel

```cpp
// multiset_max_size.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::size_type i;

   i = ms1.max_size( );
   cout << "The maximum possible length "
        << "of the multiset is " << i << "." << endl;
}
```

## <a name="multiset"></a> multiset::multiset

Erstellt eine Multimenge, die leer oder die Kopie einer ganzen anderen Multimenge oder eines Teils davon ist.

```cpp
multiset();

explicit multiset (
    const Compare& Comp);

multiset (
    const Compare& Comp,
    const Allocator& Al);

multiset(
    const multiset& Right);

multiset(
    multiset&& Right);

multiset(
    initializer_list<Type> IList);

multiset(
    initializer_list<Type> IList,
    const Compare& Comp);

multiset(
    initializer_list<Type> IList,
    const Compare& Comp,
    const Allocator& Al);


template <class InputIterator>
multiset (
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
multiset (
    InputIterator First,
    InputIterator Last,
    const Compare& Comp);

template <class InputIterator>
multiset (
    InputIterator First,
    InputIterator Last,
    const Compare& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`Al`|Die für dieses multiset-Objekt zu verwendende Speicherzuweisungsklasse, dessen Standard `Allocator` ist.|
|`Comp`|Die Vergleichsfunktion des Typs `const Compare`, die verwendet wird, um die Elemente in der Multimenge, deren Standard `Compare` ist, zu sortieren.|
|`Right`|Die Multimenge, deren Kopie die erstellte Multimenge ist.|
|`First`|Die Position des ersten Elements in dem zu kopierenden Elementbereich.|
|`Last`|Die Position des ersten Elements nach dem zu kopierenden Elementbereich.|
|`IList`|Das initializer_list-Element, aus dem die Elemente kopiert werden sollen.|

### <a name="remarks"></a>Hinweise

Alle Konstruktoren speichern ein Zuweisungsobjekt eines bestimmten Typs, das Arbeitsspeicher für die Multimenge verwaltet und später zurückgegeben werden kann, indem [get_allocator](#get_allocator) aufgerufen wird. Der Zuweisungsparameter wird häufig aus den Klassendeklarationen und den Vorverarbeitungsmakros weggelassen, die zum Ersetzen alternativer Zuweisungen verwendet werden.

Alle Konstruktoren initialisieren ihre Multimenge.

Alle Konstruktoren speichern ein Funktionsobjekt des Typs „Compare“, mit dem sich die Schlüssel der Multimenge sortieren lassen und das später zurückgegeben werden kann, indem [key_comp](#key_comp) aufgerufen wird.

Die ersten drei Konstruktoren geben eine leere ursprüngliche Multimenge an. Der zweite Konstruktor gibt den Typ der Vergleichsfunktion ( `Comp`) an, die zum Festlegen der Reihenfolge der Elemente verwendet werden soll, und der dritte Konstruktor gibt explizit den zu verwendenden Zuweisungstyp ( `Al`) an. Mit dem Schlüsselwort `explicit` werden bestimmte Arten automatischer Typumwandlung unterdrückt.

Der vierte Konstruktor gibt eine Kopie der Multimenge `Right` an.

Der fünfte Konstruktor gibt eine Kopie der Multimenge an, indem `Right` verschoben wird.

Die sechsten, siebten und achten Konstruktoren geben ein initializer_list-Element an, aus dem die Elemente kopiert werden.

Mit den folgenden drei Konstruktoren wird der `[First, Last)`-Bereich einer Multimenge kopiert, wobei sich die Explizitheit bei Angabe des Typs der Vergleichsfunktion und der Zuweisung erhöht.

### <a name="example"></a>Beispiel

```cpp
// multiset_ctor.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
{
    using namespace std;
    //multiset <int>::iterator ms1_Iter, ms2_Iter, ms3_Iter;
    multiset <int>::iterator ms4_Iter, ms5_Iter, ms6_Iter, ms7_Iter;

    // Create an empty multiset ms0 of key type integer
    multiset <int> ms0;

    // Create an empty multiset ms1 with the key comparison
    // function of less than, then insert 4 elements
    multiset <int, less<int> > ms1;
    ms1.insert(10);
    ms1.insert(20);
    ms1.insert(20);
    ms1.insert(40);

    // Create an empty multiset ms2 with the key comparison
    // function of geater than, then insert 2 elements
    multiset <int, less<int> > ms2;
    ms2.insert(10);
    ms2.insert(20);

    // Create a multiset ms3 with the
    // allocator of multiset ms1
    multiset <int>::allocator_type ms1_Alloc;
    ms1_Alloc = ms1.get_allocator();
    multiset <int> ms3(less<int>(), ms1_Alloc);
    ms3.insert(30);

    // Create a copy, multiset ms4, of multiset ms1
    multiset <int> ms4(ms1);

    // Create a multiset ms5 by copying the range ms1[ first,  last)
    multiset <int>::const_iterator ms1_bcIter, ms1_ecIter;
    ms1_bcIter = ms1.begin();
    ms1_ecIter = ms1.begin();
    ms1_ecIter++;
    ms1_ecIter++;
    multiset <int> ms5(ms1_bcIter, ms1_ecIter);

    // Create a multiset ms6 by copying the range ms4[ first,  last)
    // and with the allocator of multiset ms2
    multiset <int>::allocator_type ms2_Alloc;
    ms2_Alloc = ms2.get_allocator();
    multiset <int> ms6(ms4.begin(), ++ms4.begin(), less<int>(), ms2_Alloc);

    cout << "ms1 =";
    for (auto i : ms1)
        cout << " " << i;
    cout << endl;

    cout << "ms2 =";
    for (auto i : ms2)
        cout << " " << i;
   cout << endl;

   cout << "ms3 =";
   for (auto i : ms3)
       cout << " " << i;
    cout << endl;

    cout << "ms4 =";
    for (auto i : ms4)
        cout << " " << i;
    cout << endl;

    cout << "ms5 =";
    for (auto i : ms5)
        cout << " " << i;
    cout << endl;

    cout << "ms6 =";
    for (auto i : ms6)
        cout << " " << i;
    cout << endl;

    // Create a multiset by moving ms5
    multiset<int> ms7(move(ms5));
    cout << "ms7 =";
    for (auto i : ms7)
        cout << " " << i;
    cout << endl;

    // Create a multiset with an initializer_list
    multiset<int> ms8({1, 2, 3, 4});
    cout << "ms8=";
    for (auto i : ms8)
        cout << " " << i;
    cout << endl;
}
```

## <a name="op_eq"></a> multiset::operator=

Ersetzt die Elemente dieses `multiset` mithilfe von Elementen eines anderen `multiset`.

```cpp
multiset& operator=(const multiset& right);

multiset& operator=(multiset&& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`right`|Das `multiset`-Element, aus dem Elemente kopiert oder verschoben werden.|

### <a name="remarks"></a>Hinweise

`operator=` kopiert oder verschiebt die Elemente in `right` je nach Referenztyp (l-Wert oder r-Wert) in dieses `multiset`. Elemente, die sich vor dem Ausführen von `operator=` in diesem `multiset` befinden, werden verworfen.

### <a name="example"></a>Beispiel

```cpp
// multiset_operator_as.cpp
// compile with: /EHsc
#include <multiset>
#include <iostream>

int main( )
   {
   using namespace std;
   multiset<int> v1, v2, v3;
   multiset<int>::iterator iter;

   v1.insert(10);

   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << *iter << " ";
   cout << endl;

   v2 = v1;
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << *iter << " ";
   cout << endl;

// move v1 into v2
   v2.clear();
   v2 = move(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << *iter << " ";
   cout << endl;
   }
```

## <a name="pointer"></a> multiset::pointer

Ein Typ, der einen Zeiger auf ein Element in einer Multimenge bereitstellt.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Hinweise

Ein **pointer**-Typ kann zum Ändern des Werts eines Elements verwendet werden.

In den meisten Fällen sollte ein [iterator](#iterator)-Typ für den Zugriff auf Elemente in einem Multiset-Objekt verwendet werden.

## <a name="rbegin"></a> multiset::rbegin

Gibt einen Iterator zurück, der das erste Element in einem umgekehrten Multiset adressiert.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Rückgabewert

Ein umgekehrter bidirektionaler Iterator, mit dem das erste Element in einem umgekehrten Multiset adressiert wird bzw. mit dem das ehemals letzte Element in dem nicht umgekehrten Multiset adressiert wird.

### <a name="remarks"></a>Hinweise

`rbegin` wird bei einer umgekehrten Multimenge auf dieselbe Weise wie „rbegin“ bei einer Multimenge verwendet.

Wenn der Rückgabewert von `rbegin` einem `const_reverse_iterator`zugewiesen wird, kann das Multisetobjekt nicht geändert werden. Wenn der Rückgabewert von `rbegin` einem `reverse_iterator`zugewiesen wird, kann das Multisetobjekt geändert werden.

Mit `rbegin` lässt sich eine Multimenge rückwärts durchlaufen.

### <a name="example"></a>Beispiel

```cpp
// multiset_rbegin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;
   multiset <int>::reverse_iterator ms1_rIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_rIter = ms1.rbegin( );
   cout << "The first element in the reversed multiset is "
        << *ms1_rIter << "." << endl;

   // begin can be used to start an interation
   // throught a multiset in a forward order
   cout << "The multiset is:";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << endl;

   // rbegin can be used to start an interation
   // throught a multiset in a reverse order
   cout << "The reversed multiset is:";
   for ( ms1_rIter = ms1.rbegin( ) ; ms1_rIter != ms1.rend( ); ms1_rIter++ )
      cout << " " << *ms1_rIter;
   cout << endl;

   // A multiset element can be erased by dereferencing to its key
   ms1_rIter = ms1.rbegin( );
   ms1.erase ( *ms1_rIter );

   ms1_rIter = ms1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed multiset is "<< *ms1_rIter << "."
        << endl;
}
```

```Output
The first element in the reversed multiset is 30.
The multiset is: 10 20 30
The reversed multiset is: 30 20 10
After the erasure, the first element in the reversed multiset is 20.
```

## <a name="reference"></a> multiset::reference

Ein Typ, der auf ein in einer Multimenge gespeichertes Element verweist.

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="example"></a>Beispiel

```cpp
// multiset_ref.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;

   ms1.insert( 10 );
   ms1.insert( 20 );

   // Declare and initialize a reference &Ref1 to the 1st element
   const int &Ref1 = *ms1.begin( );

   cout << "The first element in the multiset is "
        << Ref1 << "." << endl;
}
```

```Output
The first element in the multiset is 10.
```

## <a name="rend"></a> multiset::rend

Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element in einer umgekehrten Multimenge folgt.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Rückgabewert

Ein bidirektionaler const_reverse-Iterator, der den Speicherort adressiert, der dem letzten Element in einer umgekehrten Multimenge folgt (d.h. den Speicherort, der dem ersten Element in der nicht umgekehrten Multimenge vorangegangen war).

### <a name="remarks"></a>Hinweise

`rend` wird bei einer umgekehrten Multimenge auf dieselbe Weise wie [end](#end) bei einer Multimenge verwendet.

Wenn der Rückgabewert von `rend` einem `const_reverse_iterator` zugewiesen wird, kann das Multiset-Objekt nicht geändert werden. Wenn der Rückgabewert von `rend` einem `reverse_iterator` zugewiesen wird, kann das Multiset-Objekt geändert werden.

Mit `rend` lässt sich überprüfen, ob ein umgekehrter Iterator das Ende seiner Multimenge erreicht hat.

Der von `rend` zurückgegebene Wert darf nicht dereferenziert werden.

### <a name="example"></a>Beispiel

```cpp
// multiset_rend.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main() {
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;
   multiset <int>::reverse_iterator ms1_rIter;
   multiset <int>::const_reverse_iterator ms1_crIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_rIter = ms1.rend( ) ;
   ms1_rIter--;
   cout << "The last element in the reversed multiset is "
        << *ms1_rIter << "." << endl;

   // end can be used to terminate an interation
   // throught a multiset in a forward order
   cout << "The multiset is: ";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << *ms1_Iter << " ";
   cout << "." << endl;

   // rend can be used to terminate an interation
   // throught a multiset in a reverse order
   cout << "The reversed multiset is: ";
   for ( ms1_rIter = ms1.rbegin( ) ; ms1_rIter != ms1.rend( ); ms1_rIter++ )
      cout << *ms1_rIter << " ";
   cout << "." << endl;

   ms1_rIter = ms1.rend( );
   ms1_rIter--;
   ms1.erase ( *ms1_rIter );

   ms1_rIter = ms1.rend( );
   --ms1_rIter;
   cout << "After the erasure, the last element in the "
        << "reversed multiset is " << *ms1_rIter << "." << endl;
}
```

## <a name="reverse_iterator"></a> multiset::reverse_iterator

Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem ein Element in einer umgekehrten Multimenge gelesen oder geändert werden kann.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Hinweise

Mit einem `reverse_iterator`-Typ lässt sich die Multimenge in umgekehrter Reihenfolge durchlaufen.

### <a name="example"></a>Beispiel

Im Beispiel für [rbegin](#rbegin) wird verdeutlicht, wie `reverse_iterator` deklariert und verwendet wird.

## <a name="size"></a> multiset::size

Gibt die Anzahl von Elementen in der Multimenge zurück.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Länge der Multimenge.

### <a name="example"></a>Beispiel

```cpp
// multiset_size.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int> :: size_type i;

   ms1.insert( 1 );
   i = ms1.size( );
   cout << "The multiset length is " << i << "." << endl;

   ms1.insert( 2 );
   i = ms1.size( );
   cout << "The multiset length is now " << i << "." << endl;
}
```

```Output
The multiset length is 1.
The multiset length is now 2.
```

## <a name="size_type"></a> multiset::size_type

Ein Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in einer Multimenge darstellen kann.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Beispiel

Im Beispiel für [size](#size) wird verdeutlicht, wie `size_type` deklariert und verwendet wird.

## <a name="swap"></a> multiset::swap

Tauscht die Elemente zweier Multimengen aus.

```cpp
void swap(
    multiset<Key, Compare, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`right` Die Argument-Multimenge Elemente mit dem Ziel Multiset ausgetauscht werden sollen.

### <a name="remarks"></a>Hinweise

Die Memberfunktion macht keine Verweise, Zeiger oder Iteratoren ungültig, die Elemente in zwei Multimengen bezeichnen, deren Elemente ausgetauscht werden.

### <a name="example"></a>Beispiel

```cpp
// multiset_swap.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1, ms2, ms3;
   multiset <int>::iterator ms1_Iter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );
   ms2.insert( 100 );
   ms2.insert( 200 );
   ms3.insert( 300 );

   cout << "The original multiset ms1 is:";
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << "." << endl;

   // This is the member function version of swap
   ms1.swap( ms2 );

   cout << "After swapping with ms2, list ms1 is:";
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << "." << endl;

   // This is the specialized template version of swap
   swap( ms1, ms3 );

   cout << "After swapping with ms3, list ms1 is:";
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout   << "." << endl;
}
```

```Output
The original multiset ms1 is: 10 20 30.
After swapping with ms2, list ms1 is: 100 200.
After swapping with ms3, list ms1 is: 300.
```

## <a name="upper_bound"></a> multiset::upper_bound

Gibt einen Iterator an das erste Element in einer Multimenge mit einem Schlüssel zurück, der größer als ein benutzerdefinierter Schlüssel ist.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Parameter

`key` Der Argumentschlüssel mit dem Sortierschlüssel eines Elements aus dem durchsuchten Multiset verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**Iteratoren** oder `const_iterator`-Elemente, die entweder den Speicherort eines Elements in einer Multimenge mit einem Schlüssel adressieren, der größer ist als der Argumentschlüssel, oder die, wenn für den Schlüssel keine Übereinstimmung gefunden wird, den Speicherort adressieren, der dem letzten Element in der Multimenge folgt.

### <a name="example"></a>Beispiel

```cpp
// multiset_upper_bound.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int> :: const_iterator ms1_AcIter, ms1_RcIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_RcIter = ms1.upper_bound( 20 );
   cout << "The first element of multiset ms1 with a key greater "
           << "than 20 is: " << *ms1_RcIter << "." << endl;

   ms1_RcIter = ms1.upper_bound( 30 );

   // If no match is found for the key, end( ) is returned
   if ( ms1_RcIter == ms1.end( ) )
      cout << "The multiset ms1 doesn't have an element "
              << "with a key greater than 30." << endl;
   else
      cout << "The element of multiset ms1 with a key > 40 is: "
           << *ms1_RcIter << "." << endl;

   // The element at a specific location in the multiset can be
   // found using a dereferenced iterator addressing the location
   ms1_AcIter = ms1.begin( );
   ms1_RcIter = ms1.upper_bound( *ms1_AcIter );
   cout << "The first element of ms1 with a key greater than"
        << endl << "that of the initial element of ms1 is: "
        << *ms1_RcIter << "." << endl;
}
```

```Output
The first element of multiset ms1 with a key greater than 20 is: 30.
The multiset ms1 doesn't have an element with a key greater than 30.
The first element of ms1 with a key greater than
that of the initial element of ms1 is: 20.
```

## <a name="value_comp"></a> multiset::value_comp

Ruft eine Kopie des Vergleichsobjekts ab, das zum Sortieren der Elementwerte in einer Multimenge verwendet wird.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt das Funktionsobjekt zurück, das dem Vorlagenparameter `Compare` entspricht und von einer Multimenge verwendet wird, um die jeweiligen Elemente zu sortieren.

Weitere Informationen zu `Compare` finden Sie im Abschnitt „Hinweise“ unter [multiset-Klasse](../standard-library/multiset-class.md).

### <a name="remarks"></a>Hinweise

Das gespeicherte Objekt definiert die Memberfunktion:

**bool operator**( **const Key&**`_xVal`, **const Key&**`_yVal`);

Sie gibt nur dann TRUE zurück, wenn `_xVal` in der Sortierreihenfolge `_yVal` vorausgeht und sich davon unterscheidet.

[key_compare](#key_compare) und [value_compare](#value_compare) sind Synonyme für den Vorlagenparameter `Compare`. Beide Typen werden für die Klassen „set“ und „multiset“ bereitgestellt, in denen sie identisch sind. Dies geschieht zum Zweck der Kompatibilität mit den Klassen „map“ und „multimap“, in denen sie sich unterscheiden.

### <a name="example"></a>Beispiel

```cpp
// multiset_value_comp.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;

   multiset <int, less<int> > ms1;
   multiset <int, less<int> >::value_compare vc1 = ms1.value_comp( );
   bool result1 = vc1( 2, 3 );
   if( result1 == true )
   {
      cout << "vc1( 2,3 ) returns value of true, "
           << "where vc1 is the function object of ms1."
           << endl;
   }
   else
   {
      cout << "vc1( 2,3 ) returns value of false, "
           << "where vc1 is the function object of ms1."
           << endl;
   }

   set <int, greater<int> > ms2;
   set<int, greater<int> >::value_compare vc2 = ms2.value_comp( );
   bool result2 = vc2( 2, 3 );
   if( result2 == true )
   {
      cout << "vc2( 2,3 ) returns value of true, "
           << "where vc2 is the function object of ms2."
           << endl;
   }
   else
   {
      cout << "vc2( 2,3 ) returns value of false, "
           << "where vc2 is the function object of ms2."
           << endl;
   }
}
```

```Output
vc1( 2,3 ) returns value of true, where vc1 is the function object of ms1.
vc2( 2,3 ) returns value of false, where vc2 is the function object of ms2.
```

## <a name="value_compare"></a> multiset::value_compare

Der Typ, der ein Funktionsobjekt bereitstellt, das zwei Sortierschlüssel vergleichen kann, um ihre relative Reihenfolge in der Multimenge zu bestimmen.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Hinweise

`value_compare` ist ein Synonym für den Vorlagenparameter `Compare`.

[key_compare](#key_compare) und **value_compare** sind Synonyme für den Vorlagenparameter `Compare`. Beide Typen werden für die Klassen „set“ und „multiset“ bereitgestellt, in denen sie identisch sind. Dies geschieht zum Zweck der Kompatibilität mit den Klassen „map“ und „multimap“, in denen sie sich unterscheiden.

Weitere Informationen zu `Compare` finden Sie im Abschnitt „Hinweise“ unter [multiset-Klasse](../standard-library/multiset-class.md).

### <a name="example"></a>Beispiel

Im Beispiel für [value_comp](#value_comp) wird verdeutlicht, wie `value_compare` deklariert und verwendet wird.

## <a name="value_type"></a> multiset::value_type

Ein Typ, der in seiner Funktion als Wert ein als Element gespeichertes Objekt als Multimenge beschreibt.

```cpp
typedef Key value_type;
```

### <a name="remarks"></a>Hinweise

`value_type` ist ein Synonym für den Vorlagenparameter `Key`.

[key_type](#key_type) und `value_type` sind Synonyme für den Vorlagenparameter **Key**. Beide Typen werden für die Klassen „set“ und „multiset“ bereitgestellt, in denen sie identisch sind. Dies geschieht zum Zweck der Kompatibilität mit den Klassen „map“ und „multimap“, in denen sie sich unterscheiden.

Weitere Informationen zu `Key` finden Sie im Abschnitt „Hinweise“.

### <a name="example"></a>Beispiel

```cpp
// multiset_value_type.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;

   multiset <int> :: value_type svt_Int;   // Declare value_type
   svt_Int = 10;             // Initialize value_type

   multiset <int> :: key_type skt_Int;   // Declare key_type
   skt_Int = 20;             // Initialize key_type

   ms1.insert( svt_Int );         // Insert value into s1
   ms1.insert( skt_Int );         // Insert key into s1

   // A multiset accepts key_types or value_types as elements
   cout << "The multiset has elements:";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << "." << endl;
}
```

```Output
The multiset has elements: 10 20.
```

## <a name="see-also"></a>Siehe auch

[\<Legen Sie > Elemente](http://msdn.microsoft.com/en-us/0c2d57c0-173f-4204-b579-c5f06aad8b95)<br/>
[Container](../cpp/containers-modern-cpp.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
