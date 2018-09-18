---
title: Compilerwarnung (Stufe 1) C4810 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4810
dev_langs:
- C++
helpviewer_keywords:
- C4810
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ae5fd5adf661e40faf7c4a54068660401ea8d7a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030156"
---
# <a name="compiler-warning-level-1-c4810"></a>Compilerwarnung (Stufe 1) C4810

Wert von pragma pack(show) == n

Diese Warnung wird ausgegeben, wenn Sie die **show** -Option des [pack](../../preprocessor/pack.md) -Pragmas verwenden. *n* ist der aktuelle pack-Wert.

Der folgende Code zeigt z. B. die Funktionsweise der C4810-Warnung mit dem pack-Pragma:

```
// C4810.cpp
// compile with: /W1 /LD
// C4810 expected
#pragma pack(show)
#pragma pack(4)
#pragma pack(show)
```