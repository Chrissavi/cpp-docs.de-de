---
title: Compilerfehler C2012
ms.date: 11/04/2016
f1_keywords:
- C2012
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
ms.openlocfilehash: 85c3ad1d127dcabeeed0c5727ba6bbbca86f7898
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499657"
---
# <a name="compiler-error-c2012"></a>Compilerfehler C2012

Dateiname nach "<" fehlt

In einer `#include`-Direktive fehlt der erforderliche Dateiname.

Im folgenden Beispiel wird C2012 generiert:

```
// C2012.cpp
#include <   // C2012 include the filename to resolve
```

Mögliche Lösung:

```
// C2012b.cpp
// compile with: /c
#include <stdio.h>
```