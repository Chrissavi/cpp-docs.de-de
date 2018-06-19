---
title: Compilerwarnung (Stufe 2) C4308 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4308
dev_langs:
- C++
helpviewer_keywords:
- C4308
ms.assetid: d4e5c53c-71b2-4bbc-8a7c-3a2a3180d9d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3daff15f8e6eee179f04fd466f3595af1154e035
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290009"
---
# <a name="compiler-warning-level-2-c4308"></a>Compilerwarnung (Stufe 2) C4308
negative integrale Konstante vorzeichenlosen Typ konvertiert  
  
 Ein Ausdruck konvertiert eine negative ganzzahlige Konstante in einen Typ ohne Vorzeichen. Das Ergebnis des Ausdrucks ist wahrscheinlich bedeutungslos.  
  
## <a name="example"></a>Beispiel  
  
```  
// C4308.cpp  
// compile with: /W2  
unsigned int u = (-5 + 3U);   // C4308  
  
int main()  
{  
}  
```