---
title: Menübefehlseigenschaften | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- menu items, properties
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 343c1ce255a26753c2b125d2a0a53e04808a0233
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878862"
---
# <a name="menu-command-properties"></a>Menübefehlseigenschaften
Die folgenden Informationen sind entsprechend den Menüeigenschaften geordnet, die beim Auswählen eines Menübefehls im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window) angezeigt werden. Die Eigenschaften sind hier alphabetisch aufgeführt, können im Eigenschaftenfenster jedoch auch nach Kategorie angezeigt werden.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|**Break**|Einer der folgenden Werte ist möglich:<br /><br /> -   **Keine** (Standard): kein Wechsel.<br />-   **Spalte**: Bei statischen Menüs bewirkt dieser Wert, dass der Menübefehl in eine neue Zeile gesetzt wird. Bei Popupmenüs bewirkt dieser Wert, dass der Menübefehl in eine neue Spalte gesetzt wird, ohne dass zwischen den Spalten eine Trennlinie angezeigt wird. Diese Eigenschaft wirkt sich nicht im Menü-Editor, sondern erst zur Laufzeit auf die Darstellung des Menüs aus.<br />-   **Leiste**: Wie Spalte, außer dass die neue Spalte bei Popupmenüs durch eine vertikale Linie von der alten Spalte getrennt wird. Diese Eigenschaft wirkt sich nicht im Menü-Editor, sondern erst zur Laufzeit auf die Darstellung des Menüs aus.|  
|**Beschriftung**|Text zur Beschreibung des Menübefehls (der Menüname). Einem der Buchstaben in der Beschriftung eines Menübefehls kann eine Zugriffstaste zugeordnet werden, indem ihm ein kaufmännisches Und-Zeichen (&) vorangestellt wird.|  
|**Aktiviert**|Wenn TRUE, ist der Menübefehl zu Beginn aktiviert. Typ: Boolesch. Standardwert: FALSE.|  
|**Aktiviert**|Wenn **FALSE**, ist das Menüelement deaktiviert.|  
|**Grau**|Wenn TRUE, wird der Menübefehl zu Beginn grau dargestellt und ist inaktiv. Typ: Boolesch. Standardwert: FALSE.|  
|**Hilfe**|Richtet das Menüelement rechtsbündig aus. Der Menübefehl für die **Hilfe** befindet sich beispielsweise in allen Windows-Anwendungen immer ganz rechts. Wenn Sie diese Eigenschaft für ein Menüelement festlegen, wird das Element ganz rechts am Ende des Menüs angezeigt. Bezieht sich auf Elemente des Hauptmenüs. Standardwert: **FALSE**.|  
|**ID**|Ein Symbol, das in der Headerdatei definiert ist. Typ: Symbol, ganze Zahl oder Zeichenfolge in Anführungszeichen. Sie können ein beliebiges Symbol verwenden, das üblicherweise in den Editoren verfügbar ist. Dies gilt auch, wenn das [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window) keine Dropdownliste enthält, aus der Sie auswählen können.|  
|**Popup**|Wenn TRUE, wird der Menübefehl als Popupmenü angezeigt. Typ: Boolesch. Standardwert: TRUE für Menüs der obersten Ebene in einer Menüleiste, sonst FALSE.|  
|**Eingabeaufforderung**|Enthält Text, der in der Statusleiste angezeigt werden soll, wenn dieser Menübefehl markiert wird. Der Text wird mit dem Bezeichner des Menübefehls in der Zeichenfolgentabelle gespeichert. Diese Eigenschaft ist für jeden Projekttyp verfügbar, wobei die Laufzeitfunktionalität jedoch MFC-spezifisch ist.|  
|**Rechtsbündig**|Richtet den Menübefehl auf der Menüleiste zur Laufzeit rechtsbündig aus. Typ: Boolesch. Standardwert: FALSE.|  
|**Von rechts nach links**|Ermöglicht die Darstellung der Menübefehle von rechts nach links, wenn die Benutzeroberfläche in eine Sprache übertragen werden soll, die von rechts nach links geschrieben wird, z. B. Hebräisch oder Arabisch.|  
|**Trennzeichen**|Wenn TRUE, ist der Menübefehl eine Trennlinie. Typ: Boolesch. Standardwert: FALSE.|  
  

  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Menü-Editor](../windows/menu-editor.md)