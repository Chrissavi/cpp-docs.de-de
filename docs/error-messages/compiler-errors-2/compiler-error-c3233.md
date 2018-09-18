---
title: Compilerfehler C3233 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3233
dev_langs:
- C++
helpviewer_keywords:
- C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87a5494e4894077d6f9dc61d920ed42db9872988
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035447"
---
# <a name="compiler-error-c3233"></a>Compilerfehler C3233

„type“: Der generische Typparameter wird bereits eingeschränkt.

Es ist nicht zulässig, einen generischen Parameter in mehr als einer `where` -Klausel einzuschränken.

Im folgenden Beispiel wird C3233 generiert:

```
// C3233.cpp
// compile with: /clr /LD

interface struct C {};
interface struct D {};

generic <class T>
where T : C
where T : D
ref class E {};   // C3233
```