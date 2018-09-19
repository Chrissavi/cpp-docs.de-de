---
title: Compilerfehler C3731 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3731
dev_langs:
- C++
helpviewer_keywords:
- C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 526cd57bd18d379f7c85bbe98bc7fb2dc37b9c41
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099914"
---
# <a name="compiler-error-c3731"></a>Compilerfehler C3731

Inkompatibles Ereignis "Funktion1" und der Handler "Funktion2"; Ereignisquelle und Ereignishandler müssen vom gleichen Typ sein.

Die Ereignisquelle und einen Ereignisempfänger müssen denselben Typ haben (z. B. `native` im Vergleich zu `com` Typen). Um diesen Fehler zu beheben, stellen Sie die Typen von der Ereignisquelle und Ereignishandler.

Im folgende Beispiel wird die C3731 generiert:

```
// C3731.cpp
// compile with: /clr
#using <mscorlib.dll>
[event_source(native)]
struct A {
   __event void MyEvent();
};

[event_receiver(managed)]
// try the following line instead
// [event_receiver(native)]
struct B {
   void func();
   B(A a) {
      __hook(&A::MyEvent, &a, &B::func);   // C3731
   }
};

int main() {
}
```