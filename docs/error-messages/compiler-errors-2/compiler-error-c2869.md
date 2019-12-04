---
title: Compilerfehler C2869
ms.date: 11/04/2016
f1_keywords:
- C2869
helpviewer_keywords:
- C2869
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
ms.openlocfilehash: c543a0a4afc0d24205e5afd57cf6ca0732f3edf4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755043"
---
# <a name="compiler-error-c2869"></a>Compilerfehler C2869

"Name": wurde bereits als Namespace definiert.

Sie können einen Namen, der bereits als Namespace verwendet wird, nicht wieder verwenden.

Im folgenden Beispiel wird C2869 generiert:

```cpp
// C2869.cpp
// compile with: /c
namespace A { int i; };

class A {};   // C2869, A is already used
```
