---
title: Compilerfehler C2158 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2158
dev_langs:
- C++
helpviewer_keywords:
- C2158
ms.assetid: 39028899-e95c-4809-8e65-6111118641ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e853e5915756b71b96e50374224b003eca412d99
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034901"
---
# <a name="compiler-error-c2158"></a>Compilerfehler C2158

"Typ": Die #pragma make_public-Direktive wird derzeit nur für systemeigene Nichtvorlagentypen unterstützt

Das Pragma [make_public](../../preprocessor/make-public.md) kann nur auf systemeigene Nichtvorlagentypen angewendet werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2158 generiert.

```
// C2158.cpp
// compile with: /clr /c
ref class A {};
#pragma make_public(A)   // C2158

template< typename T >
class B {};
#pragma make_public(B)   // C2158
#pragma make_public(B<int>)   // C2158

void C () {}
#pragma make_public(C)   // C2158

class D {};
#pragma make_public(D)   // OK
```