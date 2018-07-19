---
title: Compilerwarnung (Stufe 1) C4144 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4144
dev_langs:
- C++
helpviewer_keywords:
- C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b84e8a062871bfaa1d83da50175e3485f2d8bd2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281338"
---
# <a name="compiler-warning-level-1-c4144"></a>Compilerwarnung (Stufe 1) C4144 generiert
'Ausdruck': Relationaler Ausdruck als Schalterausdruck  
  
 Der angegebene relationale Ausdruck wurde als steuernder Ausdruck verwendet eine [wechseln](../../cpp/switch-statement-cpp.md) Anweisung. Die zugehörigen Case-Anweisungen werden boolesche Werte angeboten. Im folgende Beispiel wird C4144 generiert:  
  
```  
// C4144.cpp  
// compile with: /W1  
int main()  
{  
   int i = 0;  
   switch(!i) {   // C4144, remove the ! to resolve  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```