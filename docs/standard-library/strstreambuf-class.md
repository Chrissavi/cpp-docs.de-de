---
title: strstreambuf-Klasse
ms.date: 11/04/2016
f1_keywords:
- strstream/std::strstreambuf::freeze
- strstream/std::strstreambuf::overflow
- strstream/std::strstreambuf::pbackfail
- strstream/std::strstreambuf::pcount
- strstream/std::strstreambuf::seekoff
- strstream/std::strstreambuf::seekpos
- strstream/std::strstreambuf::str
- strstream/std::strstreambuf::underflow
helpviewer_keywords:
- std::strstreambuf [C++], freeze
- std::strstreambuf [C++], overflow
- std::strstreambuf [C++], pbackfail
- std::strstreambuf [C++], pcount
- std::strstreambuf [C++], seekoff
- std::strstreambuf [C++], seekpos
- std::strstreambuf [C++], str
- std::strstreambuf [C++], underflow
ms.assetid: b040b8ea-0669-4eba-8908-6a9cc159c54b
ms.openlocfilehash: 5a9fa47ab19a5935bf0c7c36dea37b3cfe6180ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512384"
---
# <a name="strstreambuf-class"></a>strstreambuf-Klasse

Beschreibt einen Streampuffer, der die Übertragung von Elementen in eine bzw. aus einer Sequenz von Elementen, die in gespeicherten steuert eine **Char** Array-Objekt.

## <a name="syntax"></a>Syntax

```cpp
class strstreambuf : public streambuf
```

## <a name="remarks"></a>Hinweise

Je nachdem, wie das Objekt aufgebaut ist, kann es nach Bedarf reserviert, erweitert und freigegeben werden, um Änderungen in der Sequenz zu berücksichtigen.

Ein aus der Klasse `strstreambuf` abgeleitetes Objekt speichert mehrere Bits mit Modusinformationen als seinen `strstreambuf`-Modus. Diese Bits geben an, ob Folgendes für die gesteuerte Sequenz zutrifft:

- Sie wurde reserviert und muss schließlich freigegeben werden.

- Sie kann geändert werden.

- Sie kann durch erneute Reservierung von Speicher erweitert werden.

- Sie wurde eingefroren und muss daher „aufgetaut“ werden, bevor das Objekt zerstört wird, oder sie muss (sofern reserviert) durch ein Element freigegeben werden, das nicht mit dem Objekt identisch ist.

Eine gesteuerte Sequenz, die eingefroren ist, kann weder geändert noch erweitert werden, unabhängig vom Status dieser einzelnen Modusbits.

Das Objekt speichert auch Zeiger auf zwei Funktionen, mit denen die `strstreambuf`-Speicherbelegung gesteuert wird. Sind diese Zeiger NULL-Zeiger, muss für das Objekt eine eigene Methode des Belegens und Freigebens von Speicher für die gesteuerte Sequenz formuliert sein.

> [!NOTE]
> Diese Klasse ist veraltet. Verwenden Sie stattdessen [stringbuf](../standard-library/sstream-typedefs.md#stringbuf) oder [wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf).

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[strstreambuf](#strstreambuf)|Konstruiert ein Objekt vom Typ `strstreambuf`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[freeze](#freeze)|Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.|
|[overflow](#overflow)|Eine geschützte virtuelle Funktion, die aufgerufen werden kann, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.|
|[pbackfail](#pbackfail)|Eine geschützte virtuelle Memberfunktion, die versucht, ein Element in den Eingabestreams zurückzuschreiben, und es dann zum aktuellen Element macht (auf das der nächste Zeiger zeigt).|
|[pcount](#pcount)|Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.|
|[seekoff](#seekoff)|Eine geschützte virtuelle Memberfunktion, die versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|
|[seekpos](#seekpos)|Eine geschützte virtuelle Memberfunktion, die versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|
|[str](#str)|Ruft [freeze](#freeze) auf und gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.|
|[underflow](#underflow)|Eine geschützte virtuelle Funktion zum Extrahieren des aktuellen Elements aus dem Eingabestream.|

## <a name="requirements"></a>Anforderungen

**Header:** \<strstream>

**Namespace:** std

## <a name="freeze"></a> strstreambuf::freeze

Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parameter

*_Freezeit*<br/>
Ein **"bool"** , der angibt, ob den Stream fixiert werden soll.

### <a name="remarks"></a>Hinweise

Wenn *_Freezeit* ist "true" ändert die Funktion den gespeicherten `strstreambuf` Modus die kontrollierte Sequenz zu fixieren. Andernfalls ist es die kontrollierte Sequenz nicht fixiert.

[str](#str) impliziert `freeze`.

> [!NOTE]
> Ein fixierter Puffer wird während der `strstreambuf`-Zerstörung nicht freigegeben. Sie müssen die Fixierung des Puffers aufheben, bevor er freigegeben wird, um einen Speicherverlust zu vermeiden.

### <a name="example"></a>Beispiel

```cpp
// strstreambuf_freeze.cpp
// compile with: /EHsc

#include <iostream>
#include <strstream>

using namespace std;

void report(strstream &x)
{
    if (!x.good())
        cout << "stream bad" << endl;
    else
        cout << "stream good" << endl;
}

int main()
{
    strstream x;

    x << "test1";
    cout << "before freeze: ";
    report(x);

    // Calling str freezes stream.
    cout.write(x.rdbuf()->str(), 5) << endl;
    cout << "after freeze: ";
    report(x);

    // Stream is bad now, wrote on frozen stream
    x << "test1.5";
    cout << "after write to frozen stream: ";
    report(x);

    // Unfreeze stream, but it is still bad
    x.rdbuf()->freeze(false);
    cout << "after unfreezing stream: ";
    report(x);

    // Clear stream
    x.clear();
    cout << "after clearing stream: ";
    report(x);

    x << "test3";
    cout.write(x.rdbuf()->str(), 10) << endl;

    // Clean up.  Failure to unfreeze stream will cause a
    // memory leak.
    x.rdbuf()->freeze(false);
}
```

```Output
before freeze: stream good
test1
after freeze: stream good
after write to frozen stream: stream bad
after unfreezing stream: stream bad
after clearing stream: stream good
test1test3
```

## <a name="overflow"></a> strstreambuf::overflow

Eine geschützte virtuelle Funktion, die aufgerufen werden kann, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.

```cpp
virtual int overflow(int _Meta = EOF);
```

### <a name="parameters"></a>Parameter

*_Meta*<br/>
Das Zeichen, das in den Puffer eingefügt werden soll, oder `EOF`.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird `EOF` zurückgegeben. Andernfalls gilt: Wenn _ *Meta* == `EOF`, wird ein anderer Wert als `EOF` zurückgegeben. Andernfalls wird \_ *Meta* zurückgegeben.

### <a name="remarks"></a>Hinweise

Wenn _ *Meta* != `EOF`, versucht die geschützte virtuelle Memberfunktion, das Element ( `char`)\_ *Meta* in den Ausgabepuffer einzufügen. Hierfür gibt es verschiedene Möglichkeiten:

- Wenn eine Schreibposition verfügbar ist, kann das Element in der Schreibposition gespeichert werden, und der nächste Zeiger für den Ausgabepuffer kann inkrementiert werden.

- Wenn der gespeicherte strstreambuf Modus anzeigt, dass die kontrollierte Sequenz änderbar, erweiterbar und nicht fixiert ist, kann die Funktion eine Schreibposition verfügbar machen, indem für den Ausgabepuffer eine neue zugewiesen wird. Das Erweitern des Ausgabepuffers erweitert auf diese Weise auch alle zugewiesenen Eingabepuffer.

## <a name="pbackfail"></a> strstreambuf::pbackfail

Eine geschützte virtuelle Memberfunktion, die versucht, ein Element in den Eingabestreams zurückzuschreiben, und es dann zum aktuellen Element macht (auf das der nächste Zeiger zeigt).

```cpp
virtual int pbackfail(int _Meta = EOF);
```

### <a name="parameters"></a>Parameter

*_Meta*<br/>
Das Zeichen, das in den Puffer eingefügt werden soll, oder `EOF`.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird `EOF` zurückgegeben. Andernfalls gilt: Wenn _ *Meta* == `EOF`, wird ein anderer Wert als `EOF` zurückgegeben. Andernfalls wird \_ *Meta* zurückgegeben.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Memberfunktion versucht, ein Element im Eingabepuffer wiederherzustellen und es dann zum aktuellen Element zu machen (der nächste Zeiger zeigt auf das Element).

Wenn _ *Meta* == `EOF`, ist das Element für den Pushback das Element, das sich bereits vor dem aktuellen Element im Stream befindet. Andernfalls wird dieses Element durch **ch** = ( `char`)\_ *Meta* ersetzt. Ein Element kann auf verschiedene Arten durch die Funktion wiederhergestellt werden:

- Wenn eine Position zur Wiederherstellung zur Verfügung steht, und das Element dort gespeicherten gleich `ch`, kann er den nächsten Zeiger für den Eingabepuffer verringert.

- Wenn eine Position zur Wiederherstellung zur Verfügung steht, und wenn der Strstreambuf-Modus angezeigt wird, die kontrollierte Sequenz kann geändert werden, kann die Funktion speichern `ch` in die Position zur Wiederherstellung und Verringern der nächste Zeiger für den Eingabepuffer.

## <a name="pcount"></a> strstreambuf::pcount

Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zähler der Anzahl von Elementen, die in die kontrollierte Sequenz geschrieben wurden.

### <a name="remarks"></a>Hinweise

Wenn [pptr](../standard-library/basic-streambuf-class.md#pptr) ein NULL-Zeiger ist, gibt die Funktion null zurück. Andernfalls wird `pptr`  -  [Pbase](../standard-library/basic-streambuf-class.md#pbase).

### <a name="example"></a>Beispiel

```cpp
// strstreambuf_pcount.cpp
// compile with: /EHsc
#include <iostream>
#include <strstream>
using namespace std;

int main( )
{
   strstream x;
   x << "test1";
   cout << x.rdbuf( )->pcount( ) << endl;
   x << "test2";
   cout << x.rdbuf( )->pcount( ) << endl;
}
```

## <a name="seekoff"></a> strstreambuf::seekoff

Eine geschützte virtuelle Memberfunktion, die versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.

```cpp
virtual streampos seekoff(streamoff _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parameter

*_Off*<br/>
Die Position, die für die Suche, relativ zum *_Way*.

*_Way*<br/>
Gibt den Startpunkt für Offsetvorgänge an. Mögliche Werte sind unter [seekdir](../standard-library/ios-base-class.md#seekdir) aufgeführt.

*_Which*<br/>
Gibt den Modus für die Zeigerposition an. Standardmäßig können Lese- und Schreibpositionen geändert werden.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion eine der beiden Streampositionen erfolgreich ändert, gibt sie die resultierende Streamposition zurück. Andernfalls schlägt sie fehl und gibt eine ungültige Streamposition zurück.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern. Für ein Objekt der Klasse strstreambuf besteht eine Streamposition lediglich aus einem Streamoffset. Das Offset null legt das erste Element der kontrollierten Sequenz fest.

Die neue Position wird wie folgt bestimmt:

- Bei `_Way` == `ios_base::beg` ist die neue Position der Anfang des Streams plus _ *Off*.

- Bei `_Way` == `ios_base::cur` ist die neue Position die aktuelle Streamposition plus _ *Off*.

- Bei `_Way` == `ios_base::end` ist die neue Position das Ende des Streams plus _ *Off*.

Wenn `_Which` & **ios_base::in** ungleich null ist, ändert die Funktion die nächste Position, die im Eingabepuffer gelesen werden soll. Wenn `_Which` & **ios_base::out** ebenfalls ungleich null, `_Way` != **ios_base::cur** und der Ausgabepuffer vorhanden ist, legt die Funktion auch die nächste zu schreibende Position so fest, dass sie der nächsten zu lesenden Position entspricht.

Ansonsten ändert die Funktion die nächste Position, die im Ausgabepuffer geschrieben werden soll, wenn `_Which` & `ios_base::out` ungleich null ist. Andernfalls schlägt der Positionierungsvorgang fehl. Damit eine Positionierung erfolgreich ist, muss die resultierende Streamposition innerhalb der kontrollierten Sequenz liegen.

## <a name="seekpos"></a> strstreambuf::seekpos

Eine geschützte virtuelle Memberfunktion, die versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.

```cpp
virtual streampos seekpos(streampos _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parameter

*_Sp*<br/>
Die Position, nach der gesucht werden soll.

*_Which*<br/>
Gibt den Modus für die Zeigerposition an. Standardmäßig können Lese- und Schreibpositionen geändert werden.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion eine der beiden Streampositionen erfolgreich ändert, gibt sie die resultierende Streamposition zurück. Andernfalls schlägt sie fehl und gibt eine ungültige Streamposition zurück. Vergleichen Sie den Rückgabewert mit `pos_type(off_type(-1))`, um festzustellen, ob die Streamposition ungültig ist.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern. Für ein Objekt der Klasse strstreambuf besteht eine Streamposition lediglich aus einem Streamoffset. Das Offset null legt das erste Element der kontrollierten Sequenz fest. Die neue Position wird von _ *Sp* bestimmt.

Wenn `_Which` & **ios_base::in** ungleich null ist, ändert die Funktion die nächste Position, die im Eingabepuffer gelesen werden soll. Wenn `_Which` & `ios_base::out` ungleich null und der Ausgabepuffer vorhanden ist, legt die Funktion auch die nächste zu schreibende Position so fest, dass sie der nächsten zu lesenden Position entspricht. Ansonsten ändert die Funktion die nächste Position, die im Ausgabepuffer geschrieben werden soll, wenn `_Which` & `ios_base::out` ungleich null ist. Andernfalls schlägt der Positionierungsvorgang fehl. Damit eine Positionierung erfolgreich ist, muss die resultierende Streamposition innerhalb der kontrollierten Sequenz liegen.

## <a name="str"></a> strstreambuf::str

Ruft [freeze](#freeze) auf und gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.

```cpp
char *str();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf den Anfang der kontrollierten Sequenz.

### <a name="remarks"></a>Hinweise

Kein abschließendes Null-Element vorhanden, sofern Sie nicht explizit ein Element einfügen.

### <a name="example"></a>Beispiel

Unter [strstreambuf::freeze](#freeze) finden Sie ein Beispiel, das **str** verwendet.

## <a name="strstreambuf"></a> strstreambuf::strstreambuf

Konstruiert ein Objekt vom Typ `strstreambuf`.

```cpp
explicit strstreambuf(streamsize count = 0);

strstreambuf(void (* _Allocfunc)(size_t),
    void (* _Freefunc)(void*));

strstreambuf(char* _Getptr,
    streamsize count,
    char* _Putptr = 0);

strstreambuf(signed char* _Getptr,
    streamsize count,
    signed char* _Putptr = 0);

strstreambuf(unsigned char* _Getptr,
    streamsize count,
    unsigned char* _Putptr = 0);

strstreambuf(const char* _Getptr,
    streamsize count);

strstreambuf(const signed char* _Getptr,
    streamsize count);

strstreambuf(const unsigned char* _Getptr,
    streamsize count);
```

### <a name="parameters"></a>Parameter

*_Allocfunc*<br/>
Funktion, mit der Speicher zugewiesen wird.

*count*<br/>
Bestimmt die Länge des Puffers verweist *_Getptr*. Wenn *_Getptr* ist kein Argument (erste Konstruktor Form), eine empfohlene Zuweisungsgröße für Puffer.

*_Freefunc*<br/>
Zum Freigeben von Pufferspeicher verwendete Funktion.

*_Getptr*<br/>
Ein Puffer, der für die Eingabe verwendet wird.

*_Putptr*<br/>
Ein Puffer, der für die Ausgabe verwendet wird.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor speichert einen NULL-Zeiger in allen Zeigern, die den Eingabepuffer, den Ausgabepuffer und die strstreambuf-Zuweisung steuern. Legt den strstreambuf-Modus so fest, dass die kontrollierte Sequenz änderbar und erweiterbar ist. Er akzeptiert auch *Anzahl* als empfohlene anfängliche Speichergröße.

Der zweite Konstruktor verhält sich wie die erste, außer dass er _ *Allocfunc* als Zeiger auf die Funktion speichert, die zur Speicherzuweisung aufzurufen ist, und \_ *Freefunc* als Zeiger auf die Funktion, die zum Freigeben dieses Speichers aufzurufen ist.

Die drei Konstruktoren:

```cpp
strstreambuf(char *_Getptr,
    streamsize count,
    char *putptr = 0);

strstreambuf(signed char *_Getptr,
    streamsize count,
    signed char *putptr = 0);

strstreambuf(unsigned char *_Getptr,
    streamsize count,
    unsigned char *putptr = 0);
```

verhalten sich wie der erste, außer dass `_Getptr` das Arrayobjekt festlegt, das die kontrollierte Sequenz enthält. (Daher darf es kein NULL-Zeiger sein.) Die Anzahl der Elemente *N* im Array wird wie folgt bestimmt:

- Wenn (`count` > 0), klicken Sie dann *N* ist `count`.

- Wenn (`count` == 0), klicken Sie dann *N* ist `strlen`(( **const** `char` *) `_Getptr` ).

- Wenn (`count` < 0), klicken Sie dann *N* ist **INT_MAX**.

Wenn `_Putptr` ein NULL-Zeiger ist, legt die Funktion nur einen Eingabepuffer fest indem sie Folgendes ausführt:

```cpp
setg(_Getptr,
    _Getptr,
    _Getptr + N);
```

Andernfalls legt die Eingabe- und Ausgabepuffer fest, indem sie Folgendes ausführt:

```cpp
setg(_Getptr,
    _Getptr,
    _Putptr);

setp(_Putptr,
    _Getptr + N);
```

In diesem Fall muss `_Putptr` im Intervall [ `_Getptr`, `_Getptr`  +  *N*] liegen.

Die drei Konstruktoren:

```cpp
strstreambuf(const char *_Getptr,
    streamsize count);

strstreambuf(const signed char *_Getptr,
    streamsize count);

strstreambuf(const unsigned char *_Getptr,
    streamsize count);
```

verhalten sich wie:

```cpp
streambuf((char *)_Getptr, count);
```

abgesehen davon, dass der gespeicherte Modus die kontrollierte Sequenz weder änderbar noch erweiterbar macht.

## <a name="underflow"></a> strstreambuf::underflow

Eine geschützte virtuelle Funktion zum Extrahieren des aktuellen Elements aus dem Eingabestream.

```cpp
virtual int underflow();
```

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird `EOF` zurückgegeben. Andernfalls wird das aktuelle Element, wie zuvor beschrieben, konvertiert in den Eingabestream zurückgegeben.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Memberfunktion versucht, das aktuelle Element extrahieren `ch` aus dem Eingabepuffer, dann fahren fort, um die aktuelle Streamposition aus, und geben Sie das Element als zurück (`int`) (`unsigned char`) **ch**. Hierfür in nur eine Möglichkeit: Wenn eine Leseposition verfügbar ist, dauert es `ch` wie das Element in der Leseposition gespeichert, und den nächsten Zeiger für den Eingabepuffer verschiebt.

## <a name="see-also"></a>Siehe auch

[streambuf](../standard-library/streambuf-typedefs.md#streambuf)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
