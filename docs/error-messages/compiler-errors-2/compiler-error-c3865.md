---
title: Compilerfehler C3865 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3865
dev_langs:
- C++
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8fd5c83d922601ca4cdffe0f3772723b31e630b6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090840"
---
# <a name="compiler-error-c3865"></a>Compilerfehler C3865

'Aufrufkonvention': kann nur für systemeigene Memberfunktionen verwendet werden

Eine Aufrufkonvention wurde verwendet, auf eine Funktion, die entweder eine globale Funktion oder in einer verwalteten Memberfunktion. Die Aufrufkonvention kann nur in einer systemeigenen (nicht verwaltete) Memberfunktion verwendet werden.

Weitere Informationen finden Sie unter [Aufrufkonventionen](../../cpp/calling-conventions.md).

Im folgende Beispiel wird die C3865 generiert:

```
// C3865.cpp
// compile with: /clr
// processor: x86
void __thiscall Func(){}   // C3865

// OK
struct MyType {
   void __thiscall Func(){}
};
```