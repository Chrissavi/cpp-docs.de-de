---
title: -Ge (Stapelüberprüfungen aktivieren) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ge
dev_langs:
- C++
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce8b049426eb403e4bc41e842fe1ff2db1617dfc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375297"
---
# <a name="ge-enable-stack-probes"></a>/Ge (Stapelüberprüfungen aktivieren)
Aktiviert stapelüberprüfungen für jeden Funktionsaufruf, der Speicher für lokale Variablen benötigt.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Ge  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieser Mechanismus ist hilfreich, wenn Sie die Funktionalität des Prüfpunkts Stapel umschreiben. Es wird empfohlen, die Verwendung von [/GH (Enable _penter-Hookfunktion)](../../build/reference/gh-enable-penter-hook-function.md) anstelle der stapelüberprüfung umschreiben.  
  
 [/ GS (Control Stack Checking Calls)](../../build/reference/gs-control-stack-checking-calls.md) hat dieselbe Wirkung.  
  
 **/ Ge** ist als veraltet markiert; ab Visual Studio 2005, generiert der Compiler automatisch stapelüberprüfung. Eine Liste der veralteten Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md).  
  
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