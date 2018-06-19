---
title: -INTEGRITYCHECK (Signaturprüfung erforderlich) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 997e3f5bb79ee3cbfa95c5762b0d3e998c56f362
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374244"
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK (Signaturprüfung erforderlich)
Gibt an, dass die digitale Signatur des Binärimages zur Ladezeit überprüft werden muss.  
  
```  
/INTEGRITYCHECK[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig **/INTEGRITYCHECK** ist deaktiviert.  
  
 Die **/INTEGRITYCHECK** -Option wird – im PE-Header der DLL-Datei oder ausführbare Datei – ein Flag für die Speicher-Manager, um für eine digitale Signatur zu überprüfen, um das Image in Windows zu laden. Diese Option muss für 32-Bit- und 64-Bit-DLLs festgelegt werden, die den Kernelmoduscode implementieren, der von bestimmten Windows-Funktionen geladen wird, und wird für alle Gerätetreiber unter Windows Vista, [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/reference/includes/win8_md.md)], [!INCLUDE[winsvr08](../../build/reference/includes/winsvr08_md.md)] und [!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)] empfohlen. Windows-Versionen vor Windows Vista ignorieren dieses Flag. Weitere Informationen finden Sie unter [erzwungen Integrität Signieren von portierbare ausführbare Datei (PE) Dateien](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
5.  In **Zusatzoptionen**, geben Sie `/INTEGRITYCHECK` oder `/INTEGRITYCHECK:NO`.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Optionen des Linkers](../../build/reference/linker-options.md)   
 [Erzwungene Integrität Signieren von portierbare ausführbare Datei (PE)-Dateien](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)   
 [Kernelmodus-Codesignatur Exemplarische Vorgehensweise](http://msdn.microsoft.com/windows/hardware/gg487328.aspx)   
 [AppInit-DLLs in Windows 7 und WindowsServer 2008](http://msdn.microsoft.com/windows/hardware/gg463040.aspx)