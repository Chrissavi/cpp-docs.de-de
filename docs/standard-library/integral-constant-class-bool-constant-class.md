---
title: integral_constant Class, bool_constant-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::integral_constant
- XTR1COMMON/std::integral_constant
- type_traits/std::bool_constant
- XTR1COMMON/std::bool_constant
dev_langs:
- C++
helpviewer_keywords:
- std::integral_constant [C++]
- std::bool_constant [C++]
ms.assetid: 11c002c6-4d31-4042-9341-f2543f43e108
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 053816fcf18ec29b5e405f84b545432e848d2b59
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44104009"
---
# <a name="integralconstant-class-boolconstant-class"></a>integral_constant Class, bool_constant-Klasse

Wandelt einen Typ und einen Wert in eine Ganzzahlkonstante um.

## <a name="syntax"></a>Syntax

```cpp
template<class T, T v>
struct integral_constant {
   static constexpr T value = v;
   typedef T value_type;
   typedef integral_constant<T, v> type;
   constexpr operator value_type() const noexcept;
   constexpr value_type operator()() const noexcept;
   };
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Konstante.

*v*<br/>
Der Wert der Konstante.

## <a name="remarks"></a>Hinweise

Die `integral_constant`-Vorlagenklasse, sofern mit einem integralen Typ *T* und einem Wert *v* dieses Typs definiert, stellt ein Objekt dar, das eine Konstante dieses integralen Typs mit dem angegebenen Wert hält. Beim Member `type` handelt es sich um ein Alias des erstellten Vorlagenspezialisierungstypen, und der Member `value` hält den Wert *v*, der beim Erstellen der Spezialisierung verwendet wurde.

Die `bool_constant` Vorlagenklasse ist eine explizite teilspezialisierung von `integral_constant` verwendet **"bool"** als die *T* Argument.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__integral_constant.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "integral_constant<int, 5> == "
        << std::integral_constant<int, 5>::value << std::endl;
    std::cout << "integral_constant<bool, false> == " << std::boolalpha
        << std::integral_constant<bool, false>::value << std::endl;

    return (0);
    }

```

```Output
integral_constant<int, 5> == 5
integral_constant<bool, false> == false
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[false_type](../standard-library/type-traits-typedefs.md#false_type)<br/>
[true_type](../standard-library/type-traits-typedefs.md#true_type)<br/>
