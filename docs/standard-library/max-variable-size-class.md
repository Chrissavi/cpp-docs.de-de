---
title: max_variable_size-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_variable_size
- stdext::max_variable_size [C++], allocated
- stdext::max_variable_size [C++], deallocated
- stdext::max_variable_size [C++], full
- stdext::max_variable_size [C++], released
- stdext::max_variable_size [C++], saved
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce8b4fde6668fe7901ecf75c153765302c6d770e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854797"
---
# <a name="maxvariablesize-class"></a>max_variable_size-Klasse

Beschreibt ein Objekt der [max-Klasse](../standard-library/allocators-header.md), das die maximale Länge eines [freelist](../standard-library/freelist-class.md)-Objekts auf eine maximale Länge einschränkt, die annähernd proportional zur Anzahl von zugewiesenen Speicherblöcken ist.

## <a name="syntax"></a>Syntax

```cpp
class max_variable_size
```

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[max_variable_size](#max_variable_size)|Konstruiert ein Objekt vom Typ `max_variable_size`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[allocated](#allocated)|Erhöht die Anzahl der zugeordneten Speicherblöcke.|
|[deallocated](#deallocated)|Verringert die Anzahl der zugeordneten Speicherblöcke.|
|[full](#full)|Gibt einen Wert zurück, der angibt, ob zur Freiliste weitere Speicherblöcke hinzugefügt werden sollen.|
|[released](#released)|Verringert die Anzahl der Speicherblöcke auf der Freiliste.|
|[saved](#saved)|Erhöht die Anzahl der Speicherblöcke auf der Freiliste.|

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="allocated"></a> max_variable_size::allocated

Erhöht die Anzahl der zugeordneten Speicherblöcke.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`_Nx`|Der Inkrementwert|

### <a name="remarks"></a>Hinweise

Diese Memberfunktion fügt `_Nx` dem gespeicherten Wert `_Nallocs` hinzu. Diese Memberfunktion wird nach jedem erfolgreichen Aufruf von `cache_freelist::allocate` auf Operator `new` aufgerufen. Das Argument `_Nx` stellt die Anzahl der Speicherblöcke im Segment dar, die vom Operator `new` zugeordnet wurde.

## <a name="deallocated"></a> max_variable_size::deallocated

Verringert die Anzahl der zugeordneten Speicherblöcke.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`_Nx`|Der Inkrementwert|

### <a name="remarks"></a>Hinweise

Die Memberfunktion entfernt `_Nx` vom gespeicherten Wert `_Nallocs`. Diese Memberfunktion wird nach jedem Aufruf von `cache_freelist::deallocate` auf Operator `delete` aufgerufen. Das Argument `_Nx` stellt die Anzahl der Speicherblöcke im Segment dar, die vom Operator `delete` verringert wurde.

## <a name="full"></a> max_variable_size::full

Gibt einen Wert zurück, der angibt, ob zur Freiliste weitere Speicherblöcke hinzugefügt werden sollen.

```cpp
bool full();
```

### <a name="return-value"></a>Rückgabewert

`true` wenn `_Nallocs / 16 + 16 <= _Nblocks`

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird von `cache_freelist::deallocate` aufgerufen. Wenn der Aufruf `true` zurückgibt, setzt `deallocate` den Speicherblock auf die Freiliste. Wenn FALSE zurückgegeben wird, ruft `deallocate` den Operator `delete` auf, um die Zuordnung für den Block aufzuheben.

## <a name="max_variable_size"></a> max_variable_size::max_variable_size

Konstruiert ein Objekt vom Typ `max_variable_size`.

```cpp
max_variable_size();
```

### <a name="remarks"></a>Hinweise

Dieser Konstruktor initialisiert die gespeicherten Werte `_Nblocks` und `_Nallocs` auf null.

## <a name="released"></a> max_variable_size::released

Verringert die Anzahl der Speicherblöcke auf der Freiliste.

```cpp
void released();
```

### <a name="remarks"></a>Hinweise

Diese Memberfunktion verringert den gespeicherten `_Nblocks`-Wert. Die `released`-Memberfunktion der aktuellen max-Klasse wird von `cache_freelist::allocate` aufgerufen, wann immer ein Speicherblock aus der Freiliste entfernt wird.

## <a name="saved"></a> max_variable_size::saved

Erhöht die Anzahl der Speicherblöcke auf der Freiliste.

```cpp
void saved();
```

### <a name="remarks"></a>Hinweise

Diese Memberfunktion inkrementiert den gespeicherten `_Nblocks`-Wert. Diese Memberfunktion wird durch `cache_freelist::deallocate` aufgerufen, wann immer ein Speicherblock der Freiliste hinzugefügt wird.

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)<br/>
