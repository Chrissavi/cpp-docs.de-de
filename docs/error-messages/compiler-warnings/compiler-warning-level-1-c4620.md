---
title: Compilerwarnung (Stufe 1) C4620
ms.date: 11/04/2016
f1_keywords:
- C4620
helpviewer_keywords:
- C4620
ms.assetid: fed29934-b797-47e8-bbea-c7e5f8dd6e93
ms.openlocfilehash: f044d3e10928bc1aaa1e111d01d04b8562b5c025
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185892"
---
# <a name="compiler-warning-level-1-c4620"></a>Compilerwarnung (Stufe 1) C4620

Keine Postfix-Form von 'Operator ++' für den Typ 'Typ' gefunden, Präfix-Form verwendet

Es ist kein Postfixinkrementoperator für den angegebenen Typ definiert. Der Compiler hat den überladenen Präfixoperator verwendet.

Diese Warnung kann vermieden werden, indem Sie einen Postfix- `++` -Operator definieren. Erstellen Sie eine Version des `++` -Operators mit zwei Argumenten, wie hier gezeigt:

```cpp
// C4620.cpp
// compile with: /W1
class A
{
public:
   A(int nData) : m_nData(nData)
   {
   }

   A operator++()
   {
      m_nData -= 1;
      return *this;
   }

   // A operator++(int)
   // {
   //    A tmp = *this;
   //    m_nData -= 1;
   //    return tmp;
   // }

private:
   int m_nData;
};

int main()
{
   A a(10);
   ++a;
   a++;   // C4620
}
```
