---
title: Erstellen eines MFC-DLL-Projekts
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.mfcdll.project
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
ms.openlocfilehash: 649a47abea23aedb9aa97bb4923e7a800348e27e
ms.sourcegitcommit: bf1940a39029dbbd861f95480f55e5e8bd25cda0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70108481"
---
# <a name="creating-an-mfc-dll-project"></a>Erstellen eines MFC-DLL-Projekts

Eine MFC-DLL ist eine Binärdatei und fungiert als gemeinsam genutzte Funktionsbibliothek, die von mehreren Anwendungen gleichzeitig verwendet werden kann. Am einfachsten erstellen Sie ein MFC-DLL-Projekt mit dem MFC-DLL-Assistenten.

> [!NOTE]
>  Die in der IDE dargestellten Features können sich je nach den aktiven Einstellungen oder der verwendeten Version von den in der Hilfe beschriebenen Features unterscheiden. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>So erstellen Sie ein MFC-DLL-Projekt mit dem MFC-DLL-Assistenten

1. Befolgen Sie die Anweisungen im Hilfethema [Erstellen einer MFC-Anwendung](creating-an-mfc-application.md) , und wählen Sie in der Liste der verfügbaren Vorlagen **MFC Dynamic Link Library** oder **MFC DLL** aus.

1. Definieren Sie die Anwendungseinstellungen auf der Seite " [Anwendungseinstellungen](../../mfc/reference/application-settings-mfc-dll-wizard.md) " des [MFC-DLL-Assistenten](../../mfc/reference/mfc-dll-wizard.md).

    > [!NOTE]
    >  Überspringen Sie diesen Schritt, um die Standardeinstellungen des Assistenten beizubehalten.

1. Klicken Sie auf **Fertig** stellen, um den Assistenten zu schließen und das neue Projekt in **Projektmappen-Explorer**zu öffnen.

Nachdem das Projekt erstellt wurde, können Sie die generierten Dateien im **Projektmappen-Explorer** anzeigen lassen. Weitere Informationen zu den vom Assistenten erstellten Dateien im Projekt finden Sie in der projekteigenen Datei "Readme.txt". Weitere Informationen zu den Dateitypen finden Sie unter [Für Visual Studio C++-Projekte erstellte Dateitypen](../../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Siehe auch

[C++-Projektvorlagen](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)<br/>
[Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Eigenschaftenseiten](../../build/reference/property-pages-visual-cpp.md)

