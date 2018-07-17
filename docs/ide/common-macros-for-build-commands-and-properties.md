---
title: Gängige Makros für Buildbefehle und -eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
dev_langs:
- C++
helpviewer_keywords:
- $(FrameworkSDKDir) macro
- ProjectName macro $(ProjectName)
- DevEnvDir macro $(DevEnvDir)
- $(DevEnvDir) macro
- TargetPath macro $(TargetPath)
- VSInstallDir macro $(VSInstallDir)
- $(InputFileName) macro
- $(SolutionFileName) macro
- macros [C++], build macros
- InputFileName macro $(InputFileName)
- $(VCInstallDir) macro
- $(IntDir) macro
- $(ConfigurationName) macro
- SolutionDir macro $(SolutionDir)
- $(TargetPath) macro
- $(Inherit) macro
- $(SolutionPath) macro
- WebDeployRoot macro $(WebDeployRoot)
- WebDeployPath macro $(WebDeployPath)
- StopEvaluating macro $(StopEvaluating)
- $(RootNamespace) macro
- $(WebDeployRoot) macro
- ProjectPath macro $(ProjectPath)
- $(ProjectPath) macro
- $(InputDir) macro
- SolutionName macro $(SolutionName)
- ProjectExt macro $(ProjectExt)
- $(TargetExt) macro
- $(ProjectFileName) macro
- TargetName macro $(TargetName)
- $(References) macro
- References macro $(References)
- TargetExt macro $(TargetExt)
- ProjectDir macro $(ProjectDir)
- $(TargetDir) macro
- SolutionExt macro $(SolutionExt)
- $(SolutionDir) macro
- ProjectFileName macro $(ProjectFileName)
- VCInstallDir macro $(VCInstallDir)
- $(InputExt) macro
- $(TargetFileName) macro
- $(SolutionExt) macro
- PlatformName macro $(PlatformName)
- IntDir macro $(IntDir)
- $(FrameworkVersion) macro
- $(ProjectDir) macro
- build macros [C++]
- InputPath macro $(InputPath)
- $(VSInstallDir) macro
- $(WebDeployPath) macro
- TargetFileName macro $(TargetFileName)
- NoInherit macro $(NoInherit)
- ConfigurationName macro $(ConfigurationName)
- $(ProjectExt) macro
- TargetDir macro $(TargetDir)
- InputName macro $(InputName)
- $(ProjectName) macro
- FrameworkSDKDir macro $(FrameworkSDKDir)
- $(ParentName) macro
- InputExt macro $(InputExt)
- $(SafeRootNamespace) macro
- InputDir macro $(InputDir)
- $(FxCopDir) macro
- $(RemoteMachine) macro
- Inherit macro $(Inherit)
- FrameworkVersion macro $(FrameworkVersion)
- $(StopEvaluating) macro
- $(OutDir) macro
- FrameworkDir macro $(FrameworkDir)
- SolutionFileName macro $(SolutionFileName)
- $(NoInherit) macro
- RemoteMachine macro $(RemoteMachine)
- properties [C++], build property macros
- $(TargetName) macro
- $(SolutionName) macro
- $(InputPath) macro
- ParentName macro $(ParentName)
- OutDir macro $(OutDir)
- SafeRootNamespace macro $(SafeRootNamespace)
- FxCopDir macro $(FxCopDir)
- $(InputName) macro
- RootNamespace macro $(RootNamespace)
- builds [C++], macros
- $(FrameworkDir) macro
- $(PlatformName) macro
- SolutionPath macro $(SolutionPath)
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b94347e48a7b8b134915456c92aea3397f97a1b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339630"
---
# <a name="common-macros-for-build-commands-and-properties"></a>Gängige Makros für Buildbefehle und -eigenschaften
Abhängig von Ihren Installationsoptionen kann Visual Studio Ihnen Hunderte von Makros zur Verfügung stellen. Diese entsprechen den MSBuild-Eigenschaften, die standardmäßig, in PROPS- oder TARGETS-Dateien oder in Ihren Projekteinstellungen festgelegt sind. Sie können diese Makros an einer beliebigen Stelle im Dialogfeld **Eigenschaftenseiten** eines Projekts verwenden, an der Zeichenfolgen akzeptiert werden. Bei diesen Makros wird keine Groß-/Kleinschreibung berücksichtigt.  
  
 Um die derzeit verfügbaren Makros in der Spalte rechts neben einem Eigenschaftennamen anzuzeigen, klicken Sie auf den Dropdownpfeil. Wenn **Bearbeiten** verfügbar ist, klicken Sie auf diese Option, und klicken Sie dann im Dialogfeld „Bearbeiten“ auf **Makros**. Weitere Informationen finden Sie unter **Specifying User-Defined Values** im Abschnitt [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md).  
  
 Makros, die als „Veraltet“ markiert sind, werden nicht mehr verwendet oder wurden von einem gleichwertigen [ItemMetadata-Makro](/visualstudio/msbuild/itemmetadata-element-msbuild) (**%(***Name***)**) ersetzt. Als „Veraltet; Migriert“ markierte Makros sind ebenfalls veraltet. Wenn das Projekt, das das Makro enthält, zudem von Visual Studio 2008 migriert wird, konvertiert Visual Studio das Makro in das entsprechende aktuelle Makro.  
  
 In der folgenden Tabelle wird eine häufig verwendete Teilmenge der verfügbaren Makros beschrieben. Diese Liste ist nicht vollständig. Ausführliche Informationen zum Erstellen von MSBuild-Eigenschaftsdefinitionen und wie diese als Makros in PROPS, TARGETS und VCXPROJ-Dateien verwendet werden, finden Sie unter [MSBuild-Eigenschaften](/visualstudio/msbuild/msbuild-properties).  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|**$(RemoteMachine)**|Auf der Debugeigenschaftenseite auf den Wert der **Remote Machine** -Eigenschaft festgelegt. Weitere Informationen finden Sie unter [Projekteinstellungen für eine C- oder C++-Debugkonfiguration](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration) .|  
|**$(Configuration)**|Der Name der aktuellen Projektkonfiguration, z.B. „Debug“.|  
|**$(Platform)**|Der Name der aktuellen Projektplattform (z.B. „Win32“).|  
|**$(ParentName)**|(Veraltet.) Der Name des Elements, das dieses Projektelement enthält. Dies wird der Name des übergeordneten Ordners oder der Projektname sein.|  
|**$(RootNameSpace)**|Der Namespace, falls vorhanden, der die Anwendung enthält.|  
|**$(IntDir)**|Der Pfad zum Verzeichnis, das für Zwischendateien angegeben wurde. Ist dies ein relativer Pfad, gelangen die Zwischendateien in diesen Pfad, der an das Projektverzeichnis angefügt wird. Dieser Pfad sollte über einen nachgestellten Schrägstrich verfügen. Dies wird in den Wert für die **Intermediate Directory** -Eigenschaft aufgelöst. Verwenden Sie nicht **$(OutDir)** , um diese Eigenschaft zu definieren.|  
|**$(OutDir)**|Der Pfad zum Ausgabedateiverzeichnis. Ist dies ein relativer Pfad, gelangen die Ausgabedateien in diesen Pfad, der an das Projektverzeichnis angefügt wird. Dieser Pfad sollte über einen nachgestellten Schrägstrich verfügen. Dies wird in den Wert für die **Output Directory** -Eigenschaft aufgelöst. Verwenden Sie nicht **$(IntDir)** , um diese Eigenschaft zu definieren.|  
|**$(DevEnvDir)**|Das Installationsverzeichnis von Visual Studio (als „Laufwerk + Pfad“ definiert). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“.|  
|**$(InputDir)**|(Veraltet; Migriert) Das Verzeichnis der Eingabedatei (als „Laufwerk + Pfad“ definiert). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“. Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$(ProjectDir)**.|  
|**$(InputPath)**|(Veraltet; Migriert) Der absolute Pfadname der Eingabedatei (als „Laufwerk + Pfad + Basisname + Dateierweiterung“ definiert). Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$(ProjectPath)**.|  
|**$(InputName)**|(Veraltet; Migriert) Der Basisname der Eingabedatei. Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$(ProjectName)**.|  
|**$(InputFileName)**|(Veraltet; Migriert) Der Dateiname der Eingabedatei (als „Basisname + Dateierweiterung“ definiert). Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$(ProjectFileName)**.|  
|**$(InputExt)**|(Veraltet; Migriert) Die Dateierweiterung der Eingabedatei. Sie umfasst den „.“ vor der Dateierweiterung. Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$(ProjectExt)**.|  
|**$(ProjectDir)**|Das Verzeichnis des Projekts (als „Laufwerk + Pfad“ definiert). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“.|  
|**$(ProjectPath)**|Der absolute Pfadname des Projekts (als „Laufwerk + Pfad + Basisname + Dateierweiterung“ definiert).|  
|**$(ProjectName)**|Der Basisname des Projekts.|  
|**$(ProjectFileName)**|Der Dateiname des Projekts (als „Basisname + Dateierweiterung“ definiert).|  
|**$(ProjectExt)**|Die Dateierweiterung des Projekts. Sie umfasst den „.“ vor der Dateierweiterung.|  
|**$(SolutionDir)**|Das Verzeichnis der Projektmappe (als „Laufwerk + Pfad“ definiert). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“. Wird nur bei der Erstellung einer Projektmappe in der IDE definiert.|  
|**$(SolutionPath)**|Der absolute Pfadname der Projektmappe (als „Laufwerk + Pfad + Basisname + Dateierweiterung“ definiert). Wird nur bei der Erstellung einer Projektmappe in der IDE definiert.|  
|**$(SolutionName)**|Der Basisname der Projektmappe. Wird nur bei der Erstellung einer Projektmappe in der IDE definiert.|  
|**$(SolutionFileName)**|Der Dateiname der Projektmappe (als „Basisname + Dateierweiterung“ definiert). Wird nur bei der Erstellung einer Projektmappe in der IDE definiert.|  
|**$(SolutionExt)**|Die Dateierweiterung der Projektmappe. Sie umfasst den „.“ vor der Dateierweiterung. Wird nur bei der Erstellung einer Projektmappe in der IDE definiert.|  
|**$(TargetDir)**|Das Verzeichnis der primären Ausgabedatei für den Build (als „Laufwerk + Pfad“ definiert). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“.|  
|**$(TargetPath)**|Der absolute Pfadname der primären Ausgabedatei für den Build (als „Laufwerk + Pfad + Basisname + Dateierweiterung“ definiert).|  
|**$(TargetName)**|Der Basisname der primären Ausgabedatei für den Build.|  
|**$(TargetFileName)**|Der Dateiname der primären Ausgabedatei für den Build (als „Basisname + Dateierweiterung“ definiert).|  
|**$(TargetExt)**|Die Dateierweiterung der primären Ausgabedatei für den Build. Sie umfasst den „.“ vor der Dateierweiterung.|  
|**$(VSInstallDir)**|Das Verzeichnis, in dem Visual Studio installiert wurde.<br /><br /> Diese Eigenschaft enthält die Version der Visual Studio-Zielversion, die sich möglicherweise vom Visual Studio-Host unterscheidet. Beim Erstellen mit `$(PlatformToolset) = v110`, enthält **$(VSInstallDir)** z. B. den Pfad zur Installation von Visual Studio 2012.|  
|**$(VCInstallDir)**|Das Verzeichnis, in dem Visual C++ installiert wurde.<br /><br /> Diese Eigenschaft enthält die Version der Visual C++-Zielversion, die sich möglicherweise vom Visual Studio-Host unterscheidet. Beim Erstellen mit `$(PlatformToolset) = v140` enthält **$(VCInstallDir)** z.B. den Pfad zur Installation von Visual C++ 2015.|  
|**$(FrameworkDir)**|Das Verzeichnis, in dem .NET Framework installiert wurde.|  
|**$(FrameworkVersion)**|Die Version von .NET Framework, die von Visual Studio verwendet wurde. In Kombination mit **$(FrameworkDir)** stellt dies den vollständigen Pfad zu der Version von .NET Framework dar, die von Visual Studio verwendet wurde.|  
|**$(FrameworkSDKDir)**|Das Verzeichnis, in dem Sie .NET Framework installiert haben. .NET Framework könnte als Teil von Visual Studio oder separat installiert worden sein.|  
|**$(WebDeployPath)**|Der relative Pfad vom Stamm der Webbereitstellung zum Speicherort der Projektausgaben. Gibt denselben Wert zurück wie <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>.|  
|**$(WebDeployRoot)**|Der absolute Pfad zum Speicherort von **\<localhost>**. Beispiel: „c:\inetpub\wwwroot“.|  
|**$(SafeParentName)**|(Veraltet.) Der Name des unmittelbar übergeordneten Elements im gültigen Namensformat. Ein Formular ist beispielsweise das übergeordnete Element einer RESX-Datei.|  
|**$(SafeInputName)**|(Veraltet.) Der Name der Datei als gültiger Klassenname, ohne die Dateierweiterung.|  
|**$(SafeRootNamespace)**|(Veraltet.) Der Namespacename, in dem die Projekt-Assistenten Code hinzufügen. Dieser Namespacename darf nur Zeichen enthalten, die in einem gültigen C++-Bezeichner zulässig sind.|  
|**$(FxCopDir)**|Der Pfad zur Datei „fxcop.cmd“. Die Datei „fxcop.cmd“ wird nicht mit allen Editionen von Visual C++ installiert.|  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von C++-Projekten in Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)