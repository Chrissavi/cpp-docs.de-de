---
title: LINK-Ausgabe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- mapfiles [C++]
- ILK files
- output files [C++], linker
- files [C++], LINK
- .ilk files
- LINK tool [C++], output
- import libraries [C++], creating
- executable files [C++], as linker output
- mapfiles [C++], LINK output
- linker [C++], output files
- DLLs [C++], as linker output
- LINK tool [C++], mapfile
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae68de707ece35825a32a404ce14032d4bbd3141
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376727"
---
# <a name="link-output"></a>LINK-Ausgabe
Link-Ausgabe enthält .exe-Dateien, DLLs, Zuordnungsdateien und Nachrichten.  
  
##  <a name="_core_output_files"></a> Ausgabedateien  
 Die standardmäßige Ausgabedatei aus dem LINK ist eine .exe-Datei. Wenn die [/DLL](../../build/reference/dll-build-a-dll.md) angegeben wird, erstellt LINK eine DLL-Datei. Sie können steuern, den Namen der Ausgabedatei mit dem [Ausgabedateiname (/ OUT)](../../build/reference/out-output-file-name.md) Option.  
  
 Im inkrementellen Modus erstellt LINK eine ILK-Datei zum Speichern von Statusinformationen für später inkrementelle Builds des Programms. Ausführliche Informationen zu ILK-Dateien finden Sie unter [ILK-Dateien](../../build/reference/dot-ilk-files-as-linker-input.md). Weitere Informationen zu inkrementellen verknüpfen, finden Sie unter der [inkrementell verknüpfen (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) Option.  
  
 Wenn der LINK erstellt ein Programm, das enthält Exporte (in der Regel eine DLL), wird auch eine LIB-Datei erstellt, es sei denn, eine .exp-Datei im Build verwendet wurde. Sie können den Dateinamen der Importbibliothek mit steuern die [IMPLIB](../../build/reference/implib-name-import-library.md) Option.  
  
 Wenn die [Zuordnungsdatei generieren (/ MAP)](../../build/reference/map-generate-mapfile.md) angegeben wird, LINK erstellt eine Zuordnungsdatei.  
  
 Wenn die [Debuginfo generieren (/ DEBUG)](../../build/reference/debug-generate-debug-info.md) angegeben wird, LINK erstellt eine PDB-Datei für die Debuginformationen für das Programm enthalten.  
  
##  <a name="_core_other_output"></a> Andere Ausgabe  
 Bei der Eingabe `link` ohne alle anderen Befehlszeileneingabe LINK zeigt eine nutzungsanweisung an, die die Optionen zusammengefasst sind.  
  
 LINK in einer Meldung Copyright- und und Befehlsdatei Eingabe wiederholt, es sei denn, die [Startbanner unterdrücken (/ NOLOGO)](../../build/reference/nologo-suppress-startup-banner-linker.md) Option verwendet wird.  
  
 Sie können die [Drucken von Statusmeldungen (/ VERBOSE)](../../build/reference/verbose-print-progress-messages.md) Option aus, um zusätzliche Details zum Build anzuzeigen.  
  
 LINK Probleme, Fehler und Warnungen Nachrichten in der Form LNK*Nnnn*. Dieser Fehlerpräfix und einen Bereich von Zahlen werden auch von LIB, DUMPBIN und EDITBIN verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)