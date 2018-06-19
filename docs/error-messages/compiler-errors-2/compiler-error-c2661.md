---
title: Compiler-Fehler C2661 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2661
dev_langs:
- C++
helpviewer_keywords:
- C2661
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcab577ae9cfd84c757ceb194d4a59ee63057993
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33231030"
---
# <a name="compiler-error-c2661"></a>Compiler-Fehler C2661 generiert
'Funktion': keine überladene Funktion akzeptiert Parameter  
  
 Mögliche Ursachen:  
  
1.  Falsche tatsächliche Parameter im Funktionsaufruf.  
  
2.  Fehlende Funktionsdeklaration.  
  
 Im folgende Beispiel wird C2661 generiert:  
  
```  
// C2661.cpp  
void func( int ){}  
void func( int, int ){}  
int main() {  
   func( );   // C2661 func( void ) was not declared  
   func( 1 );   // OK func( int ) was declared  
}  
```