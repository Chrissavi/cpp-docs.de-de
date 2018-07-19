---
title: -PDB (Programmdatenbank verwenden) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
dev_langs:
- C++
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 776d23c0c0c7ce392b1ff0d7a989c3c5503129b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375998"
---
# <a name="pdb-use-program-database"></a>/PDB (Programmdatenbank verwenden)
```  
/PDB:filename  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 *filename*  
 Ein benutzerdefinierter Name für die Programmdatenbank (PDB), die der Linker erstellt. Er ersetzt den Standardnamen.  
  
## <a name="remarks"></a>Hinweise  
 In der Standardeinstellung Wenn [/DEBUG](../../build/reference/debug-generate-debug-info.md) angegeben ist, wird der Linker erstellt eine Programmdatenbank (PDB) die Debuginformationen enthält. Der Standarddateiname für die PDB-Datei hat den Namen des Programms und die Erweiterung PDB-Datei.  
  
 Verwenden Sie/PDB:*Filename* den Namen der PDB-Datei angeben. Wenn "/ Debug" nicht angegeben ist, wird der/PDB-Option ignoriert.  
  
 Eine PDB-Datei kann bis zu 2 GB sein.  
  
 Weitere Informationen finden Sie unter [PDB-Dateien als Linkereingabe](../../build/reference/dot-pdb-files-as-linker-input.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **Debuggen** Eigenschaftenseite.  
  
4.  Ändern der **Programmdatenbank-Datei erstellen** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)