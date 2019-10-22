---
title: time_put-Klasse
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put
- locale/std::time_put::char_type
- locale/std::time_put::iter_type
- locale/std::time_put::do_put
- locale/std::time_put::put
helpviewer_keywords:
- std::time_put [C++]
- std::time_put [C++], char_type
- std::time_put [C++], iter_type
- std::time_put [C++], do_put
- std::time_put [C++], put
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
ms.openlocfilehash: 2c0ae501693a8abffc72a23be9c427f31bad65b6
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685418"
---
# <a name="time_put-class"></a>time_put-Klasse

Die Klassen Vorlage beschreibt ein Objekt, das als Gebiets Schema Aspekt fungieren kann, um Konvertierungen von Uhrzeitwerten in Sequenzen vom Typ `CharType` zu steuern.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class time_put : public locale::facet;
```

### <a name="parameters"></a>Parameter

*CharType* -\
Der Typ, der innerhalb eines Programms verwendet wird, um Zeichen zu codieren.

*OutputIterator* -\
Der Typ des Iterators, in den die Time-Put-Funktionen ihre Ausgabe schreiben.

## <a name="remarks"></a>Hinweise

Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird in **id** ein eindeutiger positiver Wert gespeichert.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[time_put](#time_put)|Der Konstruktor für Objekte des Typs `time_put`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[char_type](#char_type)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|
|[iter_type](#iter_type)|Ein Typ, der einen Ausgabeiterator beschreibt.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[do_put](#do_put)|Eine virtuelle Funktion, die Zeit- und Datumsinformationen als Sequenz von `CharType`-Objekten ausgibt.|
|[put](#put)|Gibt Zeit- und Datumsinformationen als Sequenz von `CharType`-Objekten aus.|

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="char_type"></a> time_put::char_type

Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `CharType` dar.

## <a name="do_put"></a> time_put::do_put

Eine virtuelle Funktion, die Zeit- und Datumsinformationen als Sequenz von `CharType`-Objekten ausgibt.

```cpp
virtual iter_type do_put(
    iter_type next,
    ios_base& _Iosbase,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;
```

### <a name="parameters"></a>Parameter

*nächste* \
Ein Ausgabeiterator, in den die Zeichensequenz für Zeit und Datum eingefügt werden soll.

*_Iosbase* \
Nicht verwendet.

*_Pt* \
Die Zeit- und Datumsinformationen, die ausgegeben werden.

*_Fmt* \
Das Format der Ausgabe. Siehe [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) für gültige Werte.

*_Mod* \
Ein Modifizierer für das Format. Siehe [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) für gültige Werte.

### <a name="return-value"></a>Rückgabewert

Ein Iterator an die erste Position hinter dem letzten eingefügten Element.

### <a name="remarks"></a>Hinweise

Die virtuelle geschützte Member-Funktion generiert sequenzielle Elemente, beginnend bei `next` aus Zeitwerten, die im-Objekt gespeichert sind, \* `_Pt` vom Typ `tm`. Die Funktion gibt einen Iterator zurück, der die nächste Stelle zum Einfügen eines Elements nach der generierten Ausgabe festlegt.

Die Ausgabe wird von denselben Regeln generiert, die von `strftime` verwendet werden, mit einem letzten Argument von *_Pt*, um eine Reihe von **char** -Elementen in einem Array zu generieren. Es wird davon ausgegangen, dass jedes solche **char** -Element einem äquivalenten Element vom Typ `CharType` durch eine einfache 1-zu-Eins-Zuordnung zugeordnet wird. Wenn *_mod* gleich 0 (null) ist, ist das effektive Format "% F", wobei "F" durch " *_Fmt*" ersetzt wird. Andernfalls ist das effektive Format "% MF", wobei "M" durch " *_mod*" ersetzt wird.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [put](#put), mit dem `do_put` aufgerufen wird.

## <a name="iter_type"></a> time_put::iter_type

Ein Typ, der einen Ausgabeiterator beschreibt.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `OutputIterator` dar.

## <a name="put"></a> time_put::put

Gibt Zeit- und Datumsinformationen als Sequenz von `CharType`-Objekten aus.

```cpp
iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;

iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parameter

*nächste* \
Ein Ausgabeiterator, in den die Zeichensequenz für Zeit und Datum eingefügt werden soll.

*_Iosbase* \
Nicht verwendet.

*_Fill* \
Das Zeichen vom Typ, das für den Abstand verwendet `CharType`.

*_Pt* \
Die Zeit- und Datumsinformationen, die ausgegeben werden.

*_Fmt* \
Das Format der Ausgabe. Siehe [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) für gültige Werte.

*_Mod* \
Ein Modifizierer für das Format. Siehe [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) für gültige Werte.

*erste* \
Der Anfang der Formatierungszeichenfolge für die Ausgabe. Siehe [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) für gültige Werte.

*Letzter* \
Das Ende der Formatierungszeichenfolge für die Ausgabe. Siehe [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) für gültige Werte.

### <a name="return-value"></a>Rückgabewert

Ein Iterator an die erste Position hinter dem letzten eingefügten Element.

### <a name="remarks"></a>Hinweise

Die erste Member-Funktion gibt [Do_put](#do_put)(`next`, `_Iosbase`, `_Fill`, `_Pt`, `_Fmt`, `_Mod`) zurück. Die zweite Memberfunktion kopiert jedes Element im Intervall [ `first`, `last`) außer Prozentzeichen (%) nach \* `next` ++. Für einen Prozentwert, auf den das Zeichen *C* im Intervall [`first` `last`) folgt, wertet die Funktion stattdessen `next`  =  `do_put` (`next`, `_Iosbase`, `_Fill`, `_Pt`, *C*, 0) aus und überspringt in der Vergangenheit *C*. Wenn *C* jedoch ein Qualifiziererzeichen aus dem Satz EOQ # ist, gefolgt von einem Zeichen 3 im Intervall [4 5), wertet die Funktion stattdessen 6 7 8 (9 0 , 1, 2, 3, *C*) und überspringt 5.

### <a name="example"></a>Beispiel

```cpp
// time_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream<char> pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   t.tm_hour = 5;
   t.tm_min = 30;
   t.tm_sec = 40;
   t.tm_year = 00;
   t.tm_mday = 4;
   t.tm_mon = 6;

   pszPutI.imbue( loc );
   char *pattern = "x: %X %x";
   use_facet <time_put <char> >
   (loc).put(basic_ostream<char>::_Iter(pszPutI.rdbuf( )),
          pszPutI, ' ', &t, pattern, pattern+strlen(pattern));

      cout << "num_put( ) = " << pszPutI.rdbuf( )->str( ) << endl;

      char strftimebuf[255];
      strftime(&strftimebuf[0], 255, pattern, &t);
      cout << "strftime( ) = " << &strftimebuf[0] << endl;
}
```

```Output
num_put( ) = x: 05:30:40 07/04/00
strftime( ) = x: 05:30:40 07/04/00
```

## <a name="time_put"></a> time_put::time_put

Konstruktor für Objekte des Typs `time_put`.

```cpp
explicit time_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parameter

*_Refs* \
Integerwert, der zum Angeben des Speicherverwaltungstyps für das Objekt verwendet wird.

### <a name="remarks"></a>Hinweise

Die möglichen Werte für den Parameter *_Refs* und ihre Bedeutung lauten:

- 0: Die Lebensdauer des Objekts wird von den Gebietsschemas verwaltet, in denen es enthalten ist.

- 1: Die Lebensdauer des Objekts muss manuell verwaltet werden.

- \> 1: diese Werte sind nicht definiert.

Der Konstruktor initialisiert sein Basisobjekt mit [locale:: Face(](../standard-library/locale-class.md#facet_class) *_Refs*).

## <a name="see-also"></a>Siehe auch

[\<locale>](../standard-library/locale.md)\
[time_base-Klasse](../standard-library/time-base-class.md)\
[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
