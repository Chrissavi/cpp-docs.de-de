---
title: Compilerfehler C2910
ms.date: 11/04/2016
f1_keywords:
- C2910
helpviewer_keywords:
- C2910
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
ms.openlocfilehash: 58d56ad834b34425cda4ac7ba081eabd2424e451
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408354"
---
# <a name="compiler-error-c2910"></a>Compilerfehler C2910

'Funktion': kann nicht explizit spezialisiert werden

Der Compiler hat beim Versuch, eine Funktion explizit zweimal zu spezialisieren.

Im folgende Beispiel wird die C2910 generiert:

```
// C2910.cpp
// compile with: /c
template <class T>
struct S;

template <> struct S<int> { void f() {} };
template <> void S<int>::f() {}   // C2910 delete this specialization
```

C2910 kann auch generiert werden, wenn Sie versuchen, ein nicht-Template-Element explizit spezialisiert werden kann. Sie können eine Funktionsvorlage, also nur explizit spezialisiert.

Im folgende Beispiel wird die C2910 generiert:

```
// C2910b.cpp
// compile with: /c
template <class T> struct A {
   A(T* p);
};

template <> struct A<void> {
   A(void* p);
};

template <class T>
inline A<T>::A(T* p) {}

template <> A<void>::A(void* p){}   // C2910
// try the following line instead
// A<void>::A(void* p){}
```

Dieser Fehler wird außerdem infolge einer konformitätsverbesserung für Compiler, die in Visual Studio .NET 2003 durchgeführt wurde generiert werden:.

Für Code in die Visual Studio .NET 2003 und Visual Studio .NET Version von Visual C++ gültig sein wird, entfernen Sie `template <>`.

Im folgende Beispiel wird die C2910 generiert:

```
// C2910c.cpp
// compile with: /c
template <class T> class A {
   void f();
};

template <> class A<int> {
   void f();
};

template <> void A<int>::f() {}   // C2910
// try the following line instead
// void A<int>::f(){}   // OK
```