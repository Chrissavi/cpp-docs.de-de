---
title: Compilerwarnung (Stufe 2) C4250
ms.date: 11/04/2016
f1_keywords:
- C4250
helpviewer_keywords:
- C4250
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
ms.openlocfilehash: 03826f10659cbdf6035cd4dedebecca3e3302e3a
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052114"
---
# <a name="compiler-warning-level-2-c4250"></a>Compilerwarnung (Stufe 2) C4250

"Class1": erbt "Klasse2:: Member" über Dominanz

Mindestens zwei Member haben denselben Namen. Die in `class2` wird geerbt, da Sie eine Basisklasse für die anderen Klassen ist, die diesen Member enthalten.

Um C4250 zu unterdrücken, verwenden Sie das [Warning](../../preprocessor/warning.md) -Pragma.

Da eine virtuelle Basisklasse von mehreren abgeleiteten Klassen gemeinsam genutzt wird, ist ein Name in einer abgeleiteten Klasse ein Name in einer Basisklasse. Bei der folgenden Klassenhierarchie gibt es z. b. zwei Definitionen von Func, die innerhalb des Diamanten geerbt wurden: die Vbc:: Func ()-Instanz durch die schwache Klasse und die dominante:: Func () durch die dominierende Klasse. Ein nicht qualifizierter Aufruf von Func () über ein Diamant Klassenobjekt ruft immer die dominieren:: Func ()-Instanz auf.  Wenn die schwache Klasse eine Instanz von Func () einführen würde, würde keine der Definitionen dominieren, und der-Befehl würde als mehrdeutig gekennzeichnet werden.

```cpp
// C4250.cpp
// compile with: /c /W2
#include <stdio.h>
struct vbc {
   virtual void func() { printf("vbc::func\n"); }
};

struct weak : public virtual vbc {};

struct dominant : public virtual vbc {
   void func() { printf("dominant::func\n"); }
};

struct diamond : public weak, public dominant {};

int main() {
   diamond d;
   d.func();   // C4250
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4250 generiert.

```cpp
// C4250_b.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;
class A {
public:
   virtual operator int () {
      return 2;
   }
};

class B : virtual public A {
public:
   virtual operator int () {
      return 3;
   }
};

class C : virtual public A {};

class E : public B, public C {};   // C4250

int main() {
   E eObject;
   cout << eObject.operator int() << endl;
}
```

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt eine komplexere Situation. Im folgenden Beispiel wird C4250 generiert.

```cpp
// C4250_c.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;

class V {
public:
   virtual int f() {
      return 1024;
   }
};

class B : virtual public V {
public:
   int b() {
      return f(); // B::b() calls V::f()
   }
};

class M : virtual public V {
public:
   int f() {
      return 7;
   }
};

// because of dominance, f() is M::f() inside D,
// changing the meaning of B::b's f() call inside a D
class D : public B, public M {};   // C4250

int main() {
   D d;
   cout << "value is: " << d.b();   // invokes M::f()
}
```