---
title: Compilerfehler C2499 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2499
dev_langs:
- C++
helpviewer_keywords:
- C2499
ms.assetid: b323ff4d-b3c1-4bfd-b052-ae7292d53222
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6933d27a1f396dc08275c3f5149212be7abeaaf1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225724"
---
# <a name="compiler-error-c2499"></a>Compilerfehler C2499
'Klasse': eine Klasse kann nicht ihre eigene Basisklasse  
  
 Sie haben versucht, die Klasse anzugeben, die Sie als Basisklasse definieren.  
  
 Im folgenden Beispiel wird C2499 generiert:  
  
```  
// C2499.cpp  
// compile with: /c  
class CMyClass : public CMyClass {};   // C2499  
class CMyClass{};   // OK  
```