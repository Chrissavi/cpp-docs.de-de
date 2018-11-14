---
title: function-Klasse
ms.date: 11/04/2016
f1_keywords:
- functional/std::function
- functional/std::function::result_type
- functional/std::function::assign
- functional/std::function::swap
- functional/std::function::target
- functional/std::function::target_type
- functional/std::function::operator unspecified
- functional/std::function::operator()
helpviewer_keywords:
- std::function [C++]
- std::function [C++], result_type
- std::function [C++], assign
- std::function [C++], swap
- std::function [C++], target
- std::function [C++], target_type
ms.assetid: 7b5ca76b-9ca3-4d89-8fcf-cad70a4aeae6
ms.openlocfilehash: 44c7691cc967b13b4fa94a7c51da57b7bf4d511f
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518722"
---
# <a name="function-class"></a>function-Klasse

Wrapper für ein aufrufbares Objekt.

## <a name="syntax"></a>Syntax

```cpp
template <class Fty>
class function  // Fty of type Ret(T1, T2, ..., TN)
    : public unary_function<T1, Ret>       // when Fty is Ret(T1)
    : public binary_function<T1, T2, Ret>  // when Fty is Ret(T1, T2)
{
public:
    typedef Ret result_type;

    function();
    function(nullptr_t);
    function(const function& right);
    template <class Fty2>
        function(Fty2 fn);
    template <class Fty2, class Alloc>
        function(reference_wrapper<Fty2>, const Alloc& Ax);

    template <class Fty2, class Alloc>
        void assign(Fty2, const Alloc& Ax);
    template <class Fty2, class Alloc>
        void assign(reference_wrapper<Fty2>, const Alloc& Ax);
    function& operator=(nullptr_t);
    function& operator=(const function&);
    template <class Fty2>
        function& operator=(Fty2);
    template <class Fty2>
        function& operator=(reference_wrapper<Fty2>);

    void swap(function&);
    explicit operator bool() const;

    result_type operator()(T1, T2, ....., TN) const;
    const std::type_info& target_type() const;
    template <class Fty2>
        Fty2 *target();

    template <class Fty2>
        const Fty2 *target() const;

    template <class Fty2>
        void operator==(const Fty2&) const = delete;
    template <class Fty2>
        void operator!=(const Fty2&) const = delete;
};
```

### <a name="parameters"></a>Parameter

*Fty*<br/>
Der zu umschließende Funktionstyp.

*AX*<br/>
Die Zuweisungsfunktion.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse ist ein Aufrufwrapper, dessen Aufrufsignatur `Ret(T1, T2, ..., TN)` ist. Sie können sie dazu verwenden, eine Vielzahl von aufrufbaren Objekten von einem einheitlichen Wrapper umschließen zu lassen.

Einige Memberfunktionen akzeptieren einen Operanden, der das gewünschte Zielobjekt benennt. Sie können einen solchen Operanden wie folgt festlegen:

`fn` – das aufrufbare Objekt `fn`. Nach dem Aufruf enthält das `function`-Objekt eine Kopie von `fn`

`fnref` – das aufrufbare, von `fnref.get()` benannte Objekt . Nach dem Aufruf enthält das `function`-Objekt einen Verweis auf `fnref.get()`

`right` – das aufrufbare Objekt wird, falls vorhanden, vom `function`-Objekt `right` reserviert

`npc` – ein NULL-Zeiger. Nach dem Aufruf ist das `function`-Objekt leer

In allen Fällen muss `INVOKE(f, t1, t2, ..., tN)` da, wo `f` das aufrufbare Objekt bzw. `t1, t2, ..., tN` Lvalues des Typs `T1, T2, ..., TN` sind, wohlgeformt, und, wenn `Ret` nicht „void“ ist, in `Ret` konvertierbar sein.

Ein leeres `function`-Objekt enthält kein aufrufbaren Objekt bzw. einen Verweis ebendieses.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[function](#function)|Konstruiert einen Wrapper, der entweder leer ist oder ein aufrufbares Objekt eines willkürlichen Typs mit einer festen Signatur speichert.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[result_type](#result_type)|Der Rückgabetyp des gespeicherten aufrufbaren Objekts.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[assign](#assign)|Weist ein aufrufbares Objekt diesem Funktionsobjekt zu.|
|[swap](#swap)|Tauscht zwei aufrufbare Objekte miteinander.|
|[target](#target)|Prüft, ob das gespeicherte aufrufbare Objekt wie festgelegt aufrufbar ist.|
|[target_type](#target_type)|Ruft Typinformationen für das aufrufbare Objekt ab.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[function::operator unspecified](#op_unspecified)|Prüft, ob ein gespeichertes aufrufbares Objekt existiert.|
|[function::operator()](#op_call)|Ruf ein aufrufbares Objekt auf.|
|[function::operator=](#op_eq)|Ersetzt das gespeicherte aufrufbare Objekt.|

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="assign"></a> function::assign

Weist ein aufrufbares Objekt diesem Funktionsobjekt zu.

```cpp
template <class Fx, class Alloc>
    void assign(
        Fx _Func,
        const Alloc& Ax);

template <class Fx, class Alloc>
    void assign(
        reference_wrapper<Fx> _Fnref,
        const Alloc& Ax);
```

### <a name="parameters"></a>Parameter

*_Func*<br/>
Ein aufrufbares Objekt.

*_Fnref*<br/>
Ein Verweiswrapper, der ein aufrufbares Objekt enthält.

*AX*<br/>
Ein Zuweisungsobjekt.

### <a name="remarks"></a>Hinweise

Die Memberfunktionen ersetzen jeweils das von `*this` gehaltene `callable object` durch ein aufrufbares Objekt, das als `operand` übergeben wurde. Beide weisen Speicher mit dem Zuweisungsobjekt *Ax*.

## <a name="function"></a> function::function

Konstruiert einen Wrapper, der entweder leer ist oder ein aufrufbares Objekt eines willkürlichen Typs mit einer festen Signatur speichert.

```cpp
function();
function(nullptr_t npc);
function(const function& right);
template <class Fx>
    function(Fx _Func);
template <class Fx>
    function(reference_wrapper<Fx> _Fnref);
template <class Fx, class Alloc>
    function(
        Fx _Func,
        const Alloc& Ax);

template <class Fx, class Alloc>
    function(
        reference_wrapper<Fx> _Fnref,
        const Alloc& Ax);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das zu kopierende Funktionsobjekt.

*FX*<br/>
Der Typ des aufrufbaren Objekts.

*_Func*<br/>
Das zu umschließende Objekt.

*Alloc*<br/>
Der Zuweisungstyp.

*AX*<br/>
Die Zuweisung.

*_Fnref*<br/>
Der zu umschließende aufrufbare Objektverweis.

### <a name="remarks"></a>Hinweise

Die ersten beiden Konstruktoren erstellt ein leeres `function`-Objekt. Die darauf folgenden drei Konstruktoren erstellen ein `function`-Objekt, das ein aufrufbares Objekt enthält, das als Operand übergeben wurde. Die letzten beiden Konstruktoren weisen dem Zuweisungsobjekt Ax Speicher zu.

### <a name="example"></a>Beispiel

```cpp
// std__functional__function_function.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>
#include <vector>

int square(int val)
{
    return val * val;
}

class multiply_by
{
public:
    explicit multiply_by(const int n) : m_n(n) { }

    int operator()(const int x) const
    {
        return m_n * x;
    }

private:
    int m_n;
};

int main()
{

    typedef std::vector< std::function<int (int)> > vf_t;

    vf_t v;
    v.push_back(square);
    v.push_back(std::negate<int>());
    v.push_back(multiply_by(3));

    for (vf_t::const_iterator i = v.begin(); i != v.end(); ++i)
    {
        std::cout << (*i)(10) << std::endl;
    }

    std::function<int (int)> f = v[0];
    std::function<int (int)> g;

    if (f) {
        std::cout << "f is non-empty (correct)." << std::endl;
    } else {
        std::cout << "f is empty (can't happen)." << std::endl;
    }

    if (g) {
        std::cout << "g is non-empty (can't happen)." << std::endl;
    } else {
        std::cout << "g is empty (correct)." << std::endl;
    }

    return 0;
}
```

```Output
100
-10
30
f is non-empty (correct).
g is empty (correct).
```

## <a name="op_unspecified"></a> function::operator unspecified

Prüft, ob ein gespeichertes aufrufbares Objekt existiert.

```cpp
operator unspecified();
```

### <a name="remarks"></a>Hinweise

Der Operator gibt einen Wert, der konvertiert werden kann, **"bool"** mit einem wahren Wert nur dann, wenn das Objekt nicht leer ist. Damit können Sie prüfen, ob das Objekt leer ist.

### <a name="example"></a>Beispiel

```cpp
// std__functional__function_operator_bool.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0;
    std::cout << std::boolalpha << "not empty == " << (bool)fn0 << std::endl;

    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "not empty == " << (bool)fn1 << std::endl;

    return (0);
    }
```

```Output
not empty == false
not empty == true
```

## <a name="op_call"></a> function::operator()

Ruf ein aufrufbares Objekt auf.

```cpp
result_type operator()(
    T1 t1,
    T2 t2, ...,
    TN tN);
```

### <a name="parameters"></a>Parameter

*TN*<br/>
Der Typ des n-ten Aufrufarguments.

*TN*<br/>
Das n-te Aufrufargument.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt `INVOKE(fn, t1, t2, ..., tN, Ret)` zurück, wenn `fn` das in `*this` gespeicherte Zielobjekt ist. Damit können Sie das umschlossene aufrufbare Objekt aufrufen.

### <a name="example"></a>Beispiel

```cpp
// std__functional__function_operator_call.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }
```

```Output
empty == false
val == -3
```

## <a name="op_eq"></a> function::operator=

Ersetzt das gespeicherte aufrufbare Objekt.

```cpp
function& operator=(null_ptr_type npc);
function& operator=(const function& right);
template <class Fty>
    function& operator=(Fty fn);
template <class Fty>
    function& operator=(reference_wrapper<Fty> fnref);
```

### <a name="parameters"></a>Parameter

*%npc*<br/>
Eine NULL-Zeiger-Konstante.

*right*<br/>
Das zu kopierende Funktionsobjekt.

*fn*<br/>
Das zu umschließende Objekt.

*fnref*<br/>
Der zu umschließende aufrufbare Objektverweis.

### <a name="remarks"></a>Hinweise

Die Operatoren ersetzen jeweils das von `*this` gehaltene aufrufbare Objekt durch ein aufrufbares Objekt, das als Operand übergeben wurde.

### <a name="example"></a>Beispiel

```cpp
// std__functional__function_operator_as.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "val == " << fn0(3) << std::endl;

    std::function<int (int)> fn1;
    fn1 = 0;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;

    fn1 = neg;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    fn1 = fn0;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    fn1 = std::cref(fn1);
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }
```

```Output
empty == false
val == -3
empty == true
empty == false
val == -3
empty == false
val == -3
empty == false
val == -3
```

## <a name="result_type"></a> function::result_type

Der Rückgabetyp des gespeicherten aufrufbaren Objekts.

```cpp
typedef Ret result_type;
```

### <a name="remarks"></a>Hinweise

Die Typedef stellt ein Synonym für den Typ `Ret` in der Aufrufsignatur der Vorlage dar. Damit können Sie den Rückgabetyp des umschlossenen aufrufbaren Objekts bestimmen.

### <a name="example"></a>Beispiel

```cpp
// std__functional__function_result_type.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;

    std::function<int (int)>::result_type val = fn1(3);
    std::cout << "val == " << val << std::endl;

    return (0);
    }
```

```Output
empty == false
val == -3
```

## <a name="swap"></a> function::swap

Tauscht zwei aufrufbare Objekte miteinander.

```cpp
void swap(function& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das Funktionsobjekt, mit dem getauscht werden soll.

### <a name="remarks"></a>Hinweise

Die Memberfunktion tauscht die Zielobjekte von `*this` und *rechten*. Die Funktion führt dies in konstanter Zeit aus und löst keine Ausnahmen aus.

### <a name="example"></a>Beispiel

```cpp
// std__functional__function_swap.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "val == " << fn0(3) << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << std::endl;

    fn0.swap(fn1);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }
```

```Output
empty == false
val == -3
empty == true

empty == true
empty == false
val == -3
```

## <a name="target"></a> function::target

Prüft, ob das gespeicherte aufrufbare Objekt wie festgelegt aufrufbar ist.

```cpp
template <class Fty2>
    Fty2 *target();
template <class Fty2>
    const Fty2 *target() const;
```

### <a name="parameters"></a>Parameter

*Fty2*<br/>
Der zu überprüfende Typ des aufrufbaren Zielobjekts.

### <a name="remarks"></a>Hinweise

Der Typ *Fty2* muss für die Argumenttypen aufrufbar sein `T1, T2, ..., TN` sowie des Rückgabetyps `Ret`. Wenn `target_type() == typeid(Fty2)`, dann gibt die Membervorlagenfunktion die Adresse des Zielobjekts zurück; andernfalls gibt sie 0 zurück.

Ein Typ *Fty2* wird aufgerufen, für die Argumenttypen `T1, T2, ..., TN` sowie des Rückgabetyps `Ret` If, für die Lvalues `fn, t1, t2, ..., tN` Typen `Fty2, T1, T2, ..., TN`, `INVOKE(fn, t1, t2, ..., tN)` wohlgeformt ist und, falls `Ret`nicht **"void"**, konvertierbar `Ret`.

### <a name="example"></a>Beispiel

```cpp
// std__functional__function_target.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    typedef int (*Myfun)(int);
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "no target == " << (fn0.target<Myfun>() == 0) << std::endl;

    Myfun *fptr = fn0.target<Myfun>();
    std::cout << "val == " << (*fptr)(3) << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "no target == " << (fn1.target<Myfun>() == 0) << std::endl;

    return (0);
    }
```

```Output
empty == false
no target == false
val == -3
empty == true
no target == true
```

## <a name="target_type"></a> function::target_type

Ruft Typinformationen für das aufrufbare Objekt ab.

```cpp
const std::type_info& target_type() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt `typeid(void)` zurück, wenn `*this` leer ist, andernfalls `typeid(T)`, wobei `T` der Typ des Zielobjekts ist.

### <a name="example"></a>Beispiel

```cpp
// std__functional__function_target_type.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "type == " << fn0.target_type().name() << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "type == " << fn1.target_type().name() << std::endl;

    return (0);
    }
```

```Output
empty == false
type == int (__cdecl*)(int)
empty == true
type == void
```

## <a name="see-also"></a>Siehe auch

[mem_fn](../standard-library/functional-functions.md#mem_fn)<br/>
[reference_wrapper-Klasse](../standard-library/reference-wrapper-class.md)<br/>
