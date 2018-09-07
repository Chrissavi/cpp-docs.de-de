---
title: num_get-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocnum/std::num_get
- locale/std::num_get::char_type
- locale/std::num_get::iter_type
- locale/std::num_get::do_get
- locale/std::num_get::get
dev_langs:
- C++
helpviewer_keywords:
- std::num_get [C++]
- std::num_get [C++], char_type
- std::num_get [C++], iter_type
- std::num_get [C++], do_get
- std::num_get [C++], get
ms.assetid: 9933735d-3918-4b17-abad-5fca2adc62d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2cb6364a9f1cb74f9a002e37c278f3686b9916ca
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110122"
---
# <a name="numget-class"></a>num_get-Klasse

Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von Sequenzen des Typs `CharType` in numerische Werte zu steuern.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class num_get : public locale::facet;
```

### <a name="parameters"></a>Parameter

*CharType*<br/>
Der Typ, der innerhalb eines Programms zum Codieren von Zeichen in einem Gebietsschema verwendet wird.

*InputIterator*<br/>
Der Typ des Iterators, von dem die numerische get-Funktionen ihre Eingabe lesen.

## <a name="remarks"></a>Hinweise

Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird ein eindeutiger positiver Wert in **id** gespeichert.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[num_get](#num_get)|Der Konstruktor für Objekte vom Typ `num_get`, die verwendet werden, um numerische Werte aus Sequenzen zu extrahieren.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[char_type](#char_type)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|
|[iter_type](#iter_type)|Ein Typ, der einen Eingabeiterator beschreibt.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[do_get](#do_get)|Eine virtuelle Funktion, die aufgerufen wird, um einen numerischen oder booleschen Wert aus einer Zeichenfolge aufzurufen.|
|[get](#get)|Extrahiert einen numerischen oder booleschen Wert aus einer Zeichenfolge.|

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="char_type"></a> num_get::char_type

Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Hinweise

Der Typ stellt ein Synonym für den Vorlagenparameter **CharType** dar.

## <a name="do_get"></a> num_get::do_get

Eine virtuelle Funktion, die aufgerufen wird, um einen numerischen oder booleschen Wert aus einer Zeichenfolge aufzurufen.

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```

### <a name="parameters"></a>Parameter

*Erste*<br/>
Der Anfang des Zeichenbereichs, aus dem die Zahl gelesen wird.

*last*<br/>
Das Ende des Zeichenbereichs, aus dem die Zahl gelesen wird.

*"_Iosbase"*<br/>
Die [ios_base](../standard-library/ios-base-class.md), deren Flags durch die Konvertierung verwendet werden.

*_State*<br/>
Der Zustand, zu dem die Failbit (siehe [ios_base:: iostate](../standard-library/ios-base-class.md#iostate)) bei einem Fehler hinzugefügt wird.

*val*<br/>
Der gelesene Wert.

### <a name="return-value"></a>Rückgabewert

Der Iterator, nachdem der Wert gelesen wurde.

### <a name="remarks"></a>Hinweise

Die erste virtuelle geschützte Member-Funktion

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;
```

versucht sequenzielle Elemente, die beginnend bei *erste* in der Sequenz `[first, last)` bis eine vollständige erkannt hat, nicht leeres Eingabefeld für ganze Zahlen. Wenn erfolgreich, sie dieses Feld in seinen äquivalenten Wert als Typ konvertiert **lange**, und speichert das Ergebnis in *Val*. Sie gibt einen Iterator zurück, der das erste Element nach dem numerischen Eingabefeld festlegt. Andernfalls speichert die Funktion "nothing" in *Val* und `ios_base::failbit` in `state`. Sie gibt einen Iterator zurück, der das erste Element nach jedem Präfix eines gültigen Eingabefelds für ganze Zahlen festlegt. In beiden Fällen legt die Funktion `state` für `ios_base::eofbit` fest, wenn der Rückgabewert `last` entspricht.

Das Eingabefeld für ganze Zahl wird konvertiert, indem die gleichen Regeln, die von den Überprüfungsfunktionen verwendet wird, für den Abgleich aus, und Konvertieren einer Reihe von **Char** Elemente aus einer Datei. (Jedes dieser **Char** wird davon ausgegangen, dass Element soll einem äquivalenten Element vom Typ zuordnen `Elem` Zuordnung durch eine einfache 1: 1.) Die entsprechende Überprüfungskonvertierungsspezifikation wird wie folgt bestimmt:

Wenn `iosbase.`[ios_base::flags](../standard-library/ios-base-class.md#flags)`() & ios_base::basefield == ios_base::`[oct](../standard-library/ios-functions.md#oct), ist die Konvertierungsspezifikation `lo`.

Wenn `iosbase.flags() & ios_base::basefield == ios_base::`[hex](../standard-library/ios-functions.md#hex), ist die Konvertierungsspezifikation `lx`.

Wenn `iosbase.flags() & ios_base::basefield == 0`, ist die Konvertierungsspezifikation `li`.

Andernfalls ist die Konvertierungsspezifikation `ld`.

Das Format eines Eingabefelds für ganze Zahlen hängt darüber hinaus von [localefacet](../standard-library/locale-class.md#facet_class)`fac` ab, das vom Aufruf [use_facet](../standard-library/locale-functions.md#use_facet)`<`[numpunct](../standard-library/numpunct-class.md)`<Elem>(iosbase.` [ios_base::getloc](../standard-library/ios-base-class.md#getloc)`())` zurückgegeben wird. Dies gilt insbesondere in folgenden Fällen:

`fac.` [numpunct::grouping](../standard-library/numpunct-class.md#grouping) `()` bestimmt, wie Ziffern auf der linken Seite des Dezimaltrennzeichens gruppiert werden.

`fac.` [numpunct::thousands_sep](../standard-library/numpunct-class.md#thousands_sep) `()` bestimmt die Sequenz, die Gruppen von Ziffern auf der linken Seite eines Dezimaltrennzeichens trennt.

Wenn keine Instanzen von `fac.thousands_sep()` im numerischen Eingabefeld auftreten, wird keine Gruppierungseinschränkung auferlegt. Andernfalls werden alle von `fac.grouping()` auferlegten Gruppierungseinschränkung erzwungen und Trennzeichen werden entfernt, bevor die Überprüfungskonvertierung auftritt.

Die vierte virtuelle geschützte Member-Funktion:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```

verhält sich wie die erste, außer dass sie eine Konvertierungsspezifikation von `ld` durch `lu` ersetzt. Bei Erfolg das numerische Eingabefeld in einen Wert vom Typ sie konvertiert **unsigned long** und speichert diesen Wert in *Val*.

Die fünfte virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;
```

verhält sich wie die erste, außer dass sie eine Konvertierungsspezifikation von `ld` durch `lld` ersetzt. Bei Erfolg das numerische Eingabefeld in einen Wert vom Typ sie konvertiert **long long** und speichert diesen Wert in *Val*.

Die sechste virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;
```

verhält sich wie die erste, außer dass sie eine Konvertierungsspezifikation von `ld` durch `llu` ersetzt. Bei Erfolg das numerische Eingabefeld in einen Wert vom Typ sie konvertiert **long long ohne Vorzeichen** und speichert diesen Wert in *Val*.

Die siebte virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;
```

verhält sich wie die erste, außer dass sie versucht, eine Übereinstimmung für ein vollständiges, nicht leeres Gleitkommaeingabefeld zu finden. `fac.`[numpunct::decimal_point](../standard-library/numpunct-class.md#decimal_point)`()` bestimmt die Sequenz, die ganzzahlige Ziffern von Bruchziffern trennt. Der entsprechende Überprüfungsonvertierungsspezifizierer ist `lf`.

Die achte virtuelle geschützte Member-Funktion:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```

verhält sich wie die erste, außer dass sie versucht, eine Übereinstimmung für ein vollständiges, nicht leeres Gleitkommaeingabefeld zu finden. `fac.`[numpunct::decimal_point](../standard-library/numpunct-class.md#decimal_point)`()` bestimmt die Sequenz, die ganzzahlige Ziffern von Bruchziffern trennt. Der entsprechende Überprüfungsonvertierungsspezifizierer ist `lf`.

Die neunte virtuelle geschützte Member-Funktion:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```

verhält sich wie das achte, außer dass der entsprechende Überprüfungskonvertierungsspezifizierer `Lf` ist.

Der zehnte virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```

verhält sich wie die erste, außer dass der entsprechende Überprüfungskonvertierungsspezifizierer `p` ist.

Die letzte (elfte) virtuelle geschützte Member-Funktion:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```

verhält sich wie die erste, außer dass sie versucht, eine Übereinstimmung für ein vollständiges, nicht leeres boolesches Eingabefeld zu finden. Bei Erfolg das boolesche Eingabefeld in einen Wert vom Typ sie konvertiert **"bool"** und speichert diesen Wert in *Val*.

Ein boolesches Eingabefeld akzeptiert eine von zwei Formen. Wenn `iosbase.flags() & ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) falsch ist, ist es mit einem Eingabefeld für ganze Zahlen identisch, mit der Ausnahme, dass der konvertierte Wert entweder 0 (für FALSE) oder 1 (für TRUE) sein muss. Andernfalls muss die Sequenz entweder mit `fac.`[numpunct::falsename](../standard-library/numpunct-class.md#falsename)`()` (für FALSE), oder `fac.`[numpunct::truename](../standard-library/numpunct-class.md#truename)`()` (für TRUE) übereinstimmen.

### <a name="example"></a>Beispiel

Informationen hierzu finden Sie im Beispiel für [get](#get), bei dem die virtuelle Memberfunktion durch `do_get` aufgerufen wird.

## <a name="get"></a> num_get::get

Extrahiert einen numerischen oder booleschen Wert aus einer Zeichenfolge.

```cpp
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```

### <a name="parameters"></a>Parameter

*Erste*<br/>
Der Anfang des Zeichenbereichs, aus dem die Zahl gelesen wird.

*last*<br/>
Das Ende des Zeichenbereichs, aus dem die Zahl gelesen wird.

*"_Iosbase"*<br/>
Die [ios_base](../standard-library/ios-base-class.md), deren Flags durch die Konvertierung verwendet werden.

*_State*<br/>
Der Zustand, zu dem die Failbit (siehe [ios_base:: iostate](../standard-library/ios-base-class.md#iostate)) bei einem Fehler hinzugefügt wird.

*val*<br/>
Der gelesene Wert.

### <a name="return-value"></a>Rückgabewert

Der Iterator, nachdem der Wert gelesen wurde.

### <a name="remarks"></a>Hinweise

Beide Memberfunktionen geben [do_get](#do_get)( `first`, `last`, `_Iosbase`, `_State`, `val`) zurück.

Die erste virtuelle geschützte Memberfunktion versucht, sequenzielle Elemente zuzuordnen. Sie beginnt zuerst in der Sequenz [ `first`, `last`), bis sie ein vollständiges, nicht leeres Eingabefeld für ganze Zahlen erkannt hat. Wenn erfolgreich, sie dieses Feld in seinen äquivalenten Wert als Typ konvertiert **lange** und speichert das Ergebnis in *Val*. Sie gibt einen Iterator zurück, der das erste Element nach dem numerischen Eingabefeld festlegt. Andernfalls speichert die Funktion "nothing" in *Val* und `ios_base::failbit` in _ *Zustand*. Sie gibt einen Iterator zurück, der das erste Element nach jedem Präfix eines gültigen Eingabefelds für ganze Zahlen festlegt. In beiden Fällen, wenn der Rückgabewert *letzten*, legt die Funktion `ios_base::eofbit` in *_State*.

Das Eingabefeld für ganze Zahl wird konvertiert, indem die gleichen Regeln, die von den Überprüfungsfunktionen verwendet wird, für den Abgleich aus, und Konvertieren einer Reihe von **Char** Elemente aus einer Datei. Jedes dieser **Char** wird davon ausgegangen, dass Element soll einem äquivalenten Element vom Typ zuordnen `CharType` durch eine einfache 1: 1-Zuordnung zugeordnet. Die entsprechende Überprüfungskonvertierungsspezifikation wird wie folgt bestimmt:

- Wenn `iosbase`. [Flags](../standard-library/ios-base-class.md#flags) & `ios_base::basefield` == `ios_base::`[oct](../standard-library/ios-functions.md#oct), ist die Konvertierungsspezifikation `lo`.

- Wenn **iosbase.flags** & **ios_base:: basefield** == `ios_base::`[hex](../standard-library/ios-functions.md#hex), ist die Konvertierungsspezifikation `lx`.

- Wenn **iosbase.flags** & **ios_base::basefield** == 0, ist die Konvertierungsspezifikation `li`.

- Andernfalls ist die Konvertierungsspezifikation `ld`.

Das Format eines Eingabefelds für ganze Zahlen hängt darüber hinaus von der [localefacet](../standard-library/locale-class.md#facet_class)**fac** ab, die vom Aufruf [use_facet](../standard-library/locale-functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md) \< **Elem**> ( **iosbase** zurückgegeben wird. [getloc](../standard-library/ios-base-class.md#getloc)). Dies gilt insbesondere in folgenden Fällen:

- **fac**. [grouping](../standard-library/numpunct-class.md#grouping) bestimmt, wie Ziffern auf der linken Seite des Dezimaltrennzeichens gruppiert werden.

- **fac**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep) bestimmt die Sequenz, die Gruppen von Ziffern auf der linken Seite eines Dezimaltrennzeichens trennt.

Wenn keine Instanzen von **fac**. `thousands_sep` im numerischen Eingabefeld auftreten, wird keine Gruppierungseinschränkung auferlegt. Andernfalls werden alle durch **fac**. **grouping** auferlegten Gruppierungseinschränkungen erzwungen und Trennzeichen werden entfernt, bevor die Überprüfungskonvertierung auftritt.

Die zweite virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```

verhält sich wie die erste, außer dass sie eine Konvertierungsspezifikation von `ld` durch `lu` ersetzt. Wenn erfolgreich, das numerische Eingabefeld sie in einen Wert vom Typ konvertiert **unsigned long** und speichert diesen Wert in *Val*.

Die dritte virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```

verhält sich wie die erste, außer dass sie versucht, eine Übereinstimmung für ein vollständiges, nicht leeres Gleitkommaeingabefeld zu finden. **fac**. [decimal_point](../standard-library/numpunct-class.md#decimal_point) bestimmt die Sequenz, die ganzzahlige Ziffern von Bruchziffern trennt. Der entsprechende Überprüfungsonvertierungsspezifizierer ist `lf`.

Die vierte virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```

verhält sich die dritte, außer dass der entsprechende überprüfungskonvertierungsspezifizierer `Lf`.

Die fünfte virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```

verhält sich wie die erste, außer dass der entsprechende Überprüfungskonvertierungsspezifizierer `p` ist.

Die sechste virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```

verhält sich wie die erste, außer dass sie versucht, eine Übereinstimmung für ein vollständiges, nicht leeres boolesches Eingabefeld zu finden. Bei Erfolg das boolesche Eingabefeld in einen Wert vom Typ sie konvertiert **"bool"** und speichert diesen Wert in *Val*.

Ein boolesches Eingabefeld nimmt eine von zwei Formen an. Wenn **iosbase**. **flags** & `ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) **FALSE** ist, ist es identisch mit einem Eingabefeld für ganze Zahlen, mit der Ausnahme, dass der konvertierte Wert entweder 0 für **FALSE**) oder 1 (für **TRUE**) sein muss. Andernfalls muss die Sequenz entweder mit **fac**. [falsename](../standard-library/numpunct-class.md#falsename) (für **FALSE**), oder **fac**. [truename](../standard-library/numpunct-class.md#truename) (für **TRUE**) übereinstimmen.

### <a name="example"></a>Beispiel

```cpp
// num_get_get.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   basic_stringstream<char> psz, psz2;
   psz << "-1000,56";

   ios_base::iostate st = 0;
   long double fVal;
   cout << use_facet <numpunct <char> >(loc).thousands_sep( ) << endl;

   psz.imbue( loc );
   use_facet <num_get <char> >
   (loc).get( basic_istream<char>::_Iter( psz.rdbuf( ) ),
           basic_istream<char>::_Iter(0), psz, st, fVal );

   if ( st & ios_base::failbit )
      cout << "money_get( ) FAILED" << endl;
   else
      cout << "money_get( ) = " << fVal << endl;
}
```

## <a name="iter_type"></a> num_get::iter_type

Ein Typ, der einen Eingabeiterator beschreibt.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `InputIterator` dar.

## <a name="num_get"></a> num_get::num_get

Der Konstruktor für Objekte vom Typ `num_get`, die verwendet werden, um numerische Werte aus Sequenzen zu extrahieren.

```cpp
explicit num_get(size_t _Refs = 0);
```

### <a name="parameters"></a>Parameter

*_Refs*<br/>
Integerwert, der zum Angeben des Speicherverwaltungstyps für das Objekt verwendet wird.

### <a name="remarks"></a>Hinweise

Die möglichen Werte für die *_Refs* Parameter und ihre Bedeutung:

- 0: Die Lebensdauer des Objekts wird von den Gebietsschemas verwaltet, in denen es enthalten ist.

- 1: Die Lebensdauer des Objekts muss manuell verwaltet werden.

- \> 1: Diese Werte sind nicht definiert.

Direkte Beispiele hierfür sind nicht möglich, da der Destruktor geschützt ist.

Der Konstruktor initialisiert sein Basisobjekt mit **locale::**[facet](../standard-library/locale-class.md#facet_class)( `_Refs`).

## <a name="see-also"></a>Siehe auch

[\<locale>](../standard-library/locale.md)<br/>
[Facet-Klasse](../standard-library/locale-class.md#facet_class)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
