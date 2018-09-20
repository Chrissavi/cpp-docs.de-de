---
title: Zusammenfassung von Zeichenfolgenliteralen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: d2693900-f4e2-4820-b7de-085d51827aee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a94d575ee36f38b56f64fb6298eb6f6f6e43567e
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762742"
---
# <a name="summary-of-string-literals"></a>Zusammenfassung von Zeichenfolgenliteralen

*string-literal*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**'** *s-char-sequence*<sub>opt</sub> **'**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**L'** *s-char-sequence*sub>opt</sub> **'**  
  
*s-char-sequence*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*s-char*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*s-char-sequence* *s-char*  
  
*s-char*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Alle Elemente des Quellzeichensatzes mit Ausnahme von doppelten Anführungszeichen ("), umgekehrtem Schrägstrich (\\) oder Zeilenumbruchzeichen Escapesequenz  

## <a name="see-also"></a>Siehe auch

[Lexikalische Grammatik](../c-language/lexical-grammar.md)