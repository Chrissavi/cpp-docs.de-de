---
title: Automatische Variablen (Funktions Gültigkeitsbereich)
ms.date: 04/22/2019
helpviewer_keywords:
- automatic variables
- variables, automatic
- functions [C++], scope
- scope, declared within functions
ms.assetid: 6e1a14c2-1fb0-4937-8628-8d963cc35ed4
ms.openlocfilehash: ec01f280c9de314ce670cae590c9a6917e9c0f07
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197878"
---
# <a name="automatic-function-scope-variables"></a>Automatische Variablen (Funktions Gültigkeitsbereich)

Eine Variable, die innerhalb einer Funktion deklariert wird, kann nur innerhalb des Gültigkeits Bereichs dieser Funktion verwendet werden.

```cpp
// LNK2019_AV.cpp
// compile with: /c
void test(void);

static int lnktest3 = 3;
int lnktest4 = 4;

int main() {
   static int lnktest1 = 1;
   int lnktest2 = 2;
   test();
}
```

Und dann

```cpp
// LNK2019_AV_2.cpp
// compile with: LNK2019_AV.cpp
// LNK2019 expected
extern int lnktest1;
extern int lnktest2;
extern int lnktest3;
extern int lnktest4;

void test(void) {
   int i = 0;
   i = lnktest1;
   i = lnktest2;
   i = lnktest3;
   i = lnktest4;   // OK
}
```

## <a name="see-also"></a>Weitere Informationen

[Linker-Tools-Fehler LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
