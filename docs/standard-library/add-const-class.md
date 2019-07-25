---
title: add_const-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_const
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
ms.openlocfilehash: 6f27a8e4bc0bea3a469d46a56e8885dabe5894df
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456580"
---
# <a name="addconst-class"></a>add_const-Klasse

Erstellt den „const“-Typ aus „type“.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct add_const;
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typmodifizierers enthält einen geänderten Typ, der *Ty* ist, wenn *Ty* ein Verweis, eine Funktion oder ein konstant qualifizierter Typ ist; andernfalls `const Ty`.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__add_const.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
{
    std::add_const<int>::type *p = (const int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_const<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_const<int> == int
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[remove_const-Klasse](../standard-library/remove-const-class.md)
