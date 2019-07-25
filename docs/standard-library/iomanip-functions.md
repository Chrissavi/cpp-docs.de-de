---
title: '&lt;iomanip&gt;-Funktionen'
ms.date: 11/04/2016
f1_keywords:
- iomanip/std::get_money
- iomanip/std::get_time
- iomanip/std::put_money
- iomanip/std::put_time
- iomanip/std::quoted
- iomanip/std::resetiosflags
- iomanip/std::setbase
- iomanip/std::setfill
- iomanip/std::setiosflags
- iomanip/std::setprecision
- iomanip/std::setw
ms.assetid: 3ddde610-70cc-4cfa-8a89-3e83d1d356a8
helpviewer_keywords:
- std::get_money [C++]
- std::get_time [C++]
- std::put_money [C++]
- std::put_time [C++]
- std::quoted [C++]
- std::resetiosflags [C++]
- std::setbase [C++]
- std::setfill [C++]
- std::setiosflags [C++]
- std::setprecision [C++]
- std::setw [C++]
ms.openlocfilehash: 09bb043c40774b102dee023773349223a2fbb4a9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449218"
---
# <a name="ltiomanipgt-functions"></a>&lt;iomanip&gt;-Funktionen

||||
|-|-|-|
|[get_money](#iomanip_get_money)|[get_time](#iomanip_get_time)|[put_money](#iomanip_put_money)|
|[put_time](#iomanip_put_time)|[quoted](#quoted)|[resetiosflags](#resetiosflags)|
|[setbase](#setbase)|[setfill](#setfill)|[setiosflags](#setiosflags)|
|[setprecision](#setprecision)|[setw](#setw)|

## <a name="iomanip_get_money"></a> get_money

Extrahiert mithilfe des gewünschten Formats einen Währungswert aus einem Stream, und gibt den Wert in einem Parameter zurück.

```cpp
template <class Money>
T7 get_money(Money& _Amount, bool _Intl);
```

### <a name="parameters"></a>Parameter

*_Amount*\
Der extrahierte Währungswert.

*_Intl*\
Wenn **true**, verwenden Sie das internationale Format. Der Standardwert ist **false**.

### <a name="remarks"></a>Hinweise

Der Manipulator gibt ein Objekt zurück, das beim Extrahieren aus dem `str`Stream sich `formatted input function` als verhält, das die Member- `get` `money_get` Funktion für das Gebiets Schema Element `str`aufruft, das zugeordnet ist. dabei wird *_Intl* verwendet. Geben Sie das internationale Format an. Bei erfolgreicher Ausführung speichert der-Befehl in *_Amount* den extrahierten monetären Wert. Dann gibt der Manipulator `str` zurück.

`Money` muss Typ `long double` oder eine Instanziierung von `basic_string` sein, das die gleichen Parameter und Merkmale wie `str` aufweist.

## <a name="iomanip_get_time"></a> get_time

Extrahiert einen Zeitwert mithilfe eines gewünschten Formats aus einem Stream. Gibt den Wert als Zeitstruktur in einem Parameter zurück.

```cpp
template <class Elem>
T10 put_time(struct tm *_Tptr, const Elem *_Fmt);
```

### <a name="parameters"></a>Parameter

*_Tptr*\
Die Zeit in Form einer Zeitstruktur.

*_Fmt*\
Das gewünschte Format, das Sie verwenden, um den Zeitwert zu erhalten.

### <a name="remarks"></a>Hinweise

Der Manipulator gibt ein Objekt zurück, das sich, wenn es aus dem Stream `str` extrahiert wurde, wie eine `formatted input function` verhält; diese ruft die Memberfunktion `get` für das zu `str` gehörige Gebietsschemafacet `time_get` auf, um mithilfe von `tptr`die Zeitstruktur und mithilfe von `fmt` den Anfang der mit NULL endenden Formatzeichenfolgen anzugeben. Bei Erfolg speichert der Aufruf den zu jedem extrahierten Zeitfeld gehörigen Wert in der Zeitstruktur. Dann gibt der Manipulator `str` zurück.

## <a name="iomanip_put_money"></a> put_money

Fügt einen Währungswert mithilfe des gewünschten Formats in einen Stream ein.

```cpp
template <class Money>
T8 put_money(const Money& _Amount, bool _Intl);
```

### <a name="parameters"></a>Parameter

*_Amount*\
Der Währungswert, der in den Stream eingefügt werden soll.

*_Intl*\
Auf " **true** " festgelegt, wenn der Manipulator das internationale Format verwenden soll, andernfalls " **false** ".

### <a name="return-value"></a>Rückgabewert

Gibt `str`zurück.

### <a name="remarks"></a>Hinweise

Der Manipulator gibt ein Objekt zurück, das sich, wenn es in den Stream `str` eingefügt wurde, wie eine formatierte Ausgabefunktion verhält; diese ruft die Memberfunktion `put` für das zu `str` gehörige Gebietsschemafacet `money_put` auf. Bei erfolgreicher Ausführung fügt `amount` der-Befehl entsprechend formatiert ein und verwendet * _Intl` to indicate international format and `Str.`, as the fill element. The manipulator then returns `Fill () str ".

`Money` muss Typ `long double` oder eine Instanziierung von `basic_string` sein, das die gleichen Parameter und Merkmale wie `str` aufweist.

## <a name="iomanip_put_time"></a> put_time

Schreibt einen Zeitwert mithilfe eines angegebenen Formats von einer Zeitstruktur in einen Stream.

```cpp
template <class Elem>
T10 put_time(struct tm* _Tptr, const Elem* _Fmt);
```

### <a name="parameters"></a>Parameter

*_Tptr*\
Der Zeitwert aus einer Zeitstruktur, der in den Stream geschrieben werden soll.

*_Fmt*\
Das gewünschte Format, das Sie verwenden, um den Zeitwert zu schreiben.

### <a name="remarks"></a>Hinweise

Der Manipulator gibt ein Objekt zurück, das sich, wenn es in den Stream `str` eingefügt wird, wie eine `formatted output function` verhält. Die Ausgabefunktion ruft für das zu `str` gehörige Gebietsschema `time_put` die Memberfunktion `put` auf. Die Output-Funktion gibt mithilfe von *_Tptr* die Zeitstruktur und *_Fmt* an, um den Anfang einer null-terminierten Format Zeichenfolge anzugeben. Bei Erfolg fügt der Aufruf normalen Text aus der Formatzeichenfolge und konvertierte Werte aus der Zeitstruktur ein. Dann gibt der Manipulator `str` zurück.

## <a name="quoted"></a> quoted

**(Neu in C++14)** Ein iostream-Manipulator, der mithilfe der Operatoren „>>“ und „<<“ praktisches Roundtripping von Zeichenfolgen in und aus Streams ermöglicht.

```cpp
quoted(std::string str) // or wstring
quoted(const char* str) //or wchar_t*
quoted(std::string str, char delimiter, char escape) // or wide versions
quoted(const char* str, char delimiter, char escape) // or wide versions
```

### <a name="parameters"></a>Parameter

*SRT*\
Ein Std:: String, Char\*, Zeichenfolgenliteralzeichen oder unformatierte Zeichen folgen Literale oder eine breite Version von diesen (z. b\*. Std:: wstring, wchar_t).

*Trennzeichen*\
Ein benutzerdefiniertes Zeichen oder Breitzeichen, das als Trennzeichen für den Anfang und das Ende der Zeichenfolge verwendet wird.

*Weg*\
Ein benutzerdefiniertes Zeichen oder Breitzeichen, das als Escapezeichen für Escapesequenzen in der Zeichenfolge verwendet wird.

### <a name="remarks"></a>Hinweise

Siehe auch [Verwenden von Einfügeoperatoren und Festlegen des Formats](../standard-library/using-insertion-operators-and-controlling-format.md).

### <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie Sie `quoted` mit dem standardmäßigen Trennzeichen und Escapezeichen mit schmalen Zeichenfolgen verwenden. Breite Zeichenfolgen werden ebenso unterstützt.

```cpp
#include <iostream>
#include <iomanip>
#include <sstream>

using namespace std;

void show_quoted_v_nonquoted()
{
    // Results are identical regardless of input string type:
    // string inserted { R"(This is a "sentence".)" }; // raw string literal
    // string inserted { "This is a \"sentence\"." };  // regular string literal
    const char* inserted = "This is a \"sentence\".";  // const char*
    stringstream ss, ss_quoted;
    string extracted, extracted_quoted;

    ss << inserted;
    ss_quoted << quoted(inserted);

    cout << "ss.str() is storing       : " << ss.str() << endl;
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl << endl;

    // Round-trip the strings
    ss >> extracted;
    ss_quoted >> quoted(extracted_quoted);

    cout << "After round trip: " << endl;
    cout << "Non-quoted      : " << extracted << endl;
    cout << "Quoted          : " << extracted_quoted << endl;
}

void main(int argc, char* argv[])
{
    show_quoted_v_nonquoted();

    // Keep console window open in debug mode.
    cout << endl << "Press Enter to exit" << endl;
    string input{};
    getline(cin, input);
}

/* Output:
ss.str() is storing       : This is a "sentence".
ss_quoted.str() is storing: "This is a \"sentence\"."

After round trip:
Non-quoted      : This
Quoted          : This is a "sentence".

Press Enter to exit
*/
```

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie ein Trennzeichen und/oder Escapezeichen benutzerdefiniert bereitstellen:

```cpp
#include <iostream>
#include <iomanip>
#include <sstream>

using namespace std;

void show_custom_delimiter()
{
    string inserted{ R"("This" "is" "a" "heavily-quoted" "sentence".)" };
    // string inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };
    // const char* inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };
    stringstream ss, ss_quoted;
    string extracted;

    ss_quoted << quoted(inserted, '*');
    ss << inserted;
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl;
    cout << "ss.str() is storing       : " << ss.str() << endl << endl;

    // Use the same quoted arguments as on insertion.
    ss_quoted >> quoted(extracted, '*');

    cout << "After round trip: " << endl;
    cout << "Quoted          : " << extracted << endl;

    extracted = {};
    ss >> extracted;
    cout << "Non-quoted      : " << extracted << endl << endl;
}

void show_custom_escape()
{
    string inserted{ R"(\\root\trunk\branch\nest\egg\yolk)" };
    // string inserted{ "\\\\root\\trunk\\branch\\nest\\egg\\yolk" };
    stringstream ss, ss_quoted, ss_quoted_custom;
    string extracted;

    // Use '"' as delimiter and '~' as escape character.
    ss_quoted_custom << quoted(inserted, '"', '~');
    ss_quoted << quoted(inserted);
    ss << inserted;
    cout << "ss_quoted_custom.str(): " << ss_quoted_custom.str() << endl;
    cout << "ss_quoted.str()       : " << ss_quoted.str() << endl;
    cout << "ss.str()              : " << ss.str() << endl << endl;

    // No spaces in this string, so non-quoted behaves same as quoted
    // after round-tripping.
}

void main(int argc, char* argv[])
{
    cout << "Custom delimiter:" << endl;
    show_custom_delimiter();
    cout << "Custom escape character:" << endl;
    show_custom_escape();

    // Keep console window open in debug mode.
    cout << endl << "Press Enter to exit" << endl;
    string input{};
    getline(cin, input);
}
/* Output:
Custom delimiter:
ss_quoted.str() is storing: *"This" "is" "a" "heavily-quoted" "sentence".*
ss.str() is storing       : "This" "is" "a" "heavily-quoted" "sentence".

After round trip:
Quoted          : "This" "is" "a" "heavily-quoted" "sentence".
Non-quoted      : "This"

Custom escape character:
ss_quoted_custom.str(): "\\root\trunk\branch\nest\egg\yolk"
ss_quoted.str()       : "\\\\root\\trunk\\branch\\nest\\egg\\yolk"
ss.str()              : \\root\trunk\branch\nest\egg\yolk

Press Enter to exit
*/
```

## <a name="resetiosflags"></a> resetiosflags

Löscht die angegebenen Flags.

```cpp
T1 resetiosflags(ios_base::fmtflags Mask);
```

### <a name="parameters"></a>Parameter

*Chel*\
Die zu löschenden Flags.

### <a name="return-value"></a>Rückgabewert

Der Manipulator gibt ein Objekt zurück, das beim Extrahieren aus oder Einfügen in den `str`Stream **Str**aufruft. [Setf](../standard-library/ios-base-class.md#setf) ( `ios_base::`" [f](../standard-library/ios-base-class.md#fmtflags)", "_ *Mask*"), und `str`gibt dann zurück.

### <a name="example"></a>Beispiel

Unter [setw](../standard-library/iomanip-functions.md#setw) finden Sie ein Beispiel für die Verwendung von `resetiosflags`.

## <a name="setbase"></a> setbase

Legt die Basis für Ganzzahlen fest.

```cpp
T3 setbase(int _Base);
```

### <a name="parameters"></a>Parameter

*_Base*\
Die Zahlenbasis.

### <a name="return-value"></a>Rückgabewert

Der Manipulator gibt ein Objekt zurück, das beim Extrahieren aus oder Einfügen in den `str`Stream **Str**aufruft. `setf`( **Mask**, [ios_base:: basefield](../standard-library/ios-base-class.md#fmtflags)) und gibt dann zurück `str`. `mask` Hier wird wie folgt bestimmt:

- Wenn _ *Base* 8 ist, dann `mask` ist `ios_base::`das [Oct](../standard-library/ios-functions.md#oct).

- Wenn _ *Base* gleich 10 ist, dann ist „mask“ gleich `ios_base::`[dec](../standard-library/ios-functions.md#dec).

- Wenn _ *Base* den Wert 16 hat `mask` , `ios_base::`dann ist [Hex](../standard-library/ios-functions.md#hex).

- Wenn_*Base* irgendein anderer Wert ist, dann ist „mask“ `ios_base::`[fmtflags](../standard-library/ios-base-class.md#fmtflags)(0).

### <a name="example"></a>Beispiel

Unter [setw](../standard-library/iomanip-functions.md#setw) finden Sie ein Beispiel für die Verwendung von `setbase`.

## <a name="setfill"></a> setfill

Legt das zum Auffüllen in einer rechts ausgerichteten Anzeige verwendete Zeichen fest.

```cpp
template <class Elem>
T4 setfill(Elem Ch);
```

### <a name="parameters"></a>Parameter

*Ch*\
Das zum Auffüllen in einer rechts ausgerichteten Anzeige verwendete Zeichen.

### <a name="return-value"></a>Rückgabewert

Der Vorlagen Manipulator gibt ein Objekt zurück, das beim Extrahieren aus oder Einfügen in den `str`Stream **Str**aufruft. [Ausfüllen](../standard-library/basic-ios-class.md#fill) (`Ch`), und gibt dann `str`zurück. Der Typ `Elem` muss mit dem Elementtyp für den Datenstrom `str`identisch sein.

### <a name="example"></a>Beispiel

Unter [setw](../standard-library/iomanip-functions.md#setw) finden Sie ein Beispiel für die Verwendung von `setfill`.

## <a name="setiosflags"></a> setiosflags

Legt die angegebenen Flags fest.

```cpp
T2 setiosflags(ios_base::fmtflags Mask);
```

### <a name="parameters"></a>Parameter

*Chel*\
Die festzulegenden Flags.

### <a name="return-value"></a>Rückgabewert

Der Manipulator gibt ein Objekt zurück, das beim Extrahieren aus oder Einfügen in den `str`Stream **Str**aufruft. [Setf](../standard-library/ios-base-class.md#setf) (_ *Mask*), und gibt dann `str`zurück.

### <a name="example"></a>Beispiel

Unter [setw](../standard-library/iomanip-functions.md#setw) finden Sie ein Beispiel für die Verwendung von `setiosflags`.

## <a name="setprecision"></a> setprecision

Legt die Genauigkeit für Gleitkommawerte fest.

```cpp
T5 setprecision(streamsize Prec);
```

### <a name="parameters"></a>Parameter

*Prec*\
Die Genauigkeit für Gleitkommawerte.

### <a name="return-value"></a>Rückgabewert

Der Manipulator gibt ein Objekt zurück, das beim Extrahieren aus oder Einfügen in den `str`Stream **Str**aufruft. [Genauigkeit](../standard-library/ios-base-class.md#precision) (`Prec`), und gibt dann `str`zurück.

### <a name="example"></a>Beispiel

Unter [setw](../standard-library/iomanip-functions.md#setw) finden Sie ein Beispiel für die Verwendung von `setprecision`.

## <a name="setw"></a> setw

Gibt die Breite des Anzeigefelds für das nächste Element im Stream an.

```cpp
T6 setw(streamsize Wide);
```

### <a name="parameters"></a>Parameter

*Schiedlichsten*\
Die Breite des Anzeigefelds.

### <a name="return-value"></a>Rückgabewert

Der Manipulator gibt ein Objekt zurück, das beim Extrahieren aus oder Einfügen in den `str`Stream **Str**aufruft. [Breite](../standard-library/ios-base-class.md#width) (_ *Breit*), dann wird `str`zurückgegeben.

### <a name="remarks"></a>Hinweise

Mit setw wird die Breite nur für das nächste Element im Stream festgelegt. Der Manipulator muss vor jedem Element eingefügt werden, dessen Breite festgelegt werden soll.

### <a name="example"></a>Beispiel

```cpp
// iomanip_setw.cpp
// compile with: /EHsc
// Defines the entry point for the console application.
//
// Sample use of the following manipulators:
//   resetiosflags
//   setiosflags
//   setbase
//   setfill
//   setprecision
//   setw

#include <iostream>
#include <iomanip>

using namespace std;

const double   d1 = 1.23456789;
const double   d2 = 12.3456789;
const double   d3 = 123.456789;
const double   d4 = 1234.56789;
const double   d5 = 12345.6789;
const long      l1 = 16;
const long      l2 = 256;
const long      l3 = 1024;
const long      l4 = 4096;
const long      l5 = 65536;
int         base = 10;

void DisplayDefault( )
{
   cout << endl << "default display" << endl;
   cout << "d1 = " << d1 << endl;
   cout << "d2 = " << d2 << endl;
   cout << "d3 = " << d3 << endl;
   cout << "d4 = " << d4 << endl;
   cout << "d5 = " << d5 << endl;
}

void DisplayWidth( int n )
{
   cout << endl << "fixed width display set to " << n << ".\n";
   cout << "d1 = " << setw(n) << d1 << endl;
   cout << "d2 = " << setw(n) << d2 << endl;
   cout << "d3 = " << setw(n) << d3 << endl;
   cout << "d4 = " << setw(n) << d4 << endl;
   cout << "d5 = " << setw(n) << d5 << endl;
}

void DisplayLongs( )
{
   cout << setbase(10);
   cout << endl << "setbase(" << base << ")" << endl;
   cout << setbase(base);
   cout << "l1 = " << l1 << endl;
   cout << "l2 = " << l2 << endl;
   cout << "l3 = " << l3 << endl;
   cout << "l4 = " << l4 << endl;
   cout << "l5 = " << l5 << endl;
}

int main( int argc, char* argv[] )
{
   DisplayDefault( );

   cout << endl << "setprecision(" << 3 << ")" << setprecision(3);
   DisplayDefault( );

   cout << endl << "setprecision(" << 12 << ")" << setprecision(12);
   DisplayDefault( );

   cout << setiosflags(ios_base::scientific);
   cout << endl << "setiosflags(" << ios_base::scientific << ")";
   DisplayDefault( );

   cout << resetiosflags(ios_base::scientific);
   cout << endl << "resetiosflags(" << ios_base::scientific << ")";
   DisplayDefault( );

   cout << endl << "setfill('" << 'S' << "')" << setfill('S');
   DisplayWidth(15);
   DisplayDefault( );

   cout << endl << "setfill('" << ' ' << "')" << setfill(' ');
   DisplayWidth(15);
   DisplayDefault( );

   cout << endl << "setprecision(" << 8 << ")" << setprecision(8);
   DisplayWidth(10);
   DisplayDefault( );

   base = 16;
   DisplayLongs( );

   base = 8;
   DisplayLongs( );

   base = 10;
   DisplayLongs( );

   return   0;
}
```

```Output

default display
d1 = 1.23457
d2 = 12.3457
d3 = 123.457
d4 = 1234.57
d5 = 12345.7

setprecision(3)
default display
d1 = 1.23
d2 = 12.3
d3 = 123
d4 = 1.23e+003
d5 = 1.23e+004

setprecision(12)
default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setiosflags(4096)
default display
d1 = 1.234567890000e+000
d2 = 1.234567890000e+001
d3 = 1.234567890000e+002
d4 = 1.234567890000e+003
d5 = 1.234567890000e+004

resetiosflags(4096)
default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setfill('S')
fixed width display set to 15.
d1 = SSSSS1.23456789
d2 = SSSSS12.3456789
d3 = SSSSS123.456789
d4 = SSSSS1234.56789
d5 = SSSSS12345.6789

default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setfill(' ')
fixed width display set to 15.
d1 =      1.23456789
d2 =      12.3456789
d3 =      123.456789
d4 =      1234.56789
d5 =      12345.6789

default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setprecision(8)
fixed width display set to 10.
d1 =  1.2345679
d2 =  12.345679
d3 =  123.45679
d4 =  1234.5679
d5 =  12345.679

default display
d1 = 1.2345679
d2 = 12.345679
d3 = 123.45679
d4 = 1234.5679
d5 = 12345.679

setbase(16)
l1 = 10
l2 = 100
l3 = 400
l4 = 1000
l5 = 10000

setbase(8)
l1 = 20
l2 = 400
l3 = 2000
l4 = 10000
l5 = 200000

setbase(10)
l1 = 16
l2 = 256
l3 = 1024
l4 = 4096
l5 = 65536
```

## <a name="see-also"></a>Siehe auch

[\<iomanip>](../standard-library/iomanip.md)
