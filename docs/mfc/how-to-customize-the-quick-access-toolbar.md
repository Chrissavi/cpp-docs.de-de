---
title: 'Vorgehensweise: Anpassen der Symbolleiste für den schnell Zugriff'
ms.date: 09/07/2019
helpviewer_keywords:
- quick access toolbar [MFC], customization
ms.assetid: 2554099b-0c89-4605-9249-31bf9cbcefe0
ms.openlocfilehash: 8b2eb6f7c80c77f69e2bbb65b7bb31a385014c8c
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907779"
---
# <a name="how-to-customize-the-quick-access-toolbar"></a>Vorgehensweise: Anpassen der Symbolleiste für den schnell Zugriff

Die Symbolleiste für den schnell Zugriff (QAT) ist eine anpassbare Symbolleiste, die eine Reihe von Befehlen enthält, die entweder neben der Anwendungs Schaltfläche oder unter den Registerkarten Kategorie angezeigt werden. Die folgende Abbildung zeigt eine typische Symbolleiste für den schnell Zugriff.

![Symbolleiste für das MFC-Menüband](../mfc/media/quick_access_toolbar.png "Symbolleiste für das MFC-Menüband")

Um die Symbolleiste für den schnell Zugriff anzupassen, öffnen Sie Sie im Fenster **Eigenschaften** , ändern Sie die zugehörigen Befehle, und klicken Sie dann auf das Menüband-Steuerelement

### <a name="to-open-the-quick-access-toolbar-in-the-properties-window"></a>So öffnen Sie die Symbolleiste für den schnell Zugriff im Eigenschaftenfenster

1. Klicken Sie in Visual Studio im Menü **Ansicht** auf **Ressourcenansicht**.

1. Doppelklicken Sie in **Ressourcenansicht**auf die Menüband-Ressource, um Sie auf der Entwurfs Oberfläche anzuzeigen.

1. Klicken Sie auf der Entwurfs Oberfläche mit der rechten Maustaste auf das Symbolleisten Menü schnell Zugriff und dann auf **Eigenschaften**.

## <a name="quick-access-toolbar-properties"></a>Symbolleisten Eigenschaften für den schnell Zugriff

In der folgenden Tabelle werden die Eigenschaften der Symbolleiste für den schnell Zugriff definiert.

|Eigenschaft|Definition|
|--------------|----------------|
|QAT-Position|Gibt die Position der Symbolleiste für den schnell Zugriff an, wenn die Anwendung gestartet wird. Die Position kann entweder **oberhalb** oder **unterhalb** des Menüband-Steuer Elements sein.|
|QAT-Elemente|Gibt die Befehle an, die für die Symbolleiste für den schnell Zugriff verfügbar sind.|

#### <a name="to-add-or-remove-commands-on-the-quick-access-toolbar"></a>So fügen Sie Befehle auf der Symbolleiste für den schnell Zugriff hinzu

1. Klicken Sie im Fenster **Eigenschaften** auf **QAT Items**, und klicken Sie dann auf die Schaltfläche mit den Auslassungs Punkten **(...)** .

1. Mithilfe der Schaltflächen **Hinzufügen** und **Entfernen** im Dialogfeld **QAT** -Element-Editor können Sie die Liste der Befehle auf der Symbolleiste für den schnell Zugriff ändern.

1. Wenn Sie möchten, dass ein Befehl sowohl auf der Symbolleiste für den schnell Zugriff als auch im Symbolleisten Menü für den schnell Zugriff angezeigt wird, aktivieren Sie das Kontrollkästchen neben dem Befehl. Wenn Sie möchten, dass der Befehl nur im Menü angezeigt wird, deaktivieren Sie das Kontrollkästchen.

## <a name="previewing-the-ribbon"></a>Anzeigen der Vorschau der Multifunktionsleiste

Symbolleisten Befehle für den schnell Zugriff werden nicht auf der Entwurfs Oberfläche angezeigt. Um diese anzuzeigen, müssen Sie entweder eine Vorschau der Multifunktionsleiste anzeigen oder die Anwendung ausführen.

#### <a name="to-preview-the-ribbon-control"></a>So können Sie eine Vorschau des Menüband

- Klicken Sie auf der **Symbolleiste des Menüband-Editors**auf **Menüband testen**

## <a name="see-also"></a>Siehe auch

[Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)
