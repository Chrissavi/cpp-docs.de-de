---
title: aligned_union-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::aligned_union
helpviewer_keywords:
- aligned_union
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
ms.openlocfilehash: ae03802549f7791e51dccf1ea98a7b18929a4a4b
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72690110"
---
# <a name="aligned_union-class"></a>aligned_union-Klasse

Stellt einen POD-Typ bereit, der groß genug ist und passend ausgerichtet ist, um einen Union-Typ zu speichern. Außerdem bietet er die benötigte Größe.

## <a name="syntax"></a>Syntax

```cpp
template <std::size_t Len, class... Types>
struct aligned_union;

template <std::size_t Len, class... Types>
using aligned_union_t = typename aligned_union<Len, Types...>::type;
```

### <a name="parameters"></a>Parameter

*Len* -\
Der Ausrichtungswert für den größten Typ in der Union.

*Typen*\
Die unterschiedlichen Typen in der zugrunde liegenden Union.

## <a name="remarks"></a>Hinweise

Verwenden Sie die Klassen Vorlage, um die Ausrichtung und Größe zu erhalten, die zum Speichern einer Union in nicht initialisiertem Speicher erforderlich sind. Der typedef-Member `type` benennt einen POD-Typ, der für die Speicherung eines beliebigen Typs geeignet ist, der in *Typen*aufgeführt ist die minimale Größe beträgt *len*. Der statische Member `alignment_value` vom Typ `std::size_t` enthält die strengste Ausrichtung, die für alle unter *Typen*aufgeführten Typen erforderlich ist.

## <a name="example"></a>Beispiel

Folgendes Beispiel veranschaulicht den Gebrauch von `aligned_union`, um einen ausgerichteten Stapelpuffer zuzuweisen, um eine Union zu platzieren.

```cpp
// std__type_traits__aligned_union.cpp
#include <iostream>
#include <type_traits>

union U_type
{
    int i;
    float f;
    double d;
    U_type(float e) : f(e) {}
};

typedef std::aligned_union<16, int, float, double>::type aligned_U_type;

int main()
{
    // allocate memory for a U_type aligned on a 16-byte boundary
    aligned_U_type au;
    // do placement new in the aligned memory on the stack
    U_type* u = new (&au) U_type(1.0f);
    if (nullptr != u)
    {
        std::cout << "value of u->i is " << u->i << std::endl;
        // must clean up placement objects manually!
        u->~U_type();
    }
}
```

```Output
value of u->i is 1065353216
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[alignment_of-Klasse](../standard-library/alignment-of-class.md)
