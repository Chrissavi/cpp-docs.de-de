---
title: Schwerwiegender Fehler C1202
ms.date: 11/04/2016
f1_keywords:
- C1202
helpviewer_keywords:
- C1202
ms.assetid: c859adb8-17a7-4fa1-a1f3-5820b7bf3849
ms.openlocfilehash: 64e0ee6a98d7005bb2b15833f88c31d593b5b5c2
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686560"
---
# <a name="fatal-error-c1202"></a>Schwerwiegender Fehler C1202

Der Kontext für einen rekursiven Typ oder eine Funktionsabhängigkeit ist zu komplex

Eine Vorlagendefinition war rekursiv oder hat die zulässige Komplexität überschritten.

## <a name="examples"></a>Beispiele

Im folgenden Beispiel wird C1202 generiert.

```cpp
// C1202.cpp
// processor: x86 IPF
template<int n>
class Factorial : public Factorial<n-1>  {   // C1202
public:
   operator int () {
      return Factorial <n-1>::operator int () * n;
   }
};
Factorial<7> facSeven;
```

Mögliche Lösung:

```cpp
// C1202b.cpp
// compile with: /c
template<int n>
class Factorial : public Factorial<n-1> {
public:
   operator int () {
      return Factorial <n-1>::operator int () * n;
   }
};

template <>
class Factorial<0> {
public:
   operator int () {
      return 1;
   }
};

Factorial<7> facSeven;
```
