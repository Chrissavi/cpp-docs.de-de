---
title: vector-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- vector/std::vector::allocator_type
- vector/std::vector::const_iterator
- vector/std::vector::const_pointer
- vector/std::vector::const_reference
- vector/std::vector::const_reverse_iterator
- vector/std::vector::difference_type
- vector/std::vector::iterator
- vector/std::vector::pointer
- vector/std::vector::reference
- vector/std::vector::reverse_iterator
- vector/std::vector::size_type
- vector/std::vector::value_type
- vector/std::vector::assign
- vector/std::vector::at
- vector/std::vector::back
- vector/std::vector::begin
- vector/std::vector::capacity
- vector/std::vector::cbegin
- vector/std::vector::cend
- vector/std::vector::crbegin
- vector/std::vector::crend
- vector/std::vector::clear
- vector/std::vector::data
- vector/std::vector::emplace
- vector/std::vector::emplace_back
- vector/std::vector::empty
- vector/std::vector::end
- vector/std::vector::erase
- vector/std::vector::front
- vector/std::vector::get_allocator
- vector/std::vector::insert
- vector/std::vector::max_size
- vector/std::vector::pop_back
- vector/std::vector::push_back
- vector/std::vector::rbegin
- vector/std::vector::rend
- vector/std::vector::reserve
- vector/std::vector::resize
- vector/std::vector::shrink_to_fit
- vector/std::vector::size
- vector/std::vector::swap
dev_langs:
- C++
helpviewer_keywords:
- std::vector [C++], allocator_type
- std::vector [C++], const_iterator
- std::vector [C++], const_pointer
- std::vector [C++], const_reference
- std::vector [C++], const_reverse_iterator
- std::vector [C++], difference_type
- std::vector [C++], iterator
- std::vector [C++], pointer
- std::vector [C++], reference
- std::vector [C++], reverse_iterator
- std::vector [C++], size_type
- std::vector [C++], value_type
- std::vector [C++], assign
- std::vector [C++], at
- std::vector [C++], back
- std::vector [C++], begin
- std::vector [C++], capacity
- std::vector [C++], cbegin
- std::vector [C++], cend
- std::vector [C++], crbegin
- std::vector [C++], crend
- std::vector [C++], clear
- std::vector [C++], data
- std::vector [C++], emplace
- std::vector [C++], emplace_back
- std::vector [C++], empty
- std::vector [C++], end
- std::vector [C++], erase
- std::vector [C++], front
- std::vector [C++], get_allocator
- std::vector [C++], insert
- std::vector [C++], max_size
- std::vector [C++], pop_back
- std::vector [C++], push_back
- std::vector [C++], rbegin
- std::vector [C++], rend
- std::vector [C++], reserve
- std::vector [C++], resize
- std::vector [C++], shrink_to_fit
- std::vector [C++], size
- std::vector [C++], swap
ms.assetid: a3e0a8f8-7565-4fe0-93e4-e4d74ae1b70d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ea70adff4f162c432fea96c25e37ecca917d96d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862941"
---
# <a name="vector-class"></a>vector-Klasse

Die Vektorklasse der C++-Standardbibliothek ist eine Vorlagenklasse von Sequenzcontainern, die Elemente eines bestimmten Typs in einer linearen Anordnung organisieren und schnellen, wahlfreien Zugriff auf jedes Element ermöglichen. Sie sollten der jeweils bevorzugte Container für eine Sequenz sein, wenn die Leistung mit wahlfreiem Zugriff ein wichtiger Faktor ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Type, class Allocator = allocator<Type>>
class vector
```

### <a name="parameters"></a>Parameter

*Typ* Elementdatentyp im Vektor gespeichert werden

`Allocator` Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zum Belegen und Freigeben des Arbeitsspeichers des Vektors kapselt. Dieses Argument ist optional, und der Standardwert ist **Allocator ***\<Typ >.*

## <a name="remarks"></a>Hinweise

Vektoren ermöglichen konstante Zeiteinfügungen und -löschungen am Ende der Sequenz. Für das Einfügen oder Löschen von Elementen in der Mitte eines Vektors ist lineare Zeit erforderlich. Der Container der [deque-Klasse](../standard-library/deque-class.md) ist in Bezug auf Einfügungen und Löschungen am Anfang und Ende einer Sequenz leistungsfähiger. Der Container der [list-Klasse](../standard-library/list-class.md) ist in Bezug auf Einfügungen und Löschungen an einer beliebigen Position innerhalb der Sequenz leistungsfähiger.

Eine Speicherneubelegung für einen Vektor findet statt, wenn eine Memberfunktion die Sequenz, die in dem vector-Objekt enthalten ist, über dessen aktuelle Speicherkapazität hinaus vergrößern muss. Andere Einfügungen und Löschungen können verschiedene Speicheradressen innerhalb der Sequenz ändern. In allen diesen Fällen werden Iteratoren oder Verweise auf geänderte Teile der Sequenz ungültig. Wenn keine Neuzuordnung stattfindet, bleiben nur Iteratoren und Verweise vor dem Einfüge-/Löschpunkt gültig.

Die [vector\<bool>-Klasse](../standard-library/vector-bool-class.md) ist eine vollständige Spezialisierung des Vorlagenklassenvektors für Elemente vom Typ „bool“ mit einer Zuweisung für den zugrunde liegenden Typ, der von der Spezialisierung verwendet wird.

Die [vector\<bool> reference-Klasse](../standard-library/vector-bool-class.md#reference_class) ist eine geschachtelte Klasse, deren Objekte Verweise auf Elemente (einzelne Bits) in einem vector\<bool>-Objekt bereitstellen können.

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[vector](#vector)|Erstellt einen Vektor einer bestimmten Größe bzw. mit Elementen eines bestimmten Werts oder mit einem bestimmten `allocator`-Element oder als vollständige bzw. teilweise Kopie eines anderen Vektors.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[allocator_type](#allocator_type)|Ein Typ, der die `allocator`-Klasse für das Vektorobjekt darstellt.|
|[const_iterator](#const_iterator)|Ein Typ, der einen Iterator mit wahlfreiem Zugriff bereitstellt, mit dem ein `const`-Element in einem Vektor gelesen werden kann.|
|[const_pointer](#const_pointer)|Ein Typ, der einen Zeiger auf ein `const`-Element in einem Vektor bereitstellt.|
|[const_reference](#const_reference)|Ein Typ, der einen Verweis auf ein `const`-Element bereitstellt, das in einem Vektor zum Lesen und Ausführen von `const`-Vorgängen gespeichert ist.|
|[const_reverse_iterator](#const_reverse_iterator)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem jedes `const`-Element im Vektor gelesen werden kann.|
|[difference_type](#difference_type)|Ein Typ, der die Differenz zwischen den Adressen von zwei Elementen in einem Vektor bereitstellt.|
|[Iterator](#iterator)|Ein Typ, der einen Iterator mit wahlfreiem Zugriff bereitstellt, mit dem jedes Element in einem Vektor gelesen oder geändert werden kann.|
|[Zeiger](#pointer)|Ein Typ, der einen Zeiger auf ein Element in einem Vektor bereitstellt.|
|[Verweis](#reference)|Ein Typ, der einen Verweis auf ein in einem Vektor gespeichertes Element bereitstellt.|
|[reverse_iterator](#reverse_iterator)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem jedes Element in einem umgekehrten Vektor gelesen oder geändert werden kann.|
|[size_type](#size_type)|Ein Typ, der die Anzahl von Elementen in einem Vektor zählt.|
|[value_type](#value_type)|Ein Typ, der den in einem Vektor gespeicherten Datentyp darstellt.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[assign](#assign)|Löscht einen Vektor und kopiert die angegebenen Elemente in den leeren Vektor.|
|[at](#at)|Gibt einen Verweis auf das Element an einer angegebenen Position in dem Vektor zurück.|
|[back](#back)|Gibt einen Verweis auf das letzte Element des Vektors zurück.|
|[begin](#begin)|Gibt einen Iterator mit wahlfreiem Zugriff für das erste Element im Vektor zurück.|
|[capacity](#capacity)|Gibt die Anzahl von Elementen zurück, die der Vektor enthalten kann, ohne zusätzlichen Speicher zuzuweisen.|
|[cbegin](#cbegin)|Gibt einen const-Iterator mit wahlfreiem Zugriff für das erste Element im Vektor zurück.|
|[cend](#cend)|Gibt einen für wahlfreien Zugriff eingerichteten konstanten Iterator zurück, der unmittelbar hinter das Ende des Vektors zeigt.|
|[crbegin](#crbegin)|Gibt einen const-Iterator zum ersten Element in einem umgekehrten Vektor zurück.|
|[crend](#crend)|Gibt einen const-Iterator zum Ende eines umgekehrten Vektors zurück.|
|[clear](#clear)|Löscht die Elemente des Vektors.|
|[data](#data)|Gibt einen Zeiger auf das erste Element im Vektor zurück.|
|[emplace](#emplace)|Fügt ein direkt konstruiertes Element an einer angegebenen Position in den Vektor ein.|
|[emplace_back](#emplace_back)|Fügt ein direkt konstruiertes Element am Ende des Vektors ein.|
|[empty](#empty)|Testet, ob der Vektorcontainer leer ist.|
|[end](#end)|Gibt einen Iterator mit wahlfreiem Zugriff zurück, der auf das Ende des Vektors zeigt.|
|[erase](#erase)|Entfernt ein Element oder eine Reihe von Elementen aus angegebenen Positionen in einem Vektor.|
|[front](#front)|Gibt einen Verweis auf das erste Element in einem Vektor zurück.|
|[get_allocator](#get_allocator)|Gibt ein Objekt an die `allocator`-Klasse zurück, das von einem Vektor verwendet wird.|
|[insert](#insert)|Fügt ein Element oder eine Reihe von Elementen an einer angegebenen Position in den Vektor ein.|
|[max_size](#max_size)|Gibt die Maximallänge des Vektors zurück.|
|[pop_back](#pop_back)|Löscht das Element am Ende des Vektors.|
|[push_back](#push_back)|Fügt ein Element am Ende des Vektors hinzu.|
|[rbegin](#rbegin)|Gibt einen Iterator an das erste Element in einem umgekeherten Vektor zurück.|
|[rend](#rend)|Gibt einen Iterator zum Ende eines umgekehrten Vektors zurück.|
|[reserve](#reserve)|Reserviert eine Mindestspeicherlänge für ein Vektorobjekt.|
|[resize](#resize)|Gibt eine neue Größe für einen Vektor an.|
|[shrink_to_fit](#shrink_to_fit)|Verwirft Überkapazität.|
|[size](#size)|Gibt die Anzahl von Elementen in dem Vektor zurück.|
|[swap](#swap)|Tauscht die Elemente zweier Vektoren aus.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator&#91;&#93;](#op_at)|Gibt einen Verweis auf das Vektorelement an einer angegebenen Position zurück.|
|[operator=](#op_eq)|Ersetzt die Elemente des Vektors durch eine Kopie eines anderen Vektors.|

## <a name="requirements"></a>Anforderungen

**Header:** \<vector>

**Namespace:** std

## <a name="allocator_type"></a> vector::allocator_type

Ein Typ, der die Zuweisungsklasse für das Vektorobjekt darstellt.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Hinweise

`allocator_type` ist ein Synonym für den Vorlagenparameter **Zuweisung**.

### <a name="example"></a>Beispiel

In dem Beispiel für [get_allocator](#get_allocator) finden Sie ein Beispiel, in dem `allocator_type` verwendet wird.

## <a name="assign"></a> vector::assign

Löscht einen Vektor und kopiert die angegebenen Elemente in den leeren Vektor.

```cpp
void assign(size_type Count, const Type& Val);
void assign(initializer_list<Type> IList);

template <class InputIterator>
void assign(InputIterator First, InputIterator Last);
```

### <a name="parameters"></a>Parameter

`First` Die Position des ersten Elements in dem zu kopierenden Elementbereich.

`Last` Die Position des ersten Elements hinter dem zu kopierenden Elementbereich.

`Count` Die Anzahl von Kopien eines Elements in den Vektor eingefügt wird.

`Val` Der Wert des Elements, das in den Vektor eingefügt wird.

`IList` Das initializer_list-Element, das die einzufügenden Elemente enthält.

### <a name="remarks"></a>Hinweise

Nachdem ein vorhandenes Elemente in einem Vektor gelöscht wurde, wird entweder "Einfügen eines angegebenen Elementbereichs aus dem ursprünglichen Vektor in einen Vektor" oder "Einfügen von Kopien eines neuen Elements eines angegebenen Werts in einen Vektor" zugewiesen.

### <a name="example"></a>Beispiel

```cpp
/ vector_assign.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> v1, v2, v3;

    v1.push_back(10);
    v1.push_back(20);
    v1.push_back(30);
    v1.push_back(40);
    v1.push_back(50);

    cout << "v1 = ";
    for (auto& v : v1){
        cout << v << " ";
    }
    cout << endl;

    v2.assign(v1.begin(), v1.end());
    cout << "v2 = ";
    for (auto& v : v2){
        cout << v << " ";
    }
    cout << endl;

    v3.assign(7, 4);
    cout << "v3 = ";
    for (auto& v : v3){
        cout << v << " ";
    }
    cout << endl;

    v3.assign({ 5, 6, 7 });
    for (auto& v : v3){
        cout << v << " ";
    }
    cout << endl;
}

```

## <a name="at"></a> vector::at

Gibt einen Verweis auf das Element an einer angegebenen Position in dem Vektor zurück.

```cpp
reference at(size_type _Pos);

const_reference at(size_type _Pos) const;
```

### <a name="parameters"></a>Parameter

`_Pos` Der Feldindex oder Positionsnummer Anzahl für das Element im Vektor verweisen.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Element, das im Argument indiziert ist. Wenn `_Off` größer ist als die Größe des Vektors, löst **at** eine Ausnahme aus.

### <a name="remarks"></a>Hinweise

Wenn **dem Rückgabewert von**at`const_reference` zugewiesen wird, kann das Vektorobjekt nicht geändert werden. Wenn der Rückgabewert von **at** einem **reference** zugewiesen wird, kann das Vektorobjekt geändert werden.

### <a name="example"></a>Beispiel

```cpp
// vector_at.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );
   v1.push_back( 20 );

   const int &i = v1.at( 0 );
   int &j = v1.at( 1 );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="back"></a> vector::back

Gibt einen Verweis auf das letzte Element des Vektors zurück.

```cpp
reference back();

const_reference back() const;
```

### <a name="return-value"></a>Rückgabewert

Das letzte Element des Vektors. Wenn der Vektor leer ist, ist der Rückgabewert nicht definiert.

### <a name="remarks"></a>Hinweise

Wenn **back** dem Rückgabewert von `const_reference` zugewiesen wird, kann das Vektorobjekt nicht geändert werden. Wenn der Rückgabewert von **back** einem **reference** zugewiesen wird, kann das Vektorobjekt geändert werden.

Wenn [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) beim Kompilieren als 1 oder 2 definiert ist, tritt beim Zugriff auf ein Element in einem leeren Vektor ein Laufzeitfehler auf.  Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md) .

### <a name="example"></a>Beispiel

```cpp
// vector_back.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );
   v1.push_back( 11 );

   int& i = v1.back( );
   const int& ii = v1.front( );

   cout << "The last integer of v1 is " << i << endl;
   i--;
   cout << "The next-to-last integer of v1 is "<< ii << endl;
}
```

## <a name="begin"></a> vector::begin

Gibt einen Iterator mit wahlfreiem Zugriff für das erste Element im Vektor zurück.

```cpp
const_iterator begin() const;


iterator begin();
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator mit direktem Zugriff, der das erste Element im `vector` adressiert oder auf die Position zeigt, der auf einen leeren `vector` folgt. Sie sollten den Rückgabewert immer mit [vector::end](#end) vergleichen, um sicherzustellen, dass er gültig ist.

### <a name="remarks"></a>Hinweise

Wenn der Rückgabewert von `begin` einem [vector::const_iterator](#const_iterator) zugewiesen wird, kann das `vector`-Objekt nicht geändert werden. Wenn dem Rückgabewert `begin` einem [vector::iterator](#iterator) zugewiesen wird, kann das `vector`-Objekt geändert werden.

### <a name="example"></a>Beispiel

```cpp
// vector_begin.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> c1;
    vector<int>::iterator c1_Iter;
    vector<int>::const_iterator c1_cIter;

    c1.push_back(1);
    c1.push_back(2);

    cout << "The vector c1 contains elements:";
    c1_Iter = c1.begin();
    for (; c1_Iter != c1.end(); c1_Iter++)
    {
        cout << " " << *c1_Iter;
    }
    cout << endl;

    cout << "The vector c1 now contains elements:";
    c1_Iter = c1.begin();
 *c1_Iter = 20;
    for (; c1_Iter != c1.end(); c1_Iter++)
    {
        cout << " " << *c1_Iter;
    }
    cout << endl;

    // The following line would be an error because iterator is const
    // *c1_cIter = 200;
}
```

```Output
The vector c1 contains elements: 1 2
The vector c1 now contains elements: 20 2
```

## <a name="capacity"></a> vector::capacity

Gibt die Anzahl von Elementen zurück, die der Vektor enthalten kann, ohne zusätzlichen Speicher zuzuweisen.

```cpp
size_type capacity() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Speicherlänge, die für den Vektor zugewiesen wurde.

### <a name="remarks"></a>Hinweise

Die Memberfunktion [resize](#resize) arbeitet effizienter, wenn ausreichend Arbeitsspeicher dafür zugeordnet wird. Verwenden Sie die Memberfunktion [reserve](#reserve), um die Größe des zugewiesenen Arbeitsspeichers anzugeben.

### <a name="example"></a>Beispiel

```cpp
// vector_capacity.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 1 );
   cout << "The length of storage allocated is "
        << v1.capacity( ) << "." << endl;

   v1.push_back( 2 );
   cout << "The length of storage allocated is now "
        << v1.capacity( ) << "." << endl;
}
```

```Output
The length of storage allocated is 1.
The length of storage allocated is now 2.
```

## <a name="cbegin"></a> vector::cbegin

Gibt einen `const`-Iterator zurück, mit dem das erste Element im Bereich behandelt wird.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `const`-Random-Access-Iterator, der auf das erste Element des Bereichs zeigt oder die Position direkt hinter dem Ende eines leeren Bereichs (für einen leeren Bereich gilt `cbegin() == cend()`).

### <a name="remarks"></a>Hinweise

Bei dem Rückgabewert `cbegin` können die Elemente im Bereich nicht geändert werden.

Sie können diese Memberfunktion anstelle der `begin()`-Memberfunktion verwenden, um sicherzustellen, dass der Rückgabewert `const_iterator` ist. Normalerweise wird sie zusammen mit dem [auto](../cpp/auto-cpp.md)-Typableitungs-Schlüsselwort verwendet, wie im folgenden Beispiel gezeigt. Im folgenden Beispiel ist `Container` ein beliebiger änderbarer (Nicht-`const`-)Container, der `begin()` und `cbegin()` unterstützt.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a> vector::cend

Gibt einen `const`-Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines Bereichs unmittelbar nachfolgt.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt einen `const`-Random-Access-Iterator zurück, der auf eine Position unmittelbar hinter dem Ende des Bereichs verweist.

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

## <a name="clear"></a> vector::clear

Löscht die Elemente des Vektors.

```cpp
void clear();
```

### <a name="example"></a>Beispiel

```cpp
// vector_clear.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );
   v1.push_back( 20 );
   v1.push_back( 30 );

   cout << "The size of v1 is " << v1.size( ) << endl;
   v1.clear( );
   cout << "The size of v1 after clearing is " << v1.size( ) << endl;
}
```

```Output
The size of v1 is 3
The size of v1 after clearing is 0
```

## <a name="const_iterator"></a> vector::const_iterator

Ein Typ, der einen Iterator mit wahlfreiem Zugriff bereitstellt, mit dem ein **const**-Element in einem Vektor gelesen werden kann.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Hinweise

Ein `const_iterator`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden.

### <a name="example"></a>Beispiel

In dem Beispiel für [back](#back) finden Sie ein Beispiel, in dem `const_iterator` verwendet wird.

## <a name="const_pointer"></a> vector::const_pointer

Ein Typ, der einen Zeiger auf ein **const**-Element in einem Vektor bereitstellt.

```cpp
typedef typename Allocator::const_pointer const_pointer;
```

### <a name="remarks"></a>Hinweise

Ein `const_pointer`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden.

Ein [Iterator](#iterator) wird häufiger für den Zugriff auf ein Vektorelement verwendet.

## <a name="const_reference"></a> vector::const_reference

Ein Typ, der einen Verweis auf ein **const**-Element bereitstellt, das in einem Vektor zum Lesen und Ausführen von **const**-Vorgängen gespeichert ist.

```cpp
typedef typename Allocator::const_reference const_reference;
```

### <a name="remarks"></a>Hinweise

Ein `const_reference`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden.

### <a name="example"></a>Beispiel

```cpp
// vector_const_ref.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );
   v1.push_back( 20 );

   const vector <int> v2 = v1;
   const int &i = v2.front( );
   const int &j = v2.back( );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;

   // The following line would cause an error as v2 is const
   // v2.push_back( 30 );
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="const_reverse_iterator"></a> vector::const_reverse_iterator

Ein Typ, der einen Iterator mit direktem Zugriff bereitstellt, mit dem jedes **const**-Element im Vektor gelesen werden kann.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Hinweise

Ein `const_reverse_iterator`-Typ kann nicht den Wert eines Elements ändern und wird verwendet, um den Vektor in umgekehrter Reihenfolge zu durchlaufen.

### <a name="example"></a>Beispiel

Im Beispiel für [rbegin](#rbegin) wird verdeutlicht, wie ein Iterator deklariert und verwendet wird.

## <a name="crbegin"></a> vector::crbegin

Gibt einen const-Iterator zum ersten Element in einem umgekehrten Vektor zurück.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein umgekehrter const-Iterator mit direktem Zugriff, mit dem das erste Element in einem umgekehrten [vector](../standard-library/vector-class.md) adressiert wird (bzw. mit dem das ehemals letzte Element in der nicht umgekehrten `vector` adressiert wird).

### <a name="remarks"></a>Hinweise

Bei dem Rückgabewert von `crbegin` kann das `vector`-Objekt nicht geändert werden.

### <a name="example"></a>Beispiel

```cpp
// vector_crbegin.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator v1_Iter;
   vector <int>::const_reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   v1_Iter = v1.begin( );
   cout << "The first element of vector is "
        << *v1_Iter << "." << endl;

   v1_rIter = v1.crbegin( );
   cout << "The first element of the reversed vector is "
        << *v1_rIter << "." << endl;
}
```

```Output
The first element of vector is 1.
The first element of the reversed vector is 2.
```

## <a name="crend"></a> vector::crend

Gibt einen const-Iterator zurück, mit dem die Position adressiert wird, die dem letzten Element eines umgekehrten Vektors folgt.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Rückgabewert

Ein const_reverse-Iterator mit direktem Zugriff, mit dem die Position adressiert wird, die dem letzten Element in einem umgekehrten [vector](../standard-library/vector-class.md) folgt (der Speicherort, der dem ersten Element im nicht umgekehrten `vector` vorangegangen war).

### <a name="remarks"></a>Hinweise

`crend` wird bei einem umgekehrten `vector` auf die gleiche Weise verwendet, wie [vector::cend](#cend) bei einem `vector` verwendet wird.

Mit dem Rückgabewert von `crend` (entsprechend verringert) kann das `vector`-Objekt nicht geändert werden.

`crend` kann verwendet werden, um zu testen, ob das Ende der `vector` von einem umgekehrten Iterator erreicht wurde.

Der von `crend` zurückgegebene Wert darf nicht dereferenziert werden.

### <a name="example"></a>Beispiel

```cpp
// vector_crend.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::const_reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )
      cout << *v1_rIter << endl;
}
```

```Output
2
1
```

## <a name="data"></a> vector::data

Gibt einen Zeiger auf das erste Element im Vektor zurück.

```cpp
const_pointer data() const;


pointer data();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das erste Element im [vector](../standard-library/vector-class.md) oder auf die Position, die auf einen leeren `vector` folgt.

### <a name="example"></a>Beispiel

```cpp
// vector_data.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> c1;
    vector<int>::pointer c1 ptr;
    vector<int>::const_pointer c1_cPtr;

    c1.push_back(1);
    c1.push_back(2);

    cout << "The vector c1 contains elements:";
    c1_cPtr = c1.data();
    for (size_t n = c1.size(); 0 < n; --n, c1_cPtr++)
    {
        cout << " " << *c1_cPtr;
    }
    cout << endl;

    cout << "The vector c1 now contains elements:";
    c1 ptr = c1.data();
 *c1 ptr = 20;
    for (size_t n = c1.size(); 0 < n; --n, c1 ptr++)
    {
        cout << " " << *c1 ptr;
    }
    cout << endl;
}
```

```Output
The vector c1 contains elements: 1 2
The vector c1 now contains elements: 20 2
```

## <a name="difference_type"></a> vector::difference_type

Ein Typ, der den Unterschied zwischen zwei Iteratoren, die auf Elemente innerhalb desselben Vektors verweisen, bereitstellt.

```cpp
typedef typename Allocator::difference_type difference_type;
```

### <a name="remarks"></a>Hinweise

Ein `difference_type` kann auch als die Anzahl von Elementen zwischen zwei Zeigern beschrieben werden, da ein Zeiger auf ein Element die entsprechende Adresse enthält.

Ein [Iterator](#iterator) wird häufiger für den Zugriff auf ein Vektorelement verwendet.

### <a name="example"></a>Beispiel

```cpp
// vector_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <vector>
#include <algorithm>

int main( )
{
   using namespace std;

   vector <int> c1;
   vector <int>::iterator c1_Iter, c2_Iter;

   c1.push_back( 30 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1.push_back( 10 );
   c1.push_back( 30 );
   c1.push_back( 20 );

   c1_Iter = c1.begin( );
   c2_Iter = c1.end( );

   vector <int>::difference_type   df_typ1, df_typ2, df_typ3;

   df_typ1 = count( c1_Iter, c2_Iter, 10 );
   df_typ2 = count( c1_Iter, c2_Iter, 20 );
   df_typ3 = count( c1_Iter, c2_Iter, 30 );
   cout << "The number '10' is in c1 collection " << df_typ1 << " times.\n";
   cout << "The number '20' is in c1 collection " << df_typ2 << " times.\n";
   cout << "The number '30' is in c1 collection " << df_typ3 << " times.\n";
}
```

```Output
The number '10' is in c1 collection 1 times.
The number '20' is in c1 collection 2 times.
The number '30' is in c1 collection 3 times.
```

## <a name="emplace"></a> vector::emplace

Fügt ein direkt konstruiertes Element an einer angegebenen Position in den Vektor ein.

```cpp
iterator emplace(
    const_iterator _Where,
    Type&& val);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`_Where`|Die Position im [vector](../standard-library/vector-class.md), an der das erste Element eingefügt wird.|
|`val`|Der Wert des Elements, das in den `vector` eingefügt wird.|

### <a name="return-value"></a>Rückgabewert

Die Funktion gibt einen Iterator zurück, der auf den Speicherort zeigt, an dem das neue Element in den `vector` eingefügt wurde.

### <a name="remarks"></a>Hinweise

Einfügevorgänge können sehr speicherintensiv sein. Eine Abhandlung zur Leistung von `vector` finden Sie unter [vector-Klasse](../standard-library/vector-class.md).

### <a name="example"></a>Beispiel

```cpp
// vector_emplace.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter;

   v1.push_back( 10 );
   v1.push_back( 20 );
   v1.push_back( 30 );

   cout << "v1 =" ;
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

// initialize a vector of vectors by moving v1
   vector < vector <int> > vv1;

   vv1.emplace( vv1.begin(), move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      {
      cout << "vv1[0] =";
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )
         cout << " " << *Iter;
      cout << endl;
      }
}
```

```Output
v1 = 10 20 30
vv1[0] = 10 20 30
```

## <a name="emplace_back"></a> vector::emplace_back

Fügt ein direkt konstruiertes Element am Ende des Vektors ein.

```cpp
template <class... Types>
void emplace_back(Types&&... _Args);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`_Args`|Konstruktorargumente Die Funktion leitet auf Grundlage der bereitgestellten Argumente die erforderliche die Konstruktorüberladung ab.|

### <a name="example"></a>Beispiel

```cpp
#include <vector>
struct obj
{
   obj(int, double) {}
};

int main()
{
   std::vector<obj> v;
   v.emplace_back(1, 3.14); // obj in created in place in the vector
}

```

## <a name="empty"></a> vector::empty

Testet, ob der Vektor leer ist.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Vektor leer ist; **FALSE**, wenn der Vektor nicht leer ist.

### <a name="example"></a>Beispiel

```cpp
// vector_empty.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );

   if ( v1.empty( ) )
      cout << "The vector is empty." << endl;
   else
      cout << "The vector is not empty." << endl;
}
```

```Output
The vector is not empty.
```

## <a name="end"></a> vector::end

Gibt den "past-the-end"-Iterator zurück.

```cpp
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>Rückgabewert

Der "past-the-end"-Iterator für den Vektor. Wenn der Vektor leer ist, dann gilt `vector::end() == vector::begin()`.

### <a name="remarks"></a>Hinweise

Wenn der Rückgabewert von **end** einer Variablen vom Typ `const_iterator` zugewiesen wird, kann das Vektorobjekt nicht geändert werden. Wenn der Rückgabewert von **end** einer Variablen vom Typ **iterator** zugewiesen wird, kann das Vektorobjekt geändert werden.

### <a name="example"></a>Beispiel

```cpp
// vector_end.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>
int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator v1_Iter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   for ( v1_Iter = v1.begin( ) ; v1_Iter != v1.end( ) ; v1_Iter++ )
      cout << *v1_Iter << endl;
}
```

```Output
1
2
```

## <a name="erase"></a> vector::erase

Entfernt ein Element oder eine Reihe von Elementen aus angegebenen Positionen in einem Vektor.

```cpp
iterator erase(
    const_iterator _Where);

iterator erase(
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`_Where`|Die Position des von dem Vektor zu entfernenden Elements.|
|`first`|Die Position des ersten Elements, das von dem Vektor entfernt werden soll.|
|`last`|Die Position direkt hinter dem letzten von dem Vektor entfernten Element.|

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der das erste über die entfernten Elemente hinaus verbliebene Element festlegt, oder ein Zeiger, der das Ende des Vektors darstellt, wenn kein solches Element vorhanden ist.

### <a name="example"></a>Beispiel

```cpp
// vector_erase.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter;

   v1.push_back( 10 );
   v1.push_back( 20 );
   v1.push_back( 30 );
   v1.push_back( 40 );
   v1.push_back( 50 );

   cout << "v1 =" ;
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

   v1.erase( v1.begin( ) );
   cout << "v1 =";
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

   v1.erase( v1.begin( ) + 1, v1.begin( ) + 3 );
   cout << "v1 =";
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;
}
```

```Output
v1 = 10 20 30 40 50
v1 = 20 30 40 50
v1 = 20 50
```

## <a name="front"></a> vector::front

Gibt einen Verweis auf das erste Element in einem Vektor zurück.

```cpp
reference front();

const_reference front() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das erste Element im Vektorobjekt. Wenn der Vektor leer ist, ist die Rückgabe nicht definiert.

### <a name="remarks"></a>Hinweise

Wenn `front` dem Rückgabewert von `const_reference` zugewiesen wird, kann das Vektorobjekt nicht geändert werden. Wenn der Rückgabewert von `front` einem **reference** zugewiesen wird, kann das Vektorobjekt geändert werden.

Wenn [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) beim Kompilieren als 1 oder 2 definiert ist, tritt beim Zugriff auf ein Element in einem leeren Vektor ein Laufzeitfehler auf.  Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md) .

### <a name="example"></a>Beispiel

```cpp
// vector_front.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );
   v1.push_back( 11 );

   int& i = v1.front( );
   const int& ii = v1.front( );

   cout << "The first integer of v1 is "<< i << endl;
   // by incrementing i, we move the the front reference to the second element
   i++;
   cout << "Now, the first integer of v1 is "<< i << endl;
}
```

## <a name="get_allocator"></a> vector::get_allocator

Gibt eine Kopie des Zuweisungsobjekts zurück, das zum Erstellen eines Vektors verwendet wird.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Rückgabewert

Die von dem Vektor verwendete Zuweisung.

### <a name="remarks"></a>Hinweise

Zuweisungen für die Vektorklasse geben an, wie die Klasse einen Speicher verwaltet. Für die meisten Programmieranforderungen reichen die Standardzuweisungen mit C++-Standardbibliothek-Container-Klassen aus. Schreiben und Verwenden Ihrer eigener Zuweisungsklasse ist ein C++ -Thema für Fortgeschrittene.

### <a name="example"></a>Beispiel

```cpp
// vector_get_allocator.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   // The following lines declare objects that use the default allocator.
   vector<int> v1;
   vector<int, allocator<int> > v2 = vector<int, allocator<int> >(allocator<int>( )) ;

   // v3 will use the same allocator class as v1
   vector <int> v3( v1.get_allocator( ) );

   vector<int>::allocator_type xvec = v3.get_allocator( );
   // You can now call functions on the allocator class used by vec
}
```

## <a name="insert"></a> vector::insert

Fügt ein Element oder mehrere Elemente oder ein Reihe von Elementen an einer bestimmten Position in den Vektor ein.

```cpp
iterator insert(
    const_iterator _Where,
    const Type& val);

iterator insert(
    const_iterator _Where,
    Type&& val);

void insert(
    const_iterator _Where,
    size_type count,
    const Type& val);

template <class InputIterator>
void insert(
    const_iterator _Where,
    InputIterator first,
    InputIterator last);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`_Where`|Die Position in dem Vektor, an der das erste Element eingefügt wird.|
|`val`|Der Wert des Elements, das in den Vektor eingefügt wird.|
|`count`|Die Anzahl von Elementen, die in den Vektor eingefügt werden.|
|`first`|Die Position des ersten Elements in dem zu kopierenden Elementbereich.|
|`last`|Die Position des ersten Elements nach dem zu kopierenden Elementbereich.|

### <a name="return-value"></a>Rückgabewert

Die ersten zwei `insert`-Funktionen geben einen Iterator zurück, der auf den Speicherort zeigt, an dem das neue Element in den Vektor eingefügt wurde.

### <a name="remarks"></a>Hinweise

Als Vorbedingung gilt, dass `first` und `last` keine Iteratoren für den Vektor sein dürfen, da sonst das Verhalten nicht definiert ist. Einfügevorgänge können sehr speicherintensiv sein. Eine Abhandlung zur Leistung von `vector` finden Sie unter [vector-Klasse](../standard-library/vector-class.md).

### <a name="example"></a>Beispiel

```cpp
// vector_insert.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter;

   v1.push_back( 10 );
   v1.push_back( 20 );
   v1.push_back( 30 );

   cout << "v1 =" ;
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

   v1.insert( v1.begin( ) + 1, 40 );
   cout << "v1 =";
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;
   v1.insert( v1.begin( ) + 2, 4, 50 );

   cout << "v1 =";
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

   v1.insert( v1.begin( )+1, v1.begin( )+2, v1.begin( )+4 );
   cout << "v1 =";
   for (Iter = v1.begin( ); Iter != v1.end( ); Iter++ )
      cout << " " << *Iter;
   cout << endl;

// initialize a vector of vectors by moving v1
   vector < vector <int> > vv1;

   vv1.insert( vv1.begin(), move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      {
      vector < vector <int> >::iterator Iter;
      cout << "vv1[0] =";
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )
         cout << " " << *Iter;
      cout << endl;
      }
}
```

```Output
v1 = 10 20 30
v1 = 10 40 20 30
v1 = 10 40 50 50 50 50 20 30
v1 = 10 50 50 40 50 50 50 50 20 30
vv1[0] = 10 50 50 40 50 50 50 50 20 30
```

## <a name="iterator"></a> vector::iterator

Ein Typ, der einen Iterator mit wahlfreiem Zugriff bereitstellt, mit dem jedes Element in einem Vektor gelesen oder geändert werden kann.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Hinweise

Ein **iterator**-Typ kann zum Ändern des Werts eines Elements verwendet werden.

### <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [begin](#begin).

## <a name="max_size"></a> vector::max_size

Gibt die Maximallänge des Vektors zurück.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Rückgabewert

Die mögliche Maximallänge des Vektors.

### <a name="example"></a>Beispiel

```cpp
// vector_max_size.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::size_type i;

   i = v1.max_size( );
   cout << "The maximum possible length of the vector is " << i << "." << endl;
}
```

## <a name="op_at"></a> vector::operator[]

Gibt einen Verweis auf das Vektorelement an einer angegebenen Position zurück.

```cpp
reference operator[](size_type Pos);

const_reference operator[](size_type Pos) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`Pos`|Die Position des angegebenen Vektorelements.|

### <a name="return-value"></a>Rückgabewert

Wenn die angegebene Position größer oder gleich der Größe des Containers ist, ist das Ergebnis nicht definiert.

### <a name="remarks"></a>Hinweise

Wenn `operator[]` dem Rückgabewert von `const_reference` zugewiesen wird, kann das Vektorobjekt nicht geändert werden. Wenn der Rückgabewert von `operator[]` einem Verweis zugewiesen wird, kann das Vektorobjekt geändert werden.

Wenn [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) beim Kompilieren als 1 oder 2 definiert ist, tritt beim Zugriff auf ein Element außerhalb des Vektorobjekts ein Laufzeitfehler auf.  Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md) .

### <a name="example"></a>Beispiel

```cpp
// vector_op_ref.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;

   v1.push_back( 10 );
   v1.push_back( 20 );

   int& i = v1[1];
   cout << "The second integer of v1 is " << i << endl;
}
```

## <a name="op_eq"></a> vector::operator=

Ersetzt die Elemente des Vektors durch eine Kopie eines anderen Vektors.

```cpp
vector& operator=(const vector& right);

vector& operator=(vector&& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`right`|Der [vector](../standard-library/vector-class.md), der in den `vector` kopiert wird.|

### <a name="remarks"></a>Hinweise

Nachdem ein vorhandenes Element in einem `vector` gelöscht wurde, kopiert oder verschiebt `operator=` den Inhalt von `right` in den `vector`.

### <a name="example"></a>Beispiel

```cpp
// vector_operator_as.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector<int> v1, v2, v3;
   vector<int>::iterator iter;

   v1.push_back(10);
   v1.push_back(20);
   v1.push_back(30);
   v1.push_back(40);
   v1.push_back(50);

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

## <a name="pointer"></a> vector::pointer

Ein Typ, der einen Zeiger auf ein Element in einem Vektor bereitstellt.

```cpp
typedef typename Allocator::pointer pointer;
```

### <a name="remarks"></a>Hinweise

Ein **pointer**-Typ kann zum Ändern des Werts eines Elements verwendet werden.

### <a name="example"></a>Beispiel

```cpp
// vector_pointer.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector<int> v;
   v.push_back( 11 );
   v.push_back( 22 );

   vector<int>::pointer ptr = &v[0];
   cout << *ptr << endl;
   ptr++;
   cout << *ptr << endl;
 *ptr = 44;
   cout << *ptr << endl;
}
```

```Output
11
22
44
```

## <a name="pop_back"></a> vector::pop_back

Löscht das Element am Ende des Vektors.

```cpp
void pop_back();
```

### <a name="remarks"></a>Hinweise

Ein Codebeispiel finden Sie unter [vector::push_back()](#push_back).

## <a name="push_back"></a> vector::push_back

Fügt ein Element am Ende des Vektors hinzu.

```cpp
void push_back(const T& Val);


void push_back(T&& Val);
```

### <a name="parameters"></a>Parameter

`Val` Der Wert, der am Ende des Vektors hinzugefügten Element zugewiesen werden soll.

### <a name="example"></a>Beispiel

```cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

using namespace std;

template <typename T> void print_elem(const T& t) {
    cout << "(" << t << ") ";
}

template <typename T> void print_collection(const T& t) {
    cout << "  " << t.size() << " elements: ";

    for (const auto& p : t) {
        print_elem(p);
    }
    cout << endl;
}

int main()
{
    vector<int> v;
    for (int i = 0; i < 10; ++i) {
        v.push_back(10 + i);
    }

    cout << "vector data: " << endl;
    print_collection(v);

    // pop_back() until it's empty, printing the last element as we go
    while (v.begin() != v.end()) {
        cout << "v.back(): "; print_elem(v.back()); cout << endl;
        v.pop_back();
    }
}
```

## <a name="rbegin"></a> vector::rbegin

Gibt einen Iterator an das erste Element in einem umgekeherten Vektor zurück.

```cpp
reverse_iterator rbegin();
const_reverse_iterator rbegin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein umgekehrter Iterator mit direktem Zugriff, mit dem das erste Element in einem umgekehrten Vektor adressiert wird (bzw. mit dem das ehemals letzte Element in der nicht umgekehrten Vektor adressiert wird).

### <a name="remarks"></a>Hinweise

Wenn `rbegin` dem Rückgabewert von `const_reverse_iterator` zugewiesen wird, kann das Vektorobjekt nicht geändert werden. Wenn `rbegin` dem Rückgabewert von `reverse_iterator` zugewiesen wird, kann das Vektorobjekt geändert werden.

### <a name="example"></a>Beispiel

```cpp
// vector_rbegin.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator v1_Iter;
   vector <int>::reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   v1_Iter = v1.begin( );
   cout << "The first element of vector is "
        << *v1_Iter << "." << endl;

   v1_rIter = v1.rbegin( );
   cout << "The first element of the reversed vector is "
        << *v1_rIter << "." << endl;
}
```

```Output
The first element of vector is 1.
The first element of the reversed vector is 2.
```

## <a name="reference"></a> vector::reference

Ein Typ, der einen Verweis auf ein in einem Vektor gespeichertes Element bereitstellt.

```cpp
typedef typename Allocator::reference reference;
```

### <a name="example"></a>Beispiel

Unter [at](#at) finden Sie ein Beispiel zur Verwendung von **reference** in der Vektorklasse.

## <a name="rend"></a> vector::rend

Gibt einen Iterator zurück, mit dem die Position adressiert wird, die dem letzten Element eines umgekehrten Vektors folgt.

```cpp
const_reverse_iterator rend() const;
reverse_iterator rend();
```

### <a name="return-value"></a>Rückgabewert

Ein umgekehrter Iterator mit direktem Zugriff, mit dem die Position adressiert wird, die dem letzten Element in einem umgekehrten Vektor folgt (die Position, die dem ersten Element im nicht umgekehrten Vektor vorangegangen war).

### <a name="remarks"></a>Hinweise

`rend` wird bei einem umgekehrten Vektor auf die gleiche Weise verwendet, wie [end](#end) bei einem Vektor verwendet wird.

Wenn `rend` dem Rückgabewert von `const_reverse_iterator` zugewiesen wird, kann das Vektorobjekt nicht geändert werden. Wenn `rend` dem Rückgabewert von `reverse_iterator` zugewiesen wird, kann das Vektorobjekt geändert werden.

`rend` kann verwendet werden, um zu testen, ob das Ende des Vektors von einem umgekehrten Iterator erreicht wurde.

Der von `rend` zurückgegebene Wert darf nicht dereferenziert werden.

### <a name="example"></a>Beispiel

```cpp
// vector_rend.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )
      cout << *v1_rIter << endl;
}
```

```Output
2
1
```

## <a name="reserve"></a> vector::reserve

Reserviert eine Mindestlänge von Speicher für ein Vektorobjekt und weist Speicherplatz zu, falls erforderlich.

```cpp
void reserve(size_type count);
```

### <a name="parameters"></a>Parameter

`count` Die Mindestlänge von Speicher für den Vektor zugeordnet werden.

### <a name="example"></a>Beispiel

```cpp
// vector_reserve.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   //vector <int>::iterator Iter;

   v1.push_back( 1 );
   cout << "Current capacity of v1 = "
      << v1.capacity( ) << endl;
   v1.reserve( 20 );
   cout << "Current capacity of v1 = "
      << v1.capacity( ) << endl;
}
```

```Output
Current capacity of v1 = 1
Current capacity of v1 = 20
```

## <a name="resize"></a> vector::resize

Gibt eine neue Größe für einen Vektor an.

```cpp
void resize(size_type Newsize);
void resize(size_type Newsize, Type Val);
```

### <a name="parameters"></a>Parameter

`Newsize` Die neue Größe des Vektors.

`Val` Der Initialisierungswert für neue Elemente, die in den Vektor hinzugefügt wird, wenn die neue Größe größer ist, die der ursprünglichen Größe. Wenn der Wert ausgelassen wird, verwenden die neuen Objekte ihren Standardkonstruktor.

### <a name="remarks"></a>Hinweise

Wenn die Größe der Liste unter der angeforderte Größe liegt, werden dem Vektor `Newsize`-Elemente hinzugefügt, bis er die angeforderte Größe erreicht. Wenn die Größe des Containers die angeforderte Größe übersteigt, werden die Elemente, die dem Ende des Containers am nächsten sind, gelöscht, bis der Container die Größe `Newsize` erreicht. Wenn die tatsächliche Größe des Containers der angeforderten Größe entspricht, wird keine Aktion durchgeführt.

[size](#size) gibt die aktuelle Größe des Vektors an.

### <a name="example"></a>Beispiel

```cpp
// vectorsizing.cpp
// compile with: /EHsc /W4
// Illustrates vector::reserve, vector::max_size,
// vector::resize, vector::resize, and vector::capacity.
//
// Functions:
//
//    vector::max_size - Returns maximum number of elements vector could
//                       hold.
//
//    vector::capacity - Returns number of elements for which memory has
//                       been allocated.
//
//    vector::size - Returns number of elements in the vector.
//
//    vector::resize - Reallocates memory for vector, preserves its
//                     contents if new size is larger than existing size.
//
//    vector::reserve - Allocates elements for vector to ensure a minimum
//                      size, preserving its contents if the new size is
//                      larger than existing size.
//
//    vector::push_back - Appends (inserts) an element to the end of a
//                        vector, allocating memory for it if necessary.
//
//////////////////////////////////////////////////////////////////////

// The debugger cannot handle symbols more than 255 characters long.
// The C++ Standard Library often creates symbols longer than that.
// The warning can be disabled:
//#pragma warning(disable:4786)

#include <iostream>
#include <vector>
#include <string>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }
    cout << endl;
}

void printvstats(const vector<int>& v) {
    cout << "   the vector's size is: " << v.size() << endl;
    cout << "   the vector's capacity is: " << v.capacity() << endl;
    cout << "   the vector's maximum size is: " << v.max_size() << endl;
}

int main()
{
    // declare a vector that begins with 0 elements.
    vector<int> v;

    // Show statistics about vector.
    cout << endl << "After declaring an empty vector:" << endl;
    printvstats(v);
    print("   the vector's contents: ", v);

    // Add one element to the end of the vector.
    v.push_back(-1);
    cout << endl << "After adding an element:" << endl;
    printvstats(v);
    print("   the vector's contents: ", v);

    for (int i = 1; i < 10; ++i) {
        v.push_back(i);
    }
    cout << endl << "After adding 10 elements:" << endl;
    printvstats(v);
    print("   the vector's contents: ", v);

    v.resize(6);
    cout << endl << "After resizing to 6 elements without an initialization value:" << endl;
    printvstats(v);
    print("   the vector's contents: ", v);

    v.resize(9, 999);
    cout << endl << "After resizing to 9 elements with an initialization value of 999:" << endl;
    printvstats(v);
    print("   the vector's contents: ", v);

    v.resize(12);
    cout << endl << "After resizing to 12 elements without an initialization value:" << endl;
    printvstats(v);
    print("   the vector's contents: ", v);

    // Ensure there's room for at least 1000 elements.
    v.reserve(1000);
    cout << endl << "After vector::reserve(1000):" << endl;
    printvstats(v);

    // Ensure there's room for at least 2000 elements.
    v.resize(2000);
    cout << endl << "After vector::resize(2000):" << endl;
    printvstats(v);
}
```

## <a name="reverse_iterator"></a> vector::reverse_iterator

Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem jedes Element in einem umgekehrten Vektor gelesen oder geändert werden kann.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Hinweise

Ein `reverse_iterator`-Typ wird verwendet, um den Vektor in umgekehrter Reihenfolge zu durchlaufen.

### <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [rbegin](#rbegin).

## <a name="shrink_to_fit"></a> vector::shrink_to_fit

Verwirft Überkapazität.

```cpp
void shrink_to_fit();
```

### <a name="example"></a>Beispiel

```cpp
// vector_shrink_to_fit.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   //vector <int>::iterator Iter;

   v1.push_back( 1 );
   cout << "Current capacity of v1 = "
      << v1.capacity( ) << endl;
   v1.reserve( 20 );
   cout << "Current capacity of v1 = "
      << v1.capacity( ) << endl;
   v1.shrink_to_fit();
   cout << "Current capacity of v1 = "
      << v1.capacity( ) << endl;
}
```

```Output
Current capacity of v1 = 1
Current capacity of v1 = 20
Current capacity of v1 = 1
```

## <a name="size"></a> vector::size

Gibt die Anzahl von Elementen in dem Vektor zurück.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Länge des Vektors.

### <a name="example"></a>Beispiel

```cpp
// vector_size.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::size_type i;

   v1.push_back( 1 );
   i = v1.size( );
   cout << "Vector length is " << i << "." << endl;

   v1.push_back( 2 );
   i = v1.size( );
   cout << "Vector length is now " << i << "." << endl;
}
```

```Output
Vector length is 1.
Vector length is now 2.
```

## <a name="size_type"></a> vector::size_type

Ein Typ, der die Anzahl von Elementen in einem Vektor zählt.

```cpp
typedef typename Allocator::size_type size_type;
```

### <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [capacity](#capacity).

## <a name="swap"></a> vector::swap

Tauscht die Elemente zweier Vektoren aus.

```cpp
void swap(
    vector<Type, Allocator>& right);

friend void swap(
    vector<Type, Allocator>& left,
    vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`right` Ein Vektor, der auszutauschenden Elemente oder ein Vektor, dessen Elemente mit denen des Vektors spezifiziertes `left`.

`left` Ein Vektor, dessen Elemente mit denen des Vektors spezifiziertes `right`.

### <a name="example"></a>Beispiel

```cpp
// vector_swap.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1, v2;

   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 3 );

   v2.push_back( 10 );
   v2.push_back( 20 );

   cout << "The number of elements in v1 = " << v1.size( ) << endl;
   cout << "The number of elements in v2 = " << v2.size( ) << endl;
   cout << endl;

   v1.swap( v2 );

   cout << "The number of elements in v1 = " << v1.size( ) << endl;
   cout << "The number of elements in v2 = " << v2.size( ) << endl;
}
```

```Output
The number of elements in v1 = 3
The number of elements in v2 = 2

The number of elements in v1 = 2
The number of elements in v2 = 3
```

## <a name="value_type"></a> vector::value_type

Ein Typ, der den in einem Vektor gespeicherten Datentyp darstellt.

```cpp
typedef typename Allocator::value_type value_type;
```

### <a name="remarks"></a>Hinweise

`value_type` ist ein Synonym für den Vorlagenparameter **type**.

### <a name="example"></a>Beispiel

```cpp
// vector_value_type.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   vector<int>::value_type AnInt;
   AnInt = 44;
   cout << AnInt << endl;
}
```

```Output
44
```

## <a name="vector"></a> vector::vector

Erstellt einen Vektor einer bestimmten Größe bzw. mit Elementen eines bestimmten Werts oder mit einer bestimmten Zuweisung oder als vollständige bzw. teilweise Kopie eines anderen Vektors.

```cpp
vector();
explicit vector(const Allocator& Al);
explicit vector(size_type Count);
vector(size_type Count, const Type& Val);
vector(size_type Count, const Type& Val, const Allocator& Al);

vector(const vector& Right);
vector(vector&& Right);
vector(initializer_list<Type> IList, const _Allocator& Al);

template <class InputIterator>
vector(InputIterator First, InputIterator Last);
template <class InputIterator>
vector(InputIterator First, InputIterator Last, const Allocator& Al);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-|-|
|`Al`|Die mit diesem Objekt zu verwendende Zuweisungsklasse. [get_allocator](#get_allocator) gibt die Zuweisungsklasse für das Objekt zurück.|
|`Count`|Die Anzahl der Elemente im erstellten Vektor.|
|`Val`|Der Wert der Elemente im erstellten Vektor.|
|`Right`|Der Vektor, dessen Kopie der erstellte Vektor ist.|
|`First`|Die Position des ersten Elements in dem zu kopierenden Elementbereich.|
|`Last`|Die Position des ersten Elements nach dem zu kopierenden Elementbereich.|
|`IList`|Das initializer_list-Element, in dem die zu kopierenden Elemente enthalten sind.|

### <a name="remarks"></a>Hinweise

Von allen Konstruktoren wird ein Zuweisungsobjekt (`Al`) gespeichert und der Vektor initialisiert.

Die ersten beiden Konstruktoren geben einen leeren ursprünglichen Vektor an. Der zweite gibt explizit den zu verwendenden Zuweisungstyp an (`Al`).

Der dritte Konstruktor gibt eine Wiederholung einer angegebenen Anzahl (`Count`) von Elementen mit dem Standardwert für die Klasse `Type` an.

Die vierten und fünften Konstruktoren geben eine Wiederholung einer angegebenen Anzahl (`Count`) von Elementen mit dem Wert `Val` an.

Der sechste Konstruktor gibt eine Kopie des Vektors `Right` an.

Mit dem siebten Konstruktor wird der `Right`-Vektor verschoben.

Beim achten Konstruktor wird zum Angeben des Elements ein initializer_list-Element verwendet.

Mit den neunten und zehnten Konstruktoren wird der Bereich [ `First`, `Last`) eines Vektors kopiert.

### <a name="example"></a>Beispiel

```cpp
// vector_ctor.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    vector <int>::iterator v1_Iter, v2_Iter, v3_Iter, v4_Iter, v5_Iter, v6_Iter;

    // Create an empty vector v0
    vector <int> v0;

    // Create a vector v1 with 3 elements of default value 0
    vector <int> v1(3);

    // Create a vector v2 with 5 elements of value 2
    vector <int> v2(5, 2);

    // Create a vector v3 with 3 elements of value 1 and with the allocator
    // of vector v2
    vector <int> v3(3, 1, v2.get_allocator());

    // Create a copy, vector v4, of vector v2
    vector <int> v4(v2);

    // Create a new temporary vector for demonstrating copying ranges
    vector <int> v5(5);
    for (auto i : v5) {
        v5[i] = i;
    }

    // Create a vector v6 by copying the range v5[ first,  last)
    vector <int> v6(v5.begin() + 1, v5.begin() + 3);

    cout << "v1 =";
    for (auto& v : v1){
        cout << " " << v;
    }
    cout << endl;

    cout << "v2 =";
    for (auto& v : v2){
        cout << " " << v;
    }
    cout << endl;

    cout << "v3 =";
    for (auto& v : v3){
        cout << " " << v;
    }
    cout << endl;
    cout << "v4 =";
    for (auto& v : v4){
        cout << " " << v;
    }
    cout << endl;

    cout << "v5 =";
    for (auto& v : v5){
        cout << " " << v;
    }
    cout << endl;

    cout << "v6 =";
    for (auto& v : v6){
        cout << " " << v;
    }
    cout << endl;

    // Move vector v2 to vector v7
    vector <int> v7(move(v2));
    vector <int>::iterator v7_Iter;

    cout << "v7 =";
    for (auto& v : v7){
        cout << " " << v;
    }
    cout << endl;

    vector<int> v8{ { 1, 2, 3, 4 } };
    for (auto& v : v8){
        cout << " " << v ;
    }
    cout << endl;
}

```

```Output
v1 = 0 0 0v2 = 2 2 2 2 2v3 = 1 1 1v4 = 2 2 2 2 2v5 = 0 1 2 3 4v6 = 1 2v7 = 2 2 2 2 21 2 3 4
```

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
