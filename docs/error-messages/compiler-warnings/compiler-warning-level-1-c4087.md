---
title: Compilerwarnung (Stufe 1) C4087
ms.date: 11/04/2016
f1_keywords:
- C4087
helpviewer_keywords:
- C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
ms.openlocfilehash: 84d24d95053b962c1776dc18576e4ed236b63469
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363868"
---
# <a name="compiler-warning-level-1-c4087"></a>Compilerwarnung (Stufe 1) C4087

"Funktion": Mit "void"-Parameterliste deklariert

Die Funktionsdeklaration hat keine formalen Parameter, aber der Funktionsaufruf hat tatsächlich Parameter. Zusätzliche Parameter werden entsprechend der Aufrufkonvention der Funktion übergeben.

Diese Warnung gilt für den C-Compiler.

## <a name="example"></a>Beispiel

```
// C4087.c
// compile with: /W1
int f1( void ) {
}

int main() {
   f1( 10 );   // C4087
}
```