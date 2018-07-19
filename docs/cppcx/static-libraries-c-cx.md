---
title: Statische Bibliotheken (C + c++ / CX) | Microsoft Docs
ms.custom: ''
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ffa905cbe0fd49489bd3634cb927cce57ea4ddbc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090102"
---
# <a name="static-libraries-ccx"></a>Statische Bibliotheken (C++/CX)
Eine statische Bibliothek, die in einer app für die universelle Windows-Plattform (UWP) verwendet wird, kann ISO-Standard C++-Code, einschließlich der STL-Typen und außerdem Aufrufe für Win32-APIs, die nicht von der Windows-Runtime-app-Plattform ausgeschlossen sind enthalten. Eine statische Bibliothek nutzt Windows-Runtime-Komponenten und kann Windows-Runtime-Komponenten mit bestimmten Einschränkungen erstellen.  
  
## <a name="creating-static-libraries"></a>Erstellen von statischen Bibliotheken  
  
#### <a name="to-create-a-static-library-for-use-in-a-uwp-app"></a>So erstellen Sie eine statische Bibliothek zur Verwendung in einer uwp-app  
  
1.  Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**. Klicken Sie unter **Visual C++** > **universellen Windows-** auswählen **statische Bibliothek (Uwp)**.  
  
2.  Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus. In der **Eigenschaften** Dialogfeld auf die **Konfigurationseigenschaften** > **C/C++-** Seite **Windows Runtime-Erweiterung nutzen** auf **Ja (/ Zw)**.  
  
 Wenn Sie eine neue statische Bibliothek kompiliert, wenn Sie einen Aufruf an eine Win32-API ausführen, die für uwp-apps ausgeschlossen ist, löst der Compiler Fehler C3861 aus, die "Bezeichner wurde nicht gefunden." Um nach einer alternativen Methode zu suchen, die für die Windows-Runtime unterstützt wird, finden Sie unter [Alternativen zu Windows-APIs in uwp-apps](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).  
  
 Wenn Sie eine uwp-app-Projektmappe ein statisches C++-Bibliotheksprojekt hinzufügen, müssen Sie möglicherweise eigenschafteneinstellungen des Bibliotheksprojekts aktualisieren, sodass die uwp-Support-Eigenschaft, um festgelegt ist **Ja**. Ohne diese Einstellung wird der Code aufgebaut und verknüpft, jedoch ein Fehler tritt auf, wenn Sie versuchen, überprüfen die app für Microsoft Store. Die statische Bibliothek sollte mit den gleichen Compilereinstellungen wie das Projekt kompiliert werden, in dem sie verwendet werden.  
  
 Wenn Sie eine statische Bibliothek nutzen, die öffentliche `ref` -Klassen, öffentliche Schnittstellenklassen oder öffentliche Wertklassen erstellt, gibt der Linker folgende Warnung aus:  
  
> **Warnung LNK4264:** archivieren, die in einer statischen Bibliothek archiviert mit/zw kompilierte Objektdatei Beachten Sie, dass beim Erstellen von Windows-Runtime-Typen nicht empfohlen wird, mit einer statischen Bibliothek verknüpft werden, die Windows-Runtime-Metadaten enthält.  
  
 Sie können die Warnung sicher ignorieren, nur, wenn die statische Bibliothek nicht-Windows-Runtime-Komponenten erzeugt, die außerhalb der Bibliothek selbst genutzt werden. Wenn die Bibliothek keine Komponenten verwendet, die sie definiert, kann der Linker die Implementierung optimieren, obwohl die öffentlichen Metadaten die Typinformationen enthalten. Das bedeutet, dass öffentliche Komponenten in einer statischen Bibliothek kompiliert, aber nicht zur Laufzeit aktiviert werden. Aus diesem Grund muss jede Windows-Runtime-Komponente, die für die Nutzung vorgesehen ist, von anderen Komponenten oder apps in einer Dynamic Link Library (DLL) implementiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Threading und Marshalling](../cppcx/threading-and-marshaling-c-cx.md)