---
title: weak_ptr-Klasse
ms.date: 07/29/2019
f1_keywords:
- memory/std::weak_ptr
- memory/std::weak_ptr::element_type
- memory/std::weak_ptr::expired
- memory/std::weak_ptr::lock
- memory/std::weak_ptr::owner_before
- memory/std::weak_ptr::reset
- memory/std::weak_ptr::swap
- memory/std::weak_ptr::use_count
- memory/std::weak_ptr::operator=
helpviewer_keywords:
- std::weak_ptr [C++]
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
ms.assetid: 2db4afb2-c7be-46fc-9c20-34ec2f8cc7c2
ms.openlocfilehash: d4ba30f737bc570a4ee700b3a317b5feebe8a50a
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682408"
---
# <a name="weakptr-class"></a>weak_ptr-Klasse

Umschließt einen schwach verknüpften Zeiger.

## <a name="syntax"></a>Syntax

```cpp
template<class T> class weak_ptr;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der vom schwachen Zeiger gesteuerte Typ.

## <a name="remarks"></a>Hinweise

Die Vorlagen Klasse beschreibt ein Objekt, das auf eine Ressource verweist, die von einem oder mehreren [shared_ptr](shared-ptr-class.md) -Objekten verwaltet wird. Die `weak_ptr` Objekte, die auf eine Ressource verweisen, wirken sich nicht auf den Verweis Zähler der Ressource aus. Wenn das letzte `shared_ptr` Objekt, das diese Ressource verwaltet, zerstört wird, wird die Ressource freigegeben, auch wenn `weak_ptr` Objekte vorhanden sind, die auf diese Ressource verweisen. Dieses Verhalten ist für die Vermeidung von Zyklen in Datenstrukturen von entscheidender Bedeutung.

Ein `weak_ptr`-Objekt verweist auf eine Ressource, wenn es aus einem `shared_ptr`-Objekt erstellt wurde, das diese Ressource besitzt, wenn es aus einem `weak_ptr`-Objekt erstellt wurde, das auf diese Ressource verweist, oder wenn ihm diese Ressource mit [operator=](#op_eq) zugewiesen wurde. Ein `weak_ptr` -Objekt stellt keinen direkten Zugriff auf die Ressource bereit, auf die es verweist. Code, der auf die Ressource zugreifen muss, erledigt dies über ein `shared_ptr`-Objekt, das diese Ressource besitzt, die durch Aufrufen der Memberfunktion [lock](#lock) erstellt wurde. Ein `weak_ptr` -Objekt ist abgelaufen, wenn die Ressource, auf die es verweist, freigegeben wurde `shared_ptr` , weil alle Objekte, die die Ressource besitzen, zerstört wurden. Ein Aufrufen von `lock` für ein `weak_ptr`-Objekt, das abgelaufen ist, erstellt ein leeres shared_ptr-Objekt.

Ein leeres weak_ptr-Objekt verweist nicht auf Ressourcen und verfügt über keinen Kontroll Block. Ihre Memberfunktion `lock` gibt ein leeres shared_ptr-Objekt zurück.

Ein Zyklus tritt auf, wenn es für zwei oder mehr Ressourcen, die von `shared_ptr`-Objekten gesteuert werden, `shared_ptr`-Objekte gibt, die gegenseitig auf sich verweisen. Angenommen, eine kreisförmig verknüpfte Liste mit drei Elementen hat den Kopfknoten `N0`; dieser Knoten enthält ein `shared_ptr`-Objekt, das den nächsten Knoten, `N1`, besitzt; dieser Knoten enthält ein `shared_ptr`-Objekt, das den nächsten Knoten, `N2`, besitzt; dieser Knoten wiederum enthält ein `shared_ptr`-Objekt, das den Kopfknoten `N0` besitzt, wodurch der Zyklus geschlossen wird. In dieser Situation wird der Verweis Zähler niemals auf NULL gesetzt, und die Knoten im-Schleifen werden nie freigegeben. Um den Zyklus zu vermeiden, sollte der letzte Knoten, `N2`, anstelle eines `shared_ptr`-Objekts ein `weak_ptr`-Objekt enthalten, das auf `N0` verweist. Da das `weak_ptr` Objekt `N0` nicht Besitzer ist, wirkt `N0`sich dies nicht auf den Verweis Zähler aus, und wenn der letzte Verweis des Programms auf den Haupt Knoten zerstört wurde, werden auch die Knoten in der Liste zerstört.

## <a name="members"></a>Member

|||
|-|-|
| **Konstruktoren** | |
|[weak_ptr](#weak_ptr)|Erstellt ein Objekt vom Typ `weak_ptr`.|
| **Destruktoren** | |
|[~ weak_ptr](#tilde-weak_ptr)|Erstellt ein Objekt vom Typ `weak_ptr`.|
| **Typedefs** | |
|[element_type](#element_type)|Der Typ des Elements.|
| **Member-Funktionen** | |
|[expired](#expired)|Überprüft, ob der Besitz abgelaufen ist.|
|[lock](#lock)|Bedingt exklusiven Besitz einer Ressource.|
|[owner_before](#owner_before)|Gibt **true** zurück, `weak_ptr` wenn der angegebene Zeiger vor (oder kleiner als) geordnet ist.|
|[reset](#reset)|Gibt eine in Besitz befindliche Ressource frei.|
|[swap](#swap)|Tauscht zwei `weak_ptr`-Objekte.|
|[use_count](#use_count)|Zählt die Anzahl `shared_ptr` der Objekte.|
| **Operatoren** | |
|[operator=](#op_eq)|Ersetzt eine in Besitz befindliche Ressource.|

## <a name="element_type"></a>element_type

Der Typ des Elements.

```cpp
typedef T element_type; // through C++17
using element_type = remove_extent_t<T>; // C++20
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `T` dar.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_element_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::weak_ptr<int>::element_type val = *wp0.lock();

    std::cout << "*wp0.lock() == " << val << std::endl;

    return (0);
}
```

```Output
*wp0.lock() == 5
```

## <a name="expired"></a>Frist

Testet, ob der Besitz abgelaufen ist, d. h. das Objekt, auf das verwiesen wird, wurde gelöscht.

```cpp
bool expired() const noexcept;
```

### <a name="remarks"></a>Hinweise

Die Member-Funktion gibt true `*this` zurück, wenn abgelaufen ist; andernfalls **false**.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_expired.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}
```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

## <a name="lock"></a>Sperre

Ruft ein `shared_ptr` ab, das den Besitz einer Ressource freigibt.

```cpp
shared_ptr<T> lock() const noexcept;
```

### <a name="remarks"></a>Hinweise

Die Member-Funktion gibt ein leeres [shared_ptr](shared-ptr-class.md) - `*this` Objekt zurück, wenn abgelaufen ist. `shared_ptr<T>` andernfalls wird ein-Objekt zurück `*this` gegeben, das die Ressource besitzt, auf die verweist. Gibt einen Wert zurück, der der atomaren Ausführung `expired() ? shared_ptr<T>() : shared_ptr<T>(*this)`von entspricht.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_lock.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}
```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

## <a name="op_eq"></a>Operator =

Ersetzt eine in Besitz befindliche Ressource.

```cpp
weak_ptr& operator=(const weak_ptr& ptr) noexcept;

template <class Other>
weak_ptr& operator=(const weak_ptr<Other>& ptr) noexcept;

template <class Other>
weak_ptr& operator=(const shared_ptr<Other>& ptr) noexcept;
```

### <a name="parameters"></a>Parameter

*Außer*\
Der Typ, der vom freigegebenen Argument oder schwachen Zeiger gesteuert wird.

*PTR*\
Der schwache Zeiger oder freigegebene Zeiger, der kopiert werden soll.

### <a name="remarks"></a>Hinweise

Die Operatoren geben alle die Ressource frei, auf `*this` die derzeit von verwiesen wird, und weisen den Besitz der `*this`Ressource, die von *ptr* benannt wird, Wenn ein Operator fehlschlägt, bleibt `*this` er unverändert. Jeder Operator hat einen Effekt, `weak_ptr(ptr).swap(*this)`der entspricht.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_operator_as.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::shared_ptr<int> sp1(new int(10));
    wp0 = sp1;
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::weak_ptr<int> wp1;
    wp1 = wp0;
    std::cout << "*wp1.lock() == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*wp0.lock() == 5
*wp0.lock() == 10
*wp1.lock() == 10
```

## <a name="owner_before"></a>owner_before

Gibt **true** zurück, `weak_ptr` wenn der angegebene Zeiger vor (oder kleiner als) geordnet ist.

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr) const noexcept;

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr) const noexcept;
```

### <a name="parameters"></a>Parameter

*PTR*\
Ein Lvalue-Verweis auf ein `shared_ptr` oder ein `weak_ptr`.

### <a name="remarks"></a>Hinweise

Die Template-Member- Funktion gibt `*this` true zurück, wenn vor *ptr*geordnet ist.

## <a name="reset"></a>Festlegen

Gibt die eigene Ressource frei.

```cpp
void reset() noexcept;
```

### <a name="remarks"></a>Hinweise

Die Member-Funktion gibt die Ressource frei, `*this` auf die `*this` von verwiesen wird `weak_ptr` , und konvertiert in ein leeres-Objekt.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp(new int(5));
    std::weak_ptr<int> wp(sp);
    std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    wp.reset();
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    return (0);
}
```

```Output
*wp.lock() == 5
wp.expired() == false
wp.expired() == true
```

## <a name="swap"></a>Wechsel

Tauscht zwei `weak_ptr`-Objekte.

```cpp
void swap(weak_ptr& wp) noexcept;
```

Umfasst auch die Spezialisierung:

```cpp
template<class T>
void swap(weak_ptr<T>& a, weak_ptr<T>& b) noexcept;
```

### <a name="parameters"></a>Parameter

*UA*\
Der schwache Zeiger, mit dem getauscht werden soll.

### <a name="remarks"></a>Hinweise

Nach einem `swap`verweist auf die Ressource, auf die `*this` ursprünglich von verwiesen wurde, durch *WP*, und auf die Ressource, auf die von *WP* ursprünglich `*this`verwiesen wird, wird von verwiesen. Die Funktion ändert nicht die Verweis Zähler für die beiden Ressourcen und löst keine Ausnahmen aus. Die Auswirkung der Vorlagen Spezialisierung ist die Entsprechung von `a.swap(b)`.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::shared_ptr<int> sp2(new int(10));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    sp1.swap(sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;

    swap(sp1, sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << std::endl;

    std::weak_ptr<int> wp1(sp1);
    std::weak_ptr<int> wp2(sp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    wp1.swap(wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    swap(wp1, wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
*sp1 == 10
*sp1 == 5

*wp1 == 5
*wp1 == 10
*wp1 == 5
```

## <a name="use_count"></a>use_count

Zählt die Anzahl der `shared_ptr` Objekte, die die freigegebene Ressource besitzen.

```cpp
long use_count() const noexcept;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Anzahl der `shared_ptr`-Objekte zurück, die die Ressource besitzen, auf die von `*this` gezeigt wird.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_use_count.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    return (0);
}
```

```Output
wp.use_count() == 1
wp.use_count() == 2
```

## <a name="weak_ptr"></a>weak_ptr

Erstellt ein Objekt vom Typ `weak_ptr`.

```cpp
constexpr weak_ptr() noexcept;

weak_ptr(const weak_ptr& wp) noexcept;

weak_ptr(weak_ptr&& wp) noexcept;

template <class Other>
weak_ptr(const weak_ptr<Other>& wp) noexcept;

template <class Other>
weak_ptr(weak_ptr<Other>&& sp) noexcept;

template <class Other>
weak_ptr(const shared_ptr<Other>& sp) noexcept;
```

### <a name="parameters"></a>Parameter

*Außer*\
Der Typ, der vom Argument für den gemeinsamen/schwachen Zeiger gesteuert wird. Diese Konstruktoren sind nicht an der Überladungs Auflösung beteiligt, es `element_type*`sei denn, _andere\*_  ist mit kompatibel

*UA*\
Der zu kopierende schwache Zeiger.

*El*\
Der zu kopierende gemeinsame Zeiger

### <a name="remarks"></a>Hinweise

Der Standardkonstruktor erstellt ein `weak_ptr` leeres-Objekt. Die Konstruktoren, die ein Argument annehmen, erstellen ein `weak_ptr` leeres Objekt, wenn der Argument Zeiger leer ist. Andernfalls erstellen Sie ein `weak_ptr` -Objekt, das auf die Ressource verweist, die durch das-Argument benannt wird. Der Verweis Zähler des freigegebenen Objekts wird nicht geändert.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp0;
    std::cout << "wp0.expired() == " << std::boolalpha
        << wp0.expired() << std::endl;

    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp1(sp1);
    std::cout << "*wp1.lock() == "
        << *wp1.lock() << std::endl;

    std::weak_ptr<int> wp2(wp1);
    std::cout << "*wp2.lock() == "
        << *wp2.lock() << std::endl;

    return (0);
}
```

```Output
wp0.expired() == true
*wp1.lock() == 5
*wp2.lock() == 5
```

## <a name="tilde-weak_ptr"></a>~ weak_ptr

Beschädigt ein Objekt vom Typ `weak_ptr`.

```cpp
~weak_ptr();
```

### <a name="remarks"></a>Hinweise

Der Dekonstruktor zerstört `weak_ptr` dies, aber hat keine Auswirkung auf den Verweis Zähler des Objekts, auf dessen gespeicherter Zeiger zeigt.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](cpp-standard-library-header-files.md)\
[\<memory>](memory.md)\
[shared_ptr-Klasse](shared-ptr-class.md)
