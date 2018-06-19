---
title: Compilerfehler C2594 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2594
dev_langs:
- C++
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b1de853b8992d3c02eb94c0b050d72539fc3282
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230689"
---
# <a name="compiler-error-c2594"></a>Compilerfehler C2594
'Operator': mehrdeutige Konvertierungen von "Typ1" in "Typ2"  
  
 Keine Konvertierung von *Typ1* auf *Typ2* wurde eine direktere als alle anderen Werte. Wir empfehlen zwei mögliche Lösungen für die Konvertierung von *Typ1* auf *Typ2*. Die erste Möglichkeit besteht, definieren Sie eine direkte Konvertierung vom *Typ1* auf *Typ2*, und die zweite Möglichkeit ist die Angabe eine Sequenz von Konvertierungen von *Typ1* auf  *Typ2*.  
  
 Im folgende Beispiel wird C2594 generiert. Die vorgeschlagene Lösung des Fehlers ist eine Sequenz von Konvertierungen:  
  
```  
// C2594.cpp  
// compile with: /c  
struct A{};  
struct I1 : A {};  
struct I2 : A {};  
struct D : I1, I2 {};  
  
A *f (D *p) {  
   return (A*) (p);    // C2594  
  
// try the following line instead  
// return static_cast<A *>(static_cast<I1 *>(p));  
}  
```