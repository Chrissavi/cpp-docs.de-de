---
title: Beschränkungen bei Symbolnamen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.restrictions.name
dev_langs:
- C++
helpviewer_keywords:
- symbol names
- symbols, names
- restrictions, symbol names
ms.assetid: 4ae7f695-ca86-4f4b-989a-fe6f89650ff7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 30852b22c9ff4cc74c8f0c57b3a5ed9d79a34838
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011447"
---
# <a name="symbol-name-restrictions"></a>Beschränkungen bei Symbolnamen
Die Einschränkungen für Symbolnamen lauten wie folgt:  
  
-   Alle [Symbole](../windows/symbols-resource-identifiers.md) muss innerhalb des Bereichs der Anwendung eindeutig sein. Dadurch werden Symboldefinitionskonflikte in den Headerdateien verhindert.  
  
-   Zu den gültigen Zeichen für einen Symbolnamen zählen A–Z, a–z, 0–9 und Unterstriche ( – ).  
  
-   Symbolnamen dürfen nicht mit einer Zahl beginnen und sind auf 247 Zeichen begrenzt.  
  
-   Symbolnamen dürfen keine Leerzeichen enthalten.  
  
-   Bei Symbolnamen wird die Groß-/Kleinschreibung nicht beachtet. Die Groß-/Kleinschreibung der ersten Symboldefinition wird jedoch beibehalten. Die die Symbole definierende Headerdatei wird durch den Ressourcencompiler/Editor und durch das bzw. die C++Programm(e) verwendet, um auf in einer Ressourcendatei definierte Ressourcen zu verweisen. Bei zwei Symbolnamen, die sich nur in der Groß-/Kleinschreibung unterscheiden, erkennt das C++-Programm zwei getrennte Symbole, während der Ressourcencompiler/Editor beide Namen als ein einzelnes Symbol erkennt.  
  
    > [!NOTE]
    >  Wenn Sie das im Folgenden hervorgehobene standardmäßige Symbolnamensschema (ID*_[keyword]) nicht befolgen und Ihr Symbolname dem Schlüsselwort entspricht, das dem Ressourcenskriptcompiler bekannt ist, führt der Versuch, die Ressourcenskriptdatei zu erstellen, anscheinend zu einer zufälligen Fehlergenerierung, die sich schwer diagnostizieren lässt. Halten Sie sich an die standardmäßige Namensgebung, um dies zu verhindern.  
  
 Symbolnamen weisen beschreibende Präfixe auf, die die Art der Ressource oder des Objekts andeuten, die bzw. das sie repräsentieren. Diese beschreibenden Präfixe beginnen mit der Textkombinations-ID. Die Microsoft Foundation Class-Bibliothek (MFC) verwendet die in der folgenden Tabelle gezeigten Symbolnamenskonventionen.  
  
|Kategorie|Präfix|Verwenden|  
|--------------|------------|---------|  
|Ressourcen|IDR_ IDD_ IDC_ IDI_ IDB_|Zugriffstaste oder Menü (sowie zugehörige oder benutzerdefinierte Ressourcen), Dialogfeld, Cursor, Symbol, Bitmap|  
|Menüelemente|ID_|Menüelement|  
|Befehle|ID_|Befehl|  
|Steuerelemente und untergeordnete Fenster|IDC_|Steuerelement|  
|Zeichenfolgen|IDS_|Zeichenfolge in der Zeichenfolgentabelle|  
|MFC|AFX_|Reserviert für vordefinierte MFC-Symbole|  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ändern eines Symbols oder Symbolnamens (ID)](../windows/changing-a-symbol-or-symbol-name-id.md)   
 [Beschränkungen für Symbolwerte](../windows/symbol-value-restrictions.md)   
 [Vordefinierte Symbol-IDs](../windows/predefined-symbol-ids.md)