---
title: Funktionsaufruf (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, C++ functions
- functions [C++], calling
- operator overloading [C++], function calls
- function overloading [C++], function-call operator
- function calls, operator
- operators [C++], overloading
- operator overloading [C++], examples
- function call operator ()
ms.assetid: 5094254a-045b-46f7-8653-69bc91e80dce
ms.openlocfilehash: 0064b17f0adf5cadf732321fbb62403a1da5db76
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649149"
---
# <a name="function-call-c"></a>Funktionsaufruf (C++)

Der Funktionsaufrufoperator, aufgerufen unter Verwendung von Klammern, ist ein binärer Operator.

## <a name="syntax"></a>Syntax

```
primary-expression ( expression-list )
```

## <a name="remarks"></a>Hinweise

In diesem Kontext ist `primary-expression` der erste Operand, und `expression-list`, eine möglicherweise leere Liste von Argumenten, ist der zweite Operand. Der Funktionsaufrufoperator wird für Vorgänge verwendet, die eine Anzahl von Parametern benötigen. Dies funktioniert, da eine `expression-list` eine Liste und kein einzelner Operand ist. Der Funktionsaufrufoperator muss eine nicht statische Memberfunktion sein.

Wenn der Funktionsaufrufoperator überladen ist, ändert er nicht die Art und Weise, wie Funktionen aufgerufen werden. Er ändert vielmehr die Art und Weise, wie der Operator interpretiert werden muss, wenn er auf Objekte eines angegebenen Klassentyps angewendet wird. Der folgende Code etwa wäre normalerweise ohne Bedeutung:

```cpp
Point pt;
pt( 3, 2 );
```

Bei einem entsprechenden überladenen Funktionsaufrufoperator kann jedoch diese Syntax verwendet werden, um die `x`-Koordinate um 3 Einheiten und die `y`-Koordinate um 2 Einheiten zu versetzen. Der folgende Code veranschaulicht eine solche Definition:

```cpp
// function_call.cpp
class Point
{
public:
    Point() { _x = _y = 0; }
    Point &operator()( int dx, int dy )
        { _x += dx; _y += dy; return *this; }
private:
    int _x, _y;
};

int main()
{
   Point pt;
   pt( 3, 2 );
}
```

Beachten Sie, dass der Funktionsaufrufoperator auf den Namen eines Objekts, nicht den Namen einer Funktion angewendet wird.

Sie können außerdem den Funktionsaufruf-Operator überladen und einen Zeiger auf eine Funktion verwenden (anstelle der eigentlichen Funktion).

```cpp
typedef void(*ptf)();
void func()
{
}
struct S
{
   operator ptf()
   {
      return func;
   }
};

int main()
{
   S s;
   s();//operates as s.operator ptf()()
}
```

## <a name="see-also"></a>Siehe auch

[Operatorüberladung](../cpp/operator-overloading.md)