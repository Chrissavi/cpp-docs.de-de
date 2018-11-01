---
title: Compilerfehler C2198
ms.date: 11/04/2016
f1_keywords:
- C2198
helpviewer_keywords:
- C2198
ms.assetid: 638a845c-9d7f-4115-a9aa-d72455605668
ms.openlocfilehash: a7fbc5dc6dc91dab5bfea3a81c8d5c045e485161
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651749"
---
# <a name="compiler-error-c2198"></a>Compilerfehler C2198

"Funktion": Nicht genügend Argumente für Aufruf.

Der Compiler hat nicht genügend Parameter für einen Aufruf der Funktion oder eine falsche Funktionsdeklaration gefunden.

Im folgenden Beispiel wird C2198 generiert:

```
// C2198.c
// compile with: /c
void func( int, int );
int main() {
   func( 1 );   // C2198 only one actual parameter
   func( 1, 1 );   // OK
}
```