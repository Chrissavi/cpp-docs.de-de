---
title: Zugreifen auf alle Elemente einer Auflistung
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, collections
- enumerations [MFC]
- enumerating collections [MFC]
- collections [MFC], accessing
- collection classes [MFC]
- ', '
- ', '
- ', '
- ', '
- ', '
- ', '
- ', '
ms.assetid: 7bbae518-062e-4393-81f9-b22abd2e5f59
ms.openlocfilehash: ae866b71d2a9f001c56b2c61d99749cab824b313
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57282499"
---
# <a name="accessing-all-members-of-a-collection"></a>Zugreifen auf alle Elemente einer Auflistung

Die MFC-Arrayauflistungsklassen – sowohl die vorlagenbasierten als auch die nicht vorlagenbasierten – verwenden Indizes, um auf ihre Elemente zuzugreifen. Die MFC-Listen- und Zuordnungsauflistungsklassen – sowohl die vorlagenbasierten als auch die nicht vorlagenbasierten – verwenden einen Indikator vom Typ **POSITION** zum Beschreiben einer bestimmten Position in der Auflistung. Für den Zugriff auf einen oder mehrere Member dieser Auflistungen zunächst initialisieren Sie zunächst den Positionsindikator und übergeben dann diese Position wiederholt an die Auflistung und fordert Sie auf das nächste Element zurückzugeben. Die Auflistung ist nicht verantwortlich für die Verwaltung von Statusinformationen hinsichtlich des Fortschritts der Iteration. Diese Informationen werden im Positionsindikator gespeichert. Bei einer bestimmten Position ist die Auflistung jedoch dafür verantwortlich, das nächste Element zurückzugeben.

Die folgenden Verfahren zeigen, wie Sie die drei Haupttypen von Auflistungen, die mit MFC bereitgestellt werden, durchlaufen:

- [Durchlaufen eines Arrays](#_core_to_iterate_an_array)

- [Durchlaufen einer Liste](#_core_to_iterate_a_list)

- [Durchlaufen einer Zuordnung](#_core_to_iterate_a_map)

### <a name="_core_to_iterate_an_array"></a> So durchlaufen Sie ein Array

1. Verwenden Sie die sequenziellen Indexzahlen mit der `GetAt` -Memberfunktion:

   [!code-cpp[NVC_MFCCollections#12](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_1.cpp)]

   Dieses Beispiel verwendet ein typisiertes Zeigerarray, das enthält Zeiger auf `CPerson` -Objekte enthält. Das Array wird von der Klasse `CObArray`abgeleitet, eine der nicht auf Vorlagen basierenden, vordefinierten Klassen. `GetAt` gibt einen Zeiger auf ein `CPerson` -Objekt zurück. Für typisierte Zeigerauflistungsklassen – Arrays oder Listen – gibt der erste Parameter die Basisklasse an; der zweite Parameter gibt den zu speichernden Typ an.

   Die `CTypedPtrArray` -Klasse überlädt die **[]** Operator, damit Sie Zugriff auf Elemente eines Arrays die übliche tiefgestellte Array-Syntax verwenden können. Eine Alternative zur Anweisung im Hauptteil der **für** obige Schleife ist

   [!code-cpp[NVC_MFCCollections#13](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_2.cpp)]

   Dieser Operator ist in den **const** - und nicht-**const** -Versionen vorhanden. Die **const** -Version, die für **const** -Arrays aufgerufen wird, können nur auf der rechten Seite einer Zuweisungsanweisung angezeigt werden.

### <a name="_core_to_iterate_a_list"></a> So durchlaufen Sie eine Liste

1. Verwenden Sie die Memberfunktionen `GetHeadPosition` und `GetNext` zum Navigieren durch die Liste:

   [!code-cpp[NVC_MFCCollections#14](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_3.cpp)]

   Dieses Beispiel verwendet eine typisierte Zeigerliste, um Zeiger auf `CPerson` -Objekte zu enthalten. Die List-Deklaration ähnelt der für das Array in der Prozedur [So durchlaufen Sie ein Array](#_core_to_iterate_an_array) , sie wird jedoch von der Klasse `CObList`abgeleitet. `GetNext` gibt einen Zeiger auf ein `CPerson` -Objekt zurück.

### <a name="_core_to_iterate_a_map"></a> So durchlaufen Sie eine Zuordnung

1. Verwenden Sie `GetStartPosition` , um an den Anfang der Zuordnung zu wechseln, und `GetNextAssoc` , um den nächsten Schlüssel und Wert wiederholt aus der Zuordnung abzurufen, wie im folgenden Beispiel gezeigt:

   [!code-cpp[NVC_MFCCollections#15](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_4.cpp)]

   Dieses Beispiel verwendet eine einfache Zuordnungsvorlage (statt einer typisierten Zeigerauflistung), die `CString` -Schlüssel nutzt und Zeiger auf `CPerson` -Objekte speichert. Wenn Sie Zugriffsfunktionen wie z. B. `GetNextAssoc`verwenden, bietet die Klasse Zeiger auf `CPerson` -Objekte. Wenn Sie stattdessen eine der nicht auf Vorlagen basierten Zuordnungsauflistungen verwenden, müssen Sie den zurückgegebenen `CObject` -Zeiger in einen Zeiger auf eine `CPerson`umwandeln.

    > [!NOTE]
    >  Für nicht auf Vorlagen basierende Zuordnungen erfordert der Compiler einen Verweis auf einen `CObject` -Zeiger im letzten Parameter für `GetNextAssoc`. Bei der Eingabe müssen Sie die Zeiger in diesen Typ umwandeln, wie im nächsten Beispiel gezeigt.

   Die Vorlagenlösung ist einfacher und bietet eine bessere Typsicherheit. Der nicht auf Vorlagen basierende Code ist komplizierter, wie Sie hier sehen können:

   [!code-cpp[NVC_MFCCollections#16](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_5.cpp)]

Weitere Informationen finden Sie unter [Löschen aller Objekte in einer CObject-Sammlung](../mfc/deleting-all-objects-in-a-cobject-collection.md).

## <a name="see-also"></a>Siehe auch

[Sammlungen](../mfc/collections.md)
