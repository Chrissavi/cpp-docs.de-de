---
title: Compilerfehler C2735 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2735
dev_langs:
- C++
helpviewer_keywords:
- C2735
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 732b75c8988f879af230e0513a751b8cd9c4ae67
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093120"
---
# <a name="compiler-error-c2735"></a>Compilerfehler C2735

' Schlüsselwort ' ist in Typangabe eines formalen Parameters nicht zulässig.

Das Schlüsselwort ist in diesem Kontext ungültig.

Im folgende Beispiel wird die C2735 generiert:

```
// C2735.cpp
void f(inline int){}   // C2735
```