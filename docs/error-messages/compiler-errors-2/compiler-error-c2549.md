---
title: Compilerfehler C2549 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2549
dev_langs:
- C++
helpviewer_keywords:
- C2549
ms.assetid: 29310094-54a3-4605-bc6d-a312a68daf5d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e32baf420a0bba66966b418b05642c6bcf96f180
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054551"
---
# <a name="compiler-error-c2549"></a>Compilerfehler C2549

benutzerdefinierte Konvertierung kann keinen Rückgabetyp angeben.

Im folgende Beispiel wird die C2549 generiert:

```
// C2549.cpp
// compile with: /c
class X {
public:
   int operator int() { return value; }   // C2549

   // try the following line instead
   // operator int() { return value; }
private:
   int value;
};
```