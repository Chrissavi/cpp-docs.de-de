---
title: Clang/llvm-Unterstützung in Visual Studio Visual Studio-Projekten
ms.date: 08/30/2019
ms.description: Configure a Visual Studio MSBuild project to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ MSBuild projects
ms.openlocfilehash: f0142c2583eeef10f159cd83451e1f3866990b75
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222629"
---
# <a name="clangllvm-support-in-visual-studio-projects"></a>Clang/llvm-Unterstützung in Visual Studio-Projekten

::: moniker range="<=vs-2017"

Clang-Unterstützung für cmake-und MSBuild-Projekte ist in Visual Studio 2019 verfügbar.

::: moniker-end

::: moniker range="vs-2019"

Sie können Visual Studio 2019 Version 16,2 mit clang zum Bearbeiten, erstellen und Debuggen C++ von Visual Studio-Projekten (MSBuild) verwenden, die auf Windows oder Linux abzielen.

## <a name="install"></a>Installieren

Für eine optimale IDE-Unterstützung in Visual Studio wird empfohlen, die neuesten clang-Compilertools für Windows zu verwenden. Wenn Sie diese noch nicht kennen, können Sie Sie installieren, indem Sie die Visual Studio-Installer öffnen und unter " **Desktop Entwicklung" mit C++**  optionalen Komponenten  **C++ clang-Tools für Windows** auswählen. Wenn Sie lieber eine vorhandene clang-Installation auf Ihrem Computer verwenden möchten, wählen Sie die  **C++ clang-CL für v142-Buildtools aus.** optionale Komponente. Die Microsoft C++ -Standard Bibliothek erfordert derzeit mindestens clang 8.0.0; die gebündelte Version von clang wird automatisch aktualisiert, um bei Updates in der Microsoft-Implementierung der Standard Bibliothek auf dem Laufenden zu bleiben. 

![Installation der clang-Komponente](media/clang-install-vs2019.png)

## <a name="configure-a-windows-project-to-use-clang-tools"></a>Konfigurieren eines Windows-Projekts für die Verwendung von clang-Tools

Zum Konfigurieren eines Visual Studio-Projekts für die Verwendung von clang klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Projekt Knoten, und wählen Sie **Eigenschaften**aus. In der Regel sollten Sie zuerst **alle Konfigurationen** am oberen Rand des Dialog Felds auswählen. Wählen Sie dann unter **Allgemeine** > **Platt Form Toolset**die Option **llvm (clang-cl)** aus, und klicken Sie dann auf **OK**.

![Installation der clang-Komponente](media/clang-msbuild-prop-page.png)

Wenn Sie die clang-Tools verwenden, die mit Visual Studio gebündelt sind, sind keine weiteren Schritte erforderlich. Für Windows-Projekte ruft Visual Studio standardmäßig clang im [clang-cl-](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) Modus auf und verknüpft mit der Microsoft-Implementierung der Standard Bibliothek. **Clang-cl. exe** befindet sich standardmäßig in `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`.

Wenn Sie eine benutzerdefinierte clang-Installation verwenden, können Sie die **Projekt** > **Eigenschaften** > "**VC + +-Verzeichnisse** > **Konfigurations Eigenschaften** > **ausführbare Datei" ändern. Verzeichnisse** durch Hinzufügen des benutzerdefinierten clang-Installations Stamms als erstes Verzeichnis oder Ändern des Werts `LLVMInstallDir` der-Eigenschaft. Weitere Informationen finden Sie unter [Festlegen eines benutzerdefinierten llvm](#custom_llvm_location) -Speicher Orts.

## <a name="configure-a-linux-project-to-use-clang-tools"></a>Konfigurieren eines Linux-Projekts für die Verwendung von clang-Tools

Bei Linux-Projekten verwendet Visual Studio das clang gcc-kompatible Front-End. Die Projekteigenschaften und fast alle Compilerflags sind identisch.

So konfigurieren Sie ein Visual Studio Linux-Projekt für die Verwendung von clang:

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Projekt Knoten, und wählen Sie **Eigenschaften**aus. 
1. In der Regel sollten Sie zuerst **alle Konfigurationen** am oberen Rand des Dialog Felds auswählen. 
1. Wählen Sie unter **Allgemeine** > **Platt Form Toolset**die Option **WSL_Clang_1_0** , wenn Sie das Windows-Subsystem für Linux verwenden, oder **Remote_Clang_1_0** , wenn Sie einen Remote Computer oder einen virtuellen Computer verwenden.
1. Klicken Sie auf **OK**.

![Installation der clang-Komponente](media/clang-msbuild-prop-page.png)

Unter Linux verwendet Visual Studio standardmäßig den ersten clang-Speicherort, der in der Path-Umgebungs Eigenschaft gefunden wird. Wenn Sie eine benutzerdefinierte `LLVMInstallDir` clang-Installation verwenden, müssen Sie den Wert der-Eigenschaft ändern oder einen Pfad unter den **Projekt** > **Eigenschaften** > **VC + +-Verzeichnisse**  >  **ersetzen.**  > **Ausführbare Verzeichnisse**für Konfigurations Eigenschaften. Weitere Informationen finden Sie unter [Festlegen eines benutzerdefinierten llvm](#custom_llvm_location) -Speicher Orts.

## <a name="custom_llvm_location"></a>Festlegen eines benutzerdefinierten llvm-Speicher Orts

Sie können einen benutzerdefinierten Pfad für llvm für ein oder mehrere Projekte festlegen, indem Sie eine *Verzeichnis. Build.* -Datei erstellen und diese Datei dem Stamm Ordner jedes Projekts hinzufügen. Sie können Sie dem Ordner "root Solution" hinzufügen, um Sie auf alle Projekte in der Projekt Mappe anzuwenden. Die Datei sollte wie folgt aussehen (aber durch den eigentlichen Pfad ersetzen):

```xml
<Project>
  <PropertyGroup>
    <LLVMInstallDir>c:\MyLLVMRootDir</LLVMInstallDir>
  </PropertyGroup>
</Project>
```

## <a name="set-additional-properties-edit-build-and-debug"></a>Festlegen zusätzlicher Eigenschaften, bearbeiten, erstellen und Debuggen

Nachdem Sie eine clang-Konfiguration eingerichtet haben, klicken Sie mit der rechten Maustaste erneut auf den Projekt Knoten, und wählen Sie **Projekt erneut laden**aus. Sie können das Projekt jetzt mithilfe der clang-Tools erstellen und Debuggen. Visual Studio erkennt, dass Sie den clang-Compiler verwenden, und stellt IntelliSense, Hervorhebung, Navigation und andere Bearbeitungsfunktionen bereit. Fehler und Warnungen werden in der **Ausgabefenster**angezeigt. Die Projekteigenschaften Seiten für eine clang-Konfiguration ähneln denen für MSVC, obwohl einige compilerabhängige Funktionen wie "Bearbeiten und Fortfahren" für clang-Konfigurationen nicht verfügbar sind. Um einen clang-Compiler oder eine Linkeroption festzulegen, der nicht auf den Eigenschaften Seiten verfügbar ist, können Sie ihn manuell in den Eigenschaften Seiten unter **Konfigurations Eigenschaften** > **C/(oder Linker)C++**  > -**Befehlszeile** hinzufügen. **Zusätzliche Optionen**.  > 

Beim Debuggen können Sie Breakpoints, die Arbeitsspeicher-und Datenvisualisierung und die meisten anderen Debuggingfunktionen verwenden.  

![Clang-Debugging](media/clang-debug-msbuild.png)

::: moniker-end
