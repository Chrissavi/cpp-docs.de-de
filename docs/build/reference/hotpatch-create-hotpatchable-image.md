---
title: -Hotpatch (erstellen Hotpatch-fähiges Abbild) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
dev_langs:
- C++
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb0f27c8da03104ee3633d9ea1a5f1232407931e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376204"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch (Erstellen eines Hotpatch-fähigen Abbildes)
Bereitet ein Image für Hotpatching vor.  
  
## <a name="syntax"></a>Syntax  
  
```  
/hotpatch  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn **/hotpatch** wird verwendet, in einer Kompilierung der Compiler stellt sicher, dass die erste Anweisung jeder Funktion mindestens zwei Bytes ist die für das HotPatching erforderlich ist.  
  
 Zum Abschließen der Vorbereitung auf ein Bild eines vornehmen, nachdem Sie mit **/hotpatch** um kompilieren, verwenden Sie [/FUNCTIONPADMIN (Erstellen eines Hotpatch-fähigen Abbildes)](../../build/reference/functionpadmin-create-hotpatchable-image.md) verknüpfen. Wenn Sie kompilieren und verknüpfen Sie ein Bild mit einem Aufruf von cl.exe, **/hotpatch** impliziert **/functionpadmin**.  
  
 Da Anweisungen immer zwei Bytes sind oder auf der ARM-Architektur und da X64 Kompilierung wird immer behandelt wie **/hotpatch** angegeben wurde, müssen nicht angeben **/hotpatch** bei Sie Kompilieren für diese Ziele. Sie müssen jedoch weiterhin Verknüpfen mit **/functionpadmin** um hotpatchfähige Images für sie erstellen. Die **/hotpatch** Compiler Option nur wirkt sich auf X86 Kompilierung.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **C/C++-** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Fügen Sie die Compileroption ", um die **Zusatzoptionen** Feld.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="guidance"></a>Empfehlungen  
 Weitere Informationen zur updateverwaltung finden Sie unter "Security Guidance for Update Management" [ http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx ](http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx).  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)