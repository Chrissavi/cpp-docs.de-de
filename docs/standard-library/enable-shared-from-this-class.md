---
title: enable_shared_from_this-Klasse
ms.date: 11/04/2016
f1_keywords:
- memory/std::enable_shared_from_this
helpviewer_keywords:
- enable_shared_from_this class
- enable_shared_from_this
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
ms.openlocfilehash: 9bf5055aefe505461e81703373ecb042a1f7224a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413722"
---
# <a name="enablesharedfromthis-class"></a>enable_shared_from_this-Klasse

Hilft bei der Erstellung von `shared_ptr`.

## <a name="syntax"></a>Syntax

```cpp
class enable_shared_from_this {
public:
    shared_ptr<Ty>
        shared_from_this();
    shared_ptr<const Ty> shared_from_this() const;
protected:
    enable_shared_from_this();
    enable_shared_from_this(const enable_shared_from_this&);
    enable_shared_from_this& operator=(const enable_shared_from_this&);
    ~enable_shared_from_this();
};
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der vom freigegebenen Zeiger gesteuerte Typ.

## <a name="remarks"></a>Hinweise

Aus `enable_shared_from_this` abgeleitete Objekte können mithilfe der `shared_from_this`-Methoden in Memberfunktionen [shared_ptr](../standard-library/shared-ptr-class.md)-Besitzer der Instanz erstellen, die sich den Besitz mit vorhandenen `shared_ptr`-Besitzern teilen. Andernfalls, wenn Sie ein neues erstellen `shared_ptr` mit **dies**, es unterscheidet sich von vorhandenen `shared_ptr` -Besitzer Dies können zu ungültigen verweisen oder dazu führen, dass das Objekt mehrmals gelöscht werden.

Die Konstruktoren, der Destruktor und der Zuweisungsoperator sind geschützt, um eine versehentliche falsche Verwendung zu verhindern. Der Vorlagenargumenttyp *Ty* muss der Typ der abgeleiteten Klasse sein.

Ein Beispiel für die Verwendung finden Sie unter [enable_shared_from_this::shared_from_this](#shared_from_this).

## <a name="requirements"></a>Anforderungen

**Header:** \<memory>

**Namespace:** std

## <a name="shared_from_this"></a> enable_shared_from_this::shared_from_this

Generiert ein `shared_ptr`-Objekt, das sich den Besitz der Instanz mit vorhandenen `shared_ptr`-Besitzern teilt.

```cpp
shared_ptr<T> shared_from_this();
shared_ptr<const T> shared_from_this() const;
```

### <a name="remarks"></a>Hinweise

Beim Ableiten von Objekten von der `enable_shared_from_this`-Basisklasse geben die `shared_from_this`-Vorlagenmemberfunktionen ein [shared_ptr Class](../standard-library/shared-ptr-class.md)-Objekt zurück, das sich den Besitz dieser Instanz mit vorhandenen `shared_ptr`-Besitzern teilt. Andernfalls, wenn Sie ein neues erstellen `shared_ptr` aus **dies**, es unterscheidet sich von vorhandenen `shared_ptr` -Besitzer Dies können zu ungültigen verweisen oder dazu führen, dass das Objekt mehrmals gelöscht werden. Dieses Verhalten ist bei einem Aufruf von `shared_from_this` für eine Instanz, die sich noch nicht im Besitz von einem `shared_ptr`-Objekt befindet, nicht definiert.

### <a name="example"></a>Beispiel

```cpp
// std_memory_shared_from_this.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

struct base : public std::enable_shared_from_this<base>
{
    int val;
    shared_ptr<base> share_more()
    {
        return shared_from_this();
    }
};

int main()
{
    auto sp1 = make_shared<base>();
    auto sp2 = sp1->share_more();

    sp1->val = 3;
    cout << "sp2->val == " << sp2->val << endl;
    return 0;
}
```

```Output
sp2->val == 3
```

## <a name="see-also"></a>Siehe auch

[enable_shared_from_this::shared_from_this](#shared_from_this)<br/>
[shared_ptr-Klasse](../standard-library/shared-ptr-class.md)<br/>