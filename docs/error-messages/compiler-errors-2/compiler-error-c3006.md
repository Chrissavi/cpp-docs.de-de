---
title: Compilerfehler C3006 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3006
dev_langs:
- C++
helpviewer_keywords:
- C3006
ms.assetid: 449082ec-fd45-4c47-8ab3-ba6a719e4dc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3019a4017170b13da21820931a572370db1862e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33258199"
---
# <a name="compiler-error-c3006"></a>Compilerfehler C3006
"Klausel": In der Klausel für die "directive"-Direktive von OpenMP fehlt ein erwartetes Argument.  
  
 Bei einer OpenMP-Direktive fehlt ein erwartetes Argument.  
  
 Im folgenden Beispiel wird C3006 generiert:  
  
```  
// C3006.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel shared   // C3006  
   // Try the following line instead:  
   // #pragma omp parallel shared(x) {}  
  
}  
```