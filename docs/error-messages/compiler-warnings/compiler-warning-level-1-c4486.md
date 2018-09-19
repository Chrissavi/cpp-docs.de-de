---
title: Compilerwarnung (Stufe 1) C4486 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4486
dev_langs:
- C++
helpviewer_keywords:
- C4486
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c86f821855a0686b66c93db22ca6e200064142d1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047069"
---
# <a name="compiler-warning-level-1-c4486"></a>Compilerwarnung (Stufe 1) C4486

'Funktion': eine private virtuelle Methode einer Verweisklasse oder einer Werteklasse sollte "sealed" markiert werden

Da eine private virtuelle Memberfunktion einer verwalteten Klasse oder Struktur zugegriffen noch außer Kraft gesetzt werden, es sollte markiert werden [versiegelten](../../windows/sealed-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4486 generiert.

```
// C4486.cpp
// compile with: /clr /c /W1
ref class B {
private:
   virtual void f() {}   // C4486
   virtual void f1() sealed {}   // OK
};
```

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine mögliche Verwendung der eine private versiegelt, virtuell-Funktion.

```
// C4486_b.cpp
// compile with: /clr /c
ref class B {};

ref class D : B {};

interface class I {
   B^ mf();
};

ref class E : I {
private:
   virtual B^ g() sealed = I::mf {
      return gcnew B;
   }

public:
   virtual D^ mf() {
      return gcnew D;
   }
};
```