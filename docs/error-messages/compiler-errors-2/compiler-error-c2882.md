---
title: Compilerfehler C2882 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2882
dev_langs:
- C++
helpviewer_keywords:
- C2882
ms.assetid: 617018ee-5a0d-4b8d-9612-77e8ae52679b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2885d00f31dbb9e057317e12b43b838579b33aa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33242192"
---
# <a name="compiler-error-c2882"></a>Compilerfehler C2882
'Name': Unzulässige Verwendung des Namespace-Bezeichner im Ausdruck  
  
 Sie haben versucht, die den Namen eines Namespaces in einem Ausdruck verwenden.  
  
 Im folgende Beispiel wird C2882 generiert:  
  
```  
// C2882.cpp  
// compile with: /c  
namespace A {  
   int k;  
}  
  
int i = A;   // C2882, can't assign A to i  
```