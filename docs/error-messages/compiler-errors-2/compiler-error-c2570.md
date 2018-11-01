---
title: Compilerfehler C2570
ms.date: 11/04/2016
f1_keywords:
- C2570
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
ms.openlocfilehash: 447869b029df41219f71dcc633e9ae8a3934e0ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549577"
---
# <a name="compiler-error-c2570"></a>Compilerfehler C2570

'Bezeichner': Union kann keine Basisklasse haben.

Eine Union leitet sich von einer Klasse, Struktur oder Union. Dies ist nicht zulässig. Deklarieren Sie stattdessen den abgeleiteten Typ als eine Klasse oder Struktur.

Im folgende Beispiel wird die C2570 generiert:

```
// C2570.cpp
// compile with: /c
class base {};
union hasPubBase : public base {};   // C2570
union hasNoBase {};   // OK
```