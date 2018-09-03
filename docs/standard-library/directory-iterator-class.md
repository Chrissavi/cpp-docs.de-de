---
title: directory_iterator-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::directory_iterator
- filesystem/std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::increment
- filesystem/std::experimental::filesystem::directory_iterator::operator=
- filesystem/std::experimental::filesystem::directory_iterator::operator==
- filesystem/std::experimental::filesystem::directory_iterator::operator!=
- filesystem/std::experimental::filesystem::directory_iterator::operator*
- filesystem/std::experimental::filesystem::directory_iterator::operator-&gt;
- filesystem/std::experimental::filesystem::directory_iterator::operator++
dev_langs:
- C++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::directory_iterator::directory_iterator
- std::experimental::filesystem::directory_iterator::increment
- std::experimental::filesystem::directory_iterator::operator=
- std::experimental::filesystem::directory_iterator::operator==
- std::experimental::filesystem::directory_iterator::operator!=
- std::experimental::filesystem::directory_iterator::operator*
- std::experimental::filesystem::directory_iterator::operator-&gt;
- std::experimental::filesystem::directory_iterator::operator++
ms.workload:
- cplusplus
ms.openlocfilehash: b46e4d8fc7b59f8b4919a7e36a85f29f626aa80b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845829"
---
# <a name="directoryiterator-class"></a>directory_iterator-Klasse.

Beschreibt einen Eingabeiterator, der alle Dateinamen in einem Verzeichnis durchläuft. Für einen Iterator „X“ wird der Ausdruck „*X“ zu einem „directory_entry“-Objekt ausgewertet, das den Dateinamen und alles umschließt, was zu dessen Status bekannt ist.

Die Klasse speichert ein Objekt des Typs „path“, das hier zur Veranschaulichung den Namen „mydir“ erhält, der den Namen des zu sequenzierenden Verzeichnisses darstellt, und ein Objekt des Typs „directory_entry“, das hier als „myentry“ bezeichnet wird und den aktuellen Dateinamen in der Verzeichnissequenz darstellt. Ein standardmäßig erstelltes Objekt des Typs „directory_entry“ verfügt über einen leeren „mydir“-Pfadnamen und stellt den Sequenzende-Iterator dar.

Für das Verzeichnis „abc“ mit den Einträgen „def“ und „ghi“ würde der Code:

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

z. B. „visit“ mit den Argumenten „path("abc/def")“ und „path("abc/ghi")“ aufrufen.

Weitere Informationen und Codebeispiele finden Sie unter [File System Navigation (C++) (Dateisystemnavigation (C++))](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Syntax

```cpp
class directory_iterator;
```

## <a name="directoryiteratordirectoryiterator"></a>directory_iterator::directory_iterator

```cpp
directory_iterator() noexcept;
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;
directory_iterator(const directory_iterator&) = default;
directory_iterator(directory_iterator&&) noexcept = default;
```

Der erste Konstruktor erzeugt einen Sequenzende-Iterator. Die zweiten und dritten Konstruktoren speichern „pval“ in „mydir“ und versuchen dann, „mydir“ zu öffnen und als Verzeichnis zu lesen. Bei Erfolg speichern sie den ersten Dateinamen im Verzeichnis in „myentry“. Andernfalls erzeugen sie einen Sequenzende-Iterator.

Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet.

## <a name="directoryiteratorincrement"></a>directory_iterator::increment

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

Die Funktion versucht, zum nächsten Dateinamen im Verzeichnis zu gelangen. Ist sie erfolgreich, speichert sie diesen Dateinamen in „myentry“. Andernfalls erstellt sie einen Sequenzende-Iterator.

## <a name="directoryiteratoroperator"></a>directory_iterator::operator!=

```cpp
bool operator!=(const directory_iterator& right) const;
```

Der Memberoperator gibt „!(*this == right)“ zurück.

## <a name="directoryiteratoroperator"></a>directory_iterator::operator=

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.

## <a name="directoryiteratoroperator"></a>directory_iterator::operator==

```cpp
bool operator==(const directory_iterator& right) const;
```

Der Memberoperator gibt nur dann „true“ zurück, wenn sowohl „*this“ als auch „right“ Sequenzende-Iteratoren oder beide keine Sequenzende-Iteratoren sind.

## <a name="directoryiteratoroperator"></a>directory_iterator::operator*

```cpp
const directory_entry& operator*() const;
```

Der Memberoperator gibt „myentry“ zurück.

## <a name="directoryiteratoroperator-"></a>directory_iterator::operator->

```cpp
const directory_entry * operator->() const;
```

Die Memberfunktion gibt „&**this“ zurück.

## <a name="directoryiteratoroperator"></a>directory_iterator::operator++

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

Die erste Memberfunktion ruft „increment()“ auf und gibt dann „*this“ zurück. Die zweite Memberfunktion erstellt eine Kopie des Objekts, ruft „increment()“ auf und gibt dann die Kopie zurück.

## <a name="requirements"></a>Anforderungen

**Header:** \<experimental/filesystem>

**Namespace:** std::experimental::filesystem

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md)<br/>
