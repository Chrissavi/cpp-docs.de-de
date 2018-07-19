---
title: Löschen aller Objekte in einer CObject-Sammlung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], deleting in collections
- objects in CObject collections, deleting
- CObject class [MFC], deleting in collection
- collection classes [MFC], deleting all objects
- CObject class collection
- objects in CObject collections
- collection classes [MFC], shared objects
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f57e503e43bdb637b85e4642349203b9f2e8aa6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348822"
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>Löschen aller Objekte in einer CObject-Sammlung
In diesem Artikel wird erläutert, wie alle Objekte in einer Sammlung gelöscht (ohne das Auflistungsobjekt selbst zu löschen).  
  
 So löschen Sie alle Objekte in einer Auflistung von `CObject`s (oder über abgeleitete Objekte `CObject`), verwenden Sie eine der im Artikel beschriebenen Techniken Iteration [Zugriff auf alle Mitglieder einer Sammlung](../mfc/accessing-all-members-of-a-collection.md) So löschen Sie jedes Objekt in Aktivieren.  
  
> [!CAUTION]
>  Objekte in Auflistungen können freigegeben werden. D. h. die Auflistung und dabei einen Zeiger auf das Objekt, aber andere Teile des Programms möglicherweise auch Zeiger auf das gleiche Objekt. Sie müssen darauf achten, kein Objekt zu löschen, die gemeinsam genutzt wird, bis alle Teile wurden unter Verwendung des Objekts sein.  
  
 Diesem Artikel erfahren Sie, wie die Objekte in gelöscht:  
  
-   [Eine Liste](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)  
  
-   [Ein array](#_core_to_delete_all_elements_in_an_array)  
  
-   [Eine Zuordnung](#_core_to_delete_all_elements_in_a_map)  
  
#### <a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>  So löschen Sie alle Objekte in einer Liste von Zeigern auf CObject  
  
1.  Verwendung `GetHeadPosition` und `GetNext` zum Durchlaufen der Liste.  
  
2.  Verwenden der **löschen** Operator, um jedes Objekt gelöscht werden, da sie in der Iteration entdeckt wird.  
  
3.  Rufen Sie die `RemoveAll` Funktion, um alle Elemente aus der Liste entfernen, nachdem die mit diesen Elementen verknüpften Objekte gelöscht wurden.  
  
 Im folgende Beispiel wird gezeigt, wie zum Löschen aller Objekte aus einer Liste von `CPerson` Objekte. Jedes Objekt in der Liste ist ein Zeiger auf eine `CPerson` -Objekt, das ursprünglich vom Heap zugewiesen wurde.  
  
 [!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]  
  
 Die letzte Funktionsaufruf `RemoveAll`, wird eine Liste-Memberfunktion, die alle Elemente aus der Liste entfernt werden. Die Memberfunktion `RemoveAt` ein einzelnes Element entfernt.  
  
 Beachten Sie den Unterschied zwischen dem Objekt ein Element löschen, und entfernen das Element selbst. Entfernen eines Elements aus der Liste lediglich entfernt die Liste der Verweis auf das Objekt. Das Objekt ist weiterhin im Arbeitsspeicher vorhanden. Wenn Sie ein Objekt löschen, nicht mehr vorhanden, und der Arbeitsspeicher wieder freigegeben wird. Daher ist es wichtig, um ein Element zu entfernen, sofort, nachdem das Element Objekt gelöscht wurde, damit die Liste nicht versucht, den Zugriff auf Objekte, die nicht mehr vorhanden sind.  
  
#### <a name="_core_to_delete_all_elements_in_an_array"></a>  So löschen Sie alle Elemente in einem array  
  
1.  Verwendung `GetSize` und Ganzzahlwerte für Index zum Durchlaufen des Arrays.  
  
2.  Verwenden der **löschen** Operator, um jedes Element gelöscht werden, da sie in der Iteration entdeckt wird.  
  
3.  Rufen Sie die `RemoveAll` Funktion, um alle Elemente aus dem Array entfernt werden, nachdem sie gelöscht wurden.  
  
     Der Code für das Löschen aller Elemente eines Arrays ist wie folgt:  
  
     [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]  
  
 Wie Sie mit der obigen Liste-Beispiel, das Sie aufrufen können `RemoveAll` So entfernen Sie alle Elemente in einem Array oder `RemoveAt` um ein einzelnes Element zu entfernen.  
  
#### <a name="_core_to_delete_all_elements_in_a_map"></a> So löschen Sie alle Elemente in einer Zuordnung  
  
1.  Verwendung `GetStartPosition` und `GetNextAssoc` zum Durchlaufen des Arrays.  
  
2.  Verwenden der **löschen** Operator, um den Schlüssel und/oder den Wert für jedes kartenelement gelöscht werden, da sie in der Iteration entdeckt wird.  
  
3.  Rufen Sie die `RemoveAll` Funktion, um alle Elemente aus der Zuordnung entfernen, nachdem sie gelöscht wurden.  
  
     Der Code für das Löschen aller Elemente einer `CMap` Auflistung lautet wie folgt. Jedes Element in der Zuordnung weist eine Zeichenfolge als Schlüssel und ein `CPerson` Objekt (abgeleitet von `CObject`) als Wert.  
  
     [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]  
  
 Sie erreichen `RemoveAll` So entfernen Sie alle Elemente in einer Karte oder `RemoveKey` So entfernen Sie ein einzelnes Element mit dem angegebenen Schlüssel.  
  
## <a name="see-also"></a>Siehe auch  
 [Zugreifen auf alle Elemente einer Auflistung](../mfc/accessing-all-members-of-a-collection.md)

