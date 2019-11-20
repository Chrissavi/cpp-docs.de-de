---
title: Compilerwarnung (Stufe 3) C4636
ms.date: 11/04/2016
f1_keywords:
- C4636
helpviewer_keywords:
- C4636
ms.assetid: 59112a0f-850f-41c6-bd84-8ae8dc84706a
ms.openlocfilehash: a1ee63b813c8ef468291eea4575286f40f96ff6a
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189133"
---
# <a name="compiler-warning-level-3-c4636"></a>Compilerwarnung (Stufe 3) C4636

Auf 'construct' angewendeter XML-Dokumentkommentar: Für das Tag ist ein nicht leeres Attribut erforderlich.

Ein Tag, wie etwa `cref`, wies keinen Wert auf.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4636 generiert:

```cpp
// C4636.cpp
// compile with: /clr /doc /W3 /c
/// <see cref=''/>
// /// <see cref='System::Exception'/>
ref struct A {   // C4636
   void f(int);
};

// OK
/// <see cref='System::Exception'/>
ref struct B {
   void f(int);
};
```