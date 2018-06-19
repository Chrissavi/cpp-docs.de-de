---
title: Compilerfehler Fehler C2026 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2026
dev_langs:
- C++
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6b2952daa8cc7b3642cca5ba278990fde7d1ebe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167664"
---
# <a name="compiler-error-c2026"></a>Compilerfehler Fehler C2026
Zeichenfolge zu lang, nachfolgende Zeichen gekürzt  
  
 Die Zeichenfolge wurde länger als das Limit von 16380 Einzelbyte-Zeichen.  
  
 Vor der angrenzenden Zeichenfolgen verkettet werden darf keine Zeichenfolge länger als 16380 Einzelbyte-Zeichen sein.  
  
 Eine Unicode-Zeichenfolge mit ungefähr die Hälfte dieser Länge würde auch dieser Fehler generiert.  
  
 Wenn Sie eine Zeichenfolge, die wie folgt definiert haben, wird es C2026 generiert:  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 Sie können es wie folgt zusammensetzen:  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 Sie wollen außergewöhnlich große Zeichenfolgenliterale (32 KB oder mehr) speichern in einer benutzerdefinierten Ressource oder eine externe Datei. Finden Sie unter [Erstellen einer neuen benutzerdefinierten Ressource oder Datenressource](../../windows/creating-a-new-custom-or-data-resource.md) für Weitere Informationen.