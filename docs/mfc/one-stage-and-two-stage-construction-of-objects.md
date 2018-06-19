---
title: Ein- und zweistufige Konstruktion von Objekten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c53f99932887acad4d2eab5c15ed73b66b359fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346011"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>Ein- oder zweistufige Erstellung von Objekten
Sie haben die Wahl zwischen zwei Techniken für die Erstellung von Grafikobjekten, z. B. Stifte und Pinsel:  
  
-   *Ein-Konstruktion*: Erstellen und Initialisieren des Objekts in einem Schritt ausgeführt, alle mit dem Konstruktor.  
  
-   *Zweistufige Konstruktion*: Erstellen und initialisieren Sie das Objekt in zwei separaten Phasen. Der Konstruktor erstellt das Objekt, und eine Initialisierungsfunktion initialisiert.  
  
 Zweistufige Konstruktion ist immer sicherer. Bei Erstellung der ein-konnte der Konstruktor eine Ausnahme ausgelöst, wenn Sie falsche Argumente angeben, oder die speicherbelegung fehlschlägt. Dieses Problem wird durch zweistufige Konstruktion vermieden, zwar möglicherweise für den Fehler zu überprüfen. In beiden Fällen ist das Löschen des Objekts den gleichen Prozess aus.  
  
> [!NOTE]
>  Diese Verfahren gelten für alle Objekte, die nicht nur Grafikobjekte erstellen.  
  
## <a name="example-of-both-construction-techniques"></a>Beispiel für beide Verfahren zur Erstellung  
 Im folgende kurze Beispiel zeigt beide Methoden zum Erstellen einer Pen-Objekt:  
  
 [!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Grafikobjekte](../mfc/graphic-objects.md)  
  
-   [Auswählen eines Grafikobjekts einen Gerätekontext](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [Gerätekontexte](../mfc/device-contexts.md)  
  
-   [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Grafikobjekte](../mfc/graphic-objects.md)

