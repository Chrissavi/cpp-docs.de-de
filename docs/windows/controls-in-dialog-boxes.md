---
title: Steuerelemente in Dialogfeldern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], dialog boxes
- dialog box controls, about dialog box controls
- dialog box controls
ms.assetid: e216c4f9-2fd4-429d-889a-8ebce7bad177
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: acbbbe0ecf1151f6159799592a8211bcf11fe7a1
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646942"
---
# <a name="controls-in-dialog-boxes"></a>Steuerelemente in Dialogfeldern
Sie können Steuerelemente hinzufügen, um ein Dialogfeld unter Verwendung der [Registerkarte "Dialog-Editor"](../windows/dialog-editor-tab-toolbox.md) in die [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox), können Sie wählen Sie das Steuerelement, Sie möchten, und ziehen Sie es in das Dialogfeld. Standardmäßig wird das Fenster "Toolbox" automatisch im Hintergrund festgelegt. Es wird als eine Registerkarte am linken Rand Ihrer Lösung angezeigt, wenn der Dialog-Editor geöffnet ist. Sie können jedoch anheften der **Toolbox** Einblick in die Position, indem Sie auf die **automatisch im Hintergrund** Schaltfläche in der oberen rechten Ecke des Fensters. Weitere Informationen zum Steuern des Verhaltens des in diesem Fenster finden Sie unter [Fensterverwaltung](/visualstudio/ide/customizing-window-layouts-in-visual-studio).  
  
 Die schnellste Möglichkeit zum Hinzufügen von Steuerelementen zu einem Dialogfeld, vorhandene Steuerelemente neu positionieren oder verschieben Sie die Steuerelemente in einem Dialogfeld in eine andere ist die Verwendung die Drag & Drop-Methode. Die Position des Steuerelements wird in einer gepunkteten Linie beschrieben werden, bis sie in das Dialogfeld gelöscht wird. Wenn Sie ein Steuerelement an ein Dialogfeld mit der Drag & Drop-Methode hinzufügen, erhält das Steuerelement eine Standardhöhe für diese Art von Steuerelement geeignet.  
  
 Wenn Sie ein Dialogfeld, das ein Steuerelement hinzufügen oder ihn neu anzuordnen, möglicherweise die endgültige Position von Führungslinien oder Ränder bestimmt werden oder ob Sie das Layoutraster aktiviert haben.  
  
 Nachdem Sie das Dialogfeld ein Steuerelement hinzugefügt haben, können Sie Eigenschaften wie z. B. die Beschriftung, im Ändern der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Sie können mehrere Steuerelemente auswählen und alle gleichzeitig, ihre Eigenschaften ändern.  
  
-   [Hinzufügen, Bearbeiten oder Löschen von Steuerelementen](adding-editing-or-deleting-controls.md)  
  
-   [Auswählen von Steuerelementen](../windows/selecting-controls.md)  
  
-   [Festlegen der Größe von individuellen Steuerelementen](../windows/sizing-individual-controls.md)  
  
-   [Festlegen der gleichen Breite, Höhe oder Größe für Steuerelemente](../windows/making-controls-the-same-width-height-or-size.md)  
  
-   [Festlegen der Größe des Kombinationsfelds und seiner Dropdownliste](setting-the-size-of-the-combo-box-and-its-drop-down-list.md)  
  
-   [Hinzufügen von Werten zu einem Kombinationsfeld-Steuerelement](../windows/adding-values-to-a-combo-box-control.md)  
  
-   [Festlegen der Breite einer horizontalen Bildlaufleiste](../windows/setting-the-width-of-a-horizontal-scroll-bar.md)  
  
-   [Die Anordnung von Steuerelementen in Dialogfeldern](../windows/arrangement-of-controls-on-dialog-boxes.md)  
  
-   [Benutzerdefinierte Steuerelemente im Dialog-Editor](custom-controls-in-the-dialog-editor.md)  
  
-   [Definieren von Tastenkombinationen](../windows/defining-mnemonics-access-keys.md)  
  
-   [Festlegen der Position und Größe eines Dialogfelds](../windows/specifying-the-location-and-size-of-a-dialog-box.md)  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente](../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [Dialogfeld-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md)   
 [Dialog-Editor](../windows/dialog-editor.md)