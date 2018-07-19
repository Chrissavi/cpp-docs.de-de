---
title: -Bigobj (Erhöhen der Anzahl von Abschnitten in. OBJ-Datei) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /bigobj
dev_langs:
- C++
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df8bc379462bf5937f463b464ea2972472c49808
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369954"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (Erhöhen der Anzahl von Abschnitten in der OBJ-Datei)
**/ bigobj** erhöht die Anzahl von Abschnitten, die eine Objektdatei enthalten kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
/bigobj  
```  
  
## <a name="remarks"></a>Hinweise  
 In der Standardeinstellung kann eine Objektdatei bis zu 65.536 (2^16) adressierbare Abschnitte enthalten. Dabei spielt es keine Rolle, welche Zielplattform angegeben ist. **/ bigobj** erhöht diese Adressenkapazität auf 4.294.967.296 (2 ^ 32).  
  
 Von den meisten Modulen werden keine OBJ-Dateien erzeugt, die mehr als 65.536 Abschnitte enthalten. Für computergenerierten Code oder Code, in dem häufig Gebrauch von Vorlagenbibliotheken gemacht wird, sind allerdings unter Umständen OBJ-Dateien erforderlich, die mehr Abschnitte enthalten. **/ bigobj** für Projekte der universellen Windows-Plattform (UWP) standardmäßig aktiviert ist, da der computergenerierte XAML-Code viele Header enthält. Wenn Sie diese Option auf eine uwp-app-Projekt deaktivieren, werden Sie wahrscheinlich Compilerfehler C1128 auftritt.  
  
 Linker, die vor Visual C++ 2005 ausgeliefert OBJ-Dateien, die mit erzeugt wurden können nicht gelesen werden **/bigobj**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)