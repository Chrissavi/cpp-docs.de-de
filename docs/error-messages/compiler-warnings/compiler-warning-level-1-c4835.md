---
title: Compilerwarnung (Stufe 1) C4835 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4835
dev_langs:
- C++
helpviewer_keywords:
- C4835
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70492be13d312c5d167990cfa0b6c0d741e1055f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080102"
---
# <a name="compiler-warning-level-1-c4835"></a>Compilerwarnung (Stufe 1) C4835

'Variable': die Initialisierung für exportierte Daten wird nicht ausgeführt werden, bis der ersten Ausführung von verwaltetem Code in die Host-Assembly

Wenn Sie Daten zwischen verwalteten Komponenten zugreifen zu können, empfiehlt es sich, dass Sie nicht native C++-Import verwenden / Mechanismen Export. Deklarieren Sie stattdessen die Datenmember innerhalb eines verwalteten Typs und verweisen auf die Metadaten mit `#using` auf dem Client. Weitere Information finden Sie unter [#using Directive (#using-Direktive)](../../preprocessor/hash-using-directive-cpp.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4835 generiert.

```
// C4835.cpp
// compile with: /W1 /clr /LD
int f() { return 1; }
int n = 9;

__declspec(dllexport) int m = f();   // C4835
__declspec(dllexport) int *p = &n;   // C4835
```

## <a name="example"></a>Beispiel

Im folgende Beispiel verwendet die Komponente, die im vorherigen Beispiel zeigt, dass der Wert der Variablen ist nicht wie erwartet.

```
// C4835_b.cpp
// compile with: /clr C4835.lib
#include <stdio.h>
__declspec(dllimport) int m;
__declspec(dllimport) int *p;

int main() {
   printf("%d\n", m);
   printf("%d\n", p);
}
```

```Output
0
268456008
```