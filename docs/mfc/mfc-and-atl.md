---
title: MFC und ATL
ms.date: 01/24/2018
ms.assetid: 31b1a3a8-4154-4c4a-af10-fafc23ecdc5c
ms.openlocfilehash: 54498ddf8999379d93c899c05aa41fe224616ea3
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525433"
---
# <a name="mfc-and-atl"></a>MFC und ATL

Die Microsoft Foundation Classes (MFC) stellen einen objektorientierten C++-Wrapper für Win32 für die schnelle Entwicklung von systemeigenen Desktopanwendungen bereit. Die ATL (Active Template Library) ist eine Wrapperbibliothek, mit der COM-Entwicklung vereinfacht wird und die umfassend zum Erstellen von ActiveX-Steuerelementen verwendet wird.

Sie können MFC- oder ATL-Programme mit der Visual Studio Community Edition oder höher erstellen. Bei den Express-Editionen wird MFC oder ATL nicht unterstützt.

In Visual Studio 2015 ist Visual C++ eine optionale Komponente und die MFC- und ATL-Komponenten sind optionale Unterkomponenten unter Visual C++. Wenn Sie diese Komponenten bei der ersten Installation von Visual Studio nicht auswählen, werden Sie zu deren Installation aufgefordert, wenn Sie das erste Mal versuchen, ein MFC- oder ATL-Projekt zu erstellen oder zu öffnen.

In Visual Studio 2017 und höher, MFC- und ATL-sind optionale Unterkomponenten unter der **Desktopentwicklung mit C++** Workload im Visual Studio-Installer-Programm. Sie können die ATL-Unterstützung ohne MFC installieren oder MFC und ATL-Unterstützung (MFC hängt von ATL) kombiniert. Weitere Informationen zu Workloads und Komponenten finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="related-articles"></a>Verwandte Artikel

|Titel|Beschreibung|
|-----------|-----------------|
|[MFC-Desktopanwendungen](../mfc/mfc-desktop-applications.md)|Microsoft Foundation Classes stellen einen dünnen objektorientierten Wrapper für Win32 bereit, um die schnelle Entwicklung von GUI-Anwendungen in C++ zu ermöglichen.|
|[ATL-COM-Desktop-Komponenten](../atl/atl-com-desktop-components.md)|ATL stellt Klassenvorlagen und andere Verwendungskonstrukte zur Vereinfachung von der Erstellung von COM-Objekten in C++ bereit.|
|[Freigegebene ATL-/MFC-Klassen](../atl-mfc-shared/atl-mfc-shared-classes.md)|Verweise für [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md) und andere von MFC und ATL freigegebenen Klassen.|
|[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)|Mit dem Ressourcen-Editor können Sie UI-Ressourcen wie Zeichenfolgen, Bilder und Dialogfelder bearbeiten.|
|[Visual C++](../overview/visual-cpp-in-visual-studio.md)|Übergeordnetes Thema für alle C++-Inhalte in der MSDN Library.|