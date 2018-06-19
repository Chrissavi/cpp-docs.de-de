---
title: Compilerwarnung (Stufe 2) C4056 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4056
dev_langs:
- C++
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bf5a5855d0b4291105826679e2ae81ed6d69e5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290565"
---
# <a name="compiler-warning-level-2-c4056"></a>Compilerwarnung (Stufe 2) C4056 generiert
in der Gleitkommaarithmetik Konstanten "Überlauf"  
  
 Konstante Gleitkommazahlen generiert ein Ergebnis, das den maximalen zulässigen Wert überschreitet.  
  
 Diese Warnung kann durch compileroptimierungen, die während der Arithmetik ausgeführt verursacht werden. Sie können diese Warnung gefahrlos ignorieren, wenn er beendet wurde, wenn Sie durch Deaktivieren der Optimierung ([/Od](../../build/reference/od-disable-debug.md)).  
  
 Im folgende Beispiel wird C4056 generiert:  
  
```  
// C4056.cpp  
// compile with: /W2 /LD  
#pragma warning (default : 4056)  
float fp_val = 1.0e300 * 1.0e300;   // C4056  
```