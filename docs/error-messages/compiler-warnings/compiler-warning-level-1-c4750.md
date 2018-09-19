---
title: Compilerwarnung (Stufe 1) C4750 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4750
dev_langs:
- C++
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c77c46daf30b6e0238345d9b2be3c6c5362c192
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026620"
---
# <a name="compiler-warning-level-1-c4750"></a>Compilerwarnung (Stufe 1) C4750

'Bezeichner': Funktion mit „_alloca()“ „inline“ in einer Schleife

Die „Bezeichner“-Funktion erzwingt eine Inlineerweiterung der [_alloca](../../c-runtime-library/reference/alloca.md) -Funktion in einer Schleife, die bei der Ausführung der Schleife einen Stapelüberlauf verursachen kann.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Stellen Sie sicher, dass die „Bezeichner“-Funktion nicht mit dem [__forceinline](../../cpp/inline-functions-cpp.md) -Spezifizierer geändert wird.

1. Stellen Sie sicher, dass die „Bezeichner“-Funktion keine [_alloca](../../c-runtime-library/reference/alloca.md) -Funktion enthält, die sich in einer Schleife befindet.

1. Geben Sie nicht die Kompilierungsschalter [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/Ox](../../build/reference/ox-full-optimization.md)oder [/Og](../../build/reference/og-global-optimizations.md) an.

1. Positionieren Sie die [_alloca](../../c-runtime-library/reference/alloca.md) -Funktion in einer [try-except-Anweisung](../../cpp/try-except-statement.md) , die einen Stapelüberlauf abfängt.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird `MyFunction` in einer Schleife aufgerufen und `MyFunction` ruft die `_alloca` -Funktion auf. Der `__forceinline` -Modifizierer bewirkt die Inlineerweiterung der `_alloca` -Funktion.

```
// c4750.cpp
// compile with: /O2 /W1 /c
#include <intrin.h>

char * volatile newstr;

__forceinline void myFunction(void) // C4750 warning
{
// The _alloca function does not require a __try/__except
// block because the example uses compiler option /c.
    newstr = (char * volatile) _alloca(1000);
}

int main(void)
{
    for (int i=0; i<50000; i++)
       myFunction();
    return 0;
}
```

## <a name="see-also"></a>Siehe auch

[_alloca](../../c-runtime-library/reference/alloca.md)