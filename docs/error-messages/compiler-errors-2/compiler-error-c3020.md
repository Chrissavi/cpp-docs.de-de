---
title: Compilerfehler C3020 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3020
dev_langs:
- C++
helpviewer_keywords:
- C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a9c942f6b1459cbdb88561b749290eb47d3cfb3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245367"
---
# <a name="compiler-error-c3020"></a>Compilerfehler C3020
"Var": Indexvariable von OpenMP "for-Schleife kann nicht geändert werden, im Schleifenkörper  
  
 Eine OpenMP `for` Schleife möglicherweise nicht ändern Sie den Index (Schleifenzähler) im Hauptteil der `for` Schleife.  
  
 Im folgende Beispiel wird C3020 generiert:  
  
```  
// C3020.cpp  
// compile with: /openmp  
int main() {  
   int i = 0, n = 3;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; i += n)  
         i *= 2;   // C3020  
         // try the following line instead  
         // n++;  
   }  
}  
```  
  
 Eine Variable mit [Lastprivate](../../parallel/openmp/reference/lastprivate.md) kann nicht als Index innerhalb einer parallelisierten Schleife verwendet werden.  
  
 Im folgende Beispiel erhalten C3020 für die zweite Lastprivate, da dadurch das Schreiben in Idx_a innerhalb der äußersten for-Schleife ausgelöst wird. Die erste Lastprivate wird keine Fehlermeldung ausgegeben, da dadurch das Schreiben in Idx_a außerhalb der äußersten for-Schleife (technisch gesehen ist am Ende der letzten Iteration) löst. Im folgenden Beispiel wird C3020 generiert.  
  
```  
// C3020b.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_a)   // C3020  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```  
  
 Das folgende Beispiel zeigt eine mögliche Lösung:  
  
```  
// C3020c.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_b)  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```