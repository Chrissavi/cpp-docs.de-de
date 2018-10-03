---
title: Tupelklasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- tuple/std::tuple
- tuple/std::tuple::operator=
dev_langs:
- C++
helpviewer_keywords:
- tuple class
ms.assetid: c38749be-ae4d-41f3-98ea-6aa3250de9a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f37a6bdbf35075a9a1a8cea8150e6f8ed85232a5
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234553"
---
# <a name="tuple-class"></a>Tupelklasse

Umschließt eine Sequenz von Elementen mit fester Länge.

## <a name="syntax"></a>Syntax

```
class tuple {
public:
   tuple();
   explicit tuple(P1, P2, ..., PN); // 0 < N
   tuple(const tuple&);
   template <class U1, class U2, ..., class UN>
      tuple(const tuple<U1, U2, ..., UN>&);
   template <class U1, class U2>
      tuple(const pair<U1, U2>&); // N == 2

   void swap(tuple& right);
   tuple& operator=(const tuple&);
   template <class U1, class U2, ..., class UN>
      tuple& operator=(const tuple<U1, U2, ..., UN>&);
   template <class U1, class U2>
      tuple& operator=(const pair<U1, U2>&); // N == 2
   };
```

### <a name="parameters"></a>Parameter

*TN*<br/>
Der Typ des N-ten Tupelelements.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Objekt, das N-Objekte des Typs speichert `T1`, `T2`,..., `TN`, wobei `0 <= N <= Nmax`. Das Ausmaß der eine tupelinstanz `tuple<T1, T2, ..., TN>` ist die Anzahl `N` der dazugehörigen Vorlagenargumente. Der Index des dem Vorlagenargument `Ti` und des entsprechenden gespeicherten Werts des betreffenden Typs ist `i - 1`. Während wir die Typen von 1 bis N in dieser Dokumentation Zahl ist, Werte der entsprechende Index folglich reichen von 0 bis N - 1.

## <a name="example"></a>Beispiel

```cpp
// tuple.cpp
// compile with: /EHsc

#include <vector>
#include <iomanip>
#include <iostream>
#include <tuple>
#include <string>

using namespace std;

typedef tuple <int, double, string> ids;

void print_ids(const ids& i)
{
   cout << "( "
        << get<0>(i) << ", "
        << get<1>(i) << ", "
        << get<2>(i) << " )." << endl;
}

int main( )
{
   // Using the constructor to declare and initialize a tuple
   ids p1(10, 1.1e-2, "one");

   // Compare using the helper function to declare and initialize a tuple
   ids p2;
   p2 = make_tuple(10, 2.22e-1, "two");

   // Making a copy of a tuple
   ids p3(p1);

   cout.precision(3);
   cout << "The tuple p1 is: ( ";
   print_ids(p1);
   cout << "The tuple p2 is: ( ";
   print_ids(p2);
   cout << "The tuple p3 is: ( ";
   print_ids(p3);

   vector<ids> v;

   v.push_back(p1);
   v.push_back(p2);
   v.push_back(make_tuple(3, 3.3e-2, "three"));

   cout << "The tuples in the vector are" << endl;
   for(vector<ids>::const_iterator i = v.begin(); i != v.end(); ++i)
   {
      print_ids(*i);
   }
}
```

```Output
The tuple p1 is: ( 10, 0.011, one ).
The tuple p2 is: ( 10, 0.222, two ).
The tuple p3 is: ( 10, 0.011, one ).
The tuples in the vector are
( 10, 0.011, one ).
( 10, 0.222, two ).
( 3, 0.033, three ).
```

## <a name="requirements"></a>Anforderungen

**Header:** \<tuple>

**Namespace:** std

## <a name="op_eq"></a> tuple::operator=

Weist ein `tuple`-Objekt zu.

```cpp
tuple& operator=(const tuple& right);

template <class U1, class U2, ..., class UN>
   tuple& operator=(const tuple<U1, U2, ..., UN>& right);

template <class U1, class U2>
   tuple& operator=(const pair<U1, U2>& right); // N == 2

tuple& operator=(tuple&& right);

template <class U1, class U2>
   tuple& operator=(pair<U1, U2>&& right);
```

### <a name="parameters"></a>Parameter

*AUFHEBEN*<br/>
Der Typ des N-ten kopierten Tupelelements.

*right*<br/>
Das Tupel, aus dem kopiert werden soll.

### <a name="remarks"></a>Hinweise

Die ersten beiden memberoperatoren weisen die Elemente von *rechten* zu den entsprechenden Elementen von `*this`. Der dritte Memberoperator weist dem Element am Index 0 von `*this` `right.first` zu und dem Element am Index 1 `right.second`. Alle drei Memberoperatoren geben `*this` zurück.

Die restlichen Memberoperatoren sind analog zu früheren, aber mit [Rvalue Reference Declarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

### <a name="example"></a>Beispiel

```cpp
// std__tuple__tuple_operator_as.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>
#include <utility>

typedef std::tuple<int, double, int, double> Mytuple;
int main()
    {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1;
    c1 = c0;

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c1);
    std::cout << " " << std::get<1>(c1);
    std::cout << " " << std::get<2>(c1);
    std::cout << " " << std::get<3>(c1);
    std::cout << std::endl;

    std::tuple<char, int> c2;
    c2 = std::make_pair('x', 4);

// display contents " x 4"
    std::cout << " " << std::get<0>(c2);
    std::cout << " " << std::get<1>(c2);
    std::cout << std::endl;

    return (0);
    }

```

```Output
0 1 2 3
0 1 2 3
x 4
```

## <a name="tuple_swap"></a> tuple:swap

Tauscht die Elemente zweier Tupel aus.

```cpp
template <class... Types>
   void swap(tuple<Types...&> left, tuple<Types...&> right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Ein Tupel, dessen Elemente mit denen des Tupels ausgetauscht werden *rechten*.|
|*right*|Ein Tupel, dessen Elemente mit denen des Tupels ausgetauscht werden *linken*.|

### <a name="remarks"></a>Hinweise

Die Funktion führt `left.swap(right)` aus.

## <a name="tuple"></a> tuple::tuple

Erstellt ein `tuple`-Objekt.

```cpp
constexpr tuple();
explicit constexpr tuple(const Types&...);
template <class... UTypes>
   explicit constexpr tuple(UTypes&&...);

tuple(const tuple&) = default;
tuple(tuple&&) = default;

template <class... UTypes>
   constexpr tuple(const tuple<UTypes...>&);
template <class... UTypes>
   constexpr tuple(tuple<UTypes...>&&);

// only if sizeof...(Types) == 2
template <class U1, class U2>
   constexpr tuple(const pair<U1, U2>&);
template <class U1, class U2>
   constexpr tuple(pair<U1, U2>&&);
```

### <a name="parameters"></a>Parameter

*AUFHEBEN*<br/>
Der Typ des N-ten kopierten Tupelelements.

*right*<br/>
Das Tupel, aus dem kopiert werden soll.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor erstellt ein Objekt, dessen Elemente standardmäßig erstellt werden.

Der zweite Konstruktor erstellt ein Objekt, dessen Elemente durch Kopieren aus den Argumenten `P1`, `P2`, ..., `PN` erstellt werden, wobei jedes `Pi` das Element initialisiert, das den Index `i - 1` hat.

Die dritten und vierten-Konstruktoren erstellen ein Objekt, dessen Elemente kopieren, die aus dem entsprechenden Element des erstellt *rechten*.

Der fünfte Konstruktor erstellt ein Objekt, dessen Element bei Index 0 durch Kopieren aus `right.first` und dessen Element bei Index 1 durch Kopieren aus `right.second` erstellt wird.

Die restlichen Konstruktoren sind analog zu früheren, aber mit [Rvalue Reference Declarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

### <a name="example"></a>Beispiel

```cpp
// std__tuple__tuple_tuple.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>
#include <utility>

typedef std::tuple<int, double, int, double> Mytuple;
int main()
{
    Mytuple c0(0, 1, 2, 3);

    // display contents "0 1 2 3"
    std::cout << std::get<0>(c0) << " ";
    std::cout << std::get<1>(c0) << " ";
    std::cout << std::get<2>(c0) << " ";
    std::cout << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1;
    c1 = c0;

    // display contents "0 1 2 3"
    std::cout << std::get<0>(c1) << " ";
    std::cout << std::get<1>(c1) << " ";
    std::cout << std::get<2>(c1) << " ";
    std::cout << std::get<3>(c1);
    std::cout << std::endl;

    std::tuple<char, int> c2(std::make_pair('x', 4));

    // display contents "x 4"
    std::cout << std::get<0>(c2) << " ";
    std::cout << std::get<1>(c2);
    std::cout << std::endl;

    Mytuple c3(c0);

    // display contents "0 1 2 3"
    std::cout << std::get<0>(c3) << " ";
    std::cout << std::get<1>(c3) << " ";
    std::cout << std::get<2>(c3) << " ";
    std::cout << std::get<3>(c3);
    std::cout << std::endl;

    typedef std::tuple<int, float, int, float> Mytuple2;
    Mytuple c4(Mytuple2(4, 5, 6, 7));

    // display contents "4 5 6 7"
    std::cout << std::get<0>(c4) << " ";
    std::cout << std::get<1>(c4) << " ";
    std::cout << std::get<2>(c4) << " ";
    std::cout << std::get<3>(c4);
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
x 4
0 1 2 3
4 5 6 7
```

## <a name="see-also"></a>Siehe auch

[\<tuple>](../standard-library/tuple.md)<br/>
[make_tuple](../standard-library/tuple-functions.md#make_tuple)<br/>
