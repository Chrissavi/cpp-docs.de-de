---
title: strstream-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- strstream/std::strstream::freeze
- strstream/std::strstream::pcount
- strstream/std::strstream::rdbuf
- strstream/std::strstream::str
dev_langs:
- C++
helpviewer_keywords:
- std::strstream [C++], freeze
- std::strstream [C++], pcount
- std::strstream [C++], rdbuf
- std::strstream [C++], str
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 245391a0625d94fee0a4457f87e7b633ba3d03ca
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859825"
---
# <a name="strstream-class"></a>strstream-Klasse

Beschreibt ein Objekt, das die Einfügung und Extraktion von Elementen und codierten Objekten mit einem Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.

## <a name="syntax"></a>Syntax

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>Hinweise

Das Objekt speichert ein Objekt der Klasse `strstreambuf`.

> [!NOTE]
> Diese Klasse ist veraltet. Verwenden Sie stattdessen [stringstream](../standard-library/sstream-typedefs.md#stringstream) oder [wstringstream](../standard-library/sstream-typedefs.md#wstringstream).

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[strstream](#strstream)|Konstruiert ein Objekt vom Typ `strstream`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[freeze](#freeze)|Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.|
|[pcount](#pcount)|Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.|
|[rdbuf](#rdbuf)|Gibt einen Zeiger auf das dem Stream zugeordnete `strstreambuf`-Objekt zurück.|
|[str](#str)|Ruft [freeze](../standard-library/strstreambuf-class.md#freeze) auf gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<strstream>

**Namespace:** std

## <a name="freeze"></a> strstream::freeze

Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parameter

`_Freezeit` Ein `bool` , der angibt, ob den Stream, fixiert werden soll.

### <a name="remarks"></a>Hinweise

Die Memberfunktion ruft [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*) auf.

### <a name="example"></a>Beispiel

Unter [strstreambuf::freeze](../standard-library/strstreambuf-class.md#freeze) finden Sie ein Beispiel, das **freeze** verwendet.

## <a name="pcount"></a> strstream::pcount

Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente, die in die kontrollierte Sequenz geschrieben wurden.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount) zurück.

### <a name="example"></a>Beispiel

Unter [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) finden Sie ein Beispiel, das pcount verwendet.

## <a name="rdbuf"></a> strstream::rdbuf

Gibt einen Zeiger auf das dem Stream zugeordnete strstreambuf-Objekt zurück.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das dem Stream zugeordnete strstreambuf-Objekt.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Adresse des gespeicherten Streampuffers des Typs **pointer** auf [strstreambuf](../standard-library/strstreambuf-class.md) zurück.

### <a name="example"></a>Beispiel

Unter [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) finden Sie ein Beispiel, das `rdbuf` verwendet.

## <a name="str"></a> strstream::str

Ruft [freeze](../standard-library/strstreambuf-class.md#freeze) auf und gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.

```cpp
char *str();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf den Anfang der kontrollierten Sequenz.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str) zurück.

### <a name="example"></a>Beispiel

Unter [strstream::str](../standard-library/strstreambuf-class.md#str) finden Sie ein Beispiel, das **str** verwendet.

## <a name="strstream"></a> strstream::strstream

Konstruiert ein Objekt vom Typ `strstream`.

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parameter

`count` Die Größe des Puffers.

`_Mode` Der Eingabe- und der Modus des Puffers. Weitere Informationen finden Sie unter [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

`ptr` Der Puffer.

### <a name="remarks"></a>Hinweise

Beide Konstruktoren initialisieren die Basisklasse durch Aufrufen von [streambuf](../standard-library/streambuf-typedefs.md#streambuf)( **sb**), wobei **sb** das gespeicherte Objekt der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) ist. Der erste Konstruktor initialisiert zudem **sb** durch Aufrufen von [strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf). Der zweite Konstruktor initialisiert die Basisklasse auf eine von zwei Arten:

- Wenn `_Mode` & **ios_base::app**== 0, dann muss `ptr` das erste Element eines Arrays von `count`-Elementen festlegen, und der Konstruktor ruft `strstreambuf`( `ptr`, `count`, `ptr`) auf.

- Andernfalls muss `ptr` das erste Element eines Arrays an count-Elementen bezeichnen, die eine C-Zeichenfolge enthält, deren erstes Element von `ptr` bezeichnet wird, und der Konstruktor ruft `strstreambuf`( `ptr`, `count`, `ptr`  +  `strlen`( `ptr`)) auf.

## <a name="see-also"></a>Siehe auch

[iostream](../standard-library/istream-typedefs.md#iostream)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
