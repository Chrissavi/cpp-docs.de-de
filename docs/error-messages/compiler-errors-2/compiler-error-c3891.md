---
title: Compilerfehler C3891 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3891
dev_langs:
- C++
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 021f19d50d0b83c9526956684737ad23fea9fb01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272707"
---
# <a name="compiler-error-c3891"></a>Compilerfehler C3891
"Var": Ein literal-Datenmember kann nicht als ein l-Wert verwendet werden  
  
 Ein [literal](../../windows/literal-cpp-component-extensions.md) -Variable ist eine Konstante, und der Wert kann nicht geändert werden, nachdem er in der Deklaration initialisiert wurde.  
  
 Im folgende Beispiel wird C3891 generiert:  
  
```  
// C3891.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   Y1::staticConst = 0;   // C3891  
}  
```