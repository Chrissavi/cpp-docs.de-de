---
title: Portieren auf die universelle Windows-Plattform (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f662d2e4-8940-418d-8109-cb76cb8f8569
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eefb2347cfe3a46dabbf72a46fd46fcb16f57d38
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2018
ms.locfileid: "42578403"
---
# <a name="porting-to-the-universal-windows-platform-c"></a>Portieren auf die universelle Windows-Plattform (C++)

In diesem Thema finden Sie Informationen zum Portieren von vorhandenem C++-Code auf die Windows-10-Anwendungsplattform, die universelle Windows-Plattform. *Universell* bedeutet, Ihr Code kann auf allen Geräten unter Windows 10, einschließlich Desktopcomputern, Mobiltelefonen, Tablets, und künftigen Geräten unter Windows 10 ausgeführt werden. Erstellen Sie ein einzelnes Projekt und eine einzelne XAML-basierte Benutzeroberfläche, die auf allen Geräten mit Windows 10 funktioniert. Sie können dynamische Layout-Features in XAML verwenden, damit sich die Benutzeroberfläche der App an die unterschiedlichen Displaygrößen anpassen lässt.

Die Windows-Entwicklungscenter-Dokumentation enthält eine Anleitung zum Portieren von Windows 8.1-Apps auf die universelle Windows-Plattform. Weitere Informationen finden Sie unter [Wechsel von Windows-Runtime 8 zu UWP](/windows/uwp/porting/w8x-to-uwp-root). Obwohl sich das Handbuch vor allem auf C#-Code konzentriert, gilt ein Großteil der Anleitung für C++. In den folgenden Vorgehensweisen finden Sie detailliertere Informationen.

Dieses Thema enthält die folgenden Verfahren zum Portieren von Code für die UWP.

- [Portieren einer Windows 8.1 Store-App auf UWP](#BK_81StoreApp)

- [Portieren einer Windows 8.1-Runtime-Komponente auf UWP](#BK_81Component)

Wenn Sie über eine klassische Wind32-DLL-Datei für Desktopcomputer verfügen und sie über eine UWP-Anwendung aufrufen möchten, können Sie dies ebenfalls vornehmen. Auf diese Weise können Sie eine UWP-Benutzeroberflächenebene für eine vorhandene klassische Windows C++-Desktopcomputeranwendung oder Ihren plattformübergreifenden C++-Standardcode erstellen. Siehe [Vorgehensweise: Verwenden von vorhandenem C++-Code in einer universelle Windows-Plattform-App](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md).

## <a name="BK_81StoreApp"></a> Portieren einer Windows 8.1 Store-App auf die UWP

Wenn Sie eine Windows 8.1 Store-App haben, können Sie sie mithilfe dieses Verfahrens auf jedem Gerät mit Windows 10 unter UWP ausführen.  Am besten erstellen Sie das Projekt zunächst mit Visual Studio 2017 als Windows 8.1-Projekt, um durch Änderungen im Compiler und Bibliotheken entstandene Fehler zu beheben. Nachdem Sie dies vorgenommen haben, gibt es zwei Möglichkeiten, um dies zu einem Windows 10-UWP-Projekt umzuwandeln. Die einfachste Möglichkeit (wird in der folgenden Vorgehensweise erläutert) besteht darin, indem Sie ein universelles Windows-Projekt erstellen und Ihren vorhandenen Code hineinkopieren. Wenn Sie ein universelles Projekt für Windows 8.1-Desktopcomputer und Windows Phone 8.1 verwendet haben, beginnt das Projekt zwei unterschiedliche Layouts in XAML, endet jedoch mit einem einzelnen dynamischen Layout, das die Größe anpasst.

### <a name="to-port-a-windows-81-store-app-to-the-uwp"></a>So portieren Sie einer Windows 8.1 Store-App auf UWP

1. Falls noch nicht erfolgt, öffnen Sie Ihr Windows 8.1-App-Projekt in Visual Studio 2017, und befolgen Sie die Anweisungen zum Aktualisieren der Projektdatei.

   Sie müssen die **Windows 8.1-Tools im Visual Studio**-Setup installiert haben. Wenn Sie diese Tools nicht installiert haben, starten Sie das **Visual Studio**-Setup über das Fenster **Programme und Funktionen**. Klicken Sie auf **Visual Studio 2017**, und wählen Sie im Setup-Fenster **Ändern** aus. Suchen Sie nach **Windows 8.1-Tools**, stellen Sie sicher, dass diese Option ausgewählt ist, und klicken Sie auf **OK**.

2. Öffnen Sie das Fenster **Projekteigenschaften**, und legen Sie unter **C++** > **Allgemein** das **Plattformtoolset** auf **v141** (das Toolset für Visual Studio 2017) fest.

3. Erstellen Sie das Projekt als Windows 8.1-Projekt, und lösen Sie alle Buildfehler. Fehler in dieser Phase liegen wahrscheinlich an wichtigen Änderungen an den Build-Tools und Bibliotheken. Unter [Änderungsverlauf von Visual C++ von 2003 bis 2015](../porting/visual-cpp-change-history-2003-2015.md) finden Sie eine ausführliche Erläuterung der Änderungen, die sich auf Ihren Code auswirken.

   Nachdem das Projekt ordnungsgemäß erstellt wurde, können Sie es auf universelles Windows (Windows 10) portieren.

4. Erstellen Sie ein neues universelles Windows-App-Projekt mit der leeren Vorlage. Sie möchten dem Projekt möglicherweise den gleichen Namen wie dem vorhandenen Projekt geben, obwohl sich die Projekte dazu in unterschiedlichen Verzeichnissen befinden müssen.

5. Schließen Sie die Projektmappe, und verwenden Sie dann den **Windows Explorer** oder die Befehlszeile, kopieren Sie die Codedateien (mit den Dateierweiterungen CPP, H und XAML) aus Ihrem Windows 8.1-Projekt in denselben Ordner wie die Projektdatei (VCXPROJ) für das Projekt, das Sie in Schritt 1 erstellt haben. Kopieren Sie nicht die Datei "Package.appxmanifest", und wenn Sie eigenen Code für Windows 8.1 Desktop- und -Phone haben, wählen Sie zunächst eines als Portierungsziel aus (Sie müssen später zur Angleichung an die andere Anpassungen vornehmen). Achten Sie darauf, dass Sie ebenfalls alle Inhalte aus den Unterordnern kopieren. Wenn Sie aufgefordert werden, wählen Sie aus, dass Dateien mit doppelten Namen ersetzt werden.

6. Öffnen Sie die Projektmappe erneut, und klicken Sie im Kontextmenü für den Projektknoten auf **Hinzufügen** > **Vorhandenes Element hinzufügen**. Wählen Sie alle kopierten Dateien, außer denen, die bereits Teil des Projekts sind.

   Überprüfen Sie die Unterordner, und stellen Sie sicher, dass die darin enthaltenen Dateien ebenfalls hinzufügt werden.

7. Wenn Sie nicht den gleichen Projektnamen wie bei dem alten Projekt verwenden, öffnen Sie die Datei „Package.appxmanifest“, und aktualisieren Sie den **Einstiegspunkt** entsprechend des Namespacenamens für die `App`-Klasse.

   Das Feld **Einstiegspunkt** in der Datei „Package.appxmanifest“ enthält einen bereichsbezogenen Namen für die `App`-Klasse, die den Namespace enthält, der die `App`-Klasse enthält. Wenn Sie ein universelles Windows-Projekt erstellen, wird für den Namespace der Name des Projekts festgelegt. Wenn Unterschiede zu den von Ihnen aus dem alten Projekt kopierten Dateien bestehen, müssen Sie eines der beiden Projekte aktualisieren, damit sie übereinstimmen.

8. Erstellen Sie das Projekt, und lösen Sie alle Buildfehler durch wichtige Änderungen zwischen den verschiedenen Versionen des Windows SDK.

9. Führen Sie das Projekt auf dem lokalen Desktop aus. Stellen Sie sicher, dass keine Bereitstellungsfehler vorliegen, das Layout der App angemessen ist und es korrekt auf dem Desktop funktioniert.

10. Wenn Sie unterschiedliche Codedateien für XAML für ein anderes Gerät hatten, wie z. B. Windows Phone 8.1, überprüfen Sie den Code, und ermitteln Sie, wo er von dem für das Standardgerät abweicht. Ist der Unterschied nur im Layout, können Sie die XAML-Datei mit einem **Manager für den visuellen Zustand** bearbeiten, damit sie an die Bildschirmgröße der Anzeige angepasst werden kann. Um weitere Unterschiede anzuzeigen, können Sie die Bedingungsabschnitte in Ihrem Code mithilfe der folgenden #if-Anweisungen verwenden.

    ```cpp
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)
    ```

     Diese Anweisungen gelten jeweils für UWP-Apps, Windows Phone Store-Apps, beide oder keines von beiden (nur klassische Win32-Desktop-Apps). Diese Makros sind nur in Windows SDK 8.1 und höher verfügbar. Wenn Code mit früheren Versionen des Windows SDK oder für andere Plattformen als Windows kompiliert werden muss, sollten Sie daher auch den Fall berücksichtigen, dass sie nicht definiert sind.

11. Führen Sie die App in einem Emulator oder auf einem physischen Gerät, dessen Gerätetyp von Ihrer App unterstützt wird. Um einen Emulator auszuführen, müssen Sie Visual Studio auf einem physischen Computer ausführen, nicht auf einem virtuellen Computer.

## <a name="BK_81Component"></a> Portieren einer Windows 8.1-Runtime-Komponente auf UWP

Wenn Sie eine DLL oder eine Windows-Runtime-Komponente besitzen, die bereits mit Windows 8.1 Store-Apps funktioniert, können Sie dieses Verfahren verwenden, um die Komponente oder DLL abzurufen, die mit UWP und Windows 10 funktioniert. Das grundlegende Verfahren besteht darin, ein neues Projekt zu erstellen und Ihren Code hinein zu kopieren.

### <a name="to-port-a-windows-81-runtime-component-to-the-uwp"></a>So portieren Sie eine Windows 8.1-Runtime-Komponente zur UWP

1. Suchen Sie im Dialogfeld **Neues Projekt** in Visual Studio 2017 den Knoten **Windows Universal**. Wenn dieser Knoten nicht angezeigt wird, installieren Sie zunächst die [Tools für Windows 10](http://go.microsoft.com/fwlink/p/?LinkID=617903) . Wählen Sie die Vorlage **Komponente für Windows-Runtime** , benennen Sie Ihre Komponente, und wählen Sie die Schaltfläche **OK** aus. Der Komponentenname wird als der Namespacename verwendet. Sie möchten daher möglicherweise denselben Namen wie beim Namespace Ihres alten Projekts verwenden. Dafür müssen Sie das Projekt in einem Ordner erstellen, der sich vom alten unterscheidet. Wenn Sie einen anderen Namen auswählen, können Sie den Namespace in den generierten Codedateien aktualisieren.

2. Schließen Sie das Projekt.

3. Kopieren Sie sämtliche Codedateien (.cpp, .h, .xaml usw.) aus Ihrer Windows 8.1-Komponente in Ihr neu erstelltes Projekt. Kopieren Sie nicht die Datei „Package.appxmanifest“.

4. Beheben Sie alle Fehler, die auf Umbrechungsänderungen zwischen unterschiedlichen Versionen des Windows SDK zurückgehen.

## <a name="troubleshooting"></a>Problembehandlung

Im Rahmen des Portierens von Code für die UWP können verschiedene Fehler auftreten. Hier sind einige der möglichen Probleme, die auftreten können.

### <a name="project-configuration-issues"></a>Probleme bei der Projektkonfiguration

Sie erhalten möglicherweise diese Fehlermeldung:

```Output
could not find assembly 'platform.winmd': please specify the assembly search path using /AI or by setting the LIBPATH environment variable
```

In diesem Fall wird das Projekt nicht als universelles Windows-Projekt erstellt. Überprüfen Sie die Projektdatei, und stellen Sie sicher, dass sie über die richtigen XML-Elemente verfügt, die ein Projekt als universelles Windows-Projekt bezeichnen. Die folgenden Elemente sollten vorhanden sein (die Versionsnummer der Zielplattform weicht möglicherweise ab):

```xml
<AppContainerApplication>true</AppContainerApplication>
<ApplicationType>Windows Store</ApplicationType>
<WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>
<WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>
<ApplicationTypeRevision>10.0</ApplicationTypeRevision>
```

Wenn Sie ein neues UWP-Projekt mithilfe von Visual Studio erstellt haben, sollte dieser Fehler nicht angezeigt werden.

## <a name="see-also"></a>Siehe auch

[Visual C++: Portierungsanleitung](../porting/porting-to-the-universal-windows-platform-cpp.md)  
[Entwickeln von Apps für die universelle Windows-Plattform (UWP)](/visualstudio/cross-platform/develop-apps-for-the-universal-windows-platform-uwp)  