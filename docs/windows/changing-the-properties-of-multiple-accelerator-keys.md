---
title: Ändern der Eigenschaften mehrerer Zugriffstasten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [C++], property changing
- accelerator tables [C++], changing properties
ms.assetid: b55c9bd6-b430-48bb-b942-0e6f21d7abf9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11705fcbcdb3dc73fe5c3a87844b2bc5d90cd135
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33913017"
---
# <a name="changing-the-properties-of-multiple-accelerator-keys"></a>Ändern der Eigenschaften mehrerer Zugriffstasten
### <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>Zum Ändern der Eigenschaften mehrerer Zugriffstasten  
  
1.  Öffnen Sie die Zugriffstastentabelle, indem Sie doppelklicken auf das Symbol in [Ressourcenansicht](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Wählen Sie die Zugriffstasten, die Sie ändern, indem Sie sie gedrückt halten, möchten die **STRG** -Taste Sie jeweils klicken.  
  
3.  Wechseln Sie zu der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) , und geben Sie die Werte aller ausgewählten Zugriffstasten gemeinsam nutzen.  
  
    > [!NOTE]
    >  Jeder Modifiziererwert wird als eine boolesche Eigenschaft im Eigenschaftenfenster angezeigt. Wenn Sie ändern eine [Modifizierer](../windows/accelerator-modifier-property.md) Wert im Fenster Eigenschaften die Zugriffstastentabelle behandelt das new-Modifizierer als Zusatz zum keine Modifizierer, die zuvor vorhanden waren. Aus diesem Grund, wenn Sie festlegen, dass alle Modifiziererwerte müssen Sie alle damit stellen Sie sicher, dass alle Zugriffstasten Modifizierer dieselben Einstellungen verwenden.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Bearbeiten von Zugriffstastentabellen](../windows/editing-accelerator-tables.md)   
 [Zugriffstasten-Editor](../windows/accelerator-editor.md)