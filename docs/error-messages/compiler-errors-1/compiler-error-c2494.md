---
title: Compilerfehler C2494
ms.date: 11/04/2016
f1_keywords:
- C2494
helpviewer_keywords:
- C2494
ms.assetid: 5dfd07ab-351d-49c9-b54e-f0a104776ab8
ms.openlocfilehash: 0a8be1dd5ce8d906bc4d0b1ce72295a57f68b6cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361645"
---
# <a name="compiler-error-c2494"></a>Compilerfehler C2494

'Schlüsselwort' __finally/finally-block oder kann nicht innerhalb eines Filterausdrucks aufgerufen werden

Sie können keine `keyword` in einem `__finally` oder finally-block.

Im folgende Beispiel wird die C2494 generiert:

```
// C2494.cpp
#include <malloc.h>

int main() {
   __try {}
   __except ( _alloca(100), 1 ) {}   // C2494
   __try {}
   __finally {
      _alloca(100);   // C2494
   }
}
```

C2494 kann auch auftreten, wenn **"/ CLR"**.

```
// C2494b.cpp
// compile with: /clr
#include <malloc.h>

int main() {
   char * buf;
   try {}
   catch (char * buf2) {}
   finally {
      _alloca(100);   // C2494
   }
}
```