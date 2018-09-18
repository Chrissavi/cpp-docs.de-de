---
title: Compilerfehler C2110 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2110
dev_langs:
- C++
helpviewer_keywords:
- C2110
ms.assetid: 48fd76ed-90d6-4a60-9c7b-f6ce9355b4ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 749e96748698da9b2c08e805d68e0c2ba333d22f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074902"
---
# <a name="compiler-error-c2110"></a>Compilerfehler C2110

„+“: Zwei Zeiger können nicht addiert werden.

Es wurde versucht, zwei Zeigerwerte mit dem Plus-Operator ( `+` ) zu addieren.

Im folgenden Beispiel wird C2110 generiert:

```
// C2110.cpp
int main() {
   int a = 0;
   int *pa;
   int *pb;
   a = pa + pb;   // C2110
}
```