---
title: is_reference-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_reference
dev_langs:
- C++
helpviewer_keywords:
- is_reference class
- is_reference
ms.assetid: 3d9e631f-3092-430c-843e-e914ab58c257
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7882bdd68d6d35994752c8332329e6a92b74fbfa
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959793"
---
# <a name="isreference-class"></a>is_reference-Klasse

Testet, ob der Typ ein Verweis ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_reference;
```

### <a name="parameters"></a>Parameter

*Ty* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist ein Verweis auf ein Objekt oder eine Funktion ist, andernfalls "false".

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__is_reference.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_reference<trivial> == " << std::boolalpha
        << std::is_reference<trivial>::value << std::endl;
    std::cout << "is_reference<trivial&> == " << std::boolalpha
        << std::is_reference<trivial&>::value << std::endl;
    std::cout << "is_reference<int()> == " << std::boolalpha
        << std::is_reference<int()>::value << std::endl;
    std::cout << "is_reference<int(&)()> == " << std::boolalpha
        << std::is_reference<int(&)()>::value << std::endl;

    return (0);
    }

```

```Output
is_reference<trivial> == false
is_reference<trivial&> == true
is_reference<int()> == false
is_reference<int(&)()> == true
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_pointer-Klasse](../standard-library/is-pointer-class.md)<br/>
