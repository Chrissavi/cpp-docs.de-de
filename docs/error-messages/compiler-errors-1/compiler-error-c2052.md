---
title: Compilerfehler Fehler C2052 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2052
dev_langs:
- C++
helpviewer_keywords:
- C2052
ms.assetid: 922ca43b-b64b-4ef7-9611-c7313be3fd79
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5703474a859d41bbfa62b29aa951f1e3198abb06
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33163708"
---
# <a name="compiler-error-c2052"></a>Compilerfehler Fehler C2052
'Typ': Ungültiger Typ für Case-Ausdruck  
  
 CASE-Ausdrücke müssen ganzzahlige Konstanten sein.  
  
 Im folgende Beispiel wird C2052 generiert:  
  
```  
// C2052.cpp  
int main() {  
   int index = 0;  
   switch (index) {  
      case 1:  
         return 24;  
      case 1.0:   // C2052  
      // try the following line instead  
      // case 2:  
         return 23;  
   }  
}  
```