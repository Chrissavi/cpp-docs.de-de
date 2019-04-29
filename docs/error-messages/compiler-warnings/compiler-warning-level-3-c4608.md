---
title: Compilerwarnung (Stufe 3) C4608
ms.date: 11/04/2016
f1_keywords:
- C4608
helpviewer_keywords:
- C4608
ms.assetid: 8b8f5f28-8ce9-457e-9d3d-a8c0efce9b6a
ms.openlocfilehash: 4f1bef80b8cddccc036a5151bb4cc4ac01483a36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401760"
---
# <a name="compiler-warning-level-3-c4608"></a>Compilerwarnung (Stufe 3) C4608

"union_member" wurde bereits von einem anderen Union-Member in der Initialisierungsliste initialisiert, "union_member"

In einer Initialisierungsliste wurden zwei Member desselben union-Elements initialisiert. Sie können nur auf ein Member des union-Elements zugreifen.

Im folgenden Beispiel wird C4608 generiert:

```
// C4608.cpp
// compile with: /W3 /c
class X {
public:
   X(char c) : m_i( c + 1), m_c(c) {}   // C4608
   // try the following line instead
   // X(char c) : m_c(c) {}

private:
   union {
      int m_i;
      char m_c;
   };
};

union Y {
public:
   Y(char * name) : m_number(0.3), m_string( name ) {} // C4608

private:
   double m_number;
   char * m_string;
};
```