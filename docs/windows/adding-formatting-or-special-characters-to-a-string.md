---
title: Hinzufügen von Formatierung oder Sonderzeichen zu einer Zeichenfolge | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 429ba8d836579bd3bc1d1dd8844494bf9cd17a7a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864596"
---
# <a name="adding-formatting-or-special-characters-to-a-string"></a>Hinzufügen von Formatierung oder Sonderzeichen zu einer Zeichenfolge
### <a name="to-add-formatting-or-special-characters-to-a-string"></a>Hinzufügen von Formatierung oder Sonderzeichen zu einer Zeichenfolge  
  
1.  Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Wählen Sie die Zeichenfolge, die Sie ändern möchten.  
  
3.  In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), keines der standardmäßigen Escapesequenzen für den Text im unten aufgeführten Hinzufügen der **Beschriftung** ein, und drücken Sie **EINGABETASTE**.  
  
    |Um dies zu erhalten|Geben Sie Folgendes|  
    |-----------------|---------------|  
    |Zeilenwechsel|\n|  
    |Wagenrücklauf|\r|  
    |Registerkarte|\t|  
    |Umgekehrter Schrägstrich (\\)|\\\|  
    |ASCII-Zeichen|\ddd (oktale)|  
    |Warnung (Glocke)|\a|  
  
> [!NOTE]
>  Die Zeichenfolgen-Editor unterstützt nicht den vollständigen Satz von ASCII-Zeichen mit Escapezeichen. Sie können nur die oben aufgeführten verwenden.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen-Editor](../windows/string-editor.md)   

