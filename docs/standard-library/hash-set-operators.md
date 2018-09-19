---
title: '&lt;hash_set&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- hash_set/std::operator!=
- hash_set/std::operator==
dev_langs:
- C++
ms.assetid: 403d8e4e-0b3f-43fb-bc5a-8100c4f331c5
ms.openlocfilehash: b9c6fe6b39b771b81b6508c10abd43c71774f9a7
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108253"
---
# <a name="lthashsetgt-operators"></a>&lt;hash_set&gt;-Operatoren

||||
|-|-|-|
|[operator!=](#op_neq)|[operator!= (hash_multiset)](#op_neq_hash_multiset)|[operator==](#op_eq_eq)|
|[operator== (hash_multiset)](#op_eq_eq_hash_multiset)|

## <a name="op_neq"></a> operator!=

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).

Testet, ob das hash_set-Objekt links vom Operator ungleich dem hash_set-Objekt rechts vom Operator ist.

```cpp
bool operator!=(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `hash_set`.

*right*<br/>
Ein Objekt vom Typ `hash_set`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die hash_sets ungleich sind; **FALSE**, wenn sie gleich sind.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den hash_set-Objekten basiert auf einem paarweisen Vergleich zwischen deren Elemente. Zwei hash_sets sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

Mitglieder der [< Hash_map >](../standard-library/hash-map.md) und [< Hash_set >](../standard-library/hash-set.md) Headerdateien befinden sich in der [Stdext-Namespace](../standard-library/stdext-namespace.md).

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

## <a name="op_eq_eq"></a> operator==

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).

Testet, ob das hash_set-Objekt links vom Operator gleich dem hash_set-Objekt rechts vom Operator ist.

```cpp
bool operator!==(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `hash_set`.

*right*<br/>
Ein Objekt vom Typ `hash_set`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das hash_set links vom Operator gleich des hash_set rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

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

## <a name="neq_hash_multiset"></a> operator!= (hash_multiset)

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).

Überprüft, ob das hash_multiset-Objekt links vom Operator ungleich dem hash_multiset-Objekt rechts vom Operator ist.

```cpp
bool operator!=(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `hash_multiset`.

*right*<br/>
Ein Objekt vom Typ `hash_multiset`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die hash_multisets ungleich sind; **FALSE**, wenn sie gleich sind.

### <a name="remarks"></a>Hinweise

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

## <a name="eq_eq_hash_multiset"></a> operator== (hash_multiset)

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).

Überprüft, ob das hash_multiset-Objekt links vom Operator gleich dem hash_multiset-Objekt rechts vom Operator ist.

```cpp
bool operator!==(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `hash_multiset`.

*right*<br/>
Ein Objekt vom Typ `hash_multiset`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das hash_multiset links vom Operator gleich des hash_multiset rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

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

## <a name="see-also"></a>Siehe auch

[<hash_set>](../standard-library/hash-set.md)<br/>
