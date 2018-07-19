---
title: LINK-Eingabedateien | Microsoft Docs
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
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d61a24916c3b56cf666a85483414f86753f7f59
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374826"
---
# <a name="link-input-files"></a>LINK-Eingabedateien
Sie bieten den Linker mit Dateien, die Objekte, Import- und Standardbibliotheken, Ressourcen, Moduldefinitionen und Eingabe-Befehl enthalten. LINK verwendet Dateierweiterungen keine Annahmen zum Inhalt einer Datei vornehmen. Stattdessen untersucht LINK jede Eingabedatei, um festzustellen, welche Art von Datei vorliegt.  
  
 Objektdateien in der Befehlszeile werden in der Reihenfolge verarbeitet, die sie in der Befehlszeile angezeigt werden. Bibliotheken werden in Reihenfolge durchsucht, über die Befehlszeile, mit der folgenden Einschränkung: Symbole, die nicht aufgelöste beim Importieren einer Objektdatei aus einer Bibliothek in diese Bibliothek zuerst gesucht, und klicken Sie dann die folgenden Bibliotheken aus der Befehlszeile und [DEFAULTLIB (Default Bibliothek angeben)](../../build/reference/defaultlib-specify-default-library.md) Richtlinien, und wählen Sie dann alle Bibliotheken am Anfang der Befehlszeile.  
  
> [!NOTE]
>  LINK akzeptiert ein Semikolon (oder jedes andere Zeichen) nicht mehr als Anfang eines Kommentars in der Antwort und Order-Dateien. Semikolons sind nur als Anfang eines Kommentars in Moduldefinitionsdateien (.def) erkannt.  
  
 Die folgenden Typen von Eingabedateien Replikationsverkehr:  
  
-   [OBJ-Dateien](../../build/reference/dot-obj-files-as-linker-input.md)  
  
-   [NETMODULE-Dateien](../../build/reference/netmodule-files-as-linker-input.md)  
  
-   [LIB-Dateien](../../build/reference/dot-lib-files-as-linker-input.md)  
  
-   [EXP-Dateien](../../build/reference/dot-exp-files-as-linker-input.md)  
  
-   [DEF-Dateien](../../build/reference/dot-def-files-as-linker-input.md)  
  
-   [PDB-Dateien](../../build/reference/dot-pdb-files-as-linker-input.md)  
  
-   [.RES-Dateien](../../build/reference/dot-res-files-as-linker-input.md)  
  
-   [.exe-Dateien](../../build/reference/dot-exe-files-as-linker-input.md)  
  
-   [TXT-Dateien](../../build/reference/dot-txt-files-as-linker-input.md)  
  
-   [.ILK-Dateien](../../build/reference/dot-ilk-files-as-linker-input.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)