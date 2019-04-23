---
title: Compilerfehler C3292
ms.date: 11/04/2016
f1_keywords:
- C3292
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
ms.openlocfilehash: a68d3e922532480063fe4c294e40f453885743e8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777002"
---
# <a name="compiler-error-c3292"></a>Compilerfehler C3292

Der cli-Namespace kann nicht erneut geöffnet werden.

Der cli-Namespace kann nicht in Ihrem Code deklariert werden.  Weitere Informationen finden Sie unter [Platform-, Default- und Cli-Namespaces](../../extensions/platform-default-and-cli-namespaces-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3292 generiert:

```
// C3292.cpp
// compile with: /clr /c
namespace cli {};   // C3292
```