---
title: Bildlauf und Skalierung für Ansichten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handlers [MFC]
- scaling views [MFC]
- message handling [MFC], scroll bars in view class [MFC]
- scroll bars [MFC], messages
- scrolling views [MFC]
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9758c63562a19d6b9e458fd434108a92bbc8576
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379267"
---
# <a name="scrolling-and-scaling-views"></a>Bildlauf und Skalierung für Ansichten
MFC unterstützt, Sichten, die Bildlauf und Ansichten, die automatisch auf die Größe des Rahmenfensters skaliert werden, in dem diese angezeigt wird. Klasse `CScrollView` unterstützt beide Arten von Ansichten.  
  
 Weitere Informationen zu den Bildlauf und Skalierung finden Sie in der Klasse [CScrollView](../mfc/reference/cscrollview-class.md) in der *MFC-Referenz*. Ein fortlaufendes Beispiel finden Sie unter der [Scribble-Beispiel](../visual-cpp-samples.md).  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   Bildlauf in einer Ansicht  
  
-   Skalieren einer Ansicht  
  
-   [Koordinaten](http://msdn.microsoft.com/library/windows/desktop/dd145205)  
  
##  <a name="_core_scrolling_a_view"></a> Bildlauf in einer Ansicht  
 Häufig ist die Größe eines Dokuments größer als die Größe, die der Ansicht angezeigt werden kann. Dies kann auftreten, weil die Daten des Dokuments erhöht oder der Benutzer verkleinert das Fenster, das die Sicht frames. In solchen Fällen muss die Sicht Durchführen eines Bildlaufs unterstützen.  
  
 Jeder Ansicht kann behandeln Bildlaufleisten-Nachrichten in seiner `OnHScroll` und `OnVScroll` Memberfunktionen. Können Sie entweder implementieren Bildlaufleisten-Behandlung in diese Funktionen ausführen die gesamte Arbeit selbst, oder Sie können die `CScrollView` -Klasse zur Verarbeitung von Bildlauf für Sie.  
  
 `CScrollView` führt Folgendes aus:  
  
-   Verwaltet die Fenster-und Viewport und Zuordnungsmodi  
  
-   Verschiebt automatisch als Reaktion auf Bildlaufleisten-Nachrichten  
  
 Sie können wie viel angeben, um einen Bildlauf für einen "Seite" (wenn der Benutzer in einer Bildlaufleiste klickt) und eine "Linie" (wenn der Benutzer in einen Bildlaufpfeil klickt). Planen Sie diese Werte entsprechend den Charakter Ihrer Ansicht an. Sie möchten z. B. einen Bildlauf in Schritten von 1 Pixel für eine Grafikansicht jedoch in Inkrementen von basierend auf der Zeilenhöhe im Text-Dokumenten.  
  
##  <a name="_core_scaling_a_view"></a> Skalieren einer Ansicht  
 Wenn Sie die Ansicht, um automatisch die Größe des zugehörigen Rahmenfenster anpassen möchten, können Sie `CScrollView` für die Skalierung statt Durchführen eines Bildlaufs. Die logische Sicht wird gestreckt oder verkleinert Clientbereich des Fensters genau angepasst. Eine skalierte Ansicht besitzt keine Bildlaufleisten.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Ansichten](../mfc/using-views.md)

