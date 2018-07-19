---
title: Schwerwiegender Fehler C1017 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1017
dev_langs:
- C++
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08433109a959b324621e9c837e67cf529d9f6fdb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33199718"
---
# <a name="fatal-error-c1017"></a>Schwerwiegender Fehler C1017
Ungültiger Ausdruck für Ganzzahlkonstante  
  
 Der Ausdruck in einer `#if` Richtlinie ist nicht vorhanden oder nicht auf eine Konstante ausgewertet.  
  
 Definiert Konstanten `#define` Werte, die als eine ganzzahlige Konstante ausgewertet werden soll, wenn sie verwendet werden ein `#if`, `#elif`, oder `#else` Richtlinie.  
  
 Im folgenden Beispiel wird C1017 generiert:  
  
```  
// C1017.cpp  
#define CONSTANT_NAME "YES"  
#if CONSTANT_NAME   // C1017  
#endif  
```  
  
 Mögliche Lösung:  
  
```  
// C1017b.cpp  
// compile with: /c  
#define CONSTANT_NAME 1  
#if CONSTANT_NAME  
#endif  
```  
  
 Da `CONSTANT_NAME` ergibt eine Zeichenfolge und kein ganze Zahl, die `#if` Richtlinie wird schwerwiegenden Fehler C1017 generiert.  
  
 In anderen Fällen wird der Präprozessor undefined-Konstante als 0 (null) ausgewertet. Dies kann zu unerwarteten Ergebnissen führen, verursachen, wie im folgenden Beispiel gezeigt. `YES` nicht definiert ist, damit es mit NULL ausgewertet wird. Der Ausdruck `#if` `CONSTANT_NAME` ergibt "false" und den Code zu verwendende auf `YES` wird vom Präprozessor entfernt. `NO` ist auch nicht definiert ist (null), sodass `#elif` `CONSTANT_NAME==NO` auf "true" ergibt (`0 == 0`), verursacht den Präprozessor an, lassen Sie den Code in der `#elif` Teil der Anweisung – genau das Gegenteil von das beabsichtigte Verhalten.  
  
```  
// C1017c.cpp  
// compile with: /c  
#define CONSTANT_NAME YES  
#if CONSTANT_NAME  
   // Code to use on YES...  
#elif CONSTANT_NAME==NO  
   // Code to use on NO...  
#endif  
```  
  
 Verwenden, um anzuzeigen, genau wie der Compiler Präprozessordirektiven behandelt [/p](../../build/reference/p-preprocess-to-a-file.md), [/e](../../build/reference/e-preprocess-to-stdout.md), oder [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md).