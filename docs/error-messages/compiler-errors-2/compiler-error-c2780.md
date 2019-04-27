---
title: Compilerfehler C2780
ms.date: 11/04/2016
f1_keywords:
- C2780
helpviewer_keywords:
- C2780
ms.assetid: 423793d8-a3b2-4f35-85f8-ae1d043e2b69
ms.openlocfilehash: 9a427bbd79570a2646447d5326e034035306fac6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257451"
---
# <a name="compiler-error-c2780"></a>Compilerfehler C2780

'declaration': erwartet werden N Argumente, es wurden M bereitgestellt

Eine Funktionsvorlage enthält zu wenige oder zu viele Argumente.

Im folgenden Beispiel wird C2780 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2780.cpp
template<typename T>
void f(T, T){}

int main() {
   f(1);  // C2780
   // try the following line instead
   // f(1,2);
}
```