---
title: Compilerwarnung (Stufe 1) C4216 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4216
dev_langs:
- C++
helpviewer_keywords:
- C4216
ms.assetid: 211079dc-59d0-42a7-801c-2ddab21d7232
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6f9e53115b7b162fa4c36ad9a3fa227de777bf8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042987"
---
# <a name="compiler-warning-level-1-c4216"></a>Compilerwarnung (Stufe 1) C4216

nicht dem Standard entsprechende Erweiterung: float long

Die Standard-Microsoft-Erweiterungen (/ Ze) behandeln **long float** als **doppelte**. ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) nicht. Verwendung **doppelte** um die Kompatibilität aufrechtzuerhalten. Im folgende Beispiel wird die C4216 generiert:

```
// C4216.cpp
// compile with: /W1
float long a;   // C4216

// use the line below to resolve the warning
// double a;

int main() {
}
```