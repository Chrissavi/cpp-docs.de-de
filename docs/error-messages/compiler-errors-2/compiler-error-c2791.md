---
title: Compiler-Fehler C2791 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2791
dev_langs:
- C++
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65a3d399ed6c7f25b849335328550526ecf7a816
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236495"
---
# <a name="compiler-error-c2791"></a>Compiler-Fehler C2791 generiert
Unzulässige Verwendung von 'Super': 'Class' besitzt keine Basisklassen  
  
 Das Schlüsselwort [super](../../cpp/super.md) wurde im Kontext einer Memberfunktion einer Klasse, die über keinen Basis-Klassen verwendet.  
  
 Im folgende Beispiel wird C2791 generiert:  
  
```  
// C2791.cpp  
struct D {  
   void mf() {  
      __super::mf();   // C2791  
   }  
};  
```