---
title: Compilerfehler C2082 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2082
dev_langs:
- C++
helpviewer_keywords:
- C2082
ms.assetid: 87a6d442-157c-46e8-9bff-8388f8338ae0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6939bf628072fc1c5c4e72c0012e4a190d43864
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082403"
---
# <a name="compiler-error-c2082"></a>Compilerfehler C2082

Neudefinition des formalen Parameters "Bezeichner"

Ein formaler Parameter einer Funktion wird im Funktionsrumpf erneut deklariert. Um den Fehler zu beheben, entfernen Sie die Neudefinition.

Im folgenden Beispiel wird C2082 generiert.

```
// C2082.cpp
void func(int i) {
   int i;   // C2082
   int ii;   // OK
}
```