---
title: -Gw (optimieren globaler Daten) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Gw
dev_langs:
- C++
helpviewer_keywords:
- /Gw compiler option [C++]
- -Gw compiler option [C++]
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 173b9499477ee02cbb1f052d3d85445a9ffb7732
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376438"
---
# <a name="gw-optimize-global-data"></a>/Gw (Optimieren globaler Daten)
Fasst globale Daten zur Optimierung in COMDAT-Abschnitten zusammen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Gw[-]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **/GW** Option veranlasst den Compiler, fasst globale Daten in einzelnen COMDAT-Abschnitten. Standardmäßig **/GW** ist deaktiviert und muss explizit aktiviert werden. Verwenden Sie zur expliziten Deaktivierung, **/Gw-**. Wenn beide **/GW** und [/GL](../../build/reference/gl-whole-program-optimization.md) sind aktiviert, verwendet der Linker Optimierung des gesamten Programms um COMDAT-Abschnitte über mehrere Objektdateien hinweg zu vergleichen, wobei nicht referenzierte globale Daten ausgeschlossen oder zusammenführen Identische schreibgeschützte globale Daten. Dies kann die Größe der resultierenden binären ausführbaren Datei deutlich reduzieren.  
  
 Wenn Sie separat kompilieren und verknüpfen, können Sie die [/OPT: REF](../../build/reference/opt-optimizations.md) (Linkeroption) zum Ausschließen der ausführbaren Datei mit der nicht referenzierten globalen Daten in Objektdateien kompiliert die **/GW** Option.  
  
 Sie können auch die [/OPT: ICF](../../build/reference/opt-optimizations.md) und [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) Optionen des Linkers zusammen, die in der ausführbaren Datei zusammenzuführen identischen schreibgeschützte globale Daten über mehrere Objektdateien hinweg mit kompiliert die   **/GW** Option.  
  
 Weitere Informationen finden Sie unter [Einführung/GW Compilerschalter](http://blogs.msdn.com/b/vcblog/archive/2013/09/11/introducing-gw-compiler-switch.aspx) im Visual C++-Team-Blog.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **C/C++-** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Ändern der **Zusatzoptionen** Eigenschaft einschließen **/GW** und wählen Sie dann **OK**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)