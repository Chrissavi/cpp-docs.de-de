---
title: common_type-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::common_type
helpviewer_keywords:
- common_type class
- common_type
ms.assetid: 02bc4e7b-c63d-49de-9f8a-511d3a5c1e7f
ms.openlocfilehash: 3605b34a2bfc50831c889976ac5ea884053bb642
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449492"
---
# <a name="commontype-class"></a>common_type-Klasse

Bestimmt den allgemeinen Typ mindestens eines Typs.

## <a name="syntax"></a>Syntax

```cpp
template <class... T>
struct common_type;

template <class T>
struct common_type<T> {
    typedef typename decay<T>::type type;
};

template <class T, class U>
struct common_type<T, U> {
    typedef typename decay<decltype(true declval<T>() :
    declval<U>())>::type type;
};

template <class T, class U, class... V>
struct common_type<T, U, V...> {
    typedef typename common_type<typename common_type<T, U>::type, V...>::type type;
};
```

### <a name="parameters"></a>Parameter

Liste mit Typen, die entweder [vollständige Typen](../c-language/incomplete-types.md) oder leer sind.

## <a name="remarks"></a>Hinweise

Der `type`-Member ist der allgemeine Typ, in den alle Typen in der Parameterliste konvertiert werden können.

## <a name="example"></a>Beispiel

Mit dem folgenden Programm werden einige richtige Verwendungsszenarios und Tests für Ergebnisse veranschaulicht.

```cpp
// Compile using cl.exe /EHsc
// common_type sample
#include <iostream>
#include <type_traits>

struct Base {};
struct Derived : Base {};

int main()
{
    typedef std::common_type<unsigned char, short, int>::type NumericType;
    typedef std::common_type<float, double>::type FloatType;
    typedef std::common_type<const int, volatile int>::type ModifiedIntType;
    typedef std::common_type<Base, Derived>::type ClassType;

    std::cout << std::boolalpha;
    std::cout << "Test for typedefs of common_type int" << std::endl;
    std::cout << "NumericType: "     << std::is_same<int, NumericType>::value << std::endl;
    std::cout << "FloatType: "       << std::is_same<int, FloatType>::value << std::endl;
    std::cout << "ModifiedIntType: " << std::is_same<int, ModifiedIntType>::value << std::endl;
    std::cout << "ClassType: "       << std::is_same<int, ClassType>::value << std::endl;
    std::cout << "---------------------------" << std::endl;
    std::cout << "Test for typedefs of common_type double" << std::endl;
    std::cout << "NumericType: "     << std::is_same<double, NumericType>::value << std::endl;
    std::cout << "FloatType: "       << std::is_same<double, FloatType>::value << std::endl;
    std::cout << "ModifiedIntType: " << std::is_same<double, ModifiedIntType>::value << std::endl;
    std::cout << "ClassType: "       << std::is_same<double, ClassType>::value << std::endl;
    std::cout << "---------------------------" << std::endl;
    std::cout << "Test for typedefs of common_type Base" << std::endl;
    std::cout << "NumericType: "     << std::is_same<Base, NumericType>::value << std::endl;
    std::cout << "FloatType: "       << std::is_same<Base, FloatType>::value << std::endl;
    std::cout << "ModifiedIntType: " << std::is_same<Base, ModifiedIntType>::value << std::endl;
    std::cout << "ClassType: "       << std::is_same<Base, ClassType>::value << std::endl;

    return 0;
}
```

## <a name="output"></a>Ausgabe

```Output
Test for typedefs of common_type int
NumericType: true
FloatType: false
ModifiedIntType: true
ClassType: false
---------------------------
Test for typedefs of common_type double
NumericType: false
FloatType: true
ModifiedIntType: false
ClassType: false
---------------------------
Test for typedefs of common_type Base
NumericType: false
FloatType: false
ModifiedIntType: false
ClassType: true
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
