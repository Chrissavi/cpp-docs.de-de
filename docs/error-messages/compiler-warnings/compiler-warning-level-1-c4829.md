---
title: Compilerwarnung (Stufe 1) C4829 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4829
dev_langs:
- C++
helpviewer_keywords:
- C4829
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c27ca268a3c873474cd4ed79a2b843642087c34
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286538"
---
# <a name="compiler-warning-level-1-c4829"></a>Compilerwarnung (Stufe 1) C4829
Möglicherweise falsche Parameter für Main-Funktion. Betrachten Sie "Intmain (Platform:: Array\<Platform:: String ^ > ^ Argv)'  
  
 Bestimmte Funktionen wie „main“ können keine Verweistypparameter verwenden. Auch wenn die Kompilierung erfolgreich verläuft, wird das resultierende Image wahrscheinlich nicht ausgeführt.  
  
 Im folgenden Beispiel wird C4829 generiert.  
  
```  
// C4829.cpp  
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp  
int main(Platform::String ^ s) {}   // C4829  
  
```