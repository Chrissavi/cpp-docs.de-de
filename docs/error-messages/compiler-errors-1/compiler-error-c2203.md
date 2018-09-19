---
title: Compilerfehler C2203 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2203
dev_langs:
- C++
helpviewer_keywords:
- C2203
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6db497a7967e0cefc16ecb6e5a71874f86179b29
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053764"
---
# <a name="compiler-error-c2203"></a>Compilerfehler C2203

Löschen von Grenzen für das ein Array von Operator kann nicht angegeben werden können

Mit der **/Za** (ANSI) auswählen, die `delete` delete-Operator kann ein ganzes Array jedoch keine Komponenten oder bestimmte Elemente des Arrays.

Im folgende Beispiel wird die C2203 generiert:

```
// C2203.cpp
// compile with: /Za
int main() {
   int *ar = new int[10];
   delete [4] ar;   // C2203
   // try the following line instead
   // delete [] ar;
}
```