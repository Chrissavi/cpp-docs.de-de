---
title: Gruppieren von Optionsfeldern in einem Dialogfeld | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.grouping
dev_langs:
- C++
helpviewer_keywords:
- member variables, adding to radio button groups
- variables, dialog box control member variables
- dialog box controls, grouping radio buttons
- grouping controls
- radio buttons, grouping on dialog boxes
ms.assetid: 3cc43f9e-56c8-4faa-9930-ce81733c69de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c3d0e20d8b2b88a7141672117d4c0b036682953e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641417"
---
# <a name="grouping-radio-buttons-on-a-dialog-box"></a>Gruppieren von Optionsfeldern in einem Dialogfeld
Wenn Sie ein Dialogfeld Optionsschaltflächen hinzufügen, behandeln sie als Gruppe durch Festlegen einer **Gruppe** -Eigenschaft in der **Eigenschaften** Fenster für die erste Schaltfläche in der Gruppe. Eine Steuerelement-ID für das betreffende Optionsfeld wird dann im [Assistent zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md)angezeigt und ermöglicht das Hinzufügen einer Membervariablen zur Gruppe der Optionsfelder.  
  
 Ein Dialogfeld kann mehrere Gruppen von Optionsfeldern enthalten, und jede Gruppe sollte mithilfe der folgenden Prozedur hinzugefügt werden.  
  
### <a name="to-add-a-group-of-radio-buttons-to-a-dialog-box"></a>So fügen Sie einem Dialogfeld eine Gruppe von Optionsfeldern hinzu  
  
1.  Wählen Sie das Optionsfeld-Steuerelement im Fenster [Toolbox](/visualstudio/ide/reference/toolbox) aus, und klicken Sie an die Stelle im Dialogfeld, an der Sie das Steuerelement platzieren möchten.  
  
2.  Wiederholen Sie Schritt 1, um so viele Optionsfelder hinzuzufügen, wie Sie benötigen. Achten Sie darauf, dass die Optionsfelder in der Gruppe in der Aktivierreihenfolge aufeinander folgen (weitere Informationen finden Sie unter [Ändern der Aktivierreihenfolge von Steuerelementen](../windows/changing-the-tab-order-of-controls.md)).  
  
3.  Legen Sie im Fenster [Eigenschaften](/visualstudio/ide/reference/properties-window)die Eigenschaft **Gruppe** des *ersten* Optionsfelds in der Aktivierreihenfolge auf **Wahr**fest.  
  
     Durch das Ändern der Eigenschaft **Gruppe** auf **Wahr** wird dem Eintrag des Felds im Dialogfeld des Ressourcenscripts die Formatvorlage „WS_GROUP“ hinzugefügt und so sichergestellt, dass ein Benutzer immer nur ein Optionsfeld in der Feldgruppe aktivieren kann (wenn der Benutzer auf ein Optionsfeld klickt, werden die anderen in der gleichen Gruppe deaktiviert).  
  
    > [!NOTE]
    >  Die Eigenschaft **Gruppe** sollte nur für das erste Optionsfeld einer Gruppe auf **Wahr**festgelegt werden. Wenn Sie über weitere Steuerelemente verfügen, die nicht Teil der Optionsfeldgruppe sind, legen Sie die Eigenschaft **Gruppe** des ersten Steuerelements, *das sich außerhalb der Gruppe befindet* , ebenfalls auf **Wahr** fest. Sie können das erste Steuerelement außerhalb der Gruppe schnell identifizieren, durch Drücken von **STRG**+**D** auf die Aktivierreihenfolge anzuzeigen.  
  
### <a name="to-add-a-member-variable-for-the-radio-button-group"></a>So fügen Sie eine Membervariable für die Optionsfeldgruppe hinzu  
  
1.  Klicken Sie auf das erste Optionsfeld-Steuerelement in der Aktivierreihenfolge (das dominante Steuerelement, dessen Eigenschaft **Gruppe** auf „Wahr“ festgelegt ist).  
  
2.  Wählen Sie im Kontextmenü **Variable hinzufügen** aus.  
  
3.  Aktivieren Sie im [Assistent zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md)das Kontrollkästchen **Steuerungsvariable** , und aktivieren Sie dann das Optionsfeld **Wert** .  
  
4.  Geben Sie im Feld **Variablenname** einen Namen für die neue Membervariable ein.  
  
5.  In der **Variablentyp** wählen Sie im Listenfeld **Int** oder `int`.  
  
6.  Jetzt können Sie Ihren Code ändern, um festzulegen, welches Optionsfeld aus aktiviert angezeigt werden soll. Z. B. `m_radioBox1 = 0;` wählt das erste Optionsfeld in der Gruppe.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Anordnung von Steuerelementen in Dialogfeldern](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)