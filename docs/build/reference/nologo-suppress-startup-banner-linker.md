---
title: -NOLOGO (Startbanner unterdrücken) (Linker) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.SuppressStartupBanner
- /nologo
dev_langs:
- C++
helpviewer_keywords:
- suppress startup banner linker option
- -NOLOGO linker option
- /NOLOGO linker option
- copyright message
- version numbers, preventing linker display
- banners, suppressing startup
- NOLOGO linker option
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a76e99496114c0ebdc60f81724e67dd88a482055
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374192"
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO (Startbanner unterdrücken) (Linker)
```  
/NOLOGO  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Option/nologo Verhindert die Anzeige der Copyrightmeldung und der Versionsnummer.  
  
 Diese Option unterdrückt die Anzeige von Befehlsdateien. Weitere Informationen finden Sie unter [LINK-Befehlsdateien](../../build/reference/link-command-files.md).  
  
 Standardmäßig werden diese Informationen durch den Linker an, das Fenster "Ausgabe" gesendet. In der Befehlszeile an die Standardausgabe gesendet wird, und können in eine Datei umgeleitet werden.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Diese Option sollte nur über die Befehlszeile verwendet werden.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Diese Linkeroption kann programmgesteuert geändert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)