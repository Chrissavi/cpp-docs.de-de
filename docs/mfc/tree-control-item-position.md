---
title: Position eines Elements im Struktursteuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], item position
- item position in tree controls
- tree controls [MFC], item position
- position, CTreeCtrl items
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7b7576786f456320a355920a7a9ef9e4935ab03
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382150"
---
# <a name="tree-control-item-position"></a>Position eines Elements im Struktursteuerelement
Die Anfangsposition des Elements wird festgelegt, wenn das Element dem Strukturansicht-Steuerelement hinzugefügt wird ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) mithilfe der `InsertItem` Memberfunktion. Der Aufruf der Memberfunktion gibt das Handle für das übergeordnete Element und das Handle des Elements, nach dem das neue Element eingefügt werden soll. Das zweite Handle muss ein untergeordnetes Element des angegebenen übergeordneten Elements identifiziert, oder einen der folgenden Werte: `TVI_FIRST`, `TVI_LAST`, oder `TVI_SORT`.  
  
 Wenn `TVI_FIRST` oder `TVI_LAST` angegeben ist, wird das Strukturansicht-Steuerelement platziert das neue Element am Anfang oder Ende der Liste untergeordneter Elemente des angegebenen übergeordneten Elements. Wenn `TVI_SORT` angegeben ist, wird die Strukturansicht-Steuerelements fügt das neue Element in der Liste von untergeordneten Elementen in alphabetischer Reihenfolge basierend auf den Text, der den Elementnamen.  
  
 Sie können ein übergeordnetes Element der Liste der untergeordneten Elemente in alphabetischer Reihenfolge einfügen, durch Aufrufen der [SortChildren](../mfc/reference/ctreectrl-class.md#sortchildren) Memberfunktion. Diese Funktion enthält einen Parameter, der angibt, ob alle Ebenen von untergeordneten Elementen, die aus dem angegebenen übergeordneten Element absteigender ebenfalls in alphabetischer Reihenfolge sortiert werden.  
  
 Die [SortChildrenCB](../mfc/reference/ctreectrl-class.md#sortchildrencb) Memberfunktion bietet die Möglichkeit zum Sortieren von untergeordneten Elementen, die auf Grundlage der Kriterien, die Sie definieren. Wenn Sie diese Funktion aufrufen, geben Sie eine anwendungsdefinierte Rückruffunktion, die dem Strukturansicht-Steuerelements aufrufen können, wenn die relative Position von zwei untergeordnete Elemente entschieden werden muss. Die Rückruffunktion empfängt zwei 32-Bit-Anwendung definierten Werte für die Elemente, die verglichen werden und eine dritte 32-Bit-Wert, der Sie angeben, wenn der Aufruf von `SortChildrenCB`.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

