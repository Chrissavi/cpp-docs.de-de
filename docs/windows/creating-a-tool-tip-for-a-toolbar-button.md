---
title: Erstellen eine QuickInfo für eine Symbolleisten-Schaltfläche | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tool tips [C++], adding to toolbar buttons
- "\nin tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor, creating tool tips
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 41c2fa538a7888a2f14ae34fde9133b2872d13ba
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871766"
---
# <a name="creating-a-tool-tip-for-a-toolbar-button"></a>Erstellen einer QuickInfo für eine Symbolleisten-Schaltfläche
### <a name="to-create-a-tool-tip"></a>So erstellen eine QuickInfo  
  
1.  Wählen Sie die Symbolleisten-Schaltfläche.  
  
2.  In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)in der **Prompt** Eigenschaftenfeld, fügen Sie eine Beschreibung der Schaltfläche für die Statusleiste, nachdem die Nachricht, \n und der QuickInfo-Name des Tools hinzufügen.  
  
 Ein allgemeines Beispiel für eine QuickInfo ist die Schaltfläche "Drucken" in WordPad:  
  
 1. Öffnen Sie WordPad.  
  
 2. Zeigen Sie den Mauszeiger auf die **Drucken** Symbolleisten-Schaltfläche.  
  
 3. Beachten Sie, dass das Wort "Drucken" jetzt unter den Mauszeiger unverankert ist.  
  
 4. Betrachten Sie die Statusleiste (ganz unten in der WordPad-Fenster) – Beachten Sie, dass es jetzt der Text zeigt "Das aktive Dokument gedruckt".  
  
 "Drucken" in Schritt 3 ist der "Tipp Name des Tools", und die "das aktive Dokument gedruckt" in Schritt 4 ist "Beschreibung der Schaltfläche für die Statusleiste."  
  
 Wenn Sie möchten diesen Effekt mit der **Symbolleiste** -Editor Festlegen der **Prompt** Eigenschaft, um **druckt die \nKonsolendokument**.  
  
> [!NOTE]
>  Sie können bearbeiten, indem Aufforderungstext der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 Anforderungen  
  
 MFC oder ATL  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen, verschieben und Bearbeiten von Schaltflächen der Symbolleiste](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [Symbolleisten-Editor](../windows/toolbar-editor.md)

