---
title: Compilerfehler C2206 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2206
dev_langs:
- C++
helpviewer_keywords:
- C2206
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93058e5a7a4bd4fadfbfc1830ea6e2840618463c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169581"
---
# <a name="compiler-error-c2206"></a>Compilerfehler C2206
„function“: typedef kann nicht für die Definition einer Funktion verwendet werden.  
  
 Ein `typedef` -Element wird verwendet, um einen Funktionstyp zu definieren.  
  
 Das folgende Beispiel generiert C2206:  
  
```  
// C2206.cpp  
typedef int functyp();  
typedef int MyInt;  
functyp func1 {};   // C2206  
int main() {  
   MyInt i = 0;   // OK  
}  
```