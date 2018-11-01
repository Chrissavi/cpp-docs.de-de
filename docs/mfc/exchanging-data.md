---
title: Datenaustausch
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets [MFC], data exchange
- exchanging data with property sheets [MFC]
- DDX (dialog data exchange) [MFC], property sheets
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
ms.openlocfilehash: 84e2ff9478cb3606bafb7f0408b7e2cc8fee2c00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569631"
---
# <a name="exchanging-data"></a>Datenaustausch

Wie bei den meisten Dialogfeldern ist der Datenaustausch zwischen dem Eigenschaftenblatt und die Anwendung eine der wichtigsten Funktionen des Eigenschaftenblatts an. In diesem Artikel wird beschrieben, wie diese Aufgabe wird.

Austauschen von Daten mit einem Eigenschaftenblatt ist tatsächlich eine Frage zum Austausch von Daten mit den einzelnen Eigenschaftenseiten des Eigenschaftenblatts. Das Verfahren zum Austauschen von Daten mit einer Eigenschaftenseite ist identisch mit dem Austauschen von Daten mit einem Dialogfeld, da eine [CPropertyPage](../mfc/reference/cpropertypage-class.md) Objekt ist ein spezieller [CDialog](../mfc/reference/cdialog-class.md) Objekt. Die Prozedur nutzt die Framework Dialogfeld Daten Dialogdatenaustausch (DDX) Funktion, die Daten zwischen Steuerelementen in einem Dialogfeld und den Membervariablen des Dialog Box-Objekts austauscht.

Der wichtige Unterschied zwischen den Austausch von Daten mit einem Eigenschaftenblatt und einem normalen Dialogfeld ist, dass das Eigenschaftenblatt mehrere Seiten umfasst, sodass Sie Daten mit allen Seiten im Eigenschaftenblatt austauschen müssen. Weitere Informationen über DDX, finden Sie unter [Dialogdatenaustausch und Validierung](../mfc/dialog-data-exchange-and-validation.md).

Das folgende Beispiel veranschaulicht den Austausch von Daten zwischen einer Ansicht und zwei Seiten eines Eigenschaftenblatts an:

[!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/cpp/exchanging-data_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Eigenschaftenblätter](../mfc/property-sheets-mfc.md)

