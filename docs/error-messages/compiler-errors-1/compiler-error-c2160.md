---
title: Compilerfehler C2160
ms.date: 11/04/2016
f1_keywords:
- C2160
helpviewer_keywords:
- C2160
ms.assetid: a1f694a7-fb16-4437-b7f5-a1af6da94bc5
ms.openlocfilehash: bd0c49f44bce09958541a47db0c66bc22d7f2b76
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454508"
---
# <a name="compiler-error-c2160"></a>Compilerfehler C2160

"##" kann nicht am Anfang einer Makrodefinition stehen

Eine Makrodefinition begann mit einem tokeneinfügenden Operator (##).

Im folgenden Beispiel wird C2160 generiert:

```
// C2160.cpp
// compile with: /c
#define mac(a,b) #a   // OK
#define mac(a,b) ##a   // C2160
```