---
title: is_convertible-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_convertible
dev_langs:
- C++
helpviewer_keywords:
- is_convertible class
- is_convertible
ms.assetid: 75614008-1894-42ea-bd57-974399628536
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 350fd6007ab6b89064ed6d0a7070a21e57427018
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956321"
---
# <a name="isconvertible-class"></a>is_convertible-Klasse

Testet, ob ein Typ in einen anderen konvertiert werden kann.

## <a name="syntax"></a>Syntax

```cpp
template <class From, class To>
struct is_convertible;
```

### <a name="parameters"></a>Parameter

*Von* den Ausgangsdatentyp der Konvertierung.

*Ty* den Zieltyp der Konvertierung.

## <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist TRUE, wenn der Ausdruck `To to = from;`, wobei `from` ein Objekt vom Typ `From` ist, wohlgeformt ist.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__is_convertible.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_convertible<trivial, int> == " << std::boolalpha
        << std::is_convertible<trivial, int>::value << std::endl;
    std::cout << "is_convertible<trivial, trivial> == " << std::boolalpha
        << std::is_convertible<trivial, trivial>::value << std::endl;
    std::cout << "is_convertible<char, int> == " << std::boolalpha
        << std::is_convertible<char, int>::value << std::endl;

    return (0);
    }

```

```Output
is_convertible<trivial, int> == false
is_convertible<trivial, trivial> == true
is_convertible<char, int> == true
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_base_of-Klasse](../standard-library/is-base-of-class.md)<br/>
