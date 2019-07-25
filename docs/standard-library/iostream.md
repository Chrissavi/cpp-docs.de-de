---
title: '&lt;iostream&gt;'
ms.date: 09/20/2017
f1_keywords:
- <iostream>
- iostream/std::cerr
- iostream/std::cin
- iostream/std::clog
- iostream/std::cout
- iostream/std::wcerr
- iostream/std::wcin
- iostream/std::wclog
- iostream/std::wcout
helpviewer_keywords:
- iostream header
ms.assetid: de5d39e1-7e77-4b55-bcd1-7c77b41515c8
ms.openlocfilehash: 471b149eba32d163e6e3e54e1c2820bbe0b94133
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449045"
---
# <a name="ltiostreamgt"></a>&lt;iostream&gt;

Deklariert Objekte, die das Auslesen und Schreiben in Standard-Streams steuern. Dies ist oft der einzige Header, den Sie für die Eingabe und Ausgabe eines C++ Programms benötigen.

## <a name="syntax"></a>Syntax

```cpp
#include <iostream>
```

> [!NOTE]
> Die \<iostream-> Bibliothek verwendet `#include <ios>`die `#include <streambuf>`Anweisungen `#include <istream>`,, `#include <ostream>` und.

## <a name="remarks"></a>Hinweise

Die Objekte können in zwei Gruppen unterteilt werden:

- [CIN](#cin), [cout](#cout), [Cerr](#cerr)und [Clog](#clog) sind Byte orientiert und Durchführung herkömmlicher Byte-in-a-Time-Übertragungen.

- [wcin](#wcin), [wcout](#wcout), [wcerr](#wcerr) und [clog](#wclog) sind breit ausgerichtet, und übersetzen aus und in Breitzeichen, die intern von der Anwendung bearbeitet werden.

Wenn Sie bestimmte Vorgänge für einen Stream ausführen, wie z. b. die Standardeingabe, können Sie keine Vorgänge mit einer anderen Ausrichtung auf denselben Stream ausführen. Aus diesem Grund kann ein Programm beispielsweise nicht gleichzeitig für [CIN](#cin) und [wcin](#wcin)eingesetzt werden.

Alle in diesem Header deklarierten Objekte verwenden eine besondere Eigenschaft – Sie können davon ausgehen, dass Sie vor statischen Objekten erstellt werden, die Sie definieren, in einer \<Übersetzungseinheit, die iostream-> enthält. Gleichermaßen können Sie davon ausgehen, dass diese Objekte nicht zerstört werden, bevor Sie die dektoren für statische Objekte definieren, die Sie definieren. (Die Ausgabe-Streams werden jedoch während der Beendigung des Programms geleert). Aus diesem Grund können Sie Standardstream vor Programmstart oder nach Beendigung des Programms sicher auslesen oder darin schreiben.

Diese Garantie ist jedoch nicht universell. Ein statischer Konstruktor kann eine Funktion in einer anderen Übersetzungseinheit aufrufen. Die aufgerufene Funktion kann nicht davon ausgehen, dass die in diesem Header deklarierten Objekte erstellt wurden, und zwar anhand der unsicheren Reihenfolge, in der Übersetzungseinheiten an der statischen Konstruktion beteiligt sind. Um diese Objekte in diesem Zusammenhang zu verwenden, müssen Sie zuerst ein Objekt der Klasse [ios_base:: Init](../standard-library/ios-base-class.md#init) erstellen.

### <a name="global-stream-objects"></a>Globale Streamobjekte

|||
|-|-|
|[cerr](#cerr)|Gibt den globalen `cerr`-Stream an.|
|[cin](#cin)|Gibt den globalen `cin`-Stream an.|
|[clog](#clog)|Gibt den globalen `clog`-Stream an.|
|[cout](#cout)|Gibt den globalen `cout`-Stream an.|
|[wcerr](#wcerr)|Gibt den globalen `wcerr`-Stream an.|
|[wcin](#wcin)|Gibt den globalen `wcin`-Stream an.|
|[wclog](#wclog)|Gibt den globalen `wclog`-Stream an.|
|[wcout](#wcout)|Gibt den globalen `wcout`-Stream an.|

###  <a name="cerr"></a>Cerr

Das Objekt `cerr` steuert die Ausgabe an einen zu `stderr` gehörigen Streampuffer, der in \<cstdio> deklariert wurde.

```cpp
extern ostream cerr;
```

#### <a name="return-value"></a>Rückgabewert

Ein [ostream](../standard-library/ostream-typedefs.md#ostream)-Objekt.

#### <a name="remarks"></a>Hinweise

Das Objekt steuert ungepufferte Einfügevorgänge in die Standardfehlerausgabe als Byte-Stream. Sobald das Objekt konstruiert wurde, ist der Ausdruck `cerr.`[flags](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) ungleich null und `cerr.tie() == &cout`.

#### <a name="example"></a>Beispiel

```cpp
// iostream_cerr.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

void TestWide( )
{
   int i = 0;
   wcout << L"Enter a number: ";
   wcin >> i;
   wcerr << L"test for wcerr" << endl;
   wclog << L"test for wclog" << endl;
}

int main( )
{
   int i = 0;
   cout << "Enter a number: ";
   cin >> i;
   cerr << "test for cerr" << endl;
   clog << "test for clog" << endl;
   TestWide( );
}
```

###  <a name="cin"></a>derte

Gibt den globalen `cin`-Stream an.

```cpp
extern istream cin;
```

#### <a name="return-value"></a>Rückgabewert

Ein [instream](../standard-library/istream-typedefs.md#istream)-Objekt.

#### <a name="remarks"></a>Hinweise

Das Objekt steuert Extraktionen aus der Standardausgabe als Byte-Stream. Sobald das Objekt konstruiert wurde, gibt der Aufruf `cin.`[tie](../standard-library/basic-ios-class.md#tie) `&`[cout](#cout) zurück.

#### <a name="example"></a>Beispiel

In diesem Beispiel wird `cin` das Fehlerbit auf dem Stream festgelegt, wenn es über nicht numerische Zeichen verfügt. Das Programm löscht das Fehlerbit und entfernt das ungültige Zeichen aus dem Stream, um den Vorgang fortzusetzen.

```cpp
// iostream_cin.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main()
{
   int x;
   cout << "enter choice:";
   cin >> x;
   while (x < 1 || x > 4)
   {
      cout << "Invalid choice, try again:";
      cin >> x;
      // not a numeric character, probably
      // clear the failure and pull off the non-numeric character
      if (cin.fail())
      {
         cin.clear();
         char c;
         cin >> c;
      }
   }
}
```

```Output
2
```

###  <a name="clog"></a>Clog

Gibt den globalen `clog`-Stream an.

```cpp
extern ostream clog;
```

#### <a name="return-value"></a>Rückgabewert

Ein [ostream](../standard-library/ostream-typedefs.md#ostream)-Objekt.

#### <a name="remarks"></a>Hinweise

Das Objekt steuert gepufferte Einfügevorgänge in die Standardfehlerausgabe als Byte-Stream.

#### <a name="example"></a>Beispiel

Unter [cerr](#cerr) finden Sie ein Beispiel für die Verwendung von `clog`.

###  <a name="cout"></a>cout

Gibt den globalen `cout`-Stream an.

```cpp
extern ostream cout;
```

#### <a name="return-value"></a>Rückgabewert

Ein [ostream](../standard-library/ostream-typedefs.md#ostream)-Objekt.

#### <a name="remarks"></a>Hinweise

Das Objekt steuert Einfügevorgänge für die Standardausgabe als Byte-Stream.

#### <a name="example"></a>Beispiel

Unter [cerr](#cerr) finden Sie ein Beispiel für die Verwendung von `cout`.

### <a name="wcerr"></a>wcerr

Gibt den globalen `wcerr`-Stream an.

```cpp
extern wostream wcerr;
```

#### <a name="return-value"></a>Rückgabewert

Ein [wostream](../standard-library/ostream-typedefs.md#wostream)-Objekt.

#### <a name="remarks"></a>Hinweise

Das Objekt steuert ungepufferte Einfügevorgänge in die Standardfehlerausgabe als weiten Stream. Sobald das Objekt konstruiert wurde, ist der Ausdruck `wcerr.`[flags](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) ungleich null.

#### <a name="example"></a>Beispiel

Unter [cerr](#cerr) finden Sie ein Beispiel für die Verwendung von `wcerr`.

### <a name="wcin"></a>wcin

Gibt den globalen `wcin`-Stream an.

```cpp
extern wistream wcin;
```

#### <a name="return-value"></a>Rückgabewert

Ein [wistream](../standard-library/istream-typedefs.md#wistream)-Objekt.

#### <a name="remarks"></a>Hinweise

Das Objekt steuert Extraktionen aus der Standardausgabe als weiten Stream. Sobald das Objekt konstruiert wurde, gibt der Aufruf `wcin.`[tie](../standard-library/basic-ios-class.md#tie) `&`[wcout](#wcout) zurück.

#### <a name="example"></a>Beispiel

Unter [cerr](#cerr) finden Sie ein Beispiel für die Verwendung von `wcin`.

### <a name="wclog"></a>wclog

Gibt den globalen `wclog`-Stream an.

```cpp
extern wostream wclog;
```

#### <a name="return-value"></a>Rückgabewert

Ein [wostream](../standard-library/ostream-typedefs.md#wostream)-Objekt.

#### <a name="remarks"></a>Hinweise

Das Objekt steuert gepufferte Einfügevorgänge für die Standardfehlerausgabe als weiten Stream.

#### <a name="example"></a>Beispiel

Unter [cerr](#cerr) finden Sie ein Beispiel für die Verwendung von `wclog`.

### <a name="wcout"></a>wcout

Gibt den globalen `wcout`-Stream an.

```cpp
extern wostream wcout;
```

#### <a name="return-value"></a>Rückgabewert

Ein [wostream](../standard-library/ostream-typedefs.md#wostream)-Objekt.

#### <a name="remarks"></a>Hinweise

Das Objekt steuert Einfügevorgänge für die Standardausgabe als weiten Stream.

#### <a name="example"></a>Beispiel

Unter [cerr](#cerr) finden Sie ein Beispiel für die Verwendung von `wcout`.

`CString`-Instanzen in einer `wcout`-Anweisung müssen in `const wchar_t*` umgewandelt werden, wie dies im folgenden Beispiel gezeigt ist.

```
CString cs("meow");

wcout <<(const wchar_t*) cs <<endl;
```

Weitere Informationen finden Sie unter [Basic CString Operations](../atl-mfc-shared/basic-cstring-operations.md).

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)
