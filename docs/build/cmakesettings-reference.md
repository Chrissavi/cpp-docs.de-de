---
title: CMakeSettings.json-Schemareferenz
ms.date: 10/31/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 2233c0767fb7fac2fe496e744750f380e1c3b698
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303237"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.json-Schemareferenz

::: moniker range="vs-2015"

Cmake-Projekte werden in Visual Studio 2017 und höher unterstützt.

::: moniker-end

::: moniker range=">=vs-2017"

Die **cmakesettings. JSON** -Datei enthält Informationen, die Visual Studio für IntelliSense verwendet, und zum Erstellen der Befehlszeilenargumente, die an cmake. exe für eine angegebene *Konfigurations* -und *Compilerumgebung*übergeben werden. Eine Konfiguration gibt Eigenschaften an, die für eine bestimmte Plattform und einen Buildtyp gelten, z. b. `x86-Debug` oder `Linux-Release`. Jede Konfiguration gibt eine Umgebung an, in der Informationen zum Compilertoolset (z. b. MSVC, gcc oder clang) gekapselt werden. Cmake verwendet die Befehlszeilenargumente, um die Stammdatei " *cmakecache. txt* " und andere Projektdateien für das Projekt neu zu generieren. Die Werte können in den *CMakeLists. txt* -Dateien überschrieben werden. 

Sie können Konfigurationen in der IDE hinzufügen oder entfernen und diese dann direkt in der JSON-Datei bearbeiten oder den Editor für die **cmake-Einstellungen** (Visual Studio 2019 und höher) verwenden. Sie können in der IDE problemlos zwischen den Konfigurationen wechseln, um die verschiedenen Projektdateien zu generieren. Weitere Informationen finden Sie [unter Anpassen von cmake-Buildeinstellungen in Visual Studio](customize-cmake-settings.md) .

## <a name="configurations"></a>Konfigurationen

Das `configurations` Array enthält alle Konfigurationen für ein cmake-Projekt. Weitere Informationen zu den vordefinierten Konfigurationen finden Sie unter [cmake-vordefinierte Konfigurations Referenz](cmake-predefined-configuration-reference.md) . Sie können der Datei beliebig viele vordefinierte oder benutzerdefinierte Konfigurationen hinzufügen. 

Eine `configuration` verfügt über die folgenden Eigenschaften:

- `addressSDanitizerEnabled`:, wenn `true` das Programm mit address sanitizer kompiliert (experimentell unter Windows). Kompilieren Sie unter Linux mit-fno-omit-Frame-Pointer und compileroptimierungs Level-OS oder-OO, um optimale Ergebnisse zu erzielen.
- `addressSanitizerRuntimeFlags`: Laufzeitflags, die über die ASAN_OPTIONS-Umgebungsvariable an addresssanitizer übermittelt werden. Format: Flag1 = Value: flag2 = Value2.
- `buildCommandArgs`: Gibt native Buildoptionen an, die nach „--build --“ an CMake übergeben werden. Beispielsweise wird beim Übergeben von „-v“ mithilfe des Ninja-Generators erzwungen, dass Ninja Befehlszeilen ausgibt. Weitere Informationen zu Ninja-Befehlen finden Sie unter [Ninja-Befehlszeilenargumente](#ninja).
- `buildRoot`: Gibt das Verzeichnis an, in dem CMake Buildskripts für den ausgewählten Generator erstellt.  Ist dem Schalter **-DCMAKE_BINARY_DIR** zugeordnet und gibt an, wo der CMake-Cache erstellt wird. Wenn der Ordner noch nicht vorhanden ist, wird dieser erstellt. Zu den unterstützten Makros zählen `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`und `${env.VARIABLE}`.
- `cacheGenerationCommand`: gibt ein Befehlszeilen Tool und Argumente an, z. b. " *gencache. bat Debug* ", um den Cache zu generieren. Der Befehl wird von der Shell in der angegebenen Umgebung für die Konfiguration ausgeführt, wenn der Benutzer eine Neugenerierung anfordert oder wenn die Datei "CMakeLists. txt" oder "cmakesettings. JSON" geändert wird.
- `cacheRoot`: Gibt den Pfad zu einem CMake-Cache an. Dieses Verzeichnis sollte eine vorhandene „CMakeCache.txt“-Datei enthalten.
- `clangTidyChecks`: durch Trennzeichen getrennte Liste von warnigns, die an clang-tidy übergeben werden. Platzhalter sind zulässig, und durch das Präfix "-" werden Überprüfungen entfernt.
- `cmakeCommandArgs`: Gibt zusätzliche Befehlszeilenoptionen an, die beim Aufruf zum Generieren des Caches an CMake übergeben werden.
- `cmakeToolchain`: Gibt die Toolkettendatei an. Diese wird über „-DCMAKE_TOOLCHAIN_FILE“ an CMake übergeben.
- `codeAnalysisRuleset`: Gibt den Regelsatz an, der beim Ausführen der Codeanalyse verwendet werden soll. Dies kann ein vollständiger Pfad oder der Dateiname einer Regelsatzdatei sein, die von Visual Studio installiert wird.
- `configurationType`: Gibt die Buildtypkonfiguration für den ausgewählten Generator an. Folgende stehen zur Auswahl:

  - Debuggen
  - Version
  - MinSizeRel
  - RelWithDebInfo
  
- `ctestCommandArgs`: Gibt zusätzliche Befehlszeilenoptionen an, die beim Ausführen der Tests an CTest übergeben werden.
- `description`: Beschreibung dieser Konfiguration, die in Menüs angezeigt wird.
- `enableClangTidyCodeAnalysis`: Verwenden Sie clang-tidy für die Code Analyse.
- `enableMicrosoftCodeAnalysis`: Verwenden Sie die Microsoft-Code Analysetools für die Code Analyse.
- `generator`: Gibt an, welcher CMake-Generator für diese Konfiguration verwendet werden soll. Folgende stehen zur Auswahl:
  
  **Nur Visual Studio 2019:**
  - Visual Studio 16 2019
  - Visual Studio 16 2019 Win64
  - Visual Studio 16 2019 ARM

  **Visual Studio 2017 und höher:**
  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 14 2015 ARM
  - Unix Makefiles
  - Ninja

Da Ninja für schnelle Buildgeschwindigkeiten statt für Flexibilität und Funktionalität entwickelt wurde, ist dieser als Standardwert festgelegt. Einige CMake-Projekte können jedoch mit Ninja keinen ordnungsgemäßen Build durchführen. Wenn dies auftritt, können Sie cmake anweisen, stattdessen Visual Studio-Projekte zu generieren.

Um einen Visual Studio-Generator in Visual Studio 2017 anzugeben, öffnen Sie den im Hauptmenü, indem Sie **cmake | Ändern Sie die cmake-Einstellungen**. Löschen Sie "Ninja", und geben Sie "V" ein. Dadurch wird IntelliSense aktiviert, und Sie können den gewünschten Generator auswählen.

Um einen Visual Studio-Generator in Visual Studio 2019 anzugeben, klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei " *CMakeLists. txt* ", und wählen Sie " **cmake Settings for > Project** " ( **Erweiterte Einstellungen** > **cmake-Generator**anzeigen) aus.

Wenn in der aktiven Konfiguration ein Visual Studio-Generator angegeben ist, wird standardmäßig „MSBuild.exe“ über `-m -v:minimal`-Argumente aufgerufen. Zum Anpassen des Builds können Sie in der Datei " *cmakesettings. JSON* " zusätzliche [MSBuild-Befehlszeilenargumente](../build/reference/msbuild-visual-cpp-overview.md) angeben, die über die `buildCommandArgs`-Eigenschaft an das Buildsystem übergeben werden sollen:

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `configurationType`: Gibt die Buildtypkonfiguration für den ausgewählten Generator an. Folgende stehen zur Auswahl:

  - Debuggen
  - Version
  - MinSizeRel
  - RelWithDebInfo
 
- `buildRoot`: Gibt das Verzeichnis an, in dem CMake Buildskripts für den ausgewählten Generator erstellt.  Wird **DCMAKE_BINARY_DIR** Switch zugeordnet und gibt an, wo die Datei " *cmakecache. txt* " erstellt wird. Wenn der Ordner nicht vorhanden ist, wird er erstellt. Zu den unterstützten Makros gehören `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `installRoot`: Gibt das Verzeichnis an, in dem CMake Installationsziele für den ausgewählten Generator erstellt. Unterstützte Makros sind `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `cmakeCommandArgs`: gibt zusätzliche Befehlszeilenoptionen an, die an cmake übergeben werden, wenn aufgerufen wird, um die Projektdateien zu generieren.
- `cmakeToolchain`: Gibt die Toolkettendatei an. Diese wird über „-DCMAKE_TOOLCHAIN_FILE“ an CMake übergeben.
- `buildCommandArgs`: Gibt native Buildoptionen an, die nach „--build --“ an CMake übergeben werden. Beispielsweise wird beim Übergeben von „-v“ mithilfe des Ninja-Generators erzwungen, dass Ninja Befehlszeilen ausgibt. Weitere Informationen zu Ninja-Befehlen finden Sie unter [Ninja-Befehlszeilenargumente](#ninja).
- `ctestCommandArgs`: Gibt zusätzliche Befehlszeilenoptionen an, die beim Ausführen der Tests an CTest übergeben werden.
- `codeAnalysisRuleset`: Gibt den Regelsatz an, der beim Ausführen der Codeanalyse verwendet werden soll. Dies kann ein vollständiger Pfad oder der Dateiname einer Regelsatzdatei sein, die von Visual Studio installiert wird.
- `inheritEnvironments`: Gibt mindestens eine Compilerumgebung an, von der diese Konfiguration abhängt. Dabei kann es sich um jede benutzerdefinierte Umgebung oder eine der vordefinierten Umgebungen handeln. Weitere Informationen finden Sie unter [Umgebungen](#environments).
- `installRoot`: Gibt das Verzeichnis an, in dem CMake Installationsziele für den ausgewählten Generator erstellt. Unterstützte Makros sind `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `intelliSenseMode`: Gibt den Modus zum Berechnen von IntelliSense-Informationen an. Folgende stehen zur Auswahl:

  - windows-msvc-x86
  - windows-msvc-x64
  - windows-msvc-arm
  - windows-msvc-arm64
  - android-clang-x86
  - android-clang-x64
  - android-clang-arm
  - android-clang-arm64
  - ios-clang-x86
  - ios-clang-x64
  - ios-clang-arm
  - ios-clang-arm64
  - windows-clang-x86
  - windows-clang-x64
  - windows-clang-arm
  - windows-clang-arm64
  - linux-gcc-x86
  - linux-gcc-x64
  - linux-gcc-arm

- `cacheRoot`: Gibt den Pfad zu einem CMake-Cache an. Dieses Verzeichnis sollte eine vorhandene Datei " *cmakecache. txt* " enthalten.
- `name`: Benennt die Konfiguration.  Weitere Informationen zu den vordefinierten Konfigurationen finden Sie unter [cmake-vordefinierte Konfigurations Referenz](cmake-predefined-configuration-reference.md) .
- `wslPath`: der Pfad zum Start Programm einer Instanz des Windows-Subsystems für Linux.

### <a name="additional-settings-for-cmake-linux-projects"></a>Zusätzliche Einstellungen für CMake-Projekte unter Linux. 

- `remoteMachineName`: Gibt den Namen des Linux-Remotecomputers an, auf dem CMake, Builds und der Debugger gehostet werden. Verwenden Sie den Verbindungs-Manager zum Hinzufügen neuer Linux-Computer. Unterstützte Makros sind `${defaultRemoteMachineName}`.
- `remoteCopySourcesOutputVerbosity`: Gibt den Ausführlichkeitsgrad des Quellkopiervorgangs zum Remotecomputer an. Zur Auswahl stehen „Normal“ (Regulär), „Verbose“ (Ausführlich) und „Diagnostic“ (Diagnostisch).
- `remoteCopySourcesConcurrentCopies`: gibt die Anzahl der gleichzeitigen Kopien an, die während der Synchronisierung der Quellen zum Remote Computer verwendet werden (nur SFTP).
- `remoteCopySourcesMethod`: Gibt die Methode zum Kopieren von Dateien auf den Remotecomputer an. Zur Auswahl stehen „rsync“ und „sftp“.
- `remoteCMakeListsRoot`: Gibt das Verzeichnis auf dem Remotecomputer an, das das CMake-Projekt enthält. Unterstützte Makros sind `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteBuildRoot`: Gibt das Verzeichnis auf dem Remotecomputer an, in dem CMake Buildskripts für den ausgewählten Generator erstellt. Unterstützte Makros sind `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteInstallRoot`: Gibt das Verzeichnis auf dem Remotecomputer an, in dem CMake Installationsziele für den ausgewählten Generator erstellt. Unterstützte Makros sind `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}` und `${env.VARIABLE}`, wobei `VARIABLE` eine Umgebungsvariable ist, die auf System-, Benutzer- oder Sitzungsebene definiert wurde.
- `remoteCopySources`: ein `boolean`, der angibt, ob Visual Studio Quelldateien auf den Remote Computer kopieren soll. Der Standardwert ist true. Legen Sie diesen Wert auf FALSE fest, wenn Sie die Dateisynchronisierung selbst verwalten.
- `remoteCopyBuildOutput`: ein `boolean`, der angibt, ob die Buildausgaben vom Remote System kopiert werden sollen.
- `rsyncCommandArgs`: Gibt zusätzliche Befehlszeilenoptionen an, die an „rsync“ übergeben werden.
- `remoteCopySourcesExclusionList`: eine `array`, die eine Liste von Pfaden angibt, die beim Kopieren von Quelldateien ausgeschlossen werden sollen: ein Pfad kann der Name einer Datei bzw. eines Verzeichnisses oder ein Pfad relativ zum Stamm der Kopie sein. Die Platzhalter \\\"*\\\" und \\\"?\\\" können für einen Globmusterabgleich verwendet werden.
- `cmakeExecutable`: gibt den vollständigen Pfad zur ausführbaren CMake-Programmdatei an, einschließlich des Dateinamens und der Dateierweiterung.
- `remotePreGenerateCommand`: gibt den Befehl an, der vor der Ausführung von cmake ausgeführt werden soll, um die Datei " *CMakeLists. txt* " zu analysieren.
- `remotePrebuildCommand`: Gibt den Befehl an, der vor der Erstellung auf dem Remotecomputer ausgeführt wird.
- `remotePostbuildCommand`: Gibt den Befehl an, der nach der Erstellung auf dem Remotecomputer ausgeführt wird.
- `variables`: enthält ein Name/Wert-Paar von CMake-Variablen, die als **-D** *_name_=_value_* an CMake übergeben werden. Wenn die buildanweisung des cmake-Projekts das Hinzufügen von Variablen direkt zur Datei " *cmakecache. txt* " angeben, empfiehlt es sich, diese stattdessen hinzuzufügen. Im folgenden Beispiel wird gezeigt, wie Sie die Name/Wert-Paare für das Toolset 14.14.26428 MSVC angeben können:

```json
"variables": [
    {
      "name": "CMAKE_CXX_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    },
    {
      "name": "CMAKE_C_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    }
  ]
```

Beachten Sie Folgendes: Wenn Sie die `"type"`nicht definieren, wird der `"STRING"` Typ standardmäßig angenommen.

## <a name="environments"></a>Umgebungen

Eine *Umgebung* kapselt die Umgebungsvariablen, die in dem Prozess festgelegt werden, der von Visual Studio zum Aufrufen von cmake. exe verwendet wird. Bei MSVC-Projekten sind die Variablen die Variablen, die in einer [Developer-Eingabeaufforderung](building-on-the-command-line.md) für eine bestimmte Plattform festgelegt sind. Beispielsweise ist die `msvc_x64_x64` Umgebung identisch mit dem Ausführen des **Developer-Eingabeaufforderung für vs 2017** oder **Developer-Eingabeaufforderung für vs 2019** mit den **-arch = amd64-host_arch = amd64-** Argumenten. Sie können die `env.{<variable_name>}`-Syntax in *cmakesettings. JSON* verwenden, um auf die einzelnen Umgebungsvariablen zu verweisen, z. b. zum Erstellen von Pfaden zu Ordnern.  Die folgenden vordefinierten Umgebungen werden bereitgestellt:

- linux_arm: richten Sie eine Remote Verbindung mit Arm Linux ein.
- linux_x64: Remote x64 Linux.
- linux_x86: für x86 Linux als Ziel Remote.
- msvc_arm: Arm-Zielfenster mit dem MSVC-Compiler.
- msvc_arm_x64: Arm-Zielfenster mit dem 64-Bit-MSVC-Compiler.
- msvc_arm64: arm64-Zielfenster mit dem MSVC-Compiler.
- msvc_arm64_x64: arm64-Zielfenster mit dem 64-Bit-MSVC-Compiler.
- msvc_x64: Ziel x64-Fenster mit dem MSVC-Compiler.
- msvc_x64_x64: x64-Zielfenster mit dem 64-Bit-MSVC-Compiler.
- msvc_x86: x86-Fenster mit dem MSVC-Compiler als Ziel.
- msvc_x86_x64: x86-Windows-Ziel mit dem 64-Bit-MSVC-Compiler.

### <a name="accessing-environment-variables-from-cmakeliststxt"></a>Zugreifen auf Umgebungsvariablen aus "CMakeLists. txt"

Aus einer CMakeLists. txt-Datei wird auf alle Umgebungsvariablen durch die Syntax `$ENV{variable_name}`verwiesen. Um die verfügbaren Variablen für eine Umgebung anzuzeigen, öffnen Sie die entsprechende Eingabeaufforderung, und geben Sie `SET`ein. Einige der Informationen in Umgebungsvariablen sind auch über cmake-System-Introspection-Variablen verfügbar, aber es ist möglicherweise bequemer, die Umgebungsvariable zu verwenden. Beispielsweise können die MSVC-Compilerversion oder Windows SDK Version problemlos über die Umgebungsvariablen abgerufen werden.

### <a name="custom-environment-variables"></a>Benutzerdefinierte Umgebungsvariablen

In `CMakeSettings.json`können Sie benutzerdefinierte Umgebungsvariablen Global oder pro Konfiguration im `environments` Array definieren. Eine benutzerdefinierte Umgebung ist eine bequeme Möglichkeit, einen Satz von Eigenschaften zu gruppieren, die Sie anstelle einer vordefinierten Umgebung verwenden können, oder um eine vordefinierte Umgebung zu erweitern oder zu ändern. Jedes Element im `environments`-Array besteht aus Folgendem:

- `namespace`: Benennt die Umgebung, sodass durch die Form `namespace.variable` über eine Konfiguration auf deren Variablen verwiesen werden kann. Das Standard Umgebungs Objekt wird `env` aufgerufen und mit bestimmten System Umgebungsvariablen, einschließlich `%USERPROFILE%`, aufgefüllt.
- `environment`: Identifiziert diese Gruppe von Variablen eindeutig. Ermöglicht der Gruppe, später in einem `inheritEnvironments`-Eintrag geerbt zu werden.
- `groupPriority`: eine ganze Zahl, die die Priorität dieser Variablen angibt, wenn diese ausgewertet werden. Elemente mit höherer Nummer werden zuerst ausgewertet.
- `inheritEnvironments`: ein Array von-Werten, die den Satz von Umgebungen angeben, die von dieser Gruppe geerbt werden. Durch dieses Feature können Sie Standardumgebungen vererben und benutzerdefinierte Umgebungsvariablen erstellen, die bei der Ausführung an „CMake.exe“ übergeben werden.

In folgendem Beispiel wird eine globale Variable (**BuildDir**) definiert, die in den Konfigurationen „x86-Debug“ und „x64-Debug“ geerbt wird. Jede Konfiguration verwendet die Variable, um den Wert für die Eigenschaft **buildRoot** der Konfiguration anzugeben. Beachten Sie ebenfalls, wie jede Konfiguration die Eigenschaft **inheritEnvironments** verwendet, um eine Variable anzugeben, die nur für diese Konfiguration gilt.

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x86 compiler.
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.BuildDir}\\${name}"    },
    {
      "name": "x64-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x64 compiler.
      "inheritEnvironments": [ "msvc_x64" ],
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

Im nächsten Beispiel definiert die x86-Debug-Konfiguration einen eigenen Wert für die Eigenschaft **BuildDir**. Dieser Wert überschreibt den Wert, der von der globalen Eigenschaft **BuildDir** festgelegt wird, sodass **BuildRoot** zu `D:\custom-builddir\x86-Debug` ausgewertet wird.

```json
{
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",

      // The syntax for this property is the same as the global one above.
      "environments": [
        {
          // Replace the global property entirely.
          "BuildDir": "D:\\custom-builddir"
          // This environment does not specify a namespace, hence by default "env" will be assumed.
          // "namespace" : "name" would require that this variable be referenced with "${name.BuildDir}".
        }
      ],

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      // Evaluates to "D:\custom-builddir\x86-Debug"
      "buildRoot": "${env.BuildDir}\\${name}"
    },
    {
      "name": "x64-Debug",

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x64" ],
      // Since this configuration doesn't modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="macros"></a>Makros

Die folgenden Makros können in " *cmakesettings. JSON*" verwendet werden:

- `${workspaceRoot}` – der vollständige Pfad des Arbeitsbereichs Ordners.
- `${workspaceHash}`: Hash des Speicherorts für den Arbeitsbereich; nützlich für das Erstellen eines eindeutigen Bezeichners für den aktuellen Arbeitsbereich (z.B. für die Verwendung in Ordnerpfaden)
- `${projectFile}`: der vollständige Pfad der CMakeLists.txt-Stammdatei
- `${projectDir}`: der vollständige Pfad des Ordners der CMakeLists.txt-Stammdatei
- `${thisFile}`: der vollständige Pfad der Datei `CMakeSettings.json`
- `${name}`: der Name der Konfiguration
- `${generator}`: der Name des CMake-Generators, der in dieser Konfiguration verwendet wurde

Alle Verweise auf Makros und Umgebungsvariablen in " *cmakesettings. JSON* " werden erweitert, bevor Sie an die Befehlszeile "cmake. exe" übergeben werden.

## <a name="ninja"></a> Ninja-Befehlszeilenargumente

Wenn keine Ziele festgelegt sind, wird das Standardziel erstellt.

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Option|Beschreibung|
|--------------|------------|
| --version  | Ausgabe der Ninja-Version ("1.7.1")|
|   -C DIR   | Änderung in DIR, bevor andere Aktionen ausgeführt werden|
|   -f FILE  | Angabe der Eingabedatei für den Build (Standard: build.ninja)|
|   -j N     | Ausführen von N gleichzeitigen Aufträgen (Standard: 14, abgeleitet von den verfügbaren CPUs)|
|   -k N     | Fortsetzen, bis N Aufträge fehlschlagen (Standard: 1)|
|   -l N     | Kein Starten von neuen Aufträgen, wenn die durchschnittliche Auslastung größer als N ist|
|   -n       | Testausführung (Befehle werden nicht ausgeführt, verhalten sich jedoch, als wären sie erfolgreich)|
|   -v       | Anzeigen aller Befehlszeilen während des Builds|
|   -d MODE  | Aktivieren des Debuggens (verwenden Sie „-d list“, um Modi aufzulisten)|
|   -t TOOL  | Ausführen eines Zusatztools (verwenden Sie „-t list“, um zusätzliche Tools aufzulisten). Beendet Optionen auf oberster Ebene; weitere Flags werden an das Tool übergeben.|
|   -w FLAG  | Anpassen von Warnungen (verwenden Sie „-w list“, um Warnungen aufzulisten)|

::: moniker-end
