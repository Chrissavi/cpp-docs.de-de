---
title: initializer_list-Klasse
ms.date: 11/04/2016
f1_keywords:
- initializer_list/std::initializer_list::initializer_list
- initializer_list/std::initializer_list::begin
- initializer_list/std::initializer_list::end
- initializer_list/std::initializer_list::size
ms.assetid: 1f2c0ff4-5636-4f79-b008-e75426e3d2ab
helpviewer_keywords:
- std::initializer_list::initializer_list
- std::initializer_list::begin
- std::initializer_list::end
- std::initializer_list::size
ms.openlocfilehash: de925f73ac206113aafb8661a8d5b347503150c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159300"
---
# <a name="initializerlist-class"></a>initializer_list-Klasse

Bietet Zugriff auf ein Array von Elementen, in dem jedes Mitglied von einem angegebenen Typ ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Type>
class initializer_list
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Type*|Der in `initializer_list` zu speichernde Elementdatentyp.|

## <a name="remarks"></a>Hinweise

Ein `initializer_list`-Element kann mit einer Initialisiererliste in Klammern erstellt werden:

```cpp
initializer_list<int> i1{ 1, 2, 3, 4 };
```

Der Compiler transformiert in Klammern gesetzte Initialisiererlisten mit homogenen Elementen in `initializer_list`, wenn für die Funktionssignatur `initializer_list` erforderlich ist. Ausführlichere Informationen zum Verwenden von `initializer_list` finden Sie unter [Einheitliche Initialisierung und Delegierung von Konstruktoren](../cpp/uniform-initialization-and-delegating-constructors.md).

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[initializer_list](../standard-library/forward-list-class.md#forward_list)|Konstruiert ein Objekt vom Typ `initializer_list`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|value_type|Der Typ der Elemente im `initializer_list`.|
|Verweis|Ein Typ, der einen Verweis auf ein in der `initializer_list` gespeichertes Element bereitstellt.|
|const_reference|Ein Typ, der einen Konstantenverweis auf ein in der `initializer_list` gespeichertes Element bereitstellt.|
|size_type|Ein Typ, der die Anzahl von Elementen in der `initializer_list` darstellt.|
|Iterator|Ein Typ, der einen Iterator für die `initializer_list` bereitstellt.|
|const_iterator|Ein Typ, der einen konstanten Iterator für die `initializer_list` bereitstellt.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[begin](#begin)|Gibt einen Zeiger auf das erste Element in einer `initializer_list` zurück.|
|[end](#end)|Gibt einen Zeiger auf das Element hinter dem letzten Element in einer `initializer_list` zurück.|
|[size](#size)|Gibt die Anzahl von Elementen in der `initializer_list` zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<initializer_list>

**Namespace:** std

## <a name="begin"></a> initializer_list::begin

Gibt einen Zeiger auf das erste Element in einer `initializer_list` zurück.

```cpp
constexpr const InputIterator* begin() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das erste Element von `initializer_list`. Wenn die Liste leer ist, ist der Zeiger für den Beginn und das Ende der Liste gleich.

### <a name="remarks"></a>Hinweise

## <a name="end"></a> initializer_list::end

Gibt einen Zeiger auf das Element hinter dem letzten Element in einer `initializer list` zurück.

```cpp
constexpr const InputIterator* end() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Element eine Position hinter dem letzten Element in der Liste. Wenn die Liste leer ist, entspricht dies dem Zeiger zum ersten Element in der Liste.

## <a name="initializer_list"></a> initializer_list::initializer_list

Konstruiert ein Objekt vom Typ `initializer_list`.

```cpp
constexpr initializer_list() noexcept;
initializer_list(const InputIterator First, const InputIterator Last);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Erste*|Die Position des ersten Elements in dem zu kopierenden Elementbereich.|
|*letzte*|Die Position des ersten Elements nach dem zu kopierenden Elementbereich.|

### <a name="remarks"></a>Hinweise

Eine `initializer_list` basiert auf einem Array von Objekten des angegebenen Typs. Mit dem Kopieren einer `initializer_list` wird eine zweite Instanz einer Liste erstellt, die auf die gleichen Objekte zeigt. Die zugrunde liegenden Objekte werden nicht kopiert.

### <a name="example"></a>Beispiel

```cpp
// initializer_list_class.cpp
// compile with: /EHsc
#include <initializer_list>
#include <iostream>

int main()
{
    using namespace std;
    // Create an empty initializer_list c0
    initializer_list <int> c0;

    // Create an initializer_list c1 with 1 element
    initializer_list <int> c1{ 3 };

    // Create an initializer_list c2 with 5 elements
    initializer_list <int> c2{ 5, 4, 3, 2, 1 };

    // Create a copy, initializer_list c3, of initializer_list c2
    initializer_list <int> c3(c2);

    // Create a initializer_list c4 by copying the range c3[ first,  last)
    const int* c3_ptr = c3.begin();
    c3_ptr++;
    c3_ptr++;
    initializer_list <int> c4(c3.begin(), c3_ptr);

    // Move initializer_list c4 to initializer_list c5
    initializer_list <int> c5(move(c4));

    cout << "c1 =";
    for (auto c : c1)
        cout << " " << c;
    cout << endl;

    cout << "c2 =";
    for (auto c : c2)
        cout << " " << c;
    cout << endl;

    cout << "c3 =";
    for (auto c : c3)
        cout << " " << c;
    cout << endl;

    cout << "c4 =";
    for (auto c : c4)
        cout << " " << c;
    cout << endl;

    cout << "c5 =";
    for (auto c : c5)
        cout << " " << c;
    cout << endl;
}
```

```Output
c1 = 3c2 = 5 4 3 2 1c3 = 5 4 3 2 1c4 = 5 4c5 = 5 4
```

## <a name="size"></a> initializer_list::size

Gibt die Anzahl von Elementen in der Liste zurück.

```cpp
constexpr size_t size() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Elementen in der Liste.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[<forward_list>](../standard-library/forward-list.md)<br/>
