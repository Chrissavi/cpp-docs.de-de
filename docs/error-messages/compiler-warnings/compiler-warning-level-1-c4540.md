---
title: Compilerwarnung (Stufe 1) C4540
ms.date: 11/04/2016
f1_keywords:
- C4540
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
ms.openlocfilehash: 8e514f4f3cf0cc3ee95ff709eda307b143ab3b1c
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965686"
---
# <a name="compiler-warning-level-1-c4540"></a>Compilerwarnung (Stufe 1) C4540

dynamic_cast, die verwendet werden, um in die nicht zugängliche oder mehrdeutige Basis der Lauf Zeit Test schlägt fehl ("Typ1" zu "Typ2").

Sie haben `dynamic_cast` verwendet, um von einem Typ in einen anderen zu konvertieren. Der Compiler hat festgestellt, dass bei der Umwandlung immer ein Fehler auftritt (Rückgabe **null**), weil auf eine Basisklasse (z. b.`private`) oder mehrdeutig (z. b. in der Klassenhierarchie) nicht zugegriffen werden kann.

Im folgenden finden Sie ein Beispiel für diese Warnung. Klasse **B** ist von Klasse **a**abgeleitet. Das Programm verwendet `dynamic_cast`, um eine Umwandlung von Klasse **b** (die abgeleitete Klasse) in Klasse **A**durchzuführen, was immer fehlschlägt, da Klasse **b** `private` und somit nicht darauf zugegriffen werden kann. Wenn Sie den Zugriff von **A** auf **Public** ändern, wird die Warnung aufgelöst.

```cpp
// C4540.cpp
// compile with: /W1

struct A {
   virtual void g() {}
};

struct B : private A {
   virtual void g() {}
};

int main() {
   B b;
   A * ap = dynamic_cast<A*>(&b);   // C4540
}
```