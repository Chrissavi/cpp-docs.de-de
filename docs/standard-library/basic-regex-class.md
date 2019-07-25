---
title: basic_regex-Klasse
ms.date: 03/27/2019
f1_keywords:
- regex/std::basic_regex
helpviewer_keywords:
- basic_regex class
ms.assetid: 8a18c6b4-f22a-4cfd-bc16-b4267867ebc3
ms.openlocfilehash: 8df9e927c430f3b94f5857bf18f575e79d6b922a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453439"
---
# <a name="basicregex-class"></a>basic_regex-Klasse

Umschließt einen regulären Ausdruck.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class RXtraits>
class basic_regex
```

## <a name="parameters"></a>Parameter

*Elem*\
Der zu entsprechende Elementtyp.

*Rxcharakteristika*\
Merkmalklasse für Elemente.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Objekt, das einen regulären Ausdruck enthält. Objekte dieser Vorlagen Klasse können zusammen mit geeigneten Textzeichen folgen Argumenten an die Vorlagen Funktionen [regex_match](../standard-library/regex-functions.md#regex_match), [regex_search](../standard-library/regex-functions.md#regex_search)und [regex_replace](../standard-library/regex-functions.md#regex_replace)weitergegeben werden, um nach Text zu suchen, der mit dem regulären Ausdruck übereinstimmt. Es gibt zwei Spezialisierungs Informationen dieser Vorlagen Klasse mit den Typdefinitionen [Regex](../standard-library/regex-typedefs.md#regex) für Elemente des Typs **char**und [wregex](../standard-library/regex-typedefs.md#wregex) für Elemente des Typs **wchar_t**.

Das Vorlagen Argument *rxproperties* beschreibt verschiedene wichtige Eigenschaften der Syntax der regulären Ausdrücke, die von der Vorlagen Klasse unterstützt werden. Eine Klasse, die diese Merkmale des regulären Ausdrucks angibt, muss dieselbe externe Schnittstelle wie ein Objekt der Vorlagenklasse [regex_traits-Class](../standard-library/regex-traits-class.md) haben.

Einige Funktionen akzeptieren eine Operandensequenz, die einen regulären Ausdruck definiert. Sie können eine solche Operandensequenz wie folgt angeben:

`ptr`--eine NULL-terminierte Sequenz (z. b. eine C-Zeichenfolge für *Elem* des `ptr` Typs **char**) beginnend bei (der kein NULL-Zeiger sein darf), wobei das `value_type()` abschließende Element der Wert ist und nicht Teil der operandensequenz ist.

`ptr`, `count` – eine Sequenz von `count`-Elementen, die bei `ptr` (darf kein NULL-Zeiger sein) beginnen

`str` – die vom `basic_string`-Objekt `str` angegebene Sequenz

`first`, `last` – eine Sequenz von Elementen, die durch die Iteratoren `first` und `last` im Bereich `[first, last)` abgegrenzt werden

`right` – das `basic_regex`-Objekt `right`

Diese Member-Funktionen akzeptieren auch ein `flags` Argument, das verschiedene Optionen für die Interpretation des regulären Ausdrucks angibt, zusätzlich zu den, die durch den *rxtrait* -Typ beschrieben werden.

### <a name="members"></a>Member

|Member|Standardwert|
|-|-|
|public static konstant flag_type iCase|regex_constants:: iCase|
|public static Konstanten flag_type nosubs|regex_constants:: nosubs|
|öffentliches statisches Konstanten flag_type optimieren|regex_constants:: optimieren|
|public static Konstanten flag_type COLLATE|regex_constants:: COLLATE|
|public static konstant flag_type ECMAScript|regex_constants:: ECMAScript|
|public static konstant flag_type Basic|regex_constants:: Basic|
|öffentliches statisches Konstanten flag_type erweitert|regex_constants:: Extended|
|public static konstant flag_type awk|regex_constants:: awk|
|public static konstant flag_type grep|regex_constants:: grep|
|public static konstant flag_type egrep kompilieren|regex_constants:: egrep|
|Private rxmerkmalen-Merkmale||

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_regex](#basic_regex)|Konstruiert das reguläre Ausdrucksobjekt.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[flag_type](#flag_type)|Der Typ der Syntaxoptionsflags.|
|[locale_type](#locale_type)|Der Typ des gespeicherten Gebietsschemaobjekts.|
|[value_type](#value_type)|Der Elementtyp.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[assign](#assign)|Weist dem Objekt für einen regulären Ausdruck einen Wert zu.|
|[flags](#flags)|Gibt Syntaxoptionsflags zurück.|
|[getloc](#getloc)|Gibt das gespeicherte Gebietsschemaobjekt zurück.|
|[imbue](#imbue)|Ändert das gespeicherte Gebietsschemaobjekt.|
|[mark_count](#mark_count)|Gibt die Anzahl der übereinstimmenden Teilausdrücke zurück.|
|[swap](#swap)|Tauscht zwei Objekte mit regulärem Ausdruck.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_eq)|Weist dem Objekt für einen regulären Ausdruck einen Wert zu.|

## <a name="requirements"></a>Anforderungen

**Header:** \<regex >

**Namespace:** std

## <a name="example"></a>Beispiel

```cpp
// std__regex__basic_regex.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

using namespace std;

int main()
{
    regex::value_type elem = 'x';
    regex::flag_type flag = regex::grep;

    elem = elem;  // to quiet "unused" warnings
    flag = flag;

    // constructors
    regex rx0;
    cout << "match(\"abc\", \"\") == " << boolalpha
        << regex_match("abc", rx0) << endl;

    regex rx1("abcd", regex::ECMAScript);
    cout << "match(\"abc\", \"abcd\") == " << boolalpha
        << regex_match("abc", rx1) << endl;

    regex rx2("abcd", 3);
    cout << "match(\"abc\", \"abc\") == " << boolalpha
        << regex_match("abc", rx2) << endl;

    regex rx3(rx2);
    cout << "match(\"abc\", \"abc\") == " << boolalpha
        << regex_match("abc", rx3) << endl;

    string str("abcd");
    regex rx4(str);
    cout << "match(string(\"abcd\"), \"abc\") == " << boolalpha
        << regex_match("abc", rx4) << endl;

    regex rx5(str.begin(), str.end() - 1);
    cout << "match(string(\"abc\"), \"abc\") == " << boolalpha
        << regex_match("abc", rx5) << endl;
    cout << endl;

    // assignments
    rx0 = "abc";
    rx0 = rx1;
    rx0 = str;

    rx0.assign("abcd", regex::ECMAScript);
    rx0.assign("abcd", 3);
    rx0.assign(rx1);
    rx0.assign(str);
    rx0.assign(str.begin(), str.end() - 1);

    rx0.swap(rx1);

    // mark_count
    cout << "\"abc\" mark_count == "
        << regex("abc").mark_count() << endl;
    cout << "\"(abc)\" mark_count == "
        << regex("(abc)").mark_count() << endl;

    // locales
    regex::locale_type loc = rx0.imbue(locale());
    cout << "getloc == imbued == " << boolalpha
        << (loc == rx0.getloc()) << endl;

    // initializer_list
    regex rx6({ 'a', 'b', 'c' }, regex::ECMAScript);
    cout << "match(\"abc\") == " << boolalpha
        << regex_match("abc", rx6);
    cout << endl;
}
```

```Output
match("abc", "") == false
match("abc", "abcd") == false
match("abc", "abc") == true
match("abc", "abc") == true
match(string("abcd"), "abc") == false
match(string("abc"), "abc") == true

"abc" mark_count == 0
"(abc)" mark_count == 1
getloc == imbued == true
match("abc") == true
```

## <a name="assign"></a> basic_regex::assign

Weist dem Objekt für einen regulären Ausdruck einen Wert zu.

```cpp
basic_regex& assign(
    const basic_regex& right);

basic_regex& assign(
    const Elem* ptr,
    flag_type flags = ECMAScript);

basic_regex& assign(
    const Elem* ptr,
    size_type len,
    flag_type flags = ECMAScript);

basic_regex& assign(
    initializer_list<_Elem> IList,
    flag_type flags = regex_constants::ECMAScript);

template <class STtraits, class STalloc>
basic_regex& assign(
    const basic_string<Elem, STtraits, STalloc>& str,
    flag_type flags = ECMAScript);

template <class InIt>
basic_regex& assign(
    InIt first, InIt last,
    flag_type flags = ECMAScript);
```

### <a name="parameters"></a>Parameter

*Stcharakteristika*\
Merkmalklasse für eine Zeichenfolgequelle.

*Stalloc*\
Zuweisungsklasse für eine Zeichenfolgequelle.

*InIt*\
Eingabeiteratortyp für eine Bereichsquelle.

*Richting*\
Zu kopierende RegEx-Quelle.

*PTR*\
Zeiger zum Anfang der zu kopierenden Sequenz.

*fahren*\
Syntaxoptionsflags, die beim Kopieren hinzugefügt werden.

*> len/TD*\
Länge der zu kopierenden Sequenz.

*SRT*\
Zu kopierende Zeichenfolge.

*erstes*\
Anfang der zu kopierenden Sequenz.

*letzten*\
Ende der zu kopierenden Sequenz.

*IList*\
Das zu kopierende initializer_list-Element.

### <a name="remarks"></a>Hinweise

Jede Memberfunktion ersetzt den regulären Ausdruck, der in `*this` enthalten ist durch den regulären Ausdruck, der in der Operandensequenz enthalten ist und gibt dann `*this` zurück.

## <a name="basic_regex"></a> basic_regex::basic_regex

Konstruiert das reguläre Ausdrucksobjekt.

```cpp
basic_regex();

explicit basic_regex(
    const Elem* ptr,
    flag_type flags);

explicit basic_regex(
    const Elem* ptr,
    size_type len,
    flag_type flags);

basic_regex(
    const basic_regex& right);

basic_regex(
    initializer_list<Type> IList,
    flag_type flags);

template <class STtraits, class STalloc>
explicit basic_regex(
    const basic_string<Elem, STtraits, STalloc>& str,
    flag_type flags);

template <class InIt>
explicit basic_regex(
    InIt first,
    InIt last,
    flag_type flags);
```

### <a name="parameters"></a>Parameter

*Stcharakteristika*\
Merkmalklasse für eine Zeichenfolgequelle.

*Stalloc*\
Zuweisungsklasse für eine Zeichenfolgequelle.

*InIt*\
Eingabeiteratortyp für eine Bereichsquelle.

*Richting*\
Zu kopierende RegEx-Quelle.

*PTR*\
Zeiger zum Anfang der zu kopierenden Sequenz.

*fahren*\
Syntaxoptionsflags, die beim Kopieren hinzugefügt werden.

*> len/TD*\
Länge der zu kopierenden Sequenz.

*SRT*\
Zu kopierende Zeichenfolge.

*erstes*\
Anfang der zu kopierenden Sequenz.

*letzten*\
Ende der zu kopierenden Sequenz.

*IList*\
Das zu kopierende initializer_list-Element.

### <a name="remarks"></a>Hinweise

Alle Konstruktoren speichern ein standardmäßig erstelltes Objekt vom Typ `RXtraits`.

Der erste Konstruktor erstellt ein leeres `basic_regex`-Objekt. Die anderen Konstruktoren erstellen ein `basic_regex`-Objekt, das den regulären Ausdruck enthält, der von der Operandensequenz beschrieben wird.

Ein leeres `basic_regex` -Objekt entspricht keiner Zeichen Sequenz bei der Übergabe an [regex_match](../standard-library/regex-functions.md#regex_match), [regex_search](../standard-library/regex-functions.md#regex_search)oder [regex_replace](../standard-library/regex-functions.md#regex_replace).

## <a name="flag_type"></a> basic_regex::flag_type

Der Typ der Syntaxoptionsflags.

```cpp
typedef regex_constants::syntax_option_type flag_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type).

## <a name="flags"></a> basic_regex::flags

Gibt Syntaxoptionsflags zurück.

```cpp
flag_type flags() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt den Wert des `flag_type`-Arguments zurück, das an den letzten Aufruf einer der [basic_regex::assign](#assign)-Memberfunktionen übergeben wurde. Wenn kein Aufruf erfolgt ist, wird der an den Konstruktor übergebene Wert zurückgegeben.

## <a name="getloc"></a> basic_regex::getloc

Gibt das gespeicherte Gebietsschemaobjekt zurück.

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt `traits.` [regex_traits::getloc](../standard-library/regex-traits-class.md#getloc)`()` zurück.

## <a name="imbue"></a> basic_regex::imbue

Ändert das gespeicherte Gebietsschemaobjekt.

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>Parameter

*a.a.o.* \
Das zu speichernde Gebietsschemaobjekt.

### <a name="remarks"></a>Hinweise

Die Memberfunktion leert `*this` und gibt `traits.`[regex_traits::imbue](../standard-library/regex-traits-class.md#imbue)`(loc)` zurück.

## <a name="locale_type"></a> basic_regex::locale_type

Der Typ des gespeicherten Gebietsschemaobjekts.

```cpp
typedef typename RXtraits::locale_type locale_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für [regex_traits::locale_type](../standard-library/regex-traits-class.md#locale_type).

## <a name="mark_count"></a> basic_regex::mark_count

Gibt die Anzahl der übereinstimmenden Teilausdrücke zurück.

```cpp
unsigned mark_count() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Anzahl der Erfassungsgruppen im regulären Ausdruck zurück.

## <a name="op_eq"></a> basic_regex::operator=

Weist dem Objekt für einen regulären Ausdruck einen Wert zu.

```cpp
basic_regex& operator=(const basic_regex& right);

basic_regex& operator=(const Elem *str);

template <class STtraits, class STalloc>
basic_regex& operator=(const basic_string<Elem, STtraits, STalloc>& str);
```

### <a name="parameters"></a>Parameter

*Stcharakteristika*\
Merkmalklasse für eine Zeichenfolgequelle.

*Stalloc*\
Zuweisungsklasse für eine Zeichenfolgequelle.

*Richting*\
Zu kopierende RegEx-Quelle.

*SRT*\
Zu kopierende Zeichenfolge.

### <a name="remarks"></a>Hinweise

Jeder Operator ersetzt den regulären Ausdruck, der in `*this` enthalten ist, durch den regulären Ausdruck, der in der Operandensequenz enthalten ist, und gibt dann `*this`zurück.

## <a name="swap"></a> basic_regex::swap

Tauscht zwei Objekte mit regulärem Ausdruck.

```cpp
void swap(basic_regex& right) throw();
```

### <a name="parameters"></a>Parameter

*Richting*\
Das Objekt mit regulärem Ausdruck, gegen das getauscht werden soll.

### <a name="remarks"></a>Hinweise

Die Member-Funktion tauscht die regulären Ausdrücke `*this` zwischen und *Rechts*aus. Die Funktion führt dies in konstanter Zeit aus und löst keine Ausnahmen aus.

## <a name="value_type"></a> basic_regex::value_type

Der Elementtyp.

```cpp
typedef Elem value_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für den Vorlagen Parameter *Elem*.

## <a name="see-also"></a>Siehe auch

[\<regex>](../standard-library/regex.md)\
[regex_match](../standard-library/regex-functions.md#regex_match)\
[regex_search](../standard-library/regex-functions.md#regex_search)\
[regex_replace](../standard-library/regex-functions.md#regex_replace)\
[regex](../standard-library/regex-typedefs.md#regex)\
[wregex](../standard-library/regex-typedefs.md#wregex)\
[regex_traits-Klasse](../standard-library/regex-traits-class.md)
