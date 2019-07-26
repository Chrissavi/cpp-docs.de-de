---
title: '&lt;ratio&gt;'
ms.date: 11/04/2016
f1_keywords:
- ratio/std::mega
- ratio/std::peta
- ratio/std::ratio_greater
- ratio/std::micro
- ratio/std::ratio_add
- ratio/std::ratio_not_equal
- ratio/std::hecto
- ratio/std::nano
- ratio/std::ratio_less_equal
- ratio/std::ratio_less
- ratio/std::centi
- ratio/std::ratio_greater_equal
- ratio/std::ratio_subtract
- <ratio>
- ratio/std::atto
- ratio/std::tera
- ratio/std::milli
- ratio/std::ratio_multiply
- ratio/std::kilo
- ratio/std::ratio_divide
- ratio/std::giga
- ratio/std::pico
- ratio/std::femto
- ratio/std::ratio_equal
- ratio/std::ratio
- ratio/std::exa
- ratio/std::deci
- ratio/std::deca
ms.assetid: 8543e912-2d84-45ea-b3c0-bd7bfacee405
ms.openlocfilehash: f84bea2e3f4a01bb9428eddde3efbf53b73bc2f3
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458168"
---
# <a name="ltratiogt"></a>&lt;ratio&gt;

Schließen Sie den Standardheader \<ratio> zum Definieren von Konstanten und Vorlagen mit ein, die zum Speichern und Bearbeiten von rationalen Zahlen zum Zeitpunkt der Kompilierung verwendet werden.

## <a name="syntax"></a>Syntax

```cpp
#include <ratio>
```

### <a name="ratio-template"></a>Verhältnis Vorlage

```cpp
template<std::intmax_t Numerator, std::intmax_t Denominator = 1>
struct ratio // holds the ratio of Numerator to Denominator
{
   static constexpr std::intmax_t num;
   static constexpr std::intmax_t den;
   typedef ratio<num, den> type;
}
```

Die Vorlage `ratio` definiert die statischen Konstanten `num` und `den` damit `num`  /  ==`num` Zähler/Nenner und`den` hat keine allgemeinen Faktoren. `den` `num` / `den`der Wert, der von der Vorlagen Klasse dargestellt wird. Daher wird `type` die Instanziierung `ratio<num, den>`von festgelegt.

### <a name="specializations"></a>Spezialisierungen

\<ratio > definiert auch `ratio`-Spezialisierungen, die die folgende Form aufweisen.

`template <class R1, class R2> struct ratio_specialization`

Jede Spezialisierung nimmt zwei Vorlagenparameter, die auch `ratio`-Spezialisierungen sein müssen. Der `type`-Wert wird durch einen zugeordneten logischen Vorgang bestimmt.

|Name|`type`-Wert|
|----------|------------------|
|`ratio_add`|`R1 + R2`|
|`ratio_divide`|`R1 / R2`|
|`ratio_equal`|`R1 == R2`|
|`ratio_greater`|`R1 > R2`|
|`ratio_greater_equal`|`R1 >= R2`|
|`ratio_less`|`R1 < R2`|
|`ratio_less_equal`|`R1 <= R2`|
|`ratio_multiply`|`R1 * R2`|
|`ratio_not_equal`|`!(R1 == R2)`|
|`ratio_subtract`|`R1 - R2`|

### <a name="typedefs"></a>Typedefs

Der-Header definiert die Verhältnisse für die Standard-Si-Präfixe:

```cpp
typedef ratio<1, 1000000000000000000> atto;
typedef ratio<1, 1000000000000000> femto;
typedef ratio<1, 1000000000000> pico;
typedef ratio<1, 1000000000> nano;
typedef ratio<1, 1000000> micro;
typedef ratio<1, 1000> milli;
typedef ratio<1, 100> centi;
typedef ratio<1, 10> deci;
typedef ratio<10, 1> deca;
typedef ratio<100, 1> hecto;
typedef ratio<1000, 1> kilo;
typedef ratio<1000000, 1> mega;
typedef ratio<1000000000, 1> giga;
typedef ratio<1000000000000, 1> tera;
typedef ratio<1000000000000000, 1> peta;
typedef ratio<1000000000000000000, 1> exa;
```

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)
