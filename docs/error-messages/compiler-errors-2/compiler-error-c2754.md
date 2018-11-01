---
title: Compilerfehler C2754
ms.date: 11/04/2016
f1_keywords:
- C2754
helpviewer_keywords:
- C2754
ms.assetid: 1cab66c5-da9d-4b81-b7fb-9cdc48ff1ccc
ms.openlocfilehash: cfe6f8faa1b00faf32ae53e6c25c23532c9f3a3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543016"
---
# <a name="compiler-error-c2754"></a>Compilerfehler C2754

"Spezialisierung": eine teilweise Spezialisierung kann nicht keinen abhängigen Nichttyp-Vorlagenparameter haben

Es wurde versucht, eine Vorlagenklasse teilweise spezialisiert werden, die keinen abhängigen Nichttyp-Vorlagenparameter. Dies ist nicht zulässig.

Im folgende Beispiel wird die C2754 generiert:

```
// C2754.cpp
// compile with: /c

template<class T, T t>
struct A {};

template<class T, int N>
struct B {};

template<class T> struct A<T,5> {};   // C2754
template<> struct A<int,5> {};   // OK
template<class T> struct B<T,5> {};   // OK
```