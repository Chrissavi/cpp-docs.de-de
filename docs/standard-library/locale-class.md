---
title: locale-Klasse
ms.date: 03/19/2019
f1_keywords:
- xlocale/std::locale
- xlocale/std::locale::category
- xlocale/std::locale::combine
- xlocale/std::locale::name
- xlocale/std::locale::classic
- xlocale/std::locale::global
- xlocale/std::locale::operator( )
- xlocale/std::locale::facet
- xlocale/std::locale::id
helpviewer_keywords:
- std::locale [C++]
- std::locale [C++], category
- std::locale [C++], combine
- std::locale [C++], name
- std::locale [C++], classic
- std::locale [C++], global
- std::locale [C++], facet
- std::locale [C++], id
ms.assetid: 7dd6d271-472d-4750-8fb5-ea8f55fbef62
ms.openlocfilehash: 551bca93a30bee52dc4c838864df28cb747d91df
ms.sourcegitcommit: 6ddfb8be5e5923a4d90a2c0f93f76a27ce7ac299
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2019
ms.locfileid: "74898844"
---
# <a name="locale-class"></a>locale-Klasse

Die Klasse, die ein Gebietsschemaobjekt beschreibt, das kulturspezifische Informationen als einen Satz von Facets kapselt, die zusammen eine bestimmte lokalisierte Umgebung definieren.

## <a name="syntax"></a>Syntax

```cpp
class locale;
```

## <a name="remarks"></a>Hinweise

Ein Facet ist ein Zeiger auf ein Objekt einer Klasse, die von der [facet](#facet_class)-Klasse abgeleitet wird. Diese verfügt über ein öffentliches Objekt in folgendem Format:

```cpp
static locale::id id;
```

Sie können einen offenen Satz dieser Facets definieren. Sie können auch ein Gebietsschemaobjekt erstellen, das eine beliebige Anzahl von Facets festgelegt.

Vordefinierte Gruppen dieser Facets stellen die [locale-Kategorien](#category) dar, die normalerweise in der Standard-C-Bibliothek von der Funktion `setlocale` verwaltet werden.

Category `collate` (LC_COLLATE) umfasst die Facetten:

```cpp
collate<char>
collate<wchar_t>
```

Category `ctype` (LC_CTYPE) umfasst die Facetten:

```cpp
ctype<char>
ctype<wchar_t>
codecvt<char, char, mbstate_t>
codecvt<wchar_t, char, mbstate_t>
codecvt<char16_t, char, mbstate_t>
codecvt<char32_t, char, mbstate_t>
```

Category `monetary` (LC_MONETARY) umfasst die Facetten:

```cpp
moneypunct<char, false>
moneypunct<wchar_t, false>
moneypunct<char, true>
moneypunct<wchar_t, true>
money_get<char, istreambuf_iterator<char>>
money_get<wchar_t, istreambuf_iterator<wchar_t>>
money_put<char, ostreambuf_iterator<char>>
money_put<wchar_t, ostreambuf_iterator<wchar_t>>
```

Category `numeric` (LC_NUMERIC) umfasst die Facetten:

```cpp
num_get<char, istreambuf_iterator<char>>
num_get<wchar_t, istreambuf_iterator<wchar_t>>
num_put<char, ostreambuf_iterator<char>>
num_put<wchar_t, ostreambuf_iterator<wchar_t>>
numpunct<char>
numpunct<wchar_t>
```

Category `time` (LC_TIME) umfasst die Facetten:

```cpp
time_get<char, istreambuf_iterator<char>>
time_get<wchar_t, istreambuf_iterator<wchar_t>>
time_put<char, ostreambuf_iterator<char>>
time_put<wchar_t, ostreambuf_iterator<wchar_t>>
```

Category `messages` (LC_MESSAGES) umfasst die Facetten:

```cpp
messages<char>
messages<wchar_t>
```

(Die letzte Kategorie ist für POSIX, jedoch nicht für den C-Standard erforderlich.)

Einige dieser vordefinierten Facetten werden von den `iostream`-Klassen verwendet, um die Konvertierung von numerischen Werten in und aus Textsequenzen zu steuern.

Ein Objekt der locale-Klasse speichert einen Gebietsschemanamen als Objekt der Klasse [string](../standard-library/string-typedefs.md#string). Durch Verwenden eines ungültigen Gebietsschemanamens zur Erstellung eines Gebietsschemafacets oder eines Gebietsschemaobjekts wird ein Objekt der Klasse [runtime_error](../standard-library/runtime-error-class.md) ausgelöst. Der gespeicherte Gebiets Schema Name ist `"*"`, wenn das Gebiets Schema Objekt nicht sicher sein kann, dass ein Gebiets Schema im C-Stil genau dem durch das-Objekt dargestellten Gebiets Schema entspricht. Andernfalls können Sie ein entsprechendes Gebiets Schema in der Standard-C-Bibliothek für einige Gebiets Schema Objekt `locale_object`erstellen, indem Sie `setlocale(LC_ALL , locale_object.`[Namen](#name)`().c_str())`aufrufen.

In dieser Implementierung können Sie außerdem die statische Memberfunktion aufrufen:

```cpp
static locale empty();
```

zur Erstellung eines Gebietsschemaobjekts, das keine Facets hat. Außerdem handelt es sich um ein transparentes Gebiets Schema. Wenn die Vorlagen Funktionen [has_facet](../standard-library/locale-functions.md#has_facet) und [Use_facet](../standard-library/locale-functions.md#use_facet) den angeforderten Facette in einem transparenten Gebiets Schema nicht finden können, werden zuerst das globale Gebiets Schema und dann, wenn dies transparent ist, das klassische Gebiets Schema abgefragt. Daher können Sie Folgendes schreiben:

```cpp
cout.imbue(locale::empty());
```

Nachfolgende Einfügungen in [`cout`](../standard-library/iostream.md#cout) werden durch den aktuellen Zustand des globalen Gebiets Schemas vermittelt. Sie können sogar Folgendes schreiben:

```cpp
locale loc(locale::empty(),
    locale::classic(),
    locale::numeric);

cout.imbue(loc);
```

Numerische Formatierungsregeln für nachfolgende Einfügungen in `cout` bleiben gleich wie im C-Gebietsschema, auch wenn das globale Gebietsschema Änderungsregeln für das Einfügen von Datumsangaben und Währungswerten bietet.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[locale](#locale)|Erstellt ein Gebietsschema, eine Kopie eines Gebietsschemas oder eine Kopie des Gebietsschemas, in dem ein Facet oder eine Kategorie durch ein Facet oder eine Kategorie eines anderen Gebietsschemas ersetzt wurde.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[category](#category)|Ein ganzzahliger Typ, der Bitmaskenwerte bereitstellt, um Standardfacetfamilien anzugeben.|

### <a name="member-functions"></a>Memberfunktionen

|Memberfunktion|Beschreibung|
|-|-|
|[combine](#combine)|Fügt ein Facet eines angegebenen Gebietsschemas in ein Zielgebietsschema ein.|
|[name](#name)|Gibt den gespeicherten Gebietsschemanamen zurück.|

### <a name="static-functions"></a>Statische Funktionen

|||
|-|-|
|[classic](#classic)|Die statische Memberfunktion gibt ein Gebietsschemaobjekt zurück, das das klassische C-Gebietsschema darstellt.|
|[global](#global)|Setzt das Standardgebietsschema für das Programm zurück.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_eq)|Weist ein Gebiets Schema zu.|
|[Operator!=](#op_neq)|Prüft zwei Gebietsschemen auf Ungleichheit.|
|[operator( )](#op_call)|Vergleicht zwei `basic_string`-Objekte.|
|[operator==](#op_eq_eq)|Prüft zwei Gebietsschemen auf Gleichheit.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[facet](#facet_class)|Eine Klasse, die als Basisklasse für alle Gebietsschemafacets dient.|
|[`id`](#id_class)|Die Memberklasse stellt eine einzigartige Facetidentifikation bereit, die als Index zum Suchen von Facets in einem Gebietsschema verwendet wird.|

## <a name="requirements"></a>-Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="category"></a> locale::category

Ein ganzzahliger Typ, der Bitmaskenwerte bereitstellt, um Standardfacetfamilien anzugeben.

```cpp
typedef int category;
static const int collate = LC_COLLATE;
static const int ctype = LC_CTYPE;
static const int monetary = LC_MONETARY;
static const int numeric = LC_NUMERIC;
static const int time = LC_TIME;
static const int messages = LC_MESSAGES;
static const int all = LC_ALL;
static const int none = 0;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für einen **int** -Typ, der eine Gruppe von unterschiedlichen Elementen des Typs "lokale Bitmaske" der Klasse "locale" darstellen kann oder zur Darstellung der entsprechenden C-Gebiets Schema Kategorien verwendet werden kann. Die Elemente sind:

- `collate`entsprechend der Kategorie C LC_COLLATE

- `ctype`entsprechend der Kategorie C LC_CTYPE

- `monetary`entsprechend der Kategorie C LC_MONETARY

- `numeric`entsprechend der Kategorie C LC_NUMERIC

- `time`entsprechend der Kategorie C LC_TIME

- `messages`entsprechend der POSIX-Kategorie LC_MESSAGES

Zwei weitere nützliche Werte sind:

- `none`, die keiner der C-Kategorien entspricht

- `all`, die der C-Union aller Kategorien entspricht LC_ALL

Sie können eine beliebige Gruppe von Kategorien darstellen, indem Sie `OR` mit diesen Konstanten wie in `monetary` &#124; `time`verwenden.

## <a name="classic"></a> locale::classic

Die statische Memberfunktion gibt ein Gebietsschemaobjekt zurück, das das klassische C-Gebietsschema darstellt.

```cpp
static const locale& classic();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das C-Gebietsschema.

### <a name="remarks"></a>Hinweise

Das klassische c-Gebiets Schema ist das US-englische ASCII-Gebiets Schema in der Standard-c-Bibliothek. Dabei handelt es sich um das Gebiets Schema, das implizit in nicht internationalisierten Programmen verwendet wird.

### <a name="example"></a>Beispiel

```cpp
// locale_classic.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "german" );
   locale loc2 = locale::global( loc1 );
   cout << "The name of the previous locale is: " << loc2.name( )
        << "." << endl;
   cout << "The name of the current locale is: " << loc1.name( )
        << "." << endl;

   if (loc2 == locale::classic( ) )
      cout << "The previous locale was classic." << endl;
   else
      cout << "The previous locale was not classic." << endl;

   if (loc1 == locale::classic( ) )
      cout << "The current locale is classic." << endl;
   else
      cout << "The current locale is not classic." << endl;
}
```

```Output
The name of the previous locale is: C.
The name of the current locale is: German_Germany.1252.
The previous locale was classic.
The current locale is not classic.
```

## <a name="combine"></a> locale::combine

Fügt ein Facet eines angegebenen Gebietsschemas in ein Zielgebietsschema ein.

```cpp
template <class Facet>
locale combine(const locale& source_locale) const;
```

### <a name="parameters"></a>Parameters

*source_locale*\
Das Gebietsschema enthält das Facet, das in das Zielgebietsschema eingefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Die Member-Funktion gibt ein Gebiets Schema Objekt zurück, das in ersetzt oder **\*dieses** die in *source_locale*aufgelisteten Facet`Facet` hinzufügt.

### <a name="example"></a>Beispiel

```cpp
// locale_combine.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main() {
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s; it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;

   locale loc2 ( "C" );
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;

   locale loc3 = loc2.combine<collate<_TCHAR> > (loc);
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;
}
```

## <a name="facet_class"></a> facet-Klasse

Eine Klasse, die als Basisklasse für alle Gebietsschemafacets dient.

```cpp
class facet {
protected:
    explicit facet(size_t references = 0);
    virtual ~facet();
private:
    facet(const facet&) // not defined
    void operator=(const facet&) // not defined
};
```

### <a name="remarks"></a>Hinweise

Sie können kein Objekt der Klasse `facet`kopieren oder zuweisen. Sie können Objekte, die von der Klasse `locale::facet` abgeleitet wurden, erstellen oder zerstören, aber nicht die Objekte der richtigen Basisklasse. In der Regel erstellen Sie ein Objekt `_Myfac` das von `facet` abgeleitet ist, wenn Sie eine `locale`erstellen, wie in `locale loc(locale::classic(), new _Myfac);`

In solchen Fällen sollte der Konstruktor für die Basisklasse `facet` ein Argument NULL- *Verweise* aufweisen. Wenn das Objekt nicht mehr benötigt wird, wird es gelöscht. Daher geben Sie ein *References* -Argument ungleich NULL nur in den seltenen Fällen an, in denen Sie die Verantwortung für die Lebensdauer des Objekts übernehmen.

## <a name="global"></a> locale::global

Setzt das Standardgebietsschema für das Programm zurück. Dieser-Befehl wirkt sich auf das globale Gebiets Schema C++für C und aus.

```cpp
static locale global(const locale& new_default_locale);
```

### <a name="parameters"></a>Parameters

*new_default_locale*\
Das Gebietsschema, das als Standardgebietsschema vom Programm verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Das vorherige Gebietsschema, bevor das Standardgebietsschema zurückgesetzt wurde.

### <a name="remarks"></a>Hinweise

Bei Programmstart ist das globale Gebietsschema gleich dem klassischen Gebietsschema. Die `global()`-Funktion ruft `setlocale( LC_ALL, loc.name. c_str())` auf, um ein entsprechendes Gebietsschema in der Standard-C-Bibliothek festzulegen.

### <a name="example"></a>Beispiel

```cpp
// locale_global.cpp
// compile by using: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( )
{
   locale loc ( "German_germany" );
   locale loc1;
   cout << "The initial locale is: " << loc1.name( ) << endl;
   locale loc2 = locale::global ( loc );
   locale loc3;
   cout << "The current locale is: " << loc3.name( ) << endl;
   cout << "The previous locale was: " << loc2.name( ) << endl;
}
```

```Output
The initial locale is: C
The current locale is: German_Germany.1252
The previous locale was: C
```

## <a name="id_class"></a> id-Klasse

Die Memberklasse stellt eine einzigartige Facetidentifikation bereit, die als Index zum Suchen von Facets in einem Gebietsschema verwendet wird.

```cpp
class id
{
   protected:    id();
   private:      id(const id&)
   void operator=(const id&)  // not defined
};
```

### <a name="remarks"></a>Hinweise

Die Memberklasse beschreibt das statische Memberobjekt, das von jedem Gebietsschemafacet benötigt wird. Sie können kein Objekt der Klasse `id`kopieren oder zuweisen.

## <a name="locale"></a> locale::locale

Erstellt ein Gebietsschema, eine Kopie eines Gebietsschemas oder eine Kopie des Gebietsschemas, in dem ein Facet oder eine Kategorie durch ein Facet oder eine Kategorie eines anderen Gebietsschemas ersetzt wurde. Schließt außerdem einen Dekonstruktor ein.

```cpp
locale();

explicit locale(const char* locale_name, category new_category = all);
explicit locale(const string& locale_name);
locale(const locale& from_locale);
locale(const locale& from_locale, const locale& Other, category new_category);
locale(const locale& from_locale, const char* locale_name, category new_category);

template <class Facet>
locale(const locale& from_locale, const Facet* new_facet);

~locale();
```

### <a name="parameters"></a>Parameters

*locale_name*\
Der Name eines Gebietsschemas.

*from_locale*\
Ein Gebietsschema, das zum Erstellen des neuen Gebietsschemas kopiert werden soll.

*Andere*\
Ein Gebietsschema für die Auswahl einer Kategorie.

*new_category*\
Die Kategorie, die im erstellten Gebietsschema ersetzt werden soll.

*new_facet*\
Das Facet, das im erstellten Gebietsschema ersetzt werden soll.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert das Objekt, um mit dem globalen Gebietsschema übereinzustimmen. Mit dem zweiten und dritten Konstruktoren werden alle Gebiets Schema Kategorien initialisiert, sodass das Verhalten mit dem Namen des Gebiets Schemas konsistent ist *locale_name*. Die übrigen Konstruktoren kopieren *from_locale*, wobei die folgenden Ausnahmen beachtet werden:

`locale(const locale& from_locale, const locale& Other, category new_category);`

ersetzt von *anderen* Facetten, die einer Kategorie c entsprechen, für die C-& *new_category* ungleich 0 (null) ist.

`locale(const locale& from_locale, const char* locale_name, category new_category);`

`locale(const locale& from_locale, const string& locale_name, category new_category);`

ersetzt von `locale(locale_name, all)` diese Facetten, die einer Kategorie *replace_category* entsprechen, für die `replace_category & new_category` ungleich 0 (null) ist.

`template<class Facet> locale(const locale& from_locale, Facet* new_facet);`

ersetzt in (oder fügt zu) *from_locale* die *facetnew_facet*, wenn *new_facet* kein NULL-Zeiger ist.

Wenn der Gebiets Schema Name *locale_name* ein NULL-Zeiger oder anderweitig ungültig ist, löst die Funktion [Runtime_error](../standard-library/runtime-error-class.md)aus.

### <a name="example"></a>Beispiel

```cpp
// locale_locale.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( ) {

   // Second constructor
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;

   // The first (default) constructor
   locale loc2;
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;

   // Third constructor
   locale loc3 (loc2,loc, _M_COLLATE );
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;

   // Fourth constructor
   locale loc4 (loc2, "German_Germany", _M_COLLATE );
   int result4 = use_facet<collate<_TCHAR> > ( loc4 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc4 ) << result4 << endl;
}
```

## <a name="name"></a> locale::name

Gibt den gespeicherten Gebietsschemanamen zurück.

```cpp
string name() const;
```

### <a name="return-value"></a>Rückgabewert

Eine Zeichenfolge, die den Namen des Gebietsschemas angibt.

### <a name="example"></a>Beispiel

```cpp
// locale_name.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "german" );
   locale loc2 = locale::global( loc1 );
   cout << "The name of the previous locale is: "
        << loc2.name( ) << "." << endl;
   cout << "The name of the current locale is: "
        << loc1.name( ) << "." << endl;
}
```

```Output
The name of the previous locale is: C.
The name of the current locale is: German_Germany.1252.
```

## <a name="op_eq"></a>locale:: Operator =

Weist ein Gebiets Schema zu.

```cpp
const locale& operator=(const locale& other) noexcept;
```

## <a name="op_neq"></a> locale::operator!=

Prüft zwei Gebietsschemen auf Ungleichheit.

```cpp
bool operator!=(const locale& right) const;
```

### <a name="parameters"></a>Parameters

*Rechte*\
Eines der Gebietsschemas, die auf Ungleichheit geprüft werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein boolescher Wert, der **true** ist, wenn die Gebiets Schemas keine Kopien desselben Gebiets Schemas sind. Es ist **false** , wenn die Gebiets Schemas Kopien desselben Gebiets Schemas sind.

### <a name="remarks"></a>Hinweise

Zwei Gebiets Schemata sind gleich, wenn Sie das gleiche Gebiets Schema sind, wenn eine Kopie der anderen ist, oder wenn Sie identische Namen haben.

### <a name="example"></a>Beispiel

```cpp
// locale_op_ne.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "German_Germany" );
   locale loc2( "German_Germany" );
   locale loc3( "English" );

   if ( loc1 != loc2 )
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc2 (" << loc2.name( ) << ") are not equal." << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc2 (" << loc2.name( ) << ") are equal." << endl;

   if ( loc1 != loc3 )
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc3 (" << loc3.name( ) << ") are not equal." << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc3 (" << loc3.name( ) << ") are equal." << endl;
}
```

```Output
locales loc1 (German_Germany.1252) and
loc2 (German_Germany.1252) are equal.
locales loc1 (German_Germany.1252) and
loc3 (English_United States.1252) are not equal.
```

## <a name="op_call"></a> locale::operator()

Vergleicht zwei `basic_string`-Objekte.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right) const;
```

### <a name="parameters"></a>Parameters

*Linker*\
Die linke Zeichenfolge.

*Rechte*\
Die rechte Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Die Memberfunktion gibt Folgendes zurück:

- -1, wenn die erste Sequenz im Vergleich kleiner ist als die zweite Sequenz.

- +1, wenn die zweite Sequenz kleiner als die erste Sequenz ist.

- 0, wenn die Sequenzen gleichwertig sind.

### <a name="remarks"></a>Hinweise

Die Memberfunktion führt Folgendes aus:

```cpp
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) < 0);
```

Dies bedeutet, dass Sie ein Gebiets Schema Objekt als Funktions Objekt verwenden können.

### <a name="example"></a>Beispiel

```cpp
// locale_op_compare.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

int main( )
{
   using namespace std;
   wchar_t *sa = L"ztesting";
   wchar_t *sb = L"\0x00DFtesting";
   basic_string<wchar_t> a( sa );
   basic_string<wchar_t> b( sb );

   locale loc( "German_Germany" );
   cout << loc( a,b ) << endl;

   const collate<wchar_t>& fac = use_facet<collate<wchar_t> >( loc );
   cout << ( fac.compare( sa, sa + a.length( ),
       sb, sb + b.length( ) ) < 0) << endl;
}
```

```Output
0
0
```

## <a name="op_eq_eq"></a> locale::operator==

Prüft zwei Gebietsschemen auf Gleichheit.

```cpp
bool operator==(const locale& right) const;
```

### <a name="parameters"></a>Parameters

*Rechte*\
Eines der Gebietsschemas, die auf Gleichheit geprüft werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein boolescher Wert, der **true** ist, wenn die Gebiets Schemas Kopien desselben Gebiets Schemas sind. Es ist **false** , wenn die Gebiets Schemas keine Kopien desselben Gebiets Schemas sind.

### <a name="remarks"></a>Hinweise

Zwei Gebiets Schemata sind gleich, wenn Sie das gleiche Gebiets Schema sind, wenn eine Kopie der anderen ist, oder wenn Sie identische Namen haben.

### <a name="example"></a>Beispiel

```cpp
// locale_op_eq.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "German_Germany" );
   locale loc2( "German_Germany" );
   locale loc3( "English" );

   if ( loc1 == loc2 )
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc2 (" << loc2.name( ) << ") are equal."
      << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc2 (" << loc2.name( ) << ") are not equal."
      << endl;

   if ( loc1 == loc3 )
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc3 (" << loc3.name( ) << ") are equal."
      << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc3 (" << loc3.name( ) << ") are not equal."
      << endl;
}
```

```Output
locales loc1 (German_Germany.1252)
and loc2 (German_Germany.1252) are equal.
locales loc1 (German_Germany.1252)
and loc3 (English_United States.1252) are not equal.
```

## <a name="see-also"></a>Siehe auch

[\<locale>](../standard-library/locale.md)\
[Codepages](../c-runtime-library/code-pages.md)\
[Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
