---
title: Auswählen eines transparenten oder deckenden Hintergrundes (Bildbearbeitung für Symbole) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- opaque backgrounds
- background colors, images
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- background images
- images [C++], transparency
- images [C++], opaque background
- transparent backgrounds
- transparency, background
- transparent backgrounds, images
ms.assetid: 61b743d9-c86b-405d-9a81-0806431b4363
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 244e6a63bc16b5e83bb8419dbe1b53741d566e56
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857911"
---
# <a name="choosing-a-transparent-or-opaque-background-image-editor-for-icons"></a>Auswählen eines transparenten oder deckenden Hintergrunds (Bildbearbeitung für Symbole)
Wenn Sie verschieben oder kopieren eine Auswahl aus einem Image, sind alle Pixel in der Auswahl, die mit die aktuellen Hintergrundfarbe übereinstimmen, standardmäßig transparent; Sie nicht Pixel am Zielspeicherort verdeckt.  
  
 Sie können aus einem transparenten Hintergrund (Standard), ein nicht transparenter Hintergrund wechseln und wieder zurück. Wenn Sie eine Auswahltool verwenden die **transparenten Hintergrund** und **nicht transparenter Hintergrund** Optionen werden in der Optionsauswahl angezeigt, auf die **Grafik-Editor** Symbolleiste (wie unten dargestellt).  
  
 ![Optionen im Hintergrund &#45; undurchsichtig oder transparent](../windows/media/vcimageeditoropaqtranspback.gif "VcImageEditorOpaqTranspBack")  
Transparente und nicht transparenten Optionen auf der Symbolleiste des Grafik-Editor  
  
### <a name="to-switch-between-a-transparent-and-opaque-background"></a>So wechseln Sie zwischen einem transparent und nicht transparenter Hintergrund  
  
1.  In der **Grafik-Editor** -Symbolleiste klicken Sie auf die **Option** -Auswahl, und klicken Sie dann auf den entsprechenden Hintergrund:  
  
    -   **Nicht transparenter Hintergrund (O)**: vorhandene Bild wird von allen Bereichen der Markierung verdeckt.  
  
    -   **Transparenter Hintergrund (T)**: vorhandene Abbildung über Teile der Auswahl, die der aktuellen Hintergrundfarbe übereinstimmen.  
  
 \- oder –  
  
-   Auf der **Image** im Menü auswählen oder löschen **Deckend zeichnen**.  
  
 Sie können die Farbe des Hintergrunds ändern, während eine Auswahl bereits aktiv ist zu ändern, welche Teile des Bilds transparent sind.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 Anforderungen  
  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Arbeiten mit Farben](../windows/working-with-color-image-editor-for-icons.md)