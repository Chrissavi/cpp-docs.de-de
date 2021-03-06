---
title: '&lt;variant&gt;'
ms.date: 04/04/2019
f1_keywords:
- <variant>
helpviewer_keywords:
- <variant>
ms.openlocfilehash: 1a3c861c96fedb7ef95eec66f95888ddc092bed4
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835661"
---
# <a name="ltvariantgt"></a>&lt;variant&gt;

Ein Variant-Objekt enthält und verwaltet einen Wert. Wenn die Variante einen Wert enthält, muss der Typ des Werts einer der Vorlagen Argument Typen sein, der Variant zugewiesen wird. Diese Vorlagen Argumente werden als Alternativen bezeichnet.

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:**\<variant>

**Namespace:** std

## <a name="members"></a>Member

### <a name="operators"></a>Operatoren

|Name|Beschreibung|
|-|-|
|[Operator = =](../standard-library/forward-list-operators.md#op_eq_eq)|Testet, ob das Variant-Objekt links vom Operator gleich dem Variant-Objekt rechts vom Operator ist.|
|[Operator! =](../standard-library/forward-list-operators.md#op_neq)|Testet, ob das Variant-Objekt links vom Operator ungleich dem Variant-Objekt rechts vom Operator ist.|
|[Operator<](../standard-library/forward-list-operators.md#op_lt)|Testet, ob das Variant-Objekt links vom Operator kleiner als das Variant-Objekt auf der rechten Seite ist.|
|[Operator<=](../standard-library/forward-list-operators.md#op_lt_eq)|Testet, ob das Variant-Objekt links vom Operator kleiner als oder gleich dem Variant-Objekt rechts vom Operator ist.|
|[Operator>](../standard-library/forward-list-operators.md#op_gt)|Testet, ob das Variant-Objekt links vom Operator größer als das Variant-Objekt auf der rechten Seite ist.|
|[Operator>=](../standard-library/forward-list-operators.md#op_lt_eq)|Testet, ob das Variant-Objekt links vom Operator größer als oder gleich dem Variant-Objekt rechts vom Operator ist.|

### <a name="functions"></a>Functions

|Name|Beschreibung|
|-|-|
|[get](../standard-library/variant-functions.md#get)|Ruft die Variante eines Objekts ab.|
|[get_if](../standard-library/variant-functions.md#get_if)|Ruft die Variante eines Objekts ab, falls vorhanden.|
|[holds_alternative](../standard-library/variant-functions.md#holds_alternative)|Gibt zurück, **`true`** Wenn eine Variante vorhanden ist.|
|[swap](../standard-library/variant-functions.md#swap)|Tauscht eine **Variante**aus.|
|[Sie](../standard-library/variant-functions.md#visit)|Wechselt zur nächsten **Variante**.|

### <a name="classes"></a>Klassen

|name|Beschreibung|
|-|-|
|[bad_variant_access](../standard-library/bad-variant-access-class.md)|Objekte, die ausgelöst wurden, um ungültige Zugriffe auf den Wert eines Variant-Objekts zu melden.|
|[variant](../standard-library/variant.md)|Ein Objekt, das entweder einen Wert eines seiner Alternativen Typen oder keinen Wert enthalten soll.|

### <a name="structs"></a>Strukturen

|Name|Beschreibung|
|-|-|
|[hash](../standard-library/hash-structure.md)||
|[monostate](../standard-library/monostate-structure.md)|Ein alternativer Typ für eine Variante zum Festlegen des standardmäßigen Konstruktors für den Variant-Typ.|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||
|[variant_alternative](../standard-library/variant-alternative-structure.md)|Unterstützt die Variant-Objekte.|
|[variant_size](../standard-library/variant-size-structure.md)|Unterstützt die Variant-Objekte.|

### <a name="objects"></a>Objekte

|Name|Beschreibung|
|-|-|
|[variant_npos](../standard-library/variant-functions.md#variant_npos)||

## <a name="see-also"></a>Weitere Informationen

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)
