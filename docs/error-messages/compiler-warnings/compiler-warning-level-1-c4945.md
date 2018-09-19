---
title: Compilerwarnung (Stufe 1) C4945 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4945
dev_langs:
- C++
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48797667c880bcd441065da3651adabdb955b52b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027517"
---
# <a name="compiler-warning-level-1-c4945"></a>Compilerwarnung (Stufe 1) C4945

'Symbol': Symbol aus "assembly2" kann nicht importiert: 'Symbol' wurde bereits von einer anderen Assembly 'assembly1' importiert

Ein Symbol aus einer referenzierten Assembly importiert wurden, aber das Symbol bereits aus einer anderen referenzierten Assembly importiert wurden. Entweder eine der Assemblys verweisen, und nicht der Symbolname in eine der Assemblys geändert.

In den folgenden Beispielen wird C4945 generiert:

```
// C4945a.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

Und dann

```
// C4945b.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

Und dann

```
// C4945c.cpp
// compile with: /clr /LD /W1
#using "C4945a.dll"
#using "C4945b.dll"   // C4945
```