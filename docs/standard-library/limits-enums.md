---
title: '&lt;limits&gt;-Enumerationen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 356c98ce5c93d1e05a583fc30c4758c5d15d7529
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858158"
---
# <a name="ltlimitsgt-enums"></a>&lt;limits&gt;-Enumerationen

|||
|-|-|
|[float_denorm_style](#float_denorm_style)|[float_round_style](#float_round_style)|

## <a name="float_denorm_style"></a> float_denorm_style Enumeration

Die Enumeration beschreibt die verschiedenen Methoden, die eine Implementierung für die Darstellung eines denormalisierten Gleitkommawerts auswählen kann – für Werte, die zu klein sind, um als normalisierte Werte dargestellt zu werden:

```cpp
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```

### <a name="return-value"></a>Rückgabewert

Die Enumeration gibt Folgendes zurück:

- **denorm_indeterminate**, wenn das Vorhandensein oder Fehlen von denormalisierten Formularen bei der Übersetzung nicht bestimmt werden kann.

- **denorm_absent**, wenn denormalisierte Formulare fehlen.

- **denorm_present**, wenn denormalisierte Formulare vorhanden sind.

### <a name="example"></a>Beispiel

Unter [numeric_limits::has_denorm](../standard-library/numeric-limits-class.md#has_denorm) finden Sie ein Beispiel, in dem auf die Werte dieser Enumeration zugegriffen werden kann.

## <a name="float_round_style"></a> float_round_style Enumeration

Die Enumeration beschreibt die verschiedenen Methoden, die eine Implementierung für die Rundung eines Gleitkommawerts auf einen ganzzahligen Wert auswählen kann.

```cpp
enum float_round_style {
    round_indeterminate = -1,
    round_toward_zero = 0,
    round_to_nearest = 1,
    round_toward_infinity = 2,
    round_toward_neg_infinity = 3    };
```

### <a name="return-value"></a>Rückgabewert

Die Enumeration gibt Folgendes zurück:

- **round_indeterminate**, wenn die Rundungsmethode nicht bestimmt werden kann.

- **round_toward_zero**, wenn in Richtung null gerundet wird.

- **round_to_nearest**, wenn auf die nächste ganze Zahl gerundet wird.

- **round_toward_infinity**, wenn von der null weg gerundet wird.

- **round_toward_neg_infinity**, wenn in Richtung negativerer ganzer Zahl gerundet wird.

### <a name="example"></a>Beispiel

Unter [numeric_limits::round_style](../standard-library/numeric-limits-class.md#round_style) finden Sie ein Beispiel, in dem auf die Werte dieser Enumeration zugegriffen werden kann.

## <a name="see-also"></a>Siehe auch

[\<limits>](../standard-library/limits.md)<br/>
