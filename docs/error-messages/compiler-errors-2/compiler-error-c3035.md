---
title: Compilerfehler C3035 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3035
dev_langs:
- C++
helpviewer_keywords:
- C3035
ms.assetid: af34fad2-2b45-42d0-a9ff-04eab3e91c37
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c4b454e30f926bd706a584705e75e7c73d764e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33244985"
---
# <a name="compiler-error-c3035"></a>Compilerfehler C3035
Die ordered-Direktive von OpenMP muss mit der ordered-Klausel direkt an eine For-Direktive oder eine Parallel For-Direktive gebunden werden.  
  
 Eine ordered-Klausel weist ein nicht ordnungsgemäßes Format auf.  
  
 Im folgenden Beispiel wird C3035 generiert:  
  
```  
// C3035.cpp  
// compile with: /openmp /link vcomps.lib  
int main() {  
   int n = 0, x, i;  
  
   #pragma omp parallel private(n)  
   {  
      #pragma omp ordered   // C3035  
      // Try the following line instead:  
      // #pragma omp for ordered  
       for (i = 0 ; i < 10 ; ++i)  
         ;  
   }  
}  
```