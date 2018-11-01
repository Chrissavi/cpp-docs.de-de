---
title: Compilerwarnung (Stufe 1) C4789
ms.date: 11/04/2016
f1_keywords:
- C4789
helpviewer_keywords:
- C4789
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
ms.openlocfilehash: f489915f07eefd0909cbcd806a590f93f674c258
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677395"
---
# <a name="compiler-warning-level-1-c4789"></a>Compilerwarnung (Stufe 1) C4789

> Puffer "*Bezeichner*' Größe *N* Bytes werden überlaufen; *M* Bytes werden ab Offset geschrieben *L*

## <a name="remarks"></a>Hinweise

Warnt vor einem Pufferüberlauf, wenn bestimmte CRT-Funktionen (C Run-Time) verwendet, Parameter übergeben und Zuweisungen ausgeführt werden, sodass die Datengrößen zur Kompilierzeit bekannt sind. Diese Warnung gilt für Situationen, in denen die typische Datengrößen-Konflikterkennung umgangen wird.

Die Warnung wird angezeigt, wenn Daten, deren Länge zur Kompilierzeit bekannt ist, kopiert und in einen Datenblock eingefügt werden, dessen Größe zur Kompilierzeit bekannt ist und für die Daten zu klein sein wird. Die Kopie muss mit dem systeminternen Formular einer der folgenden CRT-Funktionen erstellt werden:

- [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)

- [memset](../../c-runtime-library/reference/memset-wmemset.md)

- [Memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md), [Wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)

Die Warnung wird auch angezeigt, wenn ein Parameterdatentyp mithilfe einer Umwandlung falsch zugeordnet wird. Anschließend wird eine Kopierzuweisung über einen Ivalue-Verweis versucht.

Visual C++ kann diese Warnung für einen Codepfad generieren, der nicht ausgeführt wird. Sie können die Warnung mithilfe von `#pragma` vorübergehend deaktivieren, wie im folgenden Beispiel gezeigt:

```cpp
#pragma(push)
#pragma warning ( disable : 4789 )
// unused code that generates compiler warning C4789`
#pragma(pop)
```

Dadurch wird verhindert, dass Visual C++ die Warnung für diesen bestimmten Codeblock generiert. `#pragma(push)` behält den vorhandenen Zustand bei, bevor dieser von `#pragma warning(disable: 4789)` geändert wird. `#pragma(pop)` stellt den gepushten Zustand wieder her und entfernt die Auswirkungen der `#pragma warning(disable:4789)`. Weitere Informationen zu C++-präprozessoranweisung `#pragma`, finden Sie unter [Warnung](../../preprocessor/warning.md) und [Pragma-Direktiven und das __Pragma-Schlüsselwort](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4789 generiert.

```cpp
// C4789.cpp
// compile with: /Oi /W1 /c
#include <string.h>
#include <stdio.h>

int main()
{
    char a[20];
    strcpy(a, "0000000000000000000000000\n");   // C4789

    char buf2[20];
    memset(buf2, 'a', 21);   // C4789

    char c;
    wchar_t w = 0;
    memcpy(&c, &w, sizeof(wchar_t));
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird außerdem C4789 generiert.

```cpp
// C4789b.cpp
// compile with: /W1 /O2 /c
// processor: x86
short G;

void main()
{
   int * p = (int *)&G;
   *p = 3;   // C4789 - writes an int through a pointer to short
}
```