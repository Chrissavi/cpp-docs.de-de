---
title: -V (Versionsnummer) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /v
dev_langs:
- C++
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d3daf62c818b454a5477de04a27c4b4f308c271d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377231"
---
# <a name="v-version-number"></a>/V (Versionsnummer)
Veraltet. Eine Textzeichenfolge in der OBJ-Datei eingebettet.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Vstring  
```  
  
## <a name="arguments"></a>Argumente  
 `string`  
 Eine Zeichenfolge, die Angabe der Versionsnummer oder den Urheberrechtshinweis, in einer OBJ-Datei eingebettet werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Die Bezeichnung der Stringcan einer OBJ-Datei mit einer Versionsnummer oder copyright-Hinweis. Wenn sie einen Teil der Zeichenfolge sind, müssen alle Leerzeichen oder Tabulatorzeichen in doppelte Anführungszeichen (") eingeschlossen werden. Ein umgekehrter Schrägstrich (\\) müssen vor alle doppelten Anführungszeichen stehen, wenn sie einen Teil der Zeichenfolge sind. Ein Leerzeichen zwischen **/v** und `string` ist optional.  
  
 Sie können auch [Kommentar (C/C++)](../../preprocessor/comment-c-cpp.md) mit dem Compiler Comment-Type-Argument, um die Anzahl der Name und Version des Compilers in der OBJ-Datei zu platzieren.  
  
 Die **/v** Option ist in Visual Studio 2005; ab veraltet. **/V** wurde in erster Linie verwendet, um das Erstellen von virtuellen Gerätetreibern (VxDs) zu unterstützen, und Visual C++-Toolsets VxDs erstellen nicht mehr unterstützt wird. Eine Liste der veralteten Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md).  
  
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