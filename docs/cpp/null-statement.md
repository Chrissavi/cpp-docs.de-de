---
title: NULL-Anweisung
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
ms.openlocfilehash: 2797937b184bebe0e29f8e5eae428f601c824811
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245179"
---
# <a name="null-statement"></a>NULL-Anweisung

Die "null-Anweisung" ist eine Ausdrucksanweisung, bei der *Ausdruck* fehlt. Dies ist nützlich, wenn in der Syntax der Sprache eine Anweisung erwartet wird, jedoch keine Ausdrucksauswertung. Die Anweisung besteht aus einem Semikolon.

NULL-Anweisungen werden normalerweise als Platzhalter in Iterationsanweisungen oder als Anweisungen verwendet, um Bezeichnungen am Ende von Verbundanweisungen oder Funktionen zu platzieren.

Das folgende Codefragment zeigt, wie Sie eine Zeichenfolge zu einer anderen kopieren und die NULL-Anweisung integrieren:

```cpp
// null_statement.cpp
char *myStrCpy( char *Dest, const char *Source )
{
    char *DestStart = Dest;

    // Assign value pointed to by Source to
    // Dest until the end-of-string 0 is
    // encountered.
    while( *Dest++ = *Source++ )
        ;   // Null statement.

    return DestStart;
}

int main()
{
}
```

## <a name="see-also"></a>Siehe auch

[Ausdrucksanweisung](../cpp/expression-statement.md)