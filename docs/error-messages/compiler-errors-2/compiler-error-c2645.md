---
title: Compiler-Fehler C2645 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2645
dev_langs:
- C++
helpviewer_keywords:
- C2645
ms.assetid: 6609c2fa-c3b2-4a6b-8e8d-58fb52f67175
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0330f9f678da58648c2fd445f7a291b02c167a89
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229147"
---
# <a name="compiler-error-c2645"></a>Compiler-Fehler C2645 generiert
keine qualifizierten Namen für Zeiger auf Member (gefunden ':: *')  
  
 Die Deklaration eines Zeigers auf ein Element gibt keine Klasse an.  
  
 Im folgende Beispiel wird C2645 generiert:  
  
```  
// C2645.cpp  
class A {};  
int main() {  
   int B::* bp;   // C2645 B not defined  
   int A::* ap;   // OK  
}  
```