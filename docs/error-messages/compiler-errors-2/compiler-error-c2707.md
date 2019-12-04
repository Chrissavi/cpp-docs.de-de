---
title: Compilerfehler C2707
ms.date: 11/04/2016
f1_keywords:
- C2707
helpviewer_keywords:
- C2707
ms.assetid: 3deaf45c-74da-4c9d-acc6-b82412720b74
ms.openlocfilehash: e29812563ef1d4d7f6612ea2516f2f6327e90e1b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760438"
---
# <a name="compiler-error-c2707"></a>Compilerfehler C2707

"Bezeichner": Ungültiger Kontext für intrinsische Funktion

Strukturierte systeminterne Ausnahme Behandlungs Funktionen sind in bestimmten Kontexten ungültig:

- `_exception_code()` außerhalb eines Ausnahme Filters oder `__except` Blocks

- `_exception_info()` außerhalb eines Ausnahme Filters

- `_abnormal_termination()` außerhalb eines `__finally` Blocks

Um den Fehler zu beheben, stellen Sie sicher, dass die systeminternen Funktionen für die Ausnahmebehandlung im entsprechenden Kontext abgelegt werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2707 generiert.

```cpp
// C2707.cpp
#include <windows.h>
#include <stdio.h>

LONG MyFilter(LONG excode)
{
    return (excode == EXCEPTION_ACCESS_VIOLATION ?
        EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);   // OK
}

LONG func(void)
{
    int x, y;
    return(GetExceptionCode() == EXCEPTION_ACCESS_VIOLATION ?  // C2707
             EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);

    __try
    {
        y = 0;
        x = 4 / y;
        return 0;
     }

    __except(MyFilter(GetExceptionCode()))
    {
        return(GetExceptionCode() == EXCEPTION_ACCESS_VIOLATION ? // ok
               EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);
    }
}

int main()
{
    __try
    {
        func();
    } __except(EXCEPTION_EXECUTE_HANDLER)
    {
        printf_s("Caught exception\n");
    }
}
```
