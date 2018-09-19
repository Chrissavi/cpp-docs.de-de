---
title: Compilerfehler C2370 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2370
dev_langs:
- C++
helpviewer_keywords:
- C2370
ms.assetid: 03403e8f-f393-47c4-bd25-5c1c7ea7d5cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa760612699cf71b9394011b0883531eef4f5fb8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102403"
---
# <a name="compiler-error-c2370"></a>Compilerfehler C2370

"Bezeichner": Neudefinition; unterschiedliche Speicherklassen

Der Bezeichner wurde bereits mit einer anderen Speicherklasse deklariert.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2370 generiert:

```
// C2370.cpp
// compile with: /Za /c
extern int i;
static int i;   // C2370
int i;   // OK
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2370 generiert:

```
// C2370b.cpp
#define Thread __declspec( thread )
extern int tls_i;
int Thread tls_i;   // C2370 declaration and the definition differ
int tls_i;   // OK
```