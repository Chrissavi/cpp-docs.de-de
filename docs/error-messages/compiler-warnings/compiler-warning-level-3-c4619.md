---
title: Compilerwarnung (Stufe 3) C4619
ms.date: 11/04/2016
f1_keywords:
- C4619
helpviewer_keywords:
- C4619
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
ms.openlocfilehash: 00647e7dafe18ffad2a059b960ebed0a0f4a5d36
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580260"
---
# <a name="compiler-warning-level-3-c4619"></a>Compilerwarnung (Stufe 3) C4619

\#Pragma-Warnung: Keine Warnungsnummer 'Number' vorhanden ist

Es wurde versucht, um eine Warnung zu deaktivieren, die nicht vorhanden ist.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgende Beispiel wird die C4619 generiert:

```
// C4619.cpp
// compile with: /W3 /c
#pragma warning(default : 4619)
#pragma warning(disable : 4354)   // C4619, C4354 does not exist
```