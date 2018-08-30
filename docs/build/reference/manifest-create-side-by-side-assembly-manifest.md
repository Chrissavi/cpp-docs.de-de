---
title: -MANIFEST (Seite-an-Seite-Assemblymanifest erstellen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateManifest
dev_langs:
- C++
helpviewer_keywords:
- -MANIFEST linker option
- /MANIFEST linker option
- MANIFEST linker option
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7cdf0f5d1d736635af3d7bf1a853e9002e072ef5
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43199112"
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST (Erstellen eines Manifests für eine parallele Assembly)
```  
/MANIFEST[:{EMBED[,ID=#]|NO}]  
```  
  
## <a name="remarks"></a>Hinweise  
 /MANIFEST gibt an, dass der Linker eine parallele Manifestdatei erstellen soll. Weitere Informationen über Manifestdateien finden Sie unter [Manifestdateienreferenz](/windows/desktop/SbsCs/manifest-files-reference).  
  
 Die Standardeinstellung ist "/MANIFEST".  
  
 Die /MANIFEST:EMBED-Option gibt an, dass der Linker die Manifestdatei im Image als Ressource vom Typ "RT_MANIFEST" einbetten soll. Der optionale `ID`-Parameter ist die Ressourcen-ID, die für das Manifest verwendet werden soll. Verwenden Sie den Wert 1 für eine ausführbare Datei. Verwenden Sie den Wert 2 für eine DLL, damit diese private Abhängigkeiten angeben kann. Wenn der `ID`-Parameter nicht angegeben wird, ist der Standardwert 2, wenn die /DLL-Option festgelegt wird; andernfalls ist der Standardwert 1.  
  
 Ab Visual Studio 2008 enthalten Manifestdateien für ausführbare Dateien einen Abschnitt, der Informationen zur Benutzerkontensteuerung (UAC) angibt. Wenn Sie "/ manifest", aber keines von beiden angeben [/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md) noch [/DLL](../../build/reference/dll-build-a-dll.md), standardmäßige UAC-Fragment, das auf die UAC-Ebene-festgelegt ist *"asInvoker"* in das Manifest eingefügt wird. Weitere Informationen über UAC-Ebenen finden Sie unter [/MANIFESTUAC (bettet UAC-Informationen in Manifest)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md).  
  
 Um das UAC-Standardverhalten zu ändern, führen Sie einen der folgenden Schritte aus:  
  
-   Geben Sie die /MANIFESTUAC-Option an, und legen Sie die UAC-Ebene auf den gewünschten Wert fest.  
  
-   Oder geben Sie die /MANIFESTUAC:NO-Option an, wenn Sie im Manifest kein UAC-Fragment generieren möchten.  
  
 Wenn Sie nicht "/ manifest" angeben, aber geben Sie [Linkerkommentar](../../build/reference/manifestdependency-specify-manifest-dependencies.md) Kommentare, wird eine Manifestdatei erstellt. Wenn Sie "/MANIFEST:NO" angeben, wird keine Manifestdatei erstellt.  
  
 Wenn Sie "/MANIFEST" angeben, wird der Name der Manifestdatei aus dem Namen der Ausgabedatei und der Endung .MANIFEST zusammengesetzt. Wenn die Ausgabedatei beispielsweise "MyFile.exe" heißt, hat die Manifestdatei den Namen "MyFile.exe.manifest".  Wenn Sie/ManifestFile:*Namen*, der Name des Manifests ist angeben *Namen*.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **Manifestdatei** Eigenschaftenseite.  
  
5.  Ändern der **Manifest generieren** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)