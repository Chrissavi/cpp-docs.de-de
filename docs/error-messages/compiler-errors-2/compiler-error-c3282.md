---
title: Compilerfehler C3282 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3282
dev_langs:
- C++
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da6d4fd30d109f78949a3ec53e0d46d6a9de7dc9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056897"
---
# <a name="compiler-error-c3282"></a>Compilerfehler C3282

generischer Parameter, die Listen können nur verwendet werden, auf verwalteten oder WinRTclasses, Strukturen oder -Funktionen

Eine generische Parameterliste wurde falsch verwendet.  Weitere Informationen finden Sie unter [Generika](../../windows/generics-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3282 generiert und gezeigt, wie Sie diesen Fehler beheben.

```
// C3282.cpp
// compile with: /clr /c
generic <typename T> int x;   // C3282

ref struct GC0 {
   generic <typename T> int x;   // C3282
};

// OK
generic <typename T>
ref class M {};
```