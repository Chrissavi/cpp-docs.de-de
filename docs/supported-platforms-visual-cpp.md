---
title: Unterstützte Plattformen (Visual C++)
ms.date: 11/04/2016
ms.technology: cpp-tools
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
author: mikeblome
ms.author: mblome
ms.openlocfilehash: c8bd090acf94876ee7939b5d1d80613f688b89d7
ms.sourcegitcommit: fbc05d8581913bca6eff664e5ecfcda8e471b8b1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2019
ms.locfileid: "56809632"
---
# <a name="supported-platforms-visual-c"></a>Unterstützte Plattformen (Visual C++)

Die Apps, die mit Visual Studio erstellt werden, können wie folgt für verschiedene Plattformen eingesetzt werden.

|Betriebssystem|x86|x64|ARM|
|----------------------|---------|---------|---------|
|Windows XP|X\*|X\*||
|Windows Server 2003|X\*|X\*||
|Windows Vista|X|X||
|Windows Server 2008|X|X||
|Windows 7|X|X||
|Windows Server 2012 R2|X|X||
|Windows 8|X|X|X|
|Windows 8.1|X|X|X|
|Windows 10|X|X|X|
|Android \*\*|X|X|X|
|iOS \*\*|X|X|X|
|Linux \*\*\*|X|X|X|

\* Sie können das in Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 und Visual Studio 2012 Update 1 oder höher enthaltene Windows XP-Plattformtoolset zum Erstellen von Windows XP- und Windows Server 2003-Projekten verwenden. Weitere Informationen zum Verwenden dieses Plattformtoolsets finden Sie unter [Konfigurieren von C++11-Programmen für Windows XP](build/configuring-programs-for-windows-xp.md). Weitere Informationen zum Ändern des Plattformtoolsets finden Sie unter [How to: Modify the Target Framework and Platform Toolset (Vorgehensweise: Ändern des Zielframeworks und des Plattformtoolsets)](build/how-to-modify-the-target-framework-and-platform-toolset.md).

\*\* Sie können die Workload **Mobile-Entwicklung mit C++** im Installer für Visual Studio 2017 (oder die optionale Komponente **Visual C++ für plattformübergreifende Mobile-Entwicklung** im Visual Studio 2015-Setup) installieren, um für iOS- oder Android-Plattformen zu programmieren. Weitere Informationen finden Sie unter [Installieren von Visual C++ für die plattformübergreifende mobile Entwicklung](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development). Um iOS-Code zu erstellen, müssen Sie einen Macintosh-Computer besitzen und weitere Anforderungen erfüllen. Eine Liste der Voraussetzungen und Installationsanweisungen finden Sie unter [Installieren und Konfigurieren von Tools zum Erstellen mit iOS](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios). Sie können x86- oder ARM-Code für die Zielhardware erstellen. Verwenden Sie x86-Konfigurationen zum Entwickeln für den iOS-Simulator, Microsoft Visual Studio-Emulator für Android und einige Android-Geräte. Verwenden Sie ARM-Konfigurationen für iOS-Geräte und die meisten Android-Geräte.

\*\*\* Sie können die Workload **Linux-Entwicklung mit C++** im Installer für Visual Studio 2017 installieren, um für Linux-Plattformen zu programmieren. Anweisungen hierzu finden Sie unter [Herunterladen, Installieren und Einrichten der Linux-Workload](linux/download-install-and-setup-the-linux-development-workload.md). Dieses Toolset kompiliert Ihre ausführbare Datei auf dem Zielcomputer, sodass Sie Builds für jede unterstützte Architektur erstellen bauen können.

Weitere Informationen zum Festlegen der Zielplattformkonfiguration finden Sie unter [How to: Configure Visual C++ Projects to Target 64-Bit, x64 Platforms (Vorgehensweise: Konfigurieren von Visual C++-Projekten für 64-Bit-Zielplattformen (x64))](build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

## <a name="see-also"></a>Siehe auch

- [Visual C++-Tools und -Features in Visual Studio-Editionen](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)
- [Erste Schritte](/visualstudio/ide/getting-started-with-visual-cpp-in-visual-studio)
