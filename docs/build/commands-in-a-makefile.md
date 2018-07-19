---
title: Befehle in einem Makefile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands, makefiles
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99e1eb5b4800ff1046ca60d4d4874d386809e2e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366873"
---
# <a name="commands-in-a-makefile"></a>Befehle in einem Makefile
Eine Beschreibung Block oder mithilfe eines Rückschlusses Regel gibt einen Block von Befehlen, die ausgeführt werden, wenn die Abhängigkeit nicht mehr aktuell ist. NMAKE jeder Befehl vor der Ausführung angezeigt, es sei denn, / s, **. AUTOMATISCHE**, **! CMDSWITCHES**, oder @ verwendet wird. NMAKE sucht nach einer übereinstimmenden Rückschlussregel auf, wenn ein Beschreibungsblock von einem Befehlsblock nicht befolgt werden.  
  
 Ein Befehlsblock enthält eine oder mehrere Befehle, die jeweils in einer eigenen Zeile. Zwischen der Abhängigkeit oder einer Regel und Befehlsblock kann keine leere Zeile angezeigt. Allerdings können Sie eine Zeile, enthält nur Leerzeichen oder Tabstopps angezeigt; Diese Zeile wird als null-Befehl, und kein Fehler auftritt. Zwischen Befehlszeilen sind leere Zeilen zulässig.  
  
 Über die Befehlszeile beginnt mit Leerzeichen oder Tabstopps. Ein umgekehrten Schrägstrich (\) gefolgt von einem Zeilenumbruchzeichen wird als ein Leerzeichen im Befehl interpretiert. Verwenden Sie einen umgekehrten Schrägstrich am Ende einer Zeile, um einen Befehl auf die nächste Zeile zu fortfahren. NMAKE den umgekehrten Schrägstrich als Zeichenliteral interpretiert, wenn alle anderen Zeichen, z. B. ein Leerzeichen oder Tabstopp, den umgekehrten Schrägstrich folgt.  
  
 Ein Befehl vorangestellt wird, durch ein Semikolon (;) auf eine abhängigkeitsregel Befehlszeile oder mithilfe eines Rückschlusses angezeigt werden können, und zwar unabhängig davon, ob ein Befehlsblock folgt:  
  
```  
project.obj : project.c project.h ; cl /c project.c  
```  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
 [Befehlsmodifizierer](../build/command-modifiers.md)  
  
 [Syntax für Dateinamenteile](../build/filename-parts-syntax.md)  
  
 [Inlinedateien in einem makefile](../build/inline-files-in-a-makefile.md)  
  
## <a name="see-also"></a>Siehe auch  
 [NMAKE-Referenz](../build/nmake-reference.md)