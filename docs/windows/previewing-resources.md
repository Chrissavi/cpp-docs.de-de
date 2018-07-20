---
title: Anzeigen einer Vorschau Ressourcen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- resource previews
- code, viewing
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 32d0082d050ceb391a4346e2a4a38ff71c3cf2a3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878670"
---
# <a name="previewing-resources"></a>Anzeigen von Ressourcen in der Vorschau
Ausführen einer Vorschau für Ihre Ressourcen können Sie grafische Ressourcen anzeigen, ohne sie zu öffnen. Anzeigen einer Vorschau ist auch nützlich für ausführbare Dateien, nachdem Sie sie kompiliert haben, da der Ressourcen-IDs in Zahlen zu ändern. Da diese numerischen Bezeichnern nicht oft genug Informationen bereitstellen, hilft der Ressourcenvorschau schnell identifizieren.  
  
 Sie können das visuelle Layout der die folgenden Ressourcentypen Vorschau anzeigen:  
  
-   Bitmap  
  
-   Dialogfeld  
  
-   Symbol  
  
-   Menü  
  
-   Cursor  
  
-   Symbolleiste  
  
 Die Vorschau-Funktion gilt nicht für die Zugriffstaste, Manifest Zeichenfolgentabelle und Versionsinformationen Ressourcen.  
  
### <a name="to-preview-resources"></a>Um Ressourcen in der Vorschau anzeigen  
  
1.  In [Ressourcenansicht](../windows/resource-view-window.md) oder einem Dokumentfenster angezeigt, wählen Sie die Ressource, z. B. "IDD_ABOUTBOX".  
  
     **Hinweis** Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), klicken Sie auf die **Eigenschaftenseiten** Schaltfläche.  
  
     \- oder –  
  
3.  Auf der **Ansicht** Menü klicken Sie auf **Eigenschaftenseiten**.  
  
     Die Eigenschaftenseite für die Ressource wird geöffnet, zeigt eine Vorschau der Ressource. Sie können mithilfe der nach-oben und nach-unten-Taste, um das Strukturansicht-Steuerelement in der Ressourcenansicht oder das Dokumentfenster zu navigieren. Die Eigenschaftenseite bleibt geöffnet und zeigt alle Ressourcen, die Fokus hat und kann in der Vorschau angezeigt werden.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Öffnen eine Ressourcenskriptdatei außerhalb eines Projekts (eigenständig)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)

