---
title: Compilerfehler C3457 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3457
dev_langs:
- C++
helpviewer_keywords:
- C3457
ms.assetid: 5c1e366a-fa75-4cca-b9a3-86d4ebe4090e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 794c3deb042c383f3802ce32f3f7c4580f6061a6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021498"
---
# <a name="compiler-error-c3457"></a>Compilerfehler C3457

'attribut': Das Attribut unterstützt keine unbenannten Argumente.

Quellanmerkungsattribute unterstützen im Gegensatz zu benutzerdefinierten CLR-Attributen oder Compilerattributen nur benannte Argumente.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3457 generiert:

```
#include "SourceAnnotations.h"
[vc_attributes::Post( 1 )] int f();   // C3457
[vc_attributes::Post( Valid=vc_attributes::Yes )] int f2();   // OK
```