---
title: Compiler-Fehler C2734 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2734
dev_langs:
- C++
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6fdc5dda82fe7410afc6e8580f3bedd8ddc289ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237358"
---
# <a name="compiler-error-c2734"></a>Compiler-Fehler C2734 generiert
'Bezeichner': Konstantes Objekt muss initialisiert werden, wenn nicht "extern"  
  
 Der Bezeichner wurde deklariert `const` , aber nicht initialisiert oder `extern`.  
  
 Im folgende Beispiel wird C2734 generiert:  
  
```  
// C2734.cpp  
const int j;   // C2734  
extern const int i;   // OK, declared as extern  
```