---
title: '&lt;hash_set&gt;-Operatoren'
ms.date: 03/27/2019
f1_keywords:
- hash_set/std::operator!=
- hash_set/std::operator==
ms.assetid: 403d8e4e-0b3f-43fb-bc5a-8100c4f331c5
ms.openlocfilehash: 04b662ea260ca650fc51b17c804594fe25434f61
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845793"
---
# <a name="lthash_setgt-operators"></a>&lt;hash_set&gt;-Operatoren

[Operator! =](#op_neq)\
[Operator! = (hash_multiset)](#op_neq_hash_multiset)\
[Operator = =](#op_eq_eq)\
[Operator = = (hash_multiset)](#op_eq_eq_hash_multiset)

## <a name="operator"></a><a name="op_neq"></a> Operator! =

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).

Testet, ob das hash_set-Objekt links vom Operator ungleich dem hash_set-Objekt rechts vom Operator ist.

```cpp
bool operator!=(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken*\
Ein Objekt vom Typ `hash_set`.

*Richting*\
Ein Objekt vom Typ `hash_set`.

### <a name="return-value"></a>Rückgabewert

**`true`** , wenn die Hash_sets nicht gleich sind. , **`false`** Wenn Hash_sets gleich sind.

### <a name="remarks"></a>Bemerkungen

Der Vergleich zwischen den hash_set-Objekten basiert auf einem paarweisen Vergleich zwischen deren Elemente. Zwei hash_sets sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

Die Elemente der [<hash_map->](../standard-library/hash-map.md) und [<hash_set ](../standard-library/hash-set.md) Header Dateien befinden sich im [stdext-Namespace](../standard-library/stdext-namespace.md).

### <a name="example"></a>Beispiel

```cpp
// hash_set_op_ne.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1, hs2, hs3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hs1.insert ( i );
      hs2.insert ( i * i );
      hs3.insert ( i );
   }

   if ( hs1 != hs2 )
      cout << "The hash_sets hs1 and hs2 are not equal." << endl;
   else
      cout << "The hash_sets hs1 and hs2 are equal." << endl;

   if ( hs1 != hs3 )
      cout << "The hash_sets hs1 and hs3 are not equal." << endl;
   else
      cout << "The hash_sets hs1 and hs3 are equal." << endl;
}
```

```Output
The hash_sets hs1 and hs2 are not equal.
The hash_sets hs1 and hs3 are equal.
```

## <a name="operator"></a><a name="op_eq_eq"></a> Operator = =

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).

Testet, ob das hash_set-Objekt links vom Operator gleich dem hash_set-Objekt rechts vom Operator ist.

```cpp
bool operator!==(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken*\
Ein Objekt vom Typ `hash_set`.

*Richting*\
Ein Objekt vom Typ `hash_set`.

### <a name="return-value"></a>Rückgabewert

**`true`** , wenn die hash_set auf der linken Seite des Operators gleich der hash_set rechts vom Operator ist. andernfalls **`false`** .

### <a name="remarks"></a>Bemerkungen

Der Vergleich zwischen den hash_set-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei hash_sets sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// hash_set_op_eq.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i );
   }

   if ( s1 == s2 )
      cout << "The hash_sets s1 and s2 are equal." << endl;
   else
      cout << "The hash_sets s1 and s2 are not equal." << endl;

   if ( s1 == s3 )
      cout << "The hash_sets s1 and s3 are equal." << endl;
   else
      cout << "The hash_sets s1 and s3 are not equal." << endl;
}
```

```Output
The hash_sets s1 and s2 are not equal.
The hash_sets s1 and s3 are equal.
```

## <a name="operator-hash_multiset"></a><a name="op_neq_hash_multiset"></a> Operator! = (hash_multiset)

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).

Überprüft, ob das hash_multiset-Objekt links vom Operator ungleich dem hash_multiset-Objekt rechts vom Operator ist.

```cpp
bool operator!=(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken*\
Ein Objekt vom Typ `hash_multiset`.

*Richting*\
Ein Objekt vom Typ `hash_multiset`.

### <a name="return-value"></a>Rückgabewert

**`true`** , wenn die Hash_multisets nicht gleich sind. , **`false`** Wenn Hash_multisets gleich sind.

### <a name="remarks"></a>Bemerkungen

Der Vergleich zwischen den hash_multiset-Objekten basiert auf einem paarweisen Vergleich zwischen deren Elemente. Zwei hash_multisets sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// hashset_op_ne.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1, hs2, hs3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hs1.insert ( i );
      hs2.insert ( i * i );
      hs3.insert ( i );
   }

   if ( hs1 != hs2 )
      cout << "The hash_multisets hs1 and hs2 are not equal." << endl;
   else
      cout << "The hash_multisets hs1 and hs2 are equal." << endl;

   if ( hs1 != hs3 )
      cout << "The hash_multisets hs1 and hs3 are not equal." << endl;
   else
      cout << "The hash_multisets hs1 and hs3 are equal." << endl;
}
```

```Output
The hash_multisets hs1 and hs2 are not equal.
The hash_multisets hs1 and hs3 are equal.
```

## <a name="operator-hash_multiset"></a><a name="op_eq_eq_hash_multiset"></a> Operator = = (hash_multiset)

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).

Überprüft, ob das hash_multiset-Objekt links vom Operator gleich dem hash_multiset-Objekt rechts vom Operator ist.

```cpp
bool operator!==(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken*\
Ein Objekt vom Typ `hash_multiset`.

*Richting*\
Ein Objekt vom Typ `hash_multiset`.

### <a name="return-value"></a>Rückgabewert

**`true`** , wenn die Hash_multiset auf der linken Seite des Operators gleich der Hash_multiset rechts vom Operator ist. andernfalls **`false`** .

### <a name="remarks"></a>Bemerkungen

Der Vergleich zwischen den hash_multiset-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei hash_multisets sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// hash_multiset_op_eq.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i );
   }

   if ( s1 == s2 )
      cout << "The hash_multisets s1 and s2 are equal." << endl;
   else
      cout << "The hash_multisets s1 and s2 are not equal." << endl;

   if ( s1 == s3 )
      cout << "The hash_multisets s1 and s2 are equal." << endl;
   else
      cout << "The hash_multisets s1 and s2 are not equal." << endl;
}
```

```Output
The hash_multisets s1 and s2 are not equal.
The hash_multisets s1 and s2 are equal.
```

## <a name="see-also"></a>Weitere Informationen

[<hash_set>](../standard-library/hash-set.md)
