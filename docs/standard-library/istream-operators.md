---
title: '&lt;istream&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- istream/std::operator&gt;&gt;
dev_langs:
- C++
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5068c0bd540b1c44d2cdc484c2e511276bd12666
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853059"
---
# <a name="ltistreamgt-operators"></a>&lt;iStream&gt;-Operatoren

## <a name="op_gt_gt"></a> Operator&gt;&gt;

Extrahiert von Zeichenfolgen und Zeichen aus dem Stream.

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem* str);

template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char& Ch);

template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

### <a name="parameters"></a>Parameter

`Ch` Ein Zeichen.

`Istr` Ein Datenstrom.

`str` Eine Zeichenfolge.

`val` Ein Typ.

### <a name="return-value"></a>Rückgabewert

Ein Stream

### <a name="remarks"></a>Hinweise

Die `basic_istream`-Klasse definiert außerdem mehrere Extraktionsoperatoren. Weitere Informationen finden Sie unter [basic_istream::operator>>](../standard-library/basic-istream-class.md#op_gt_gt).

Die Vorlagenfunktion:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

extrahiert bis zu *N*-1-Elemente und speichert sie in das Array, beginnend mit _*Str*. Wenn `Istr`. [Breite](../standard-library/ios-base-class.md#width) ist größer als 0 (null), *N* ist `Istr`. **Breite**ist, andernfalls ist die Größe des größten Arrays mit **Elem** , deklariert werden. Die Funktion speichert immer den Wert **Elem()** nach beliebigen extrahierten Elementen, die gespeichert werden. Die Extraktion hält früh am Ende der Datei, an einem Zeichen mit dem Wert **Elem**(0) (das nicht extrahiert wurde), oder an einem beliebigen Element (das nicht extrahiert wurde), welches von [ws](../standard-library/istream-functions.md#ws) verworfen werden würde. Wenn die Funktion keine Elemente extrahiert, ruft es `Istr`. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**) auf. In jedem Fall ruft `Istr`. **Breite**(0) und gibt `Istr`.

**Sicherheitshinweis** Die null-terminierte Zeichenfolge, die aus dem Eingabestream extrahiert wird, darf nicht die Größe des Zielpuffers `str` überschreiten. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).

Die Vorlagenfunktion:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

extrahiert ein Element, wenn möglich, und speichert es in `Ch`. Andernfalls ruft **ist**. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**) auf. In jedem Fall gibt sie `Istr` zurück.

Die Vorlagenfunktion:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

gibt `Istr` >> ( `char`**\***) `str` zurück.

Die Vorlagenfunktion:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

gibt `Istr` >> ( **char&**) `Ch` zurück.

Die Vorlagenfunktion:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

gibt `Istr` >> ( **char \***) `str` zurück.

Die Vorlagenfunktion:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

gibt `Istr` >> ( **char&**) `Ch` zurück.

Die Vorlagenfunktion:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

gibt `Istr` `>>` `val` (und konvertiert ein `rvalue reference` auf `Istr` zu einer `lvalue` im Prozess).

### <a name="example"></a>Beispiel

```cpp
// istream_op_extract.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   ws( cin );
   char c[10];

   cin.width( 9 );
   cin >> c;
   cout << c << endl;
}
```

## <a name="see-also"></a>Siehe auch

[\<istream>](../standard-library/istream.md)<br/>
