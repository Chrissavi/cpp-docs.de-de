---
title: Compilerfehler C2372
ms.date: 11/04/2016
f1_keywords:
- C2372
helpviewer_keywords:
- C2372
ms.assetid: 406bea63-c8d3-4231-9d26-c70af6980840
ms.openlocfilehash: db13a6bc108588fbbd9c15e2bcc647bea073a333
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603462"
---
# <a name="compiler-error-c2372"></a>Compilerfehler C2372

'Bezeichner': Neudefinition; unterschiedliche Dereferenzierungstypen

Der Bezeichner ist bereits mit einem anderen abgeleiteten Typ definiert.

Im folgenden Beispiel wird C2326 generiert:

```
// C2372.cpp
// compile with: /c
extern int *fp;
extern int fp[];   // C2372
extern int fp2[];   // OK
```