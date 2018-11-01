---
title: Compilerfehler C3363
ms.date: 11/04/2016
f1_keywords:
- C3363
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
ms.openlocfilehash: 05a9a339a48ede37f83696e7c524858c3fb03b54
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50427989"
---
# <a name="compiler-error-c3363"></a>Compilerfehler C3363

"Typ" : "Typ-ID" kann nur auf einen Typ angewendet werden.

Der [typeid](../../windows/typeid-cpp-component-extensions.md) -Operator wurde falsch verwendet.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3363 generiert:

```
// C3363.cpp
// compile with: /clr
int main() {
   System::typeid;   // C3363
}
```