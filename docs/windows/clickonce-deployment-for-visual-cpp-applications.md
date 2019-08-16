---
title: ClickOnce-Bereitstellung für Visual C++-Anwendungen
ms.date: 11/04/2016
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
ms.openlocfilehash: 4408db9d129c03ee5df9b006b03c6586df02afb1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513765"
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>ClickOnce-Bereitstellung für Visual C++-Anwendungen

Visual Studio bietet zwei verschiedene Technologien für die Bereitstellung von Windows-Anwendungen: Die Bereitstellung mit ClickOnce oder dem [Windows Installer](/windows/win32/Msi/windows-installer-portal).

## <a name="clickonce-deployment-in-c"></a>ClickOnce-Bereitstellung in C++

Die visuelle C++ Entwicklungsumgebung unterstützt die Bereitstellung von Visual Studio C++ -Projekten mit ClickOnce nicht direkt, aber die Tools sind zur Verwendung verfügbar.

> [!NOTE]
>  Visual Studio unterstützt ClickOnce in den Visual C#- und Visual Basic-Entwicklungsumgebungen. Wenn Ihr Visual Studio C++ -Projekt eine Abhängigkeit von einem visuellen C# Projekt ist, können Sie die Anwendung (einschließlich ihrer Abhängigkeiten) mithilfe der ClickOnce-Bereitstellung C# aus der visuellen Entwicklungsumgebung veröffentlichen.

Sie müssen zunächst ein [ClickOnce-Anwendungsmanifest](/visualstudio/deployment/clickonce-application-manifest) und ein [ClickOnce-Bereitstellungsmanifest](/visualstudio/deployment/clickonce-deployment-manifest) mithilfe von [Mage.exe (Manifest Generation and Editing Tool)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) oder der GUI-Version des Tools erstellen, um eine Visual C++-Anwendung mit ClickOnce bereitzustellen (Informationen finden Sie unter [MageUI.exe (Manifest Generation and Editing Tool, grafischer Client)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).

Sie verwenden zunächst Mage.exe, um das Anwendungsmanifest zu erstellen; die so erstellte Datei hat die Erweiterung .manifest. Anschließend verwenden Sie Mage.exe, um das Bereitstellungsmanifest zu erstellen; die erstellte Datei hat die Erweiterung .application. Danach signieren Sie die Manifeste.

Im Anwendungsmanifest muss der Zielprozessor (**x86**, **x64** oder **ARM**) angegeben werden. Informationen zu diesen Optionen finden Sie unter [Deploying Prerequisites for 64-bit Applications (Bereitstellen der erforderlichen Komponenten für 64-Bit-Anwendungen)](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications).

Die Namen des Anwendungs- und des Bereitstellungsmanifests müssen sich vom Namen der C++-Anwendung unterscheiden. Dadurch wird ein Konflikt vermieden zwischen dem durch Mage.exe erstellten Anwendungsmanifest und dem externen Manifest, welches Teil der C++-Anwendung ist.

Im Rahmen der Bereitstellung müssen alle Visual C++-Bibliotheken installiert werden, von denen die Anwendung abhängt. Zum Bestimmen der Abhängigkeiten einer einzelnen Anwendung können Sie depends.exe oder das Dienstprogramm DUMPBIN mit der Option /DEPENDENTS verwenden. Weitere Informationen zu Abhängigkeiten finden Sie unter [Understanding the Dependencies of a Visual C++ Application (Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung)](understanding-the-dependencies-of-a-visual-cpp-application.md). Möglicherweise müssen Sie „VCRedist.exe“ ausführen. Dieses Hilfsprogramm installiert Visual C++-Bibliotheken auf dem Zielcomputer.

Möglicherweise müssen Sie für die Anwendung einen Bootstrapper (Programm zum Installieren erforderlicher Komponenten) erstellen, um die erforderlichen Komponenten bereitzustellen. Informationen zum Bootstrapper finden Sie unter [Creating Bootstrapper Packages (Erstellen von Bootstrapperpaketen)](/visualstudio/deployment/creating-bootstrapper-packages).

Eine ausführlichere Beschreibung der Technologie finden Sie unter [ClickOnce Security and Deployment (ClickOnce-Sicherheit und Bereitstellung)](/visualstudio/deployment/clickonce-security-and-deployment). Ein ausführliches Beispiel der ClickOnce-Bereitstellung finden Sie unter [Walkthrough: Manually Deploying a ClickOnce Application (Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung)](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).

## <a name="see-also"></a>Siehe auch

[Mage.exe (Tool zum Generieren und Bearbeiten von Manifesten)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)<br>
[MageUI.exe (Tool zum Generieren und Bearbeiten von Manifesten, grafischer Client)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)<br>
[Makecert.exe (Tool für die Zertifikaterstellung)](/windows/win32/SecCrypto/makecert)<br>
[Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](deploying-native-desktop-applications-visual-cpp.md)<br>
[Bereitstellen von Anwendungen, Diensten und Komponenten](/visualstudio/deployment/deploying-applications-services-and-components)<br>
[ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[Erstellen von Bootstrapperpaketen](/visualstudio/deployment/creating-bootstrapper-packages)<br>
[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br>
[Interoperabilität von nativem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)
