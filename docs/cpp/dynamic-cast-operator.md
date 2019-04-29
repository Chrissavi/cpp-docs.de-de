---
title: dynamic_cast-Operator
ms.date: 11/19/2018
f1_keywords:
- dynamic_cast_cpp
helpviewer_keywords:
- dynamic_cast keyword [C++]
ms.assetid: f380ada8-6a18-4547-93c9-63407f19856b
ms.openlocfilehash: 3b359885eb72f9272fb1efe14afe9a6cbe6ddb30
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399040"
---
# <a name="dynamiccast-operator"></a>dynamic_cast-Operator

Konvertiert den Operanden `expression` in ein Objekt vom Typ `type-id`.

## <a name="syntax"></a>Syntax

```
dynamic_cast < type-id > ( expression )
```

## <a name="remarks"></a>Hinweise

`type-id` muss ein Zeiger oder ein Verweis auf einen zuvor definierten Klassentyp oder ein "Zeiger auf void" sein. Der `expression`-Typ muss ein Zeiger sein, wenn `type-id` ein Zeiger ist, oder ein lvalue, wenn `type-id` ein Verweis ist.

Finden Sie unter ["static_cast"](../cpp/static-cast-operator.md) eine Erläuterung des Unterschieds zwischen statischen und dynamischen umwandlungskonvertierungen erklärt, und wann sie jeweils zu verwenden sind.

Es gibt zwei wichtige Änderungen im Verhalten von **Dynamic_cast** in verwaltetem Code:

- **Dynamic_cast** in einen Zeiger auf den zugrunde liegenden Typ einer geschachtelten Enumeration wird zur Laufzeit einen Fehler, 0, anstelle des konvertierten Zeigers zurückgeben.

- **Dynamic_cast** löst eine Ausnahme nicht mehr bei `type-id` wird ein innerer Zeiger auf einen Werttyp handelt, die Umwandlung führt zu einem Laufzeitfehler.  Die Umwandlung gibt jetzt den 0-Zeigerwert zurück, statt auszulösen.

Wenn `type-id` ein Zeiger auf eine eindeutig zugreifbare direkte oder indirekte Basisklasse von `expression` ist, ist ein Zeiger auf das eindeutige Unterobjekt vom Typ `type-id` das Ergebnis. Zum Beispiel:

```cpp
// dynamic_cast_1.cpp
// compile with: /c
class B { };
class C : public B { };
class D : public C { };

void f(D* pd) {
   C* pc = dynamic_cast<C*>(pd);   // ok: C is a direct base class
                                   // pc points to C subobject of pd
   B* pb = dynamic_cast<B*>(pd);   // ok: B is an indirect base class
                                   // pb points to B subobject of pd
}
```

Diese Art der Konvertierung wird als "Typumwandlung nach oben (Upcast)" bezeichnet, da ein Zeiger in einer Klassenhierarchie nach oben verschoben wird, von einer abgeleiteten Klasse zu der Klasse, von der sie abgeleitet wurde. Eine Typumwandlung nach oben ist eine implizite Konvertierung.

Wenn `type-id` "void*" ist, wird eine Laufzeitüberprüfung durchgeführt, um den tatsächlichen Typ von `expression` zu bestimmen. Das Ergebnis ist ein Zeiger auf das vollständige Objekt, auf das durch `expression` gezeigt wird. Zum Beispiel:

```cpp
// dynamic_cast_2.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};

void f() {
   A* pa = new A;
   B* pb = new B;
   void* pv = dynamic_cast<void*>(pa);
   // pv now points to an object of type A

   pv = dynamic_cast<void*>(pb);
   // pv now points to an object of type B
}
```

Wenn `type-id` nicht "void*" ist, wird eine Laufzeitüberprüfung durchgeführt, um festzustellen, ob das Objekt, auf das durch `expression` gezeigt wird, in einen Typ konvertiert werden kann, auf den durch `type-id` gezeigt wird.

Wenn der Typ von `expression` eine Basisklasse vom Typ `type-id` ist, wird eine Laufzeitüberprüfung durchgeführt, um festzustellen, ob `expression` tatsächlich auf ein vollständiges Objekt vom Typ `type-id` zeigt. Wenn dies der Fall ist, ist das Ergebnis ein Zeiger auf ein vollständiges Objekt vom Typ `type-id`. Zum Beispiel:

```cpp
// dynamic_cast_3.cpp
// compile with: /c /GR
class B {virtual void f();};
class D : public B {virtual void f();};

void f() {
   B* pb = new D;   // unclear but ok
   B* pb2 = new B;

   D* pd = dynamic_cast<D*>(pb);   // ok: pb actually points to a D
   D* pd2 = dynamic_cast<D*>(pb2);   // pb2 points to a B not a D
}
```

Diese Art der Konvertierung wird als "Typumwandlung" bezeichnet, da ein Zeiger in einer Klassenhierarchie nach unten verschoben wird, von einer angegebenen Klasse zu einer von dieser abgeleiteten Klasse.

Im Fall der Mehrfachvererbung werden Möglichkeiten für Mehrdeutigkeit eingeführt. Betrachten Sie die Klassenhierarchie, die in der folgenden Abbildung gezeigt wird.

Bei CLR-Typen **Dynamic_cast** führt keine Aktion, wenn die Konvertierung implizit durchgeführt werden kann, oder einer MSIL- `isinst` -Anweisung, die eine dynamische Prüfung ausführt, und gibt **"nullptr"** Wenn die Konvertierung schlägt fehl.

Das folgende Beispiel verwendet **Dynamic_cast** zu bestimmen, ob eine Klasse eine Instanz eines bestimmten Typs ist:

```cpp
// dynamic_cast_clr.cpp
// compile with: /clr
using namespace System;

void PrintObjectType( Object^o ) {
   if( dynamic_cast<String^>(o) )
      Console::WriteLine("Object is a String");
   else if( dynamic_cast<int^>(o) )
      Console::WriteLine("Object is an int");
}

int main() {
   Object^o1 = "hello";
   Object^o2 = 10;

   PrintObjectType(o1);
   PrintObjectType(o2);
}
```

![Klassenhierarchie, die mehrfacher Vererbung](../cpp/media/vc39011.gif "Klassenhierarchie, die mehrfacher Vererbung") <br/>
Klassenhierarchie mit mehrfacher Vererbung

Ein Zeiger auf ein Objekt vom Typ `D` kann sicher in `B` oder `C` umgewandelt werden. Wenn jedoch `D` umgewandelt wird, um auf ein `A`-Objekt zu zeigen, welche Instanz von `A` würde daraus resultieren? Dies führt zu einem Fehler aufgrund mehrdeutiger Umwandlung. Um dieses Problem zu umgehen, können Sie zwei eindeutige Umwandlungen ausführen. Zum Beispiel:

```cpp
// dynamic_cast_4.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};
class D : public B {virtual void f();};

void f() {
   D* pd = new D;
   B* pb = dynamic_cast<B*>(pd);   // first cast to B
   A* pa2 = dynamic_cast<A*>(pb);   // ok: unambiguous
}
```

Alle anderen Mehrdeutigkeiten können eingeführt werden, wenn Sie virtuelle Basisklassen verwenden. Betrachten Sie die Klassenhierarchie, die in der folgenden Abbildung gezeigt wird.

![Klassenhierarchie, die von virtuellen Basisklassen](../cpp/media/vc39012.gif "Klassenhierarchie, die von virtuellen Basisklassen") <br/>
Klassenhierarchie mit virtuellen Basisklassen

In dieser Hierarchie ist `A` eine virtuelle Basisklasse. Bei einer Instanz der Klasse `E` und einen Zeiger auf die `A` -Unterobjekt wird ein **Dynamic_cast** in einen Zeiger auf `B` Mehrdeutigkeitsfehler. Sie müssen in das vollständige `E`-Objekt zurückumwandeln und anschließend auf eine eindeutige Weise entlang die Hierarchie arbeiten, um zu dem richtigen `B`-Objekt zu gelangen.

Betrachten Sie die Klassenhierarchie, die in der folgenden Abbildung gezeigt wird.

![Klassenhierarchie, die doppelten Basisklassen](../cpp/media/vc39013.gif "Klassenhierarchie, die doppelten Basisklassen") <br/>
Klassenhierarchie mit doppelten Basisklassen

Bei einem Objekt vom Typ `E` und einem Zeiger auf das `D`-Unterobjekt können drei Konvertierungen vorgenommen werden, um vom `D`-Unterobjekt auf das `A`-Unterobjekt zu navigieren, das sich am weitesten links befindet. Durchführen können eine **Dynamic_cast** Konvertierung von der `D` Zeiger auf ein `E` Zeiger, dann eine Konvertierung (entweder **Dynamic_cast** oder eine implizite Konvertierung) von `E`zu `B`, und schließlich eine implizite Konvertierung von `B` zu `A`. Zum Beispiel:

```cpp
// dynamic_cast_5.cpp
// compile with: /c /GR
class A {virtual void f();};
class B : public A {virtual void f();};
class C : public A { };
class D {virtual void f();};
class E : public B, public C, public D {virtual void f();};

void f(D* pd) {
   E* pe = dynamic_cast<E*>(pd);
   B* pb = pe;   // upcast, implicit conversion
   A* pa = pb;   // upcast, implicit conversion
}
```

Die **Dynamic_cast** Operator kann auch verwendet werden, um eine "übergreifende Umwandlung" auszuführen. Bei Verwenden der gleichen Klassenhierarchie ist es beispielsweise möglich, einen Zeiger aus dem `B`-Unterobjekt in das `D`-Unterobjekt umzuwandeln, solange das vollständige Objekt vom Typ `E` ist.

Im Fall von übergreifenden Umwandlungen ist es tatsächlich möglich, in nur zwei Schritten die Konvertierung von einem Zeiger auf `D` in einen Zeiger auf das `A`-Unterobjekt, das am weitesten links steht, durchzuführen. Sie können eine übergreifende Umwandlung von `D` in `B` und dann eine implizite Konvertierung von `B` in `A` ausführen. Zum Beispiel:

```cpp
// dynamic_cast_6.cpp
// compile with: /c /GR
class A {virtual void f();};
class B : public A {virtual void f();};
class C : public A { };
class D {virtual void f();};
class E : public B, public C, public D {virtual void f();};

void f(D* pd) {
   B* pb = dynamic_cast<B*>(pd);   // cross cast
   A* pa = pb;   // upcast, implicit conversion
}
```

Ein null-Zeiger-Wert wird in der null-Zeigerwert des Zieltyps von konvertiert **Dynamic_cast**.

Wenn Sie `dynamic_cast < type-id > ( expression )` verwenden, wenn `expression` nicht sicher in den Typ `type-id` konvertiert werden kann, führt die Laufzeitüberprüfung zu einem Umwandlungsfehler. Zum Beispiel:

```cpp
// dynamic_cast_7.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};

void f() {
   A* pa = new A;
   B* pb = dynamic_cast<B*>(pa);   // fails at runtime, not safe;
   // B not derived from A
}
```

Der Wert eines Fehlers bei einer Umwandlung in einen Zeigertyp ist der NULL-Zeiger. Eine fehlgeschlagene Umwandlung in den Referenztyp löst eine [Bad_cast-Ausnahme](../cpp/bad-cast-exception.md).   Wenn `expression` nicht zeigen bzw. verweisen auf ein gültiges Objekt, ein `__non_rtti_object` Ausnahme ausgelöst.

Finden Sie unter [Typeid](../cpp/typeid-operator.md) eine Erläuterung der `__non_rtti_object` Ausnahme.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der Basisklassenzeiger (Struktur A) auf ein Objekt (Struktur C) erstellt.  Dies sowie die Tatsache, dass virtuelle Funktionen vorhanden sind, ermöglicht Laufzeitpolymorphie.

In dem Beispiel wird außerdem eine nicht virtuelle Funktion in der Hierarchie aufgerufen.

```cpp
// dynamic_cast_8.cpp
// compile with: /GR /EHsc
#include <stdio.h>
#include <iostream>

struct A {
    virtual void test() {
        printf_s("in A\n");
   }
};

struct B : A {
    virtual void test() {
        printf_s("in B\n");
    }

    void test2() {
        printf_s("test2 in B\n");
    }
};

struct C : B {
    virtual void test() {
        printf_s("in C\n");
    }

    void test2() {
        printf_s("test2 in C\n");
    }
};

void Globaltest(A& a) {
    try {
        C &c = dynamic_cast<C&>(a);
        printf_s("in GlobalTest\n");
    }
    catch(std::bad_cast) {
        printf_s("Can't cast to C\n");
    }
}

int main() {
    A *pa = new C;
    A *pa2 = new B;

    pa->test();

    B * pb = dynamic_cast<B *>(pa);
    if (pb)
        pb->test2();

    C * pc = dynamic_cast<C *>(pa2);
    if (pc)
        pc->test2();

    C ConStack;
    Globaltest(ConStack);

   // will fail because B knows nothing about C
    B BonStack;
    Globaltest(BonStack);
}
```

```Output
in C
test2 in B
in GlobalTest
Can't cast to C
```

## <a name="see-also"></a>Siehe auch

[Umwandlungsoperatoren](../cpp/casting-operators.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)