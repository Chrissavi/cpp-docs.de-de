---
title: Compilerfehler C3233
ms.date: 11/04/2016
f1_keywords:
- C3233
helpviewer_keywords:
- C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
ms.openlocfilehash: 110d1ef84ca2f558f597afadadbede61a89da20c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751104"
---
# <a name="compiler-error-c3233"></a>Compilerfehler C3233

„type“: Der generische Typparameter wird bereits eingeschränkt.

Es ist nicht zulässig, einen generischen Parameter in mehr als einer `where` -Klausel einzuschränken.

Im folgenden Beispiel wird C3233 generiert:

```cpp
// C3233.cpp
// compile with: /clr /LD

interface struct C {};
interface struct D {};

generic <class T>
where T : C
where T : D
ref class E {};   // C3233
```
