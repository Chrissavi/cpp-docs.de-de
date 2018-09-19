---
title: Compilerfehler C3065 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3065
dev_langs:
- C++
helpviewer_keywords:
- C3065
ms.assetid: e7a0bc69-1c68-459e-a7c4-93c65609ff7c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35867da62dad9e399e4b4672f84478e4ea9688a5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104934"
---
# <a name="compiler-error-c3065"></a>Compilerfehler C3065

Die Eigenschaftendeklaration im Nichtklassenbereich ist nicht zulässig.

Der __declspec-Modifizierer einer [Eigenschaft](../../cpp/property-cpp.md) wurde außerhalb einer Klasse verwendet.  Eine Eigenschaft kann nur innerhalb einer Klasse deklariert werden.

Im folgenden Beispiel wird C3065 generiert:

```
// C3065.cpp
// compile with: /c
__declspec(property(get=get_i)) int i;   // C3065

class x {
public:
   __declspec(property(get=get_i)) int i;   // OK
};
```