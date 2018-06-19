---
title: Compiler-Fehler C2650 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2650
dev_langs:
- C++
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee76b2d80ff76033f6776b91ee90e52ef5e200cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232234"
---
# <a name="compiler-error-c2650"></a>Compiler-Fehler C2650 generiert
'Operator': eine virtuelle Funktion ist nicht möglich  
  
 Ein `new` oder `delete` Operator deklariert ist `virtual`. Diese Operatoren sind `static` Memberfunktionen dar und nicht mit `virtual`.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2650 generiert:  
  
```  
// C2650.cpp  
// compile with: /c  
class A {  
   virtual void* operator new( unsigned int );   // C2650  
   // try the following line instead  
   // void* operator new( unsigned int );  
};  
```