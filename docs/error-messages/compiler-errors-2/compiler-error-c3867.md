---
title: Compilerfehler C3867
ms.date: 11/04/2016
f1_keywords:
- C3867
helpviewer_keywords:
- C3867
ms.assetid: bc5de03f-e01a-4407-88c3-2c63f0016a1e
ms.openlocfilehash: 9308e238c86c7b8a957720228a823688fac289d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242876"
---
# <a name="compiler-error-c3867"></a>Compilerfehler C3867

'Func': Funktionsaufruf fehlt die Argumentliste. Verwenden Sie ' & Func' um einen Zeiger auf Member zu erstellen.

Sie haben versucht, die Adresse einer Memberfunktion zu verwenden, ohne die Memberfunktion mit dem Klassennamen und dem address-of-Operator zu qualifizieren.

Dieser Fehler kann außerdem infolge einer Konformitätsverbesserung für Compiler für Visual C++ 2005 auftreten: Verbesserte Pointer-to-Member-Konformität. Code, der vor Visual C++ 2005 kompiliert wurde, generiert nun C3867.

## <a name="example"></a>Beispiel

Der Compiler kann „C3867“ mit einem irreführenden Auflösungsvorschlag ausgegeben. Verwenden Sie nach Möglichkeit die am stärksten abgeleitete Klasse.

Im folgenden Beispiel wird C3867 generiert und gezeigt, wie Sie diesen Fehler beheben.

```
// C3867_1.cpp
// compile with: /c
struct Base {
protected:
   void Test() {}
};

class Derived : public Base {
   virtual void Bar();
};

void Derived::Bar() {
   void (Base::*p1)() = Test;   // C3867
   &Derived::Test;   // OK
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3867 generiert und gezeigt, wie Sie diesen Fehler beheben.

```
// C3867_2.cpp
#include<stdio.h>

struct S {
   char *func() {
      return "message";
   }
};

class X {
public:
   void f() {}
};

int main() {
   X::f;   // C3867

   // OK
   X * myX = new X;
   myX->f();

   S s;
   printf_s("test %s", s.func);   // C3867
   printf_s("test %s", s.func());   // OK
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3867 generiert und gezeigt, wie Sie diesen Fehler beheben.

```
// C3867_3.cpp
class X {
public:
   void mf(){}
};

int main() {
   void (X::*pmf)() = X::mf;   // C3867

   // try the following line instead
   void (X::*pmf2)() = &X::mf;
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3867 generiert.

```
// C3867_4.cpp
// compile with: /c
class A {
public:
   void f(int) {}

   typedef void (A::*TAmtd)(int);

   struct B {
      TAmtd p;
   };

   void g() {
      B b1;
      b1.p = f;   // C3867
   }
};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3867 generiert.

```
// C3867_5.cpp
// compile with: /EHsc
#include <iostream>

class Testpm {
public:
   void m_func1() {
      std::cout << m_num << "\tm_func1\n";
    }

   int m_num;
   typedef void (Testpm::*pmfn1)();
   void func(Testpm* p);
};

void Testpm::func(Testpm* p) {
   pmfn1 s = m_func1;   // C3867
   pmfn1 s2 = &Testpm::m_func1;   // OK
   (p->*s2)();
}

int main() {
   Testpm *pTestpm = new Testpm;
   pTestpm->m_num = 10;

   pTestpm->func(pTestpm);
}
```