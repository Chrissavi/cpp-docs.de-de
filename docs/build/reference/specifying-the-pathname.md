---
title: Festlegen des Pfadnamens | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2dd121909fbe0aa2f9305b7bd5779b995a69719
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375661"
---
# <a name="specifying-the-pathname"></a>Festlegen des Pfadnamens
Akzeptiert jede Option Ausgabedateioptionen eine *Pathname* Argument, das einen Speicherort und einen Namen für die Ausgabedatei angeben kann. Das Argument kann einen Laufwerksnamen Verzeichnis und Dateinamen enthalten. Es darf kein Leerzeichen zwischen der Option und dem Argument.  
  
 Wenn *Pathname* enthält ein Dateiname ohne Erweiterung, generiert der Compiler der Ausgabe eine standarderweiterung. Wenn *Pathname* enthält ein Verzeichnis, aber kein Dateiname erstellt der Compiler eine Datei mit einem Standardnamen im angegebenen Verzeichnis. Der Standardname basiert auf der Basisname der Quelldatei und die standarderweiterung basierend auf dem Typ der Ausgabedatei. Wenn Sie die Einstellung *Pathname* vollständig, erstellt der Compiler eine Datei mit einem Standardnamen in ein Standardverzeichnis.  
  
 Alternativ können Sie die *Pathname* Argument kann einen Gerätenamen (AUX, CON, PRN oder NUL) anstatt einem Dateinamen sein. Verwenden Sie ein Leerzeichen zwischen der Option und der Name des Laufwerks oder einen Doppelpunkt nicht als Teil der Name des Mediums an.  
  
|Gerätename|Bedeutung|  
|-----------------|----------------|  
|AUX|Externes Gerät|  
|CON|Konsole|  
|PRN|Drucker|  
|NUL|NULL-Gerät (keine Datei erstellt)|  
  
## <a name="example"></a>Beispiel  
 Die folgende Befehlszeile sendet eine Zuordnungsdatei an den Drucker an:  
  
```  
CL /FmPRN HELLO.CPP  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabedatei (/ F) Optionen](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)