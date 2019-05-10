---
title: '&lt;chrono&gt;'
ms.date: 05/07/2019
f1_keywords:
- chrono/std::chrono::nanoseconds
- chrono/std::chrono::minutes
- chrono/std::chrono::seconds
- <chrono>
- chrono/std::chrono::hours
- chrono/std::chrono::milliseconds
- chrono/std::chrono::microseconds
ms.assetid: 844de749-f306-482e-89bc-6f53c99c8324
ms.openlocfilehash: 44620b6ea6c970027a8e9a023c0972c6dec43ee0
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220245"
---
# <a name="ltchronogt"></a>&lt;chrono&gt;

Schließen Sie den Standardheader \<chrono> zum Definieren von Klassen und Funktionen ein, die die Zeitdauer und Zeitangaben darstellen und bearbeiten.

Ab Visual Studio 2015, die Implementierung der `steady_clock` wurde geändert, um die C++-standardanforderungen für Zuverlässigkeit und Monotonie zu erfüllen. `steady_clock` basiert nun auf QueryPerformanceCounter(), und `high_resolution_clock` ist jetzt ein typedef-Element für `steady_clock`. Daher in der Microsoft C++ Compiler `steady_clock::time_point` ist jetzt eine Typedefinition für `chrono::time_point<steady_clock>`, aber dies ist nicht unbedingt der Fall bei anderen Implementierungen.

## <a name="syntax"></a>Syntax

```cpp
#include <chrono>
```

### <a name="classes"></a>Klassen

|Name|Beschreibung|
|----------|-----------------|
|[duration-Klasse](../standard-library/duration-class.md)|Beschreibt einen Typ, der ein Zeitintervall enthält.|
|[time_point-Klasse](../standard-library/time-point-class.md)|Beschreibt einen Typ, der einen bestimmten Zeitpunkt darstellt.|

### <a name="structs"></a>Strukturen

|Name|Beschreibung|
|----------|-----------------|
|[common_type-Struktur](../standard-library/common-type-structure.md)|Beschreibt Spezialisierungen der Vorlagenklasse [common_type](../standard-library/common-type-class.md) für Instanziierungen von `duration` und `time_point`.|
|[duration_values-Struktur](../standard-library/duration-values-structure.md)|Stellt bestimmte Werte für den `duration`-Vorlagenparameter `Rep` bereit.|
|[steady_clock-Struktur](../standard-library/steady-clock-struct.md)|Stellt eine `steady` Uhr dar.|
|[system_clock-Struktur](../standard-library/system-clock-structure.md)|Stellt einen auf der Echtzeituhr des Systems basierten *Uhrtyp* dar.|
|[treat_as_floating_point-Struktur](../standard-library/treat-as-floating-point-structure.md)|Gibt an, ob ein Typ als Gleitkommatyp behandelt werden kann.|

### <a name="functions"></a>Funktionen

|Name|Beschreibung|
|----------|-----------------|
|[duration_cast](../standard-library/chrono-functions.md#duration_cast)|Wandelt einen `duration`-Objekt in einen angegebenen Typ um.|
|[time_point_cast](../standard-library/chrono-functions.md#time_point_cast)|Wandelt einen `time_point`-Objekt in einen angegebenen Typ um.|

### <a name="operators"></a>Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[operator-](../standard-library/chrono-operators.md#operator-)|Operator für die Subtraktion oder Negation von `duration`- und `time_point`-Objekten.|
|[Operator!=](../standard-library/chrono-operators.md#op_neq)|Ungleichheitsoperator, der mit `duration`- oder `time_point`-Objekten verwendet wird.|
|[operator modulo](../standard-library/chrono-operators.md#op_modulo)|Operator für Modulo-Vorgänge für `duration`-Objekte.|
|[operator*](../standard-library/chrono-operators.md#op_star)|Multiplikationsoperator für `duration`-Objekte.|
|[operator/](../standard-library/chrono-operators.md#op_div)|Divisionsoperator für `duration`-Objekte.|
|[operator+](../standard-library/chrono-operators.md#op_add)|Fügt `duration`- und `time_point`-Objekte hinzu.|
|[operator&lt;](../standard-library/chrono-operators.md#op_lt)|Bestimmt, ob ein `duration`- oder `time_point`-Objekt kleiner als ein anderes `duration`- oder `time_point`-Objekt ist.|
|[operator&lt;=](../standard-library/chrono-operators.md#op_lt_eq)|Bestimmt, ob ein `duration`- oder `time_point`-Objekt kleiner als oder gleich einem anderen `duration`- oder `time_point`-Objekt ist.|
|[operator==](../standard-library/chrono-operators.md#op_eq_eq)|Bestimmt, ob zwei `duration`-Objekte Zeitintervalle mit derselben Länge darstellen, oder ob zwei `time_point`-Objekte den gleichen Zeitpunkt darstellen.|
|[operator&gt;](../standard-library/chrono-operators.md#op_gt)|Bestimmt, ob ein `duration`- oder `time_point`-Objekt größer als ein anderes `duration`- oder `time_point`-Objekt ist.|
|[operator&gt;=](../standard-library/chrono-operators.md#op_gt_eq)|Bestimmt, ob ein `duration`- oder `time_point`-Objekt größer als oder gleich einem anderen `duration`- oder `time_point`-Objekt ist.|

### <a name="predefined-duration-types"></a>Vordefinierte duration-Typen

Weitere Informationen zu Verhältnistypen, die in den folgenden typedefs-Elementen verwendet werden, finden Sie unter [\<ratio>](../standard-library/ratio.md).

|TypeDef|Beschreibung|
|-------------|-----------------|
|`typedef duration<long long, nano> nanoseconds;`|Synonym für einen `duration`-Typ, der über einen Teilstrichpunkt von einer Nanosekunde verfügt.|
|`typedef duration<long long, micro> microseconds;`|Synonym für einen `duration`-Typ, der über einen Teilstrichpunkt von einer Mikrosekunde verfügt.|
|`typedef duration<long long, milli> milliseconds;`|Synonym für einen `duration`-Typ, der über einen Teilstrichpunkt von einer Millisekunde verfügt.|
|`typedef duration<long long> seconds;`|Synonym für einen `duration`-Typ, der über einen Teilstrichpunkt von einer Sekunde verfügt.|
|`typedef duration<int, ratio<60> > minutes;`|Synonym für einen `duration`-Typ, der über einen Teilstrichpunkt von einer Minute verfügt.|
|`typedef duration<int, ratio<3600> > hours;`|Synonym für einen `duration`-Typ, der über einen Teilstrichpunkt von einer Stunde verfügt.|

### <a name="literals"></a>Literale

**(C ++ 11)**  Der \<Chrono >-Header definiert die folgenden [benutzerdefinierte Literale](../cpp/user-defined-literals-cpp.md) , dass Sie für mehr Komfort, typsicherheit und verwaltbarkeit des Codes verwenden können. Diese Literale werden im `literals::chrono_literals`-Inlinenamespace definiert und sind im Bereich enthalten, wenn std::chrono innerhalb des Bereichs liegt.

|Literal|Beschreibung|
|-------------|-----------------|
|chrono::hours operator "" h(unsigned long long Val)|Gibt die Stunden als Integralwert an.|
|chrono::duration\<double, ratio\<3600> > operator "" h(long double Val)|Gibt die Stunden als Gleitkommawert an.|
|chrono::minutes (operator "" min)(unsigned long long Val)|Gibt die Minuten als Integralwert an.|
|chrono::duration\<double, ratio\<60> > (operator "" min)( long double Val)|Gibt die Minuten als Gleitkommawert an.|
|chrono::seconds operator "" s(unsigned long long Val)|Gibt die Minuten als Integralwert an.|
|chrono::duration\<double> operator "" s(long double Val)|Gibt die Sekunden als Gleitkommawert an.|
|chrono::milliseconds operator "" ms(unsigned long long Val)|Gibt die Millisekunden als Integralwert an.|
|chrono::duration\<double, milli> operator "" ms(long double Val)|Gibt die Millisekunden als Gleitkommawert an.|
|chrono::microseconds operator "" us(unsigned long long Val)|Gibt die Mikrosekunden als Integralwert an.|
|chrono::duration\<double, micro> operator "" us(long double Val)|Gibt die Mikrosekunden als Gleitkommawert an.|
|chrono::nanoseconds operator "" ns(unsigned long long Val)|Gibt die Nanosekunden als Integralwert an.|
|chrono::duration\<double, nano> operator "" ns(long double Val)|Gibt die Nanosekunden als Gleitkommawert an.|
|||

In den folgenden Beispielen wird die Verwendung von chrono-Literalen veranschaulicht.

```cpp
constexpr auto day = 24h;
constexpr auto week = 24h* 7;
constexpr auto my_duration_unit = 108ms;
```

## <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
