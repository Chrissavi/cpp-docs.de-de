---
title: Compilerfehler C2541
ms.date: 11/04/2016
f1_keywords:
- C2541
helpviewer_keywords:
- C2541
ms.assetid: ed95180f-00df-4e62-a8e9-1b6dab8281bf
ms.openlocfilehash: de24503d256b8c7649ce87969b1b2f6a4709ac8f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740844"
---
# <a name="compiler-error-c2541"></a>Compilerfehler C2541

"Delete": delete: Objekte, die keine Zeiger sind, können nicht gelöscht werden.

Der [Delete](../../cpp/delete-operator-cpp.md) -Operator wurde für ein Objekt verwendet, das kein Zeiger ist.

Im folgenden Beispiel wird C2541 generiert:

```cpp
// C2541.cpp
int main() {
   int i;
   delete i;   // C2541 i not a pointer

   // OK
   int *ip = new int;
   delete ip;
}
```
