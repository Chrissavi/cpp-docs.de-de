---
title: '&lt;memory&gt;-Operatoren'
ms.date: 11/04/2016
f1_keywords:
- memory/std::operator!=
- memory/std::operator>
- memory/std::operator>=
- memory/std::operator<
- memory/std::operator<=
- memory/std::operator<<
- memory/std::operator==
ms.assetid: 257e3ba9-c4c2-4ae8-9b11-b156ba9c28de
ms.openlocfilehash: ca1412efb4d095ef9a371b3739d4c282683821dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348457"
---
# <a name="ltmemorygt-operators"></a>&lt;memory&gt;-Operatoren

||||
|-|-|-|
|[Operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Prüft auf Ungleichheit zwischen Objekten.

```cpp
template <class Type, class Other>
bool operator!=(
    const allocator<Type>& left,
    const allocator<Other>& right) throw();

template <class T, class Del1, class U, class Del2>
bool operator!=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator!=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Eines der Objekte, die auf Ungleichheit geprüft werden sollen.

*right*<br/>
Eines der Objekte, die auf Ungleichheit geprüft werden sollen.

*Ty1*<br/>
Der vom linken gemeinsamen Zeiger gesteuerte Typ.

*Ty2*<br/>
Der vom rechten gemeinsamen Zeiger gesteuerte Typ.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Objekte nicht gleich sind; **FALSE**, wenn die Objekte gleich sind.

### <a name="remarks"></a>Hinweise

Der erste Vorlagenoperator gibt "false" zurück. (Alle standardmäßigen allocator-Objekte sind gleich.)

Der zweite und der dritte Vorlagenoperator geben `!(left == right)` zurück.

### <a name="example"></a>Beispiel

```cpp
// memory_op_me.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   allocator<double> Alloc;
   vector <char>:: allocator_type v1Alloc;

   if ( Alloc != v1Alloc )
      cout << "The allocator objects Alloc & v1Alloc not are equal."
           << endl;
   else
      cout << "The allocator objects Alloc & v1Alloc are equal."
           << endl;
}
```

```Output
The allocator objects Alloc & v1Alloc are equal.
```

### <a name="example"></a>Beispiel

```cpp
// std__memory__operator_ne.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(0));
    std::shared_ptr<int> sp1(new int(0));

    std::cout << "sp0 != sp0 == " << std::boolalpha
        << (sp0 != sp0) << std::endl;
    std::cout << "sp0 != sp1 == " << std::boolalpha
        << (sp0 != sp1) << std::endl;

    return (0);
    }
```

```Output
sp0 != sp0 == false
sp0 != sp1 == true
```

## <a name="op_eq_eq"></a> operator==

Prüft auf Gleichheit zwischen Objekten.

```cpp
template <class Type, class Other>
bool operator==(
    const allocator<Type>& left,
    const allocator<Other>& right) throw();

template <class Ty1, class Del1, class Ty2, class Del2>
bool operator==(
    const unique_ptr<Ty1, Del1>& left,
    const unique_ptr<Ty2, Del2>& right);

template <class Ty1, class Ty2>
bool operator==(
    const shared_ptr<Ty1>& left;,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Eines der Objekte, die auf Gleichheit geprüft werden sollen.

*right*<br/>
Eines der Objekte, die auf Gleichheit geprüft werden sollen.

*Ty1*<br/>
Der vom linken gemeinsamen Zeiger gesteuerte Typ.

*Ty2*<br/>
Der vom rechten gemeinsamen Zeiger gesteuerte Typ.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Objekte gleich sind, **"false"** Wenn Objekte nicht gleich sind.

### <a name="remarks"></a>Hinweise

Der erste Vorlagenoperator gibt "true" zurück. (Alle standardmäßigen allocator-Objekte sind gleich.)

Der zweite und der dritte Vorlagenoperator geben `left.get() ==  right.get()` zurück.

### <a name="example"></a>Beispiel

```cpp
// memory_op_eq.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   allocator<char> Alloc;
   vector <int>:: allocator_type v1Alloc;

   allocator<char> cAlloc(Alloc);
   allocator<int> cv1Alloc(v1Alloc);

   if ( cv1Alloc == v1Alloc )
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."
           << endl;

   if ( cAlloc == Alloc )
      cout << "The allocator objects cAlloc & Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cAlloc & Alloc are not equal."
           << endl;
}
```

```Output
The allocator objects cv1Alloc & v1Alloc are equal.
The allocator objects cAlloc & Alloc are equal.
```

### <a name="example"></a>Beispiel

```cpp
// std__memory__operator_eq.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(0));
    std::shared_ptr<int> sp1(new int(0));

    std::cout << "sp0 == sp0 == " << std::boolalpha
        << (sp0 == sp0) << std::endl;
    std::cout << "sp0 == sp1 == " << std::boolalpha
        << (sp0 == sp1) << std::endl;

    return (0);
    }
```

```Output
sp0 == sp0 == true
sp0 == sp1 == false
```

## <a name="op_gt_eq"></a> operator&gt;=

Testet, ob ein Objekt größer gleich einem zweiten Objekt ist.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator>=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U, Del2>& right);

template <class Ty1, class Ty2>
bool operator>=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Eines der zu vergleichenden Objekte.

*right*<br/>
Eines der zu vergleichenden Objekte.

*Ty1*<br/>
Der vom linken gemeinsamen Zeiger gesteuerte Typ.

*Ty2*<br/>
Der vom rechten gemeinsamen Zeiger gesteuerte Typ.

### <a name="remarks"></a>Hinweise

Die vorlagenoperatoren geben zurück `left.get() >= right.get()`.

## <a name="op_lt"></a> operator&lt;

Testet, ob ein Objekt kleiner als ein zweites Objekt ist.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator<(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator<(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Eines der zu vergleichenden Objekte.

*right*<br/>
Eines der zu vergleichenden Objekte.

*Ty1*<br/>
Der vom linken Zeiger gesteuerte Typ.

*Ty2*<br/>
Der vom rechten Zeiger gesteuerte Typ.

## <a name="op_lt_eq"></a> operator&lt;=

Testet, ob ein Objekt kleiner gleich einem zweiten Objekt ist.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator<=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator<=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Eines der zu vergleichenden Objekte.

*right*<br/>
Eines der zu vergleichenden Objekte.

*Ty1*<br/>
Der vom linken gemeinsamen Zeiger gesteuerte Typ.

*Ty2*<br/>
Der vom rechten gemeinsamen Zeiger gesteuerte Typ.

### <a name="remarks"></a>Hinweise

Die vorlagenoperatoren geben zurück. `left.get() <= right.get()`

## <a name="op_gt"></a> operator&gt;

Testet, ob ein Objekt größer als ein zweites Objekt ist.

```cpp
template <class Ty1, class Del1, class Ty2, class Del2>
bool operator>(
    const unique_ptr<Ty1, Del1>& left,
    const unique_ptr<Ty2&, Del2gt;& right);

template <class Ty1, class Ty2>
bool operator>(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Eines der zu vergleichenden Objekte.

*right*<br/>
Eines der zu vergleichenden Objekte.

*Ty1*<br/>
Der vom linken gemeinsamen Zeiger gesteuerte Typ.

*Ty2*<br/>
Der vom rechten gemeinsamen Zeiger gesteuerte Typ.

## <a name="op_lt_lt"></a> operator&lt;&lt;

Schreibt den freigegebenen Zeiger auf den Stream.

```cpp
template <class Elem, class Tr, class Ty>
std::basic_ostream<Elem, Tr>& operator<<(std::basic_ostream<Elem, Tr>& out,
    shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>Parameter

*Elem*<br/>
Der Typ des Streamelements.

*Tr*<br/>
Der Typ des Streamelements.

*Ty*<br/>
Der vom freigegebenen Zeiger gesteuerte Typ.

*out*<br/>
Der Ausgabestream.

*sp*<br/>
Der freigegebene Zeiger.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt `out << sp.get()` zurück.

### <a name="example"></a>Beispiel

```cpp
// std__memory__operator_sl.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(5));

    std::cout << "sp0 == " << sp0 << " (varies)" << std::endl;

    return (0);
    }
```

```Output
sp0 == 3f3040 (varies)
```

## <a name="see-also"></a>Siehe auch

[\<memory>](../standard-library/memory.md)<br/>
