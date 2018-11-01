---
title: Kommentare in einem Makefile
ms.date: 11/04/2016
helpviewer_keywords:
- makefiles, comments
ms.assetid: 76fd9e3d-5966-47f4-a091-c9e80b232b49
ms.openlocfilehash: 91fb9001378973c86ffaaf7fd841e3c679444ef9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625848"
---
# <a name="comments-in-a-makefile"></a>Kommentare in einem Makefile

Stellen Sie einen Kommentar mit einem Nummernzeichen voran (##). NMAKE: ignoriert Text aus dem Nummernzeichen auf das nächste neue Zeilenumbruchzeichen. Beispiele:

```
# Comment on line by itself
OPTIONS = /MAP  # Comment on macro definition line

all.exe : one.obj two.obj  # Comment on dependency line
    link one.obj two.obj
# Comment in commands block
#   copy *.obj \objects  # Command turned into comment
    copy one.exe \release

.obj.exe:  # Comment on inference rule line
    link $<

my.exe : my.obj ; link my.obj  # Err: cannot comment this
# Error: # must be the first character
.obj.exe: ; link $<  # Error: cannot comment this
```

Um ein literalen Nummernzeichen anzugeben, fügen sie davor ein Caretzeichen (**^**) wie folgt:

```
DEF = ^#define  #Macro for a C preprocessing directive
```

## <a name="see-also"></a>Siehe auch

[Inhalt eines Makefiles](../build/contents-of-a-makefile.md)