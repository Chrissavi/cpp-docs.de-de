---
title: Compilerfehler C3290
ms.date: 11/04/2016
f1_keywords:
- C3290
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
ms.openlocfilehash: f2a346354d8da7d78c5517b01b4438bfb8af50ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222706"
---
# <a name="compiler-error-c3290"></a>Compilerfehler C3290

"Typ": Eine trivial-Eigenschaft darf keinen Referenztyp aufweisen.

Eine Eigenschaft wurde falsch deklariert. Wenn Sie eine triviale Eigenschaft deklarieren, erstellt der Compiler eine Variable, die von der Eigenschaft aktualisiert wird, und es ist nicht möglich, eine Nachverfolgungsverweisvariable in einer Klasse zu verwenden.

Finden Sie unter [Eigenschaft](../../extensions/property-cpp-component-extensions.md) und [Verweisoperator nachverfolgung](../../extensions/tracking-reference-operator-cpp-component-extensions.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3290 generiert.

```
// C3290.cpp
// compile with: /clr /c
ref struct R {};

ref struct X {
   R^ mr;

   property R % y;   // C3290
   property R ^ x;   // OK

   // OK
   property R% prop {
      R% get() {
         return *mr;
      }

      void set(R%) {}
   }
};

int main() {
   X x;
   R% xp = x.prop;
}
```