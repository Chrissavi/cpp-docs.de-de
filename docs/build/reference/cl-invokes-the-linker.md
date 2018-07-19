---
title: CL des Linkers | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- compiling source code [C++], without linking
- invoking linker from the compiler
- LINK tool [C++], invoking from CL compiler
- cl.exe compiler [C++], compiling without linking
- cl.exe compiler [C++], controlling linker
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc9c5c4815dc83b37d0b7971d5fd0f31db51e39e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371914"
---
# <a name="cl-invokes-the-linker"></a>CL: Starten des Linkers
CL Ruft den Linker automatisch nach dem Kompilieren, es sei denn, die/c-Option verwendet wird. CL wird an den Linker übergeben, die Namen der OBJ-Dateien, die während des Kompilierens erstellt und die Namen aller anderen Dateien, die in der Befehlszeile angegeben. Der Linker verwendet die in der Umgebungsvariablen LINK aufgeführten Optionen. / Link-Option können Sie die Optionen des Linkers in der CL-Befehlszeile angeben. Optionen, die die Option/Link folgen, überschreiben die in der Umgebungsvariablen LINK. Die Optionen in der folgenden Tabelle unterdrücken Sie verknüpfen.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|/c|Kompilieren ohne Verknüpfen|  
|/ E/EP, / P|Vorverarbeiten Sie ohne kompilieren und verknüpfen|  
|/Zg|Funktionsprototypen generieren|  
|/Zs|Überprüfen Sie syntax|  
  
 Weitere Details zu verknüpfen, finden Sie unter [Optionen des Linkers](../../build/reference/linker-options.md).  
  
## <a name="example"></a>Beispiel  
 Angenommen, Sie drei C-Quelldateien kompilieren: MAIN.c, MOD1.c und MOD2.c. Jede Datei enthält einen Aufruf an eine Funktion, die in einer anderen Datei definiert:  
  
-   MAIN.c ruft die Funktion `func1` in MOD1.c und die Funktion `func2` in MOD2.c auf.  
  
-   MOD1.c ruft die Standardbibliotheksfunktionen `printf_s` und `scanf_s`.  
  
-   MOD2.c ruft Grafikfunktionen `myline` und `mycircle`, die in der Bibliothek MYGRAPH.lib definiert werden.  
  
 Um dieses Programm zu erstellen, kompilieren Sie mit der folgenden Befehlszeile:  
  
```  
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib  
```  
  
 CL zuerst kompiliert die C-Quelldateien und erstellt die Objektdateien MAIN.obj, MOD1.obj und MOD2.obj. Der Compiler fügt den Namen der Standardbibliothek in jeder OBJ-Datei. Weitere Informationen finden Sie unter [Use Run-Time Library](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
 CL übergibt die Namen der die OBJ-Dateien zusammen mit dem Namen MYGRAPH.lib an den Linker. Der Linker löst externe Verweise wie folgt aus:  
  
1.  In den Verweis auf MAIN.obj `func1` wird mit der Definition in MOD1.obj; aufgelöst den Verweis auf `func2` wird mit der Definition in MOD2.obj aufgelöst.  
  
2.  In der Verweise auf MOD1.obj `printf_s` und `scanf_s` mit den Definitionen in die Bibliothek, die der Linker sucht mit dem Namen innerhalb von MOD1.obj aufgelöst werden.  
  
3.  In der Verweise auf MOD2.obj `myline` und `mycircle` mit den Definitionen aus MYGRAPH.lib aufgelöst werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)