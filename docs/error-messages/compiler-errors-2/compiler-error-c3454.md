---
title: Compilerfehler C3454
ms.date: 11/04/2016
f1_keywords:
- C3454
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
ms.openlocfilehash: 1909dc772413c16d39271dc839a0ec0db206da03
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756681"
---
# <a name="compiler-error-c3454"></a>Compilerfehler C3454

[attribut] ist in der Klassendeklaration nicht zulässig

Es muss eine Klasse für es definiert werden, damit es ein Attribut sein kann.

Weitere Informationen finden Sie unter [attribute](../../windows/attributes/attribute.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3454 generiert:

```cpp
// C3454.cpp
// compile with: /clr /c
using namespace System;

[attribute]   // C3454
ref class Attr1;

[attribute]   // OK
ref class Attr2 {};
```
