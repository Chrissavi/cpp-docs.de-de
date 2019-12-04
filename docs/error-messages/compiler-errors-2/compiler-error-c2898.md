---
title: Compilerfehler C2898
ms.date: 11/04/2016
f1_keywords:
- C2898
helpviewer_keywords:
- C2898
ms.assetid: 68466e11-2541-4f6b-b772-13a642f30dfb
ms.openlocfilehash: d06741735f6358856b70c4264755fe559d4f88a9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735761"
---
# <a name="compiler-error-c2898"></a>Compilerfehler C2898

' Deklaration ': Element Funktions Vorlagen können nicht virtuell sein.

Im folgenden Beispiel wird C2898 generiert:

```cpp
// C2898.cpp
// compile with: /c
class X {
public:
   template<typename T> virtual void f(T t) {}   // C2898
};
```
