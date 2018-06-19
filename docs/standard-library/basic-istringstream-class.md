---
title: basic_istringstream-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- sstream/std::basic_istringstream
- sstream/std::basic_istringstream::allocator_type
- sstream/std::basic_istringstream::rdbuf
- sstream/std::basic_istringstream::str
- sstream/std::basic_istringstream::swap
dev_langs:
- C++
helpviewer_keywords:
- std::basic_istringstream [C++]
- std::basic_istringstream [C++], allocator_type
- std::basic_istringstream [C++], rdbuf
- std::basic_istringstream [C++], str
- std::basic_istringstream [C++], swap
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0754ba9dc63f77793ced17e7950c7fc3ea3290d7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847441"
---
# <a name="basicistringstream-class"></a>basic_istringstream-Klasse

Beschreibt ein Objekt, das die Extrahierung von Elementen und codierten Objekten aus einem Streampuffer der Klasse [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> steuert.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_istringstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>Parameter

`Alloc` Die Allocator-Klasse.

`Elem` Der Typ des grundlegenden Elements der Zeichenfolge.

*TR* für das grundlegende Element der Zeichenfolge spezialisierten Zeichenmerkmale.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Objekt, das das Extrahieren von Elementen und codierten Objekten aus einem Streampuffer der Klasse [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> mit Elementen des Typs **Elem** steuert, dessen Zeichenmerkmale durch die Klasse **Tr** bestimmt, und dessen Elemente durch eine Zuweisung der `Alloc`-Klasse zugewiesen werden. Das Objekt speichert ein Objekt der Klasse basic_stringbuf< **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_istringstream](#basic_istringstream)|Konstruiert ein Objekt vom Typ `basic_istringstream`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[allocator_type](#allocator_type)|Der Type stellt ein Synonym für den Vorlagenparameter `Alloc` dar.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[rdbuf](#rdbuf)|Gibt die Adresse des gespeicherten Streampuffers des Typs `pointer` an [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`> zurück.|
|[str](#str)|Legt den Text in einem Zeichenfolgenpuffer fest, ohne die Schreibposition zu ändern, oder ruft ihn ab.|
|[swap](#swap)|Tauscht die Werte in diesem `basic_istringstream`-Objekt gegen die Werte im bereitgestellten Objekt.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_eq)|Weist die Werte aus dem Objektparameter diesem `basic_istringstream`-Objekt zu.|

## <a name="requirements"></a>Anforderungen

**Header:** \<sstream>

**Namespace:** std

## <a name="allocator_type"></a> basic_istringstream::allocator_type

Der Type stellt ein Synonym für den Vorlagenparameter `Alloc` dar.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_istringstream"></a> basic_istringstream::basic_istringstream

Konstruiert ein Objekt vom Typ `basic_istringstream`.

```cpp
explicit basic_istringstream(
    ios_base::openmode _Mode = ios_base::in);

explicit basic_istringstream(
    const basic_string<Elem, Tr, Alloc>& str,
    ios_base::openmode _Mode = ios_base::in);

basic_istringstream(
    basic_istringstream&& right);
```

### <a name="parameters"></a>Parameter

`_Mode` Eine der Aufzählungen in [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode).

`str` Ein Objekt vom Typ `basic_string`.

`right` Ein Rvalue-Verweis, der eine `basic_istringstream` Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert die Basisklasse durch Aufruf von [basic_istream](../standard-library/basic-istream-class.md)( `sb`), bei der `sb` das gespeicherte Objekt der Klasse [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`> ist. Er initialisiert zudem `sb`sb`basic_stringbuf` durch Aufrufen von <  `Elem``Tr`, `Alloc`>( `_Mode` &#124; `ios_base::in`).

Der zweite Konstruktor initialisiert die Basisklasse durch Aufrufen von `basic_istream(sb)`. Er initialisiert zudem `sb` durch Aufrufen von `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `str`, `_Mode` &#124; `ios_base::in`).

Der dritte Konstruktor initialisiert das Objekt mit dem Inhalt von `right`, das als rvalue-Verweis behandelt wird.

## <a name="op_eq"></a> basic_istringstream::operator=

Weist die Werte aus dem Objektparameter diesem `basic_istringstream`-Objekt zu.

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>Parameter

`right` Ein Rvalue-Verweis auf eine `basic_istringstream` Objekt.

### <a name="remarks"></a>Hinweise

Der Member-Operator ersetzt den Inhalt des Objekts durch den Inhalt von `right`, das als rvalue-Verweis-Verschiebezuweisung verarbeitet wird.

## <a name="rdbuf"></a> basic_istringstream::rdbuf

Gibt die Adresse des gespeicherten Streampuffers des Typs **pointer** zurück, die ein Zeiger auf [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> ist.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des gespeicherten Streampuffers des Typs **pointer**, die ein Zeiger auf basic_stringbuf< **Elem**, **Tr**, `Alloc`> ist.

### <a name="example"></a>Beispiel

Sie finden ein Beispiel, in dem `rdbuf` verwendet wird, unter [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="str"></a> basic_istringstream::str

Legt den Text in einem Zeichenfolgenpuffer fest, ohne die Schreibposition zu ändern, oder ruft ihn ab.

```cpp
basic_string<Elem, Tr, Alloc> str() const;


void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parameter

`_Newstr` Die neue Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Gibt ein Objekt der Klasse [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`> zurück, dessen gesteuerte Sequenz eine Kopie der von **\*this** gesteuerten Sequenz ist.

### <a name="remarks"></a>Hinweise

Die erste Memberfunktion gibt [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str) zurück. Die zweite Memberfunktion ruft `rdbuf` -> **str**( `_Newstr`) auf.

### <a name="example"></a>Beispiel

Unter [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str) finden Sie ein Beispiel, in dem **str** verwendet wird.

## <a name="swap"></a> basic_istringstream::swap

Tauscht die Werte zweier `basic_istringstream`-Objekte aus.

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`right`|Ein `lvalue`-Verweis auf ein `basic_istringstream`-Objekt.|

### <a name="remarks"></a>Hinweise

Die Memberfunktion tauscht die Werte dieses Objekts und die Werte von `right` aus.

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
