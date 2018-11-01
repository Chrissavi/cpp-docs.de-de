---
title: numeric_limits-Klasse
ms.date: 11/04/2016
f1_keywords:
- limits/std::numeric_limits
- limits/std::numeric_limits::denorm_min
- limits/std::numeric_limits::digits
- limits/std::numeric_limits::digits10
- limits/std::numeric_limits::epsilon
- limits/std::numeric_limits::has_denorm
- limits/std::numeric_limits::has_denorm_loss
- limits/std::numeric_limits::has_infinity
- limits/std::numeric_limits::has_quiet_NaN
- limits/std::numeric_limits::has_signaling_NaN
- limits/std::numeric_limits::infinity
- limits/std::numeric_limits::is_bounded
- limits/std::numeric_limits::is_exact
- limits/std::numeric_limits::is_iec559
- limits/std::numeric_limits::is_integer
- limits/std::numeric_limits::is_modulo
- limits/std::numeric_limits::is_signed
- limits/std::numeric_limits::is_specialized
- limits/std::numeric_limits::lowest
- limits/std::numeric_limits::max
- limits/std::numeric_limits::max_digits10
- limits/std::numeric_limits::max_exponent
- limits/std::numeric_limits::max_exponent10
- limits/std::numeric_limits::min
- limits/std::numeric_limits::min_exponent
- limits/std::numeric_limits::min_exponent10
- limits/std::numeric_limits::quiet_NaN
- limits/std::numeric_limits::radix
- limits/std::numeric_limits::round_error
- limits/std::numeric_limits::round_style
- limits/std::numeric_limits::signaling_NaN
- limits/std::numeric_limits::tinyness_before
- limits/std::numeric_limits::traps
helpviewer_keywords:
- std::numeric_limits [C++]
- std::numeric_limits [C++], denorm_min
- std::numeric_limits [C++], digits
- std::numeric_limits [C++], digits10
- std::numeric_limits [C++], epsilon
- std::numeric_limits [C++], has_denorm
- std::numeric_limits [C++], has_denorm_loss
- std::numeric_limits [C++], has_infinity
- std::numeric_limits [C++], has_quiet_NaN
- std::numeric_limits [C++], has_signaling_NaN
- std::numeric_limits [C++], infinity
- std::numeric_limits [C++], is_bounded
- std::numeric_limits [C++], is_exact
- std::numeric_limits [C++], is_iec559
- std::numeric_limits [C++], is_integer
- std::numeric_limits [C++], is_modulo
- std::numeric_limits [C++], is_signed
- std::numeric_limits [C++], is_specialized
- std::numeric_limits [C++], lowest
- std::numeric_limits [C++], max
- std::numeric_limits [C++], max_digits10
- std::numeric_limits [C++], max_exponent
- std::numeric_limits [C++], max_exponent10
- std::numeric_limits [C++], min
- std::numeric_limits [C++], min_exponent
- std::numeric_limits [C++], min_exponent10
- std::numeric_limits [C++], quiet_NaN
- std::numeric_limits [C++], radix
- std::numeric_limits [C++], round_error
- std::numeric_limits [C++], round_style
- std::numeric_limits [C++], signaling_NaN
- std::numeric_limits [C++], tinyness_before
- std::numeric_limits [C++], traps
ms.assetid: 9e817177-0e91-48e6-b680-0531c4b26625
ms.openlocfilehash: 861850f192281d64ef02ec4a241315c05cd3318f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564618"
---
# <a name="numericlimits-class"></a>numeric_limits-Klasse

Die Vorlagenklasse beschreibt arithmetische Eigenschaften der integrierten numerischen Typen.

## <a name="syntax"></a>Syntax

```cpp
template <class Type>
class numeric_limits
```

### <a name="parameters"></a>Parameter

*Type*<br/>
Der grundlegende Elementdatentyp, dessen Eigenschaften getestet, abgefragt oder festgelegt werden.

## <a name="remarks"></a>Hinweise

Der Header definiert explizite spezialisierungen für die Typen **"wchar_t"**, **"bool"**, **Char**, **signiert Char**, **ohne Vorzeichen Char**, **kurze**, **unsigned short**, **Int**, **ganze Zahl ohne Vorzeichen**, **lang**, **unsigned long**, **"float"**, **doppelte**, **long double**, **long Long**, **long long ohne Vorzeichen**, **char16_t**, und **char32_t**. Für diese expliziten spezialisierungen ist der Member [numeric_limits:: is_specialized](#is_specialized) ist **"true"**, und alle relevanten Elemente haben sinnvolle Werte. Das Programm kann zusätzliche explizite Spezialisierungen bereitstellen. Die meisten Memberfunktionen der Klasse beschreiben oder testen mögliche Implementierungen von **"float"**.

Für eine beliebige Spezialisierung gibt es keine Member, die sinnvolle Werte haben. Ein Memberobjekt, das keinen sinnvollen Wert speichert 0 (null) (oder **"false"**) und gibt eine Memberfunktion, die keinen sinnvollen Wert zurückgibt `Type(0)`.

### <a name="static-functions-and-constants"></a>Statische Funktionen und Konstanten

|||
|-|-|
|[denorm_min](#denorm_min)|Gibt den kleinsten denormalisierten Wert ungleich 0 zurück.|
|[Ziffern](#digits)|Gibt die Anzahl von Basisziffern zurück, die der Typ ohne Genauigkeitsverlust darstellen kann.|
|[digits10](#digits10)|Gibt die Anzahl von Dezimalziffern zurück, die der Typ ohne Genauigkeitsverlust darstellen kann.|
|[epsilon](#epsilon)|Gibt die Differenz zwischen 1 und dem kleinsten Wert größer als 1 zurück, die der Datentyp darstellen kann.|
|[has_denorm](#has_denorm)|Testet, ob ein Typ denormalisierte Werte unterstützt.|
|[has_denorm_loss](#has_denorm_loss)|Testet, ob ein Genauigkeitsverlust nicht als ungenaues Ergebnis, sondern als Denormalisierungsverlust erkannt wird.|
|[has_infinity](#has_infinity)|Testet, ob ein Typ eine Darstellung für positive Unendlichkeit hat.|
|[has_quiet_NaN](#has_quiet_nan)|Testet, ob ein Typ eine Darstellung für eine stille NaN (Not a Number) hat, also eine nicht anzeigende NaN.|
|[has_signaling_NaN](#has_signaling_nan)|Testet, ob ein Typ eine Darstellung für eine anzeigenden NaN (Not a Number) hat.|
|[infinity](#infinity)|Die Darstellung für positive Unendlichkeit für einen Typ, sofern verfügbar.|
|[is_bounded](#is_bounded)|Testet, ob die Menge von Werten, die ein Typ darstellen kann, endlich ist.|
|[is_exact](#is_exact)|Testet, ob die für einen Typ ausgeführten Berechnungen keine Rundungsfehler haben.|
|[is_iec559](#is_iec559)|Testet, ob ein Typ den IEC 559-Standards entspricht.|
|[is_integer](#is_integer)|Testet, ob ein Typ eine Ganzzahldarstellung hat.|
|[is_modulo](#is_modulo)|Testet, ob ein Typ eine Modulodarstellung hat.|
|[is_signed](#is_signed)|Testet, ob ein Typ eine vorzeichenbehaftete Darstellung hat.|
|[is_specialized](#is_specialized)|Testet, ob ein Typ eine explizite Spezialisierung hat, die in der Vorlagenklasse `numeric_limits`definiert ist.|
|[lowest](#lowest)|Gibt den kleinsten negativen begrenzten Wert zurück.|
|[max](#max)|Gibt den größten endlichen Wert für einen Typ zurück.|
|[max_digits10](#max_digits10)|Gibt die Anzahl von Dezimalstellen zurück, die dazu erforderlich ist sicherzustellen, dass zwei unterschiedliche Werte des Typs unterschiedliche Dezimaldarstellungen haben.|
|[max_exponent](#max_exponent)|Gibt den größten positiven ganzzahligen Exponenten zurück, den der Gleitkommatyp als einen endlichen Wert darstellen kann, wenn eine Basis mit diesem Exponenten potenziert wird.|
|[max_exponent10](#max_exponent10)|Gibt den größten positiven ganzzahligen Exponenten zurück, den der Gleitkommatyp als einen endlichen Wert darstellen kann, wenn eine Basis von zehn mit diesem Exponenten potenziert wird.|
|[Min.](#min)|Gibt den kleinsten normalisierten Wert für einen Typ zurück.|
|[min_exponent](#min_exponent)|Gibt den größten negativen ganzzahligen Exponenten zurück, den der Gleitkommatyp als einen endlichen Wert darstellen kann, wenn eine Basis mit diesem Exponenten potenziert wird.|
|[min_exponent10](#min_exponent10)|Gibt den größten negativen ganzzahligen Exponenten zurück, den der Gleitkommatyp als einen endlichen Wert darstellen kann, wenn eine Basis von zehn mit diesem Exponenten potenziert wird.|
|[quiet_NaN](#quiet_nan)|Gibt die Darstellung einer stillen NaN (Not a Number) für den Typ zurück.|
|[radix](#radix)|Gibt die ganzzahlige Basis (als Radix bezeichnet) zurück, die für die Darstellung eines Typs verwendet wird.|
|[round_error](#round_error)|Gibt den größten Rundungsfehler für den Typ zurück.|
|[round_style](#round_style)|Gibt einen Wert zurück, der die verschiedenen Methoden beschreibt, die eine Implementierung für die Rundung eines Gleitkommawerts auf einen ganzzahligen Wert auswählen kann.|
|[signaling_NaN](#signaling_nan)|Gibt die Darstellung einer anzeigenden NaN (Not a Number) für den Typ zurück.|
|[tinyness_before](#tinyness_before)|Testet, ob ein Typ für einen Wert vor dessen Rundung ermitteln kann, ob der Wert zu klein ist, um als normalisierter Wert dargestellt zu werden.|
|[traps](#traps)|Testet, ob für einen Typ Auffangen, bei dem arithmetischen Ausnahmen gemeldet werden, implementiert ist.|

## <a name="requirements"></a>Anforderungen

**Header:** \<limits>

**Namespace:** std

## <a name="denorm_min"></a> numeric_limits::denorm_min

Gibt den kleinsten denormalisierten Wert ungleich 0 zurück.

```cpp
static constexpr Type denorm_min() throw();
```

### <a name="return-value"></a>Rückgabewert

Der kleinste denormalisierte Wert ungleich 0.

### <a name="remarks"></a>Hinweise

**long double** ist identisch mit **doppelte** für die C++-Compiler.

Die Funktion gibt den kleinsten Wert für den Typ an, die die gleiche ist als [min](#min) Wenn [Has_denorm](#has_denorm) ist nicht gleich `denorm_present`.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_denorm_min.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The smallest nonzero denormalized value" << endl
        << "for float objects is: "
        << numeric_limits<float>::denorm_min( ) << endl;
   cout << "The smallest nonzero denormalized value" << endl
        << "for double objects is: "
        << numeric_limits<double>::denorm_min( ) << endl;
   cout << "The smallest nonzero denormalized value" << endl
        << "for long double objects is: "
        << numeric_limits<long double>::denorm_min( ) << endl;

   // A smaller value will round to zero
   cout << numeric_limits<float>::denorm_min( )/2 <<endl;
   cout << numeric_limits<double>::denorm_min( )/2 <<endl;
   cout << numeric_limits<long double>::denorm_min( )/2 <<endl;
}
```

```Output
The smallest nonzero denormalized value
for float objects is: 1.4013e-045
The smallest nonzero denormalized value
for double objects is: 4.94066e-324
The smallest nonzero denormalized value
for long double objects is: 4.94066e-324
0
0
0
```

## <a name="digits"></a> numeric_limits::digits

Gibt die Anzahl von Basisziffern zurück, die der Typ ohne Genauigkeitsverlust darstellen kann.

```cpp
static constexpr int digits = 0;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Basisziffern, die der Typ ohne Genauigkeitsverlust darstellen kann.

### <a name="remarks"></a>Hinweise

Der Member speichert die Anzahl der Basisziffern, die der Typ ohne Änderung darstellen kann. Dies ist die Anzahl der Bits außer den Vorzeichenbits für einen vordefinierten Ganzzahltyp, oder die Anzahl der Mantissaziffern für einen vordefinierten Gleitkommatyp.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_digits_min.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << numeric_limits<float>::digits <<endl;
   cout << numeric_limits<double>::digits <<endl;
   cout << numeric_limits<long double>::digits <<endl;
   cout << numeric_limits<int>::digits <<endl;
   cout << numeric_limits<__int64>::digits <<endl;
}
```

```Output
24
53
53
31
63
```

## <a name="digits10"></a> numeric_limits::digits10

Gibt die Anzahl von Dezimalziffern zurück, die der Typ ohne Genauigkeitsverlust darstellen kann.

```cpp
static constexpr int digits10 = 0;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Dezimalziffern, die der Typ ohne Genauigkeitsverlust darstellen kann.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_digits10.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << numeric_limits<float>::digits10 <<endl;
   cout << numeric_limits<double>::digits10 <<endl;
   cout << numeric_limits<long double>::digits10 <<endl;
   cout << numeric_limits<int>::digits10 <<endl;
   cout << numeric_limits<__int64>::digits10 <<endl;
   float f = (float)99999999;
   cout.precision ( 10 );
   cout << "The float is; " << f << endl;
}
```

```Output
6
15
15
9
18
The float is; 100000000
```

## <a name="epsilon"></a> numeric_limits::epsilon

Die Funktion gibt die Differenz zwischen 1 und dem kleinsten Wert größer als 1 zurück, die der Datentyp darstellen kann.

```cpp
static constexpr Type epsilon() throw();
```

### <a name="return-value"></a>Rückgabewert

Die Differenz zwischen 1 und dem kleinsten Wert größer als 1, die der Datentyp darstellen kann.

### <a name="remarks"></a>Hinweise

Der Wert ist FLT_EPSILON für Typ **float**. `epsilon` ist für ein Typ die kleinste positive Gleitkommazahl *N*, sodass *N* + `epsilon` + *N* darstellbar ist.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_epsilon.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The difference between 1 and the smallest "
        << "value greater than 1" << endl
        << "for float objects is: "
        << numeric_limits<float>::epsilon( ) << endl;
   cout << "The difference between 1 and the smallest "
        << "value greater than 1" << endl
        << "for double objects is: "
        << numeric_limits<double>::epsilon( ) << endl;
   cout << "The difference between 1 and the smallest "
        << "value greater than 1" << endl
        << "for long double objects is: "
        << numeric_limits<long double>::epsilon( ) << endl;
}
```

```Output
The difference between 1 and the smallest value greater than 1
for float objects is: 1.19209e-007
The difference between 1 and the smallest value greater than 1
for double objects is: 2.22045e-016
The difference between 1 and the smallest value greater than 1
for long double objects is: 2.22045e-016
```

## <a name="has_denorm"></a> numeric_limits::has_denorm

Testet, ob ein Typ denormalisierte Werte unterstützt.

```cpp
static constexpr float_denorm_style has_denorm = denorm_absent;
```

### <a name="return-value"></a>Rückgabewert

Ein Enumerationswert des Typs **const**`float_denorm_style`, wodurch angegeben wird, ob der Typ denormalisierte Werte zulässt.

### <a name="remarks"></a>Hinweise

Der Member speichert `denorm_present` für ein Gleitkommatyp, der denormalisierte hat Werte effektiv eine Variable Anzahl von Exponentenbits.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_has_denorm.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects allow denormalized values: "
        << numeric_limits<float>::has_denorm
        << endl;
   cout << "Whether double objects allow denormalized values: "
        << numeric_limits<double>::has_denorm
        << endl;
   cout << "Whether long int objects allow denormalized values: "
        << numeric_limits<long int>::has_denorm
        << endl;
}
```

```Output
Whether float objects allow denormalized values: 1
Whether double objects allow denormalized values: 1
Whether long int objects allow denormalized values: 0
```

## <a name="has_denorm_loss"></a> numeric_limits::has_denorm_loss

Testet, ob ein Genauigkeitsverlust nicht als ungenaues Ergebnis, sondern als Denormalisierungsverlust erkannt wird.

```cpp
static constexpr bool has_denorm_loss = false;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Verlust der Genauigkeit als Denormalisierungsverlust erkannt wird; **FALSE** wenn nicht.

### <a name="remarks"></a>Hinweise

Der Member speichert TRUE für einen Typ, der bestimmt, ob ein Wert Genauigkeit verloren hat, da er als denormalisiertes Ergebnis (klein, um als normalisierte Werte darstellen) bereitgestellt wird oder ungenau ist (nicht das gleiche Ergebnis, daher nicht Teil des Einschränkungen des Exponentenbereichs und der Genauigkeit), eine Option mit IEC 559 Gleitkommadarstellungen, die einige Ergebnisse beeinflussen können.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_has_denorm_loss.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects can detect denormalized loss: "
        << numeric_limits<float>::has_denorm_loss
        << endl;
   cout << "Whether double objects can detect denormalized loss: "
        << numeric_limits<double>::has_denorm_loss
        << endl;
   cout << "Whether long int objects can detect denormalized loss: "
        << numeric_limits<long int>::has_denorm_loss
        << endl;
}
```

```Output
Whether float objects can detect denormalized loss: 1
Whether double objects can detect denormalized loss: 1
Whether long int objects can detect denormalized loss: 0
```

## <a name="has_infinity"></a> numeric_limits::has_infinity

Testet, ob ein Typ eine Darstellung für positive Unendlichkeit hat.

```cpp
static constexpr bool has_infinity = false;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Typ eine Darstellung für positive Unendlichkeit hat; **FALSE**, wenn nicht.

### <a name="remarks"></a>Hinweise

Gibt das Element **TRUE** zurück, wenn [is_iec559](#is_iec559) **TRUE** ist.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_has_infinity.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have infinity: "
        << numeric_limits<float>::has_infinity
        << endl;
   cout << "Whether double objects have infinity: "
        << numeric_limits<double>::has_infinity
        << endl;
   cout << "Whether long int objects have infinity: "
        << numeric_limits<long int>::has_infinity
        << endl;
}
```

```Output
Whether float objects have infinity: 1
Whether double objects have infinity: 1
Whether long int objects have infinity: 0
```

## <a name="has_quiet_nan"></a> numeric_limits::has_quiet_NaN

Testet, ob ein Typ eine Darstellung für eine stille NaN (Not a Number) hat, also eine nicht anzeigende NaN.

```cpp
static constexpr bool has_quiet_NaN = false;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der **Typ** eine Darstellung für einen stillen NaN hat; **FALSE**, wenn nicht.

### <a name="remarks"></a>Hinweise

Ein stilles NAN ist eine Codierung für keine Zahl, die das Vorhandensein in einem Ausdruck nicht signalisiert. Der Rückgabewert ist **TRUE**, wenn [is_iec559](#is_iec559) wahr ist.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_has_quiet_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have quiet_NaN: "
        << numeric_limits<float>::has_quiet_NaN
        << endl;
   cout << "Whether double objects have quiet_NaN: "
        << numeric_limits<double>::has_quiet_NaN
        << endl;
   cout << "Whether long int objects have quiet_NaN: "
        << numeric_limits<long int>::has_quiet_NaN
        << endl;
}
```

```Output
Whether float objects have quiet_NaN: 1
Whether double objects have quiet_NaN: 1
Whether long int objects have quiet_NaN: 0
```

## <a name="has_signaling_nan"></a> numeric_limits::has_signaling_NaN

Testet, ob ein Typ eine Darstellung für eine anzeigenden NaN (Not a Number) hat.

```cpp
static constexpr bool has_signaling_NaN = false;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Typ eine Darstellung für einen signalisierenden NAN hat; **FALSE**, wenn nicht.

### <a name="remarks"></a>Hinweise

Ein stilles NAN ist eine Codierung für keine Zahl, die das Vorhandensein in einem Ausdruck nicht signalisiert. Der Rückgabewert ist **TRUE**, wenn [is_iec559](#is_iec559) wahr ist.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_has_signaling_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have a signaling_NaN: "
        << numeric_limits<float>::has_signaling_NaN
        << endl;
   cout << "Whether double objects have a signaling_NaN: "
        << numeric_limits<double>::has_signaling_NaN
        << endl;
   cout << "Whether long int objects have a signaling_NaN: "
        << numeric_limits<long int>::has_signaling_NaN
        << endl;
}
```

```Output
Whether float objects have a signaling_NaN: 1
Whether double objects have a signaling_NaN: 1
Whether long int objects have a signaling_NaN: 0
```

## <a name="infinity"></a> numeric_limits::infinity

Die Darstellung für positive Unendlichkeit für einen Typ, sofern verfügbar.

```cpp
static constexpr Type infinity() throw();
```

### <a name="return-value"></a>Rückgabewert

Die Darstellung für positive Unendlichkeit für einen Typ, sofern verfügbar.

### <a name="remarks"></a>Hinweise

Der Rückgabewert ist nur aussagekräftig, wenn [has_infinity](#has_infinity) **TRUE** ist.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_infinity.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << numeric_limits<float>::has_infinity <<endl;
   cout << numeric_limits<double>::has_infinity<<endl;
   cout << numeric_limits<long double>::has_infinity <<endl;
   cout << numeric_limits<int>::has_infinity <<endl;
   cout << numeric_limits<__int64>::has_infinity <<endl;

   cout << "The representation of infinity for type float is: "
        << numeric_limits<float>::infinity( ) <<endl;
   cout << "The representation of infinity for type double is: "
        << numeric_limits<double>::infinity( ) <<endl;
   cout << "The representation of infinity for type long double is: "
        << numeric_limits<long double>::infinity( ) <<endl;
}
```

```Output
1
1
1
0
0
The representation of infinity for type float is: inf
The representation of infinity for type double is: inf
The representation of infinity for type long double is: inf
```

## <a name="is_bounded"></a> numeric_limits::is_bounded

Testet, ob die Menge von Werten, die ein Typ darstellen kann, endlich ist.

```cpp
static constexpr bool is_bounded = false;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Typ einen begrenzten Satz der darstellbaren Werte hat; **FALSE**, wenn dies nicht der Fall ist.

### <a name="remarks"></a>Hinweise

Alle vordefinierte Typen verfügen über einen begrenzten Satz der darstellbaren Werte und geben **TRUE** zurück.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_is_bounded.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have bounded set "
        << "of representable values: "
        << numeric_limits<float>::is_bounded
        << endl;
   cout << "Whether double objects have bounded set "
        << "of representable values: "
        << numeric_limits<double>::is_bounded
        << endl;
   cout << "Whether long int objects have bounded set "
        << "of representable values: "
        << numeric_limits<long int>::is_bounded
        << endl;
   cout << "Whether unsigned char objects have bounded set "
        << "of representable values: "
        << numeric_limits<unsigned char>::is_bounded
        << endl;
}
```

```Output
Whether float objects have bounded set of representable values: 1
Whether double objects have bounded set of representable values: 1
Whether long int objects have bounded set of representable values: 1
Whether unsigned char objects have bounded set of representable values: 1
```

## <a name="is_exact"></a> numeric_limits::is_exact

Testet, ob die für einen Typ ausgeführten Berechnungen keine Rundungsfehler haben.

```cpp
static constexpr bool is_exact = false;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Berechnungen keine Rundungsfehler haben; **FALSE**, wenn nicht.

### <a name="remarks"></a>Hinweise

Alle vordefinierten Ganzzahltypen stellen ihre Werte genau dar und geben **FALSE** zurück. Eine rationale oder Festkommadarstellung wird auch als genau betrachtet, nicht aber eine Gleitkommadarstellung.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_is_exact.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<float>::is_exact
        << endl;
   cout << "Whether double objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<double>::is_exact
        << endl;
   cout << "Whether long int objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<long int>::is_exact
        << endl;
   cout << "Whether unsigned char objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<unsigned char>::is_exact
        << endl;
}
```

```Output
Whether float objects have calculations free of rounding errors: 0
Whether double objects have calculations free of rounding errors: 0
Whether long int objects have calculations free of rounding errors: 1
Whether unsigned char objects have calculations free of rounding errors: 1
```

## <a name="is_iec559"></a> numeric_limits::is_iec559

Testet, ob ein Typ den IEC 559-Standards entspricht.

```cpp
static constexpr bool is_iec559 = false;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Typ den IEC 559-Standards entspricht; **FALSE**, wenn nicht.

### <a name="remarks"></a>Hinweise

Der IEC 559 ist eine internationale Norm zur Darstellung von Gleitkommawerten und wird in den USA auch als IEEE 754 bezeichnet.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_is_iec559.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects conform to iec559 standards: "
        << numeric_limits<float>::is_iec559
        << endl;
   cout << "Whether double objects conform to iec559 standards: "
        << numeric_limits<double>::is_iec559
        << endl;
   cout << "Whether int objects conform to iec559 standards: "
        << numeric_limits<int>::is_iec559
        << endl;
   cout << "Whether unsigned char objects conform to iec559 standards: "
        << numeric_limits<unsigned char>::is_iec559
        << endl;
}
```

```Output
Whether float objects conform to iec559 standards: 1
Whether double objects conform to iec559 standards: 1
Whether int objects conform to iec559 standards: 0
Whether unsigned char objects conform to iec559 standards: 0
```

## <a name="is_integer"></a> numeric_limits::is_integer

Testet, ob ein Typ eine Ganzzahldarstellung hat.

```cpp
static constexpr bool is_integer = false;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Typ die Darstellung einer Ganzzahl hat; **FALSE**, wenn nicht.

### <a name="remarks"></a>Hinweise

Alle vordefinierten Integertypen haben eine ganzzahlige Darstellung.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_is_integer.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have an integral representation: "
        << numeric_limits<float>::is_integer
        << endl;
   cout << "Whether double objects have an integral representation: "
        << numeric_limits<double>::is_integer
        << endl;
   cout << "Whether int objects have an integral representation: "
        << numeric_limits<int>::is_integer
        << endl;
   cout << "Whether unsigned char objects have an integral representation: "
        << numeric_limits<unsigned char>::is_integer
        << endl;
}
```

```Output
Whether float objects have an integral representation: 0
Whether double objects have an integral representation: 0
Whether int objects have an integral representation: 1
Whether unsigned char objects have an integral representation: 1
```

## <a name="is_modulo"></a> numeric_limits::is_modulo

Testet, ob ein **Typ** eine Modulodarstellung hat.

```cpp
static constexpr bool is_modulo = false;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Typ eine Modulodarstellung hat; **FALSE**, wenn nicht.

### <a name="remarks"></a>Hinweise

Eine Modulo-Repräsentation ist eine Repräsentation, bei der alle Ergebnisse durch eine Modulodivision reduziert zurückgegeben werden. Alle vordefinierten Integertypen haben eine ganzzahlige Darstellung.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_is_modulo.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have a modulo representation: "
        << numeric_limits<float>::is_modulo
        << endl;
   cout << "Whether double objects have a modulo representation: "
        << numeric_limits<double>::is_modulo
        << endl;
   cout << "Whether signed char objects have a modulo representation: "
        << numeric_limits<signed char>::is_modulo
        << endl;
   cout << "Whether unsigned char objects have a modulo representation: "
        << numeric_limits<unsigned char>::is_modulo
        << endl;
}
```

```Output
Whether float objects have a modulo representation: 0
Whether double objects have a modulo representation: 0
Whether signed char objects have a modulo representation: 1
Whether unsigned char objects have a modulo representation: 1
```

## <a name="is_signed"></a> numeric_limits::is_signed

Testet, ob ein Typ eine vorzeichenbehaftete Darstellung hat.

```cpp
static constexpr bool is_signed = false;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Typ eine Modulodarstellung hat; **FALSE**, wenn nicht.

### <a name="remarks"></a>Hinweise

Der Member speichert TRUE für einen Typ, der eine signierte Darstellung hat. Dies ist der Fall für alle vordefinierten Gleitkomma- und signierten Integer-Typen.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_is_signaled.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have a signed representation: "
        << numeric_limits<float>::is_signed
        << endl;
   cout << "Whether double objects have a signed representation: "
        << numeric_limits<double>::is_signed
        << endl;
   cout << "Whether signed char objects have a signed representation: "
        << numeric_limits<signed char>::is_signed
        << endl;
   cout << "Whether unsigned char objects have a signed representation: "
        << numeric_limits<unsigned char>::is_signed
        << endl;
}
```

```Output
Whether float objects have a signed representation: 1
Whether double objects have a signed representation: 1
Whether signed char objects have a signed representation: 1
Whether unsigned char objects have a signed representation: 0
```

## <a name="is_specialized"></a> numeric_limits::is_specialized

Testet, ob ein Typ eine explizite Spezialisierung hat, die in der Vorlagenklasse `numeric_limits`definiert ist.

```cpp
static constexpr bool is_specialized = false;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Typ eine explizite Spezialisierung hat, die in der Vorlagenklasse definiert ist; **FALSE**, wenn nicht.

### <a name="remarks"></a>Hinweise

Alle skalaren Typen außer Zeiger haben eine explizite Spezialisierung für Vorlagenklasse `numeric_limits`.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_is_specialized.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<float>::is_specialized
        << endl;
   cout << "Whether float* objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<float*>::is_specialized
        << endl;
   cout << "Whether int objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<int>::is_specialized
        << endl;
   cout << "Whether int* objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<int*>::is_specialized
        << endl;
}
```

```Output
Whether float objects have an explicit specialization in the class: 1
Whether float* objects have an explicit specialization in the class: 0
Whether int objects have an explicit specialization in the class: 1
Whether int* objects have an explicit specialization in the class: 0
```

## <a name="lowest"></a> numeric_limits::lowest

Gibt den kleinsten negativen begrenzten Wert zurück.

```cpp
static constexpr Type lowest() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den kleinsten negativen begrenzten Wert zurück.

### <a name="remarks"></a>Hinweise

Gibt den kleinsten negativen begrenzten Wert für den Typ (Dies ist in der Regel `min()` für ganzzahlige Typen und `-max()` für Gleitkomma-Datentypen). Der Rückgabewert ist aussagekräftig Wenn `is_bounded` ist **"true"**.

## <a name="max"></a> numeric_limits::max

Gibt den größten endlichen Wert für einen Typ zurück.

```cpp
static constexpr Type max() throw();
```

### <a name="return-value"></a>Rückgabewert

Der größte endliche Wert für einen Typ.

### <a name="remarks"></a>Hinweise

Der endliche Höchstwert ist INT_MAX für Typ **Int** und FLT_MAX für Typ **"float"**. Der Rückgabewert ist aussagekräftig, wenn [is_bounded](#is_bounded) **wahr** ist.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_max.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main() {
   cout << "The maximum value for type float is:  "
        << numeric_limits<float>::max( )
        << endl;
   cout << "The maximum value for type double is:  "
        << numeric_limits<double>::max( )
        << endl;
   cout << "The maximum value for type int is:  "
        << numeric_limits<int>::max( )
        << endl;
   cout << "The maximum value for type short int is:  "
        << numeric_limits<short int>::max( )
        << endl;
}
```

## <a name="max_digits10"></a> numeric_limits::max_digits10

Gibt die Anzahl von Dezimalstellen zurück, die dazu erforderlich ist sicherzustellen, dass zwei unterschiedliche Werte des Typs unterschiedliche Dezimaldarstellungen haben.

```cpp
static constexpr int max_digits10 = 0;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl von Dezimalstellen zurück, die dazu erforderlich ist sicherzustellen, dass zwei unterschiedliche Werte des Typs unterschiedliche Dezimaldarstellungen haben.

### <a name="remarks"></a>Hinweise

Der Member speichert die Anzahl von Dezimalstellen, die dazu erforderlich ist sicherzustellen, dass zwei unterschiedliche Werte des Typs unterschiedliche Dezimaldarstellungen haben.

## <a name="max_exponent"></a> numeric_limits::max_exponent

Gibt den größten positiven ganzzahligen Exponenten zurück, den der Gleitkommatyp als einen endlichen Wert darstellen kann, wenn eine Basis mit diesem Exponenten potenziert wird.

```cpp
static constexpr int max_exponent = 0;
```

### <a name="return-value"></a>Rückgabewert

Der maximale ganzzahlige Basis-basierte Exponent, der vom Typ dargestellt werden kann.

### <a name="remarks"></a>Hinweise

Die Rückgabe der Memberfunktion ist nur für Gleitkommatypen relevant. `max_exponent` ist der Wert FLT_MAX_EXP für Typ **Gleitkomma**.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_max_exponent.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The maximum radix-based exponent for type float is:  "
        << numeric_limits<float>::max_exponent
        << endl;
   cout << "The maximum radix-based exponent for type double is:  "
        << numeric_limits<double>::max_exponent
        << endl;
   cout << "The maximum radix-based exponent for type long double is:  "
        << numeric_limits<long double>::max_exponent
        << endl;
}
```

```Output
The maximum radix-based exponent for type float is:  128
The maximum radix-based exponent for type double is:  1024
The maximum radix-based exponent for type long double is:  1024
```

## <a name="max_exponent10"></a> numeric_limits::max_exponent10

Gibt den größten positiven ganzzahligen Exponenten zurück, den der Gleitkommatyp als einen endlichen Wert darstellen kann, wenn eine Basis von zehn mit diesem Exponenten potenziert wird.

```cpp
static constexpr int max_exponent10 = 0;
```

### <a name="return-value"></a>Rückgabewert

Die maximale ganzzahlige Basis 10 Exponent darstellbar vom Typ.

### <a name="remarks"></a>Hinweise

Die Rückgabe der Memberfunktion ist nur für Gleitkommatypen relevant. `max_exponent` ist der Wert FLT_MAX_10 für Typ **Gleitkomma**.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_max_exponent10.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The maximum base 10 exponent for type float is:  "
           << numeric_limits<float>::max_exponent10
           << endl;
   cout << "The maximum base 10 exponent for type double is:  "
           << numeric_limits<double>::max_exponent10
           << endl;
   cout << "The maximum base 10 exponent for type long double is:  "
           << numeric_limits<long double>::max_exponent10
           << endl;
}
```

```Output
The maximum base 10 exponent for type float is:  38
The maximum base 10 exponent for type double is:  308
The maximum base 10 exponent for type long double is:  308
```

## <a name="min"></a> numeric_limits::min

Gibt den kleinsten normalisierten Wert für einen Typ zurück.

```cpp
static constexpr Type min() throw();
```

### <a name="return-value"></a>Rückgabewert

Der kleinste normalisierte Wert für einen Typ.

### <a name="remarks"></a>Hinweise

Der normalisierte Mindestwert ist INT_MIN für Typ **Int** und FLT_MIN für Typ **"float"**. Der Rückgabewert ist aussagekräftig Wenn [Is_bounded](#is_bounded) ist **"true"** oder, wenn [Is_signed](#is_signed) ist **"false"**.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_min.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The minimum value for type float is:  "
        << numeric_limits<float>::min( )
        << endl;
   cout << "The minimum value for type double is:  "
        << numeric_limits<double>::min( )
        << endl;
   cout << "The minimum value for type int is:  "
        << numeric_limits<int>::min( )
        << endl;
   cout << "The minimum value for type short int is:  "
        << numeric_limits<short int>::min( )
        << endl;
}
```

```Output
The minimum value for type float is:  1.17549e-038
The minimum value for type double is:  2.22507e-308
The minimum value for type int is:  -2147483648
The minimum value for type short int is:  -32768
```

## <a name="min_exponent"></a> numeric_limits::min_exponent

Gibt den größten negativen ganzzahligen Exponenten zurück, den der Gleitkommatyp als einen endlichen Wert darstellen kann, wenn eine Basis mit diesem Exponenten potenziert wird.

```cpp
static constexpr int min_exponent = 0;
```

### <a name="return-value"></a>Rückgabewert

Der minimale ganzzahlige Basis-basierte Exponent, der vom Typ dargestellt werden kann.

### <a name="remarks"></a>Hinweise

Die Memberfunktion ist nur für Gleitkommatypen relevant. `min_exponent` ist der Wert FLT_MIN_EXP für Typ **Gleitkomma**.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_min_exponent.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The minimum radix-based exponent for type float is:  "
        << numeric_limits<float>::min_exponent
        << endl;
   cout << "The minimum radix-based exponent for type double is:  "
        << numeric_limits<double>::min_exponent
        << endl;
   cout << "The minimum radix-based exponent for type long double is:  "
         << numeric_limits<long double>::min_exponent
        << endl;
}
```

```Output
The minimum radix-based exponent for type float is:  -125
The minimum radix-based exponent for type double is:  -1021
The minimum radix-based exponent for type long double is:  -1021
```

## <a name="min_exponent10"></a> numeric_limits::min_exponent10

Gibt den größten negativen ganzzahligen Exponenten zurück, den der Gleitkommatyp als einen endlichen Wert darstellen kann, wenn eine Basis von zehn mit diesem Exponenten potenziert wird.

```cpp
static constexpr int min_exponent10 = 0;
```

### <a name="return-value"></a>Rückgabewert

Der maximale ganzzahlige Basis 10 Exponent darstellbar vom Typ.

### <a name="remarks"></a>Hinweise

Die Memberfunktion ist nur für Gleitkommatypen relevant. `min_exponent10` ist der Wert FLT_MIN_10_EXP für Typ **Gleitkomma**.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_min_exponent10.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The minimum base 10 exponent for type float is:  "
        << numeric_limits<float>::min_exponent10
        << endl;
   cout << "The minimum base 10 exponent for type double is:  "
        << numeric_limits<double>::min_exponent10
        << endl;
   cout << "The minimum base 10 exponent for type long double is:  "
        << numeric_limits<long double>::min_exponent10
        << endl;
}
```

```Output
The minimum base 10 exponent for type float is:  -37
The minimum base 10 exponent for type double is:  -307
The minimum base 10 exponent for type long double is:  -307
```

## <a name="quiet_nan"></a> numeric_limits::quiet_NaN

Gibt die Darstellung einer stillen NaN (Not a Number) für den Typ zurück.

```cpp
static constexpr Type quiet_NaN() throw();
```

### <a name="return-value"></a>Rückgabewert

Die Darstellung einer stillen NaN für den Typ.

### <a name="remarks"></a>Hinweise

Der Rückgabewert ist nur aussagekräftig, wenn [has_quiet_NaN](#has_quiet_nan) **wahr** ist.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_quiet_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The quiet NaN for type float is:  "
        << numeric_limits<float>::quiet_NaN( )
        << endl;
   cout << "The quiet NaN for type int is:  "
        << numeric_limits<int>::quiet_NaN( )
        << endl;
   cout << "The quiet NaN for type long double is:  "
        << numeric_limits<long double>::quiet_NaN( )
        << endl;
}
```

```Output
The quiet NaN for type float is:  1.#QNAN
The quiet NaN for type int is:  0
The quiet NaN for type long double is:  1.#QNAN
```

## <a name="radix"></a> numeric_limits::radix

Gibt die ganzzahlige Basis (als Radix bezeichnet) zurück, die für die Darstellung eines Typs verwendet wird.

```cpp
static constexpr int radix = 0;
```

### <a name="return-value"></a>Rückgabewert

Die ganzzahlige Basis für die Darstellung des Typs.

### <a name="remarks"></a>Hinweise

Die Basis für die vordefinierten Integertypen ist 2 und die Basis, auf die der Exponent potenziert wird, oder FLT_RADIX, für die vordefinierten Gleitkommadatentypen.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_radix.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The base for type float is:  "
        << numeric_limits<float>::radix
        << endl;
   cout << "The base for type int is:  "
        << numeric_limits<int>::radix
        << endl;
   cout << "The base for type long double is:  "
        << numeric_limits<long double>::radix
        << endl;
}
```

```Output
The base for type float is:  2
The base for type int is:  2
The base for type long double is:  2
```

## <a name="round_error"></a> numeric_limits::round_error

Gibt den größten Rundungsfehler für den Typ zurück.

```cpp
static constexpr Type round_error() throw();
```

### <a name="return-value"></a>Rückgabewert

Der größte Rundungsfehler für den Typ.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_round_error.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The maximum rounding error for type float is:  "
        << numeric_limits<float>::round_error( )
        << endl;
   cout << "The maximum rounding error for type int is:  "
        << numeric_limits<int>::round_error( )
        << endl;
   cout << "The maximum rounding error for type long double is:  "
        << numeric_limits<long double>::round_error( )
        << endl;
}
```

```Output
The maximum rounding error for type float is:  0.5
The maximum rounding error for type int is:  0
The maximum rounding error for type long double is:  0.5
```

## <a name="round_style"></a> numeric_limits::round_style

Gibt einen Wert zurück, der die verschiedenen Methoden beschreibt, die eine Implementierung für die Rundung eines Gleitkommawerts auf einen ganzzahligen Wert auswählen kann.

```cpp
static constexpr float_round_style round_style = round_toward_zero;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert aus der `float_round_style`-Enumeration, der den Rundungsmodus beschreibt.

### <a name="remarks"></a>Hinweise

Gibt einen Wert zurück, der die verschiedenen Methoden beschreibt, die eine Implementierung für die Rundung eines Gleitkommawerts auf einen ganzzahligen Wert auswählen kann.

Der Rundungsmodus ist fest in dieser Implementierung programmiert.Selbst wenn das Programm mit einem anderen Rundungsmodus gestartet wird, wird dieser Wert nicht geändert.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_round_style.cpp
// compile with: /EHsc
#include <iostream>
#include <float.h>
#include <limits>

using namespace std;

int main( )
{
   cout << "The rounding style for a double type is: "
        << numeric_limits<double>::round_style << endl;
   _controlfp_s(NULL,_RC_DOWN,_MCW_RC );
   cout << "The rounding style for a double type is now: "
        << numeric_limits<double>::round_style << endl;
   cout << "The rounding style for an int type is: "
        << numeric_limits<int>::round_style << endl;
}
```

```Output
The rounding style for a double type is: 1
The rounding style for a double type is now: 1
The rounding style for an int type is: 0
```

## <a name="signaling_nan"></a> numeric_limits::signaling_NaN

Gibt die Darstellung einer anzeigenden NaN (Not a Number) für den Typ zurück.

```cpp
static constexpr Type signaling_NaN() throw();
```

### <a name="return-value"></a>Rückgabewert

Die Darstellung einer signalisierenden NaN für den Typ.

### <a name="remarks"></a>Hinweise

Der Rückgabewert ist nur aussagekräftig, wenn [has_signaling_NaN](#has_signaling_nan) **wahr** ist.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_signaling_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The signaling NaN for type float is:  "
        << numeric_limits<float>::signaling_NaN( )
        << endl;
   cout << "The signaling NaN for type int is:  "
        << numeric_limits<int>::signaling_NaN( )
        << endl;
   cout << "The signaling NaN for type long double is:  "
        << numeric_limits<long double>::signaling_NaN( )
        << endl;
}
```

## <a name="tinyness_before"></a> numeric_limits::tinyness_before

Testet, ob ein Typ für einen Wert vor dessen Rundung ermitteln kann, ob der Wert zu klein ist, um als normalisierter Wert dargestellt zu werden.

```cpp
static constexpr bool tinyness_before = false;
```

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn der Typ kleine Werte vor dessen Rundung; erkennen kann **"false"** Wenn dies nicht möglich.

### <a name="remarks"></a>Hinweise

Typen, die Winzigkeiten erkennen können, wurden als Option mit IEC 559-Gleitkommadarstellungen eingeschlossen, und seine Implementierung kann einige Ergebnisse beeinflussen.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_tinyness_before.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float types can detect tinyness before rounding: "
        << numeric_limits<float>::tinyness_before
        << endl;
   cout << "Whether double types can detect tinyness before rounding: "
        << numeric_limits<double>::tinyness_before
        << endl;
   cout << "Whether long int types can detect tinyness before rounding: "
        << numeric_limits<long int>::tinyness_before
        << endl;
   cout << "Whether unsigned char types can detect tinyness before rounding: "
        << numeric_limits<unsigned char>::tinyness_before
        << endl;
}
```

```Output
Whether float types can detect tinyness before rounding: 1
Whether double types can detect tinyness before rounding: 1
Whether long int types can detect tinyness before rounding: 0
Whether unsigned char types can detect tinyness before rounding: 0
```

## <a name="traps"></a> numeric_limits::traps

Testet, ob für einen Typ Auffangen, bei dem arithmetischen Ausnahmen gemeldet werden, implementiert ist.

```cpp
static constexpr bool traps = false;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn Fehlerbehebung für den Typ implementiert wird; **FALSE**, wenn nicht.

### <a name="example"></a>Beispiel

```cpp
// numeric_limits_traps.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float types have implemented trapping: "
        << numeric_limits<float>::traps
        << endl;
   cout << "Whether double types have implemented trapping: "
        << numeric_limits<double>::traps
        << endl;
   cout << "Whether long int types have implemented trapping: "
        << numeric_limits<long int>::traps
        << endl;
   cout << "Whether unsigned char types have implemented trapping: "
        << numeric_limits<unsigned char>::traps
        << endl;
}
```

```Output
Whether float types have implemented trapping: 1
Whether double types have implemented trapping: 1
Whether long int types have implemented trapping: 0
Whether unsigned char types have implemented trapping: 0
```

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
