---
title: Compilerfehler C3365 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3365
dev_langs:
- C++
helpviewer_keywords:
- C3365
ms.assetid: 875ec3a4-522c-4e3d-9b67-48808b857f6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8cb585c2d1142651e5edd01085dd904be60bc86
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044716"
---
# <a name="compiler-error-c3365"></a>Compilerfehler C3365

Operator-Operator: Unterschiedliche Operanden vom Typ "Typ1" und "Typ2".

Es wurde versucht, Delegaten mit unterschiedlichen Typen zu erstellen.  Finden Sie unter [wie: definieren und verwenden Delegaten (C++ / CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md) für Weitere Informationen zu Delegaten.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3365 generiert:

```cpp
// C3365.cpp
// compile with: /clr
delegate void D1();
delegate void D2(int);

ref class R {
public:
   void f(){}
   void g(int){}
};

int main() {
   D1^ d1 = gcnew D1(gcnew R, &R::f);
   D2^ d2 = gcnew D2(gcnew R, &R::g);
   D1^ d3 = gcnew D1(gcnew R, &R::f);

   d1 += d2;   // C3365
   d1 += d3;   // OK
   d1();
}
```