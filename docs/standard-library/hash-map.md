---
title: '&lt;hash_map&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 01/18/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <hash_map>
- std::<hash_map>
dev_langs:
- C++
helpviewer_keywords:
- hash_map header
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0e3948e8697825af6cdd785117647943b33bac0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850052"
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;

> [!NOTE]
> Dieser Header ist veraltet. Die Alternative ist [ \<"unordered_map" >](unordered-map.md).

Definiert die Containervorlagenklassen „hash_map“ und „hash_multimap“ und deren unterstützende Vorlagen.

## <a name="syntax"></a>Syntax

> #<a name="include-hashmap"></a>Einschließen von < Hash_map >

### <a name="operators"></a>Operatoren

|Hash_map-Version|Hash_multimap-Version|Beschreibung|
|-----------------------|----------------------------|-----------------|
|[operator!= (hash_map)](hash-map-operators.md#op_neq)|[operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|Überprüft, ob das hash_map- oder hash_multimap-Objekt links vom Operator ungleich dem hash_map- oder hash_multimap-Objekt rechts vom Operator ist.|
|[operator== (hash_map)](hash-map-operators.md#op_eq_eq)|[operator== (hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|Überprüft, ob das hash_map- oder hash_multimap-Objekt links vom Operator gleich dem hash_map- oder hash_multimap-Objekt rechts vom Operator ist.|

### <a name="specialized-template-functions"></a>Spezialisierte Vorlagenfunktionen

|Hash_map-Version|Hash_multimap-Version|Beschreibung|
|-----------------------|----------------------------|-----------------|
|[swap (hash_map)](hash-map-class.md#swap)|[swap (hash_multimap)](hash-multimap-class.md#swap)|Tauscht die Elemente zweier hash_map- oder hash_multimap-Objekte aus.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[hash_compare-Klasse](hash-compare-class.md)|Beschreibt ein Objekt, das von jedem hashassoziativen Container – hash_map, hash_multimap, hash_set oder hash_multiset – als standardmäßiges **Traits** -Parameterobjekt verwendet werden kann, um die darin enthaltenen Elemente zu sortieren und zu hashen.|
|[value_compare-Klasse](value-compare-class.md)|Stellt ein Funktionsobjekt bereit, das die Elemente einer hash_map vergleichen kann, indem die Werte ihrer Schlüssel verglichen werden, um deren relative Reihenfolge in der hash_map zu bestimmen.|
|[hash_map-Klasse](hash-map-class.md)|Speichert Daten und ruft sie schnell aus einer Auflistung ab, in der jedes Element ein Paar ist, das einen Sortierschlüssel mit eindeutigem Wert und einen zugeordneten Datenwert aufweist.|
|[hash_multimap-Klasse](hash-multimap-class.md)|Speichert Daten und ruft sie schnell aus einer Auflistung ab, in der jedes Element ein Paar ist, das einen Sortierschlüssel, dessen Wert nicht eindeutig sein muss, und einen zugeordneten Datenwert aufweist.|

## <a name="requirements"></a>Anforderungen

**Header:** \<hash_map>

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[Headerdateien der Verweis](cpp-standard-library-header-files.md)
[Threadsicherheit in der C++-Standardbibliothek](thread-safety-in-the-cpp-standard-library.md)
[C++-Standardbibliotheksreferenz](cpp-standard-library-reference.md)
