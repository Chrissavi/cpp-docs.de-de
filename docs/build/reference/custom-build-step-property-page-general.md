---
title: 'Eigenschaftenseite für benutzerdefinierten Buildschritt: Allgemein'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
ms.openlocfilehash: 329923140cf5a8f05e5c032ddb9e25c0ea45ec2a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273078"
---
# <a name="custom-build-step-property-page-general"></a>Eigenschaftenseite für benutzerdefinierten Buildschritt: Allgemein

Für jede Kombination von Projektkonfiguration und Zielplattform im Projekt können Sie einen benutzerdefinierten Schritt angeben, der ausgeführt werden muss, wenn das Projekt erstellt wird.

Die Linux-Version dieser Seite finden Sie unter [Benutzerdefinierte Buildschritteigenschaften (Linux C++)](../../linux/prop-pages/custom-build-step-linux.md).

## <a name="uielement-list"></a>UIElement-Liste

- **Befehlszeile**

   Der vom benutzerdefinierten Buildschritt auszuführende Befehl.

- **Beschreibung**

   Eine Meldung, die anzeigt, wann der benutzerdefinierte Buildschritt läuft.

- **Ausgaben**

   Die Ausgabedatei, die der benutzerdefinierte Buildschritt generiert. Diese Einstellung ist erforderlich, damit inkrementelle Builds ordnungsgemäß funktionieren.

- **Zusätzliche Abhängigkeiten**

   Eine durch Semikolons getrennte Liste von zusätzlichen Eingabedateien, die für den benutzerdefinierten Buildschritt verwendet werden soll.

- **Im Anschluss ausführen und vorher ausführen**

   Diese Optionen definieren, wann ein benutzerdefinierter Buildschritt im Buildprozess relativ zu den aufgelisteten Zielen ausgeführt wird. Die am häufigste aufgelisteten Ziele sind BuildGenerateSources, BuildCompile und BuildLink, da sie die Hauptschritte im Buildprozess darstellen. Andere oft aufgelisteten Ziele sind Midl, CLCompile und Link.

- **Ausgabe als Inhalt behandeln**

   Diese Option ist nur bei der Universellen Windows-Plattform oder Windows Phone-Apps von Bedeutung, bei denen alle Inhaltsdateien im APPX-Paket enthalten sind.

### <a name="to-specify-a-custom-build-step"></a>So legen Sie einen benutzerdefinierten Buildschritt fest

1. Wählen Sie in der Menüleiste **Projekt** und **Eigenschaften** aus. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Navigieren Sie im Dialogfeld **Eigenschaftenseiten** zur Seite **Konfigurationseigenschaften** > **Benutzerdefinierter Buildschritt** > **Allgemein**.

1. Ändern Sie die Einstellungen.

## <a name="see-also"></a>Siehe auch

[Referenz für C++-Projekt Seite](property-pages-visual-cpp.md)
