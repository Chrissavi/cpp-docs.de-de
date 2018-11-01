---
title: '&lt;utility&gt;-Operatoren'
ms.date: 11/04/2016
f1_keywords:
- utility/std::operator!=
- utility/std::operator&gt;
- utility/std::operator&gt;=
- utility/std::operator&lt;
- utility/std::operator&lt;=
- utility/std::operator==
ms.assetid: a6617109-2cec-4a69-948f-6c87116eda5f
helpviewer_keywords:
- std::operator!= (utility)
- std::operator&gt; (utility)
- std::operator&gt;= (utility)
- std::operator&lt; (utility)
- std::operator&lt;= (utility)
- std::operator== (utility)
ms.openlocfilehash: 418b18851aaf8da44ee0ed2df7ff9e60a0b5ef1f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653677"
---
# <a name="ltutilitygt-operators"></a>&lt;utility&gt;-Operatoren

||||
|-|-|-|
|[Operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Testet, ob das pair-Objekt links vom Operator ungleich dem pair-Objekt rechts vom Operator ist.

```cpp
template <class Type>
constexpr bool operator!=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator!=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `pair`.

*right*<br/>
Ein Objekt vom Typ `pair`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Paare ungleich sind; **FALSE**, wenn die Paare gleich sind.

### <a name="remarks"></a>Hinweise

Ein Paar ist gleich einem anderen, wenn jedes ihrer entsprechenden Elemente gleich ist. Zwei Paare sind ungleich, wenn das erste oder das zweite Element eines Paars nicht gleich dem entsprechenden Element des anderen Paars ist.

### <a name="example"></a>Beispiel

```cpp
// utility_op_ne.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3;

   p1 = make_pair ( 10, 1.11e-1 );
   p2 = make_pair ( 1000, 1.11e-3 );
   p3 = make_pair ( 10, 1.11e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl << endl;

   if ( p1 != p2 )
      cout << "The pairs p1 and p2 are not equal." << endl;
   else
      cout << "The pairs p1 and p2 are equal." << endl;

   if ( p1 != p3 )
      cout << "The pairs p1 and p3 are not equal." << endl;
   else
      cout << "The pairs p1 and p3 are equal." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.111 ).
The pair p2 is: ( 1000, 0.00111 ).
The pair p3 is: ( 10, 0.111 ).

The pairs p1 and p2 are not equal.
The pairs p1 and p3 are equal.
```

## <a name="op_eq_eq"></a> operator==

Testet, ob das pair-Objekt links vom Operator gleich dem pair-Objekt rechts vom Operator ist.

```cpp
template <class T, class U>
constexpr bool operator==(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `pair`.

*right*<br/>
Ein Objekt vom Typ `pair`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Paare gleich sind; **FALSE**, wenn die `pair`-Objekte ungleich sind.

### <a name="remarks"></a>Hinweise

Ein Paar ist gleich einem anderen, wenn jedes ihrer entsprechenden Elemente gleich ist. Die Funktion gibt `left` zurück. **first** == `right`. **first** && `left`. **second** == `right`. **second**. Zwei Paare sind ungleich, wenn das erste oder das zweite Element eines Paars nicht gleich dem entsprechenden Element des anderen Paars ist.

### <a name="example"></a>Beispiel

```cpp
// utility_op_eq.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3;

   p1 = make_pair ( 10, 1.11e-1 );
   p2 = make_pair ( 1000, 1.11e-3 );
   p3 = make_pair ( 10, 1.11e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl << endl;

   if ( p1 == p2 )
      cout << "The pairs p1 and p2 are equal." << endl;
   else
      cout << "The pairs p1 and p2 are not equal." << endl;

   if ( p1 == p3 )
      cout << "The pairs p1 and p3 are equal." << endl;
   else
      cout << "The pairs p1 and p3 are not equal." << endl;
}
```

## <a name="op_lt"></a> operator&lt;

Testet, ob das pair-Objekt links vom Operator kleiner als das pair-Objekt rechts vom Operator ist.

```cpp
template <class T, class U>
constexpr bool operator<(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt des Typs `pair` auf der linken Seite des Operators.

*right*<br/>
Ein Objekt des Typs `pair` auf der rechten Seite des Operators.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das `pair`-Objekt links vom Operator strikt kleiner als das `pair`-Objekt rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Die `left` `pair` Objekt wird als strikt kleiner als der `right` `pair` Objekt, wenn *linken* ist kleiner als und ungleich *rechten*.

In einem Vergleich von Paaren haben die ersten Elemente der Werte der beiden Paare die höchste Priorität. Unterscheiden sie sich, wird das Ergebnis ihres Vergleichs als Ergebnis des Vergleichs des Paars verwendet. Sind die Werte der ersten Elemente nicht unterschiedlich, werden die Werte der zweiten Elemente verglichen, und das Ergebnis von deren Vergleich wird als Ergebnis des Vergleichs des Paars verwendet.

### <a name="example"></a>Beispiel

```cpp
// utility_op_lt.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl << endl;

   if ( p1 < p2 )
      cout << "The pair p1 is less than the pair p2." << endl;
   else
      cout << "The pair p1 is not less than the pair p2." << endl;

   if ( p1 < p3 )
      cout << "The pair p1 is less than the pair p3." << endl;
   else
      cout << "The pair p1 is not less than the pair p3." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).

The pair p1 is less than the pair p2.
The pair p1 is not less than the pair p3.
```

## <a name="op_lt_eq"></a> operator&lt;=

Testet, ob das pair-Objekt links vom Operator kleiner gleich dem pair-Objekt rechts vom Operator ist.

```cpp
template <class Type>
constexpr bool operator<=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator<=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt des Typs `pair` auf der linken Seite des Operators.

*right*<br/>
Ein Objekt des Typs `pair` auf der rechten Seite des Operators.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das `pair`-Objekt links vom Operator kleiner gleich dem `pair`-Objekt rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

In einem Vergleich von Paaren haben die ersten Elemente der Werte der beiden Paare die höchste Priorität. Unterscheiden sie sich, wird das Ergebnis ihres Vergleichs als Ergebnis des Vergleichs des Paars verwendet. Sind die Werte der ersten Elemente nicht unterschiedlich, werden die Werte der zweiten Elemente verglichen, und das Ergebnis von deren Vergleich wird als Ergebnis des Vergleichs des Paars verwendet.

### <a name="example"></a>Beispiel

```cpp
// utility_op_le.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3, p4;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );
   p4 = make_pair ( 10, 2.22e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;
   cout << "The pair p4 is: ( " << p4.first << ", "
        << p4.second << " )." << endl << endl;

   if ( p1 <= p2 )
      cout << "The pair p1 is less than or equal to the pair p2." << endl;
   else
      cout << "The pair p1 is greater than the pair p2." << endl;

   if ( p1 <= p3 )
      cout << "The pair p1 is less than or equal to the pair p3." << endl;
   else
      cout << "The pair p1 is greater than the pair p3." << endl;

   if ( p1 <= p4 )
      cout << "The pair p1 is less than or equal to the pair p4." << endl;
   else
      cout << "The pair p1 is greater than the pair p4." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).
The pair p4 is: ( 10, 0.222 ).

The pair p1 is less than or equal to the pair p2.
The pair p1 is greater than the pair p3.
The pair p1 is less than or equal to the pair p4.
```

## <a name="op_gt"></a> operator&gt;

Testet, ob das pair-Objekt links vom Operator größer als das pair-Objekt rechts vom Operator ist.

```cpp
template <class Type>
constexpr bool operator>(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator>(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt des Typs `pair` auf der linken Seite des Operators.

*right*<br/>
Ein Objekt des Typs `pair` auf der rechten Seite des Operators.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das `pair`-Objekt links vom Operator strikt größer als das `pair`-Objekt rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Die `left` `pair` Objekt wird als strikt größer als die `right` `pair` Objekt, wenn *linken* ist größer als und ungleich *rechten*.

In einem Vergleich von Paaren haben die ersten Elemente der Werte der beiden Paare die höchste Priorität. Unterscheiden sie sich, wird das Ergebnis ihres Vergleichs als Ergebnis des Vergleichs des Paars verwendet. Sind die Werte der ersten Elemente nicht unterschiedlich, werden die Werte der zweiten Elemente verglichen, und das Ergebnis von deren Vergleich wird als Ergebnis des Vergleichs des Paars verwendet.

### <a name="example"></a>Beispiel

```cpp
// utility_op_gt.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3, p4;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );
   p4 = make_pair ( 10, 2.22e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;
   cout << "The pair p4 is: ( " << p4.first << ", "
        << p4.second << " )." << endl << endl;

   if ( p1 > p2 )
      cout << "The pair p1 is greater than the pair p2." << endl;
   else
      cout << "The pair p1 is not greater than the pair p2." << endl;

   if ( p1 > p3 )
      cout << "The pair p1 is greater than the pair p3." << endl;
   else
      cout << "The pair p1 is not greater than the pair p3." << endl;

   if ( p1 > p4 )
      cout << "The pair p1 is greater than the pair p4." << endl;
   else
      cout << "The pair p1 is not greater than the pair p4." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).
The pair p4 is: ( 10, 0.222 ).

The pair p1 is not greater than the pair p2.
The pair p1 is greater than the pair p3.
The pair p1 is not greater than the pair p4.
```

## <a name="op_gt_eq"></a> operator&gt;=

Testet, ob das pair-Objekt links vom Operator größer gleich dem pair-Objekt rechts vom Operator ist.

```cpp
template <class Type>
constexpr bool operator>=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator>=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt des Typs `pair` auf der linken Seite des Operators.

*right*<br/>
Ein Objekt des Typs `pair` auf der rechten Seite des Operators.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das `pair`-Objekt links vom Operator größer gleich dem `pair`-Objekt rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

In einem Vergleich von Paaren haben die ersten Elemente der Werte der beiden Paare die höchste Priorität. Unterscheiden sie sich, wird das Ergebnis ihres Vergleichs als Ergebnis des Vergleichs des Paars verwendet. Sind die Werte der ersten Elemente nicht unterschiedlich, werden die Werte der zweiten Elemente verglichen, und das Ergebnis von deren Vergleich wird als Ergebnis des Vergleichs des Paars verwendet.

### <a name="example"></a>Beispiel

```cpp
// utility_op_ge.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3, p4;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );
   p4 = make_pair ( 10, 2.22e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;
   cout << "The pair p4 is: ( " << p4.first << ", "
        << p4.second << " )." << endl << endl;

   if ( p1 >= p2 )
      cout << "Pair p1 is greater than or equal to pair p2." << endl;
   else
      cout << "The pair p1 is less than the pair p2." << endl;

   if ( p1 >= p3 )
      cout << "Pair p1 is greater than or equal to pair p3." << endl;
   else
      cout << "The pair p1 is less than the pair p3." << endl;

   if ( p1 >= p4 )
      cout << "Pair p1 is greater than or equal to pair p4." << endl;
   else
      cout << "The pair p1 is less than the pair p4." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).
The pair p4 is: ( 10, 0.222 ).

The pair p1 is less than the pair p2.
Pair p1 is greater than or equal to pair p3.
Pair p1 is greater than or equal to pair p4.
```

## <a name="see-also"></a>Siehe auch

[\<utility>](../standard-library/utility.md)<br/>
