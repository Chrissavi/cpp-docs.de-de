---
title: Compilerwarnung (Stufe 1) C4549 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4549
dev_langs:
- C++
helpviewer_keywords:
- C4549
ms.assetid: 81a07676-625b-4f58-9b0c-3ee22830b04a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b36a7516c244c49e56d7070684f5914407d625c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027361"
---
# <a name="compiler-warning-level-1-c4549"></a>Compilerwarnung (Stufe 1) C4549

'Operator': Operator vor dem Komma keine Auswirkungen hat; Wollten Sie "Operator"?

Der Compiler hat ein falsch formatiertes Kommaausdruck.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Im folgende Beispiel wird die C4549 generiert:

```
// C4549.cpp
// compile with: /W1
#pragma warning (default : 4549)

int main() {
   int i = 0, k = 0;

   if ( i == 0, k )   // C4549
   // try the following line instead
   // if ( i == 0 )
      i++;
}
```