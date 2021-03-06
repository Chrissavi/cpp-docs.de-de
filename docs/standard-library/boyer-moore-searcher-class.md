---
title: boyer_moore_searcher-Klasse
ms.date: 08/03/2019
f1_keywords:
- functional/std::boyer_moore_searcher
helpviewer_keywords:
- std::boyer_moore_searcher [C++]
ms.openlocfilehash: d6fa4dd203336107614ca3431f38846f0c3c89af
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039813"
---
# <a name="boyer_moore_searcher-class"></a>boyer_moore_searcher-Klasse

Die- `boyer_moore_searcher` Klasse ist ein Funktions Objekttyp, der den Boyer-Moore-Algorithmus verwendet, um nach einer im Konstruktor des Objekts angegebenen Sequenz zu suchen. Die Suche erfolgt innerhalb einer anderen Sequenz, die für den Funktions Aufrufoperator des Objekts bereitgestellt wird. Diese Klasse wird als Parameter an eine der über Ladungen von " [Std:: Search](algorithm-functions.md#search)" übergeben.

## <a name="syntax"></a>Syntax

```cpp
template <
    class RandomAccessIterator1,
    class Hash = hash<typename iterator_traits<RandomAccessIterator1>::value_type>,
    class BinaryPredicate = equal_to<>>
class boyer_moore_searcher
{
    boyer_moore_searcher(
        RandomAccessIterator1 pat_first,
        RandomAccessIterator1 pat_last,
        Hash hf = Hash(),
        BinaryPredicate pred = BinaryPredicate());

    template <class RandomAccessIterator2>
    pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
        RandomAccessIterator2 first,
        RandomAccessIterator2 last) const;
};
```

## <a name="members"></a>Member

| Member | BESCHREIBUNG |
| - | - |
| **Konstruktor** | |
| [boyer_moore_searcher](#boyer-moore-searcher-constructor) | Erstellt eine Searcher-Instanz. |
| **Operatoren** | |
| [Operator ()](#operator-call) | Ruft den Vorgang für die Sequenz auf. |

## <a name="boyer_moore_searcher-constructor"></a><a name="boyer-moore-searcher-constructor"></a> boyer_moore_searcher-Konstruktor

Erstellt ein `boyer_moore_searcher` Funktions Objekt, indem die zu suchende Sequenz, ein Hash Funktions Objekt und ein Gleichheits Prädikat verwendet werden.

```cpp
boyer_moore_searcher(
    RandomAccessIterator pat_first,
    RandomAccessIterator pat_last,
    Hash hf = Hash(),
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>Parameter

*pat_first*\
Das ursprüngliche Element der Sequenz, nach der gesucht werden soll.

*pat_last*\
Das Ende der Sequenz, nach der gesucht werden soll.

*HF*\
Ein Aufruf bares Objekt, das zum Hash der Sequenz Elemente verwendet wird.

*pred*\
Das optionale Gleichheits Vergleichs Prädikat für Sequenz Elemente. Wenn kein Gleichheits Vergleichstyp angegeben wird, ist der Standardwert `std::equal_to` .

### <a name="remarks"></a>Bemerkungen

Löst eine beliebige Ausnahme aus, die vom Kopierkonstruktor der Typen *BinaryPredicate*, *Hash*oder *RandomAccessIterator* ausgelöst wird, oder den calloperator von *BinaryPredicate* oder *Hash*.

Diese Klasse ist neu in c++ 17.

## <a name="operator"></a><a name="operator-call"></a> Operator ()

Der calloperator des Funktions Objekts. Sucht innerhalb der Argument Sequenz `[first, last)` nach der Sequenz, die für den Konstruktor angegeben wird.

```cpp
template <class ForwardIterator2>
pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
    RandomAccessIterator2 first,
    RandomAccessIterator2 last) const;
```

### <a name="parameters"></a>Parameter

*erstes*\
Das ursprüngliche Element der Sequenz, in der gesucht werden soll.

*letzten*\
Das Ende der Sequenz, in der gesucht werden soll.

### <a name="remarks"></a>Bemerkungen

Wenn das Suchmuster `[pat_first, pat_last)` leer ist, wird zurückgegeben `make_pair(first, first)` . Wenn das Suchmuster nicht gefunden wird, wird zurückgegeben `make_pair(last, last)` . Andernfalls wird ein paar von Iteratoren an den Anfang und das Ende einer Sequenz in zurückgegeben, `[first, last)` das `[pat_first, pat_last)` entsprechend der Prädikat- *präd*gleich ist.

Diese Klasse ist neu in c++ 17.

## <a name="see-also"></a>Weitere Informationen

[\<functional>](functional.md)\
[algorithmusfunktionen](algorithm-functions.md)\
[boyer_moore_horspool_searcher-Klasse](boyer-moore-horspool-searcher-class.md)\
[Std:: Search](algorithm-functions.md#search)
