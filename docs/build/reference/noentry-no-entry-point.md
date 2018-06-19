---
title: -NOENTRY (kein Einstiegspunkt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
dev_langs:
- C++
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44f35c995a0c839fdc0d4ccf3d286e332793cf70
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374036"
---
# <a name="noentry-no-entry-point"></a>/NOENTRY (Kein Einstiegspunkt)
```  
/NOENTRY  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Option/NOENTRY ist erforderlich für das Erstellen einer reinen Ressourcen-DLL, die keinen ausführbaren Code enthält. Weitere Informationen finden Sie unter [Erstellen einer DLL Resource-Only](../../build/creating-a-resource-only-dll.md).  
  
 Sie können mit dieser Option verhindern, dass LINK einen Verweis auf `_main` in die DLL einbindet.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **Linker** Ordner.  
  
3.  Wählen Sie die **erweitert** Eigenschaftenseite.  
  
4.  Ändern der **kein Einstiegspunkt** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer DLL als reine Ressource](../../build/creating-a-resource-only-dll.md)   
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)