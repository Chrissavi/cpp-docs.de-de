---
title: Compilerfehler C3798 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3798
dev_langs:
- C++
helpviewer_keywords:
- C3798
ms.assetid: b2f8b1d8-8812-49b8-a346-28e48f02ba5c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da4ca81f2110ff1f76fdc9d0377234087a532017
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269053"
---
# <a name="compiler-error-c3798"></a>Compilerfehler C3798
"Spezifizierer": Eigenschaftendeklaration keine Überschreibungsspezifizierer (sollte in der Eigenschaft Get/Set-Methoden stattdessen platziert werden)  
  
 Eine Eigenschaft wurde falsch deklariert. Weitere Informationen finden Sie unter  
  
-   [Eigenschaft](../../windows/property-cpp-component-extensions.md)  
  
-   [abstract](../../windows/abstract-cpp-component-extensions.md)  
  
-   [sealed](../../windows/sealed-cpp-component-extensions.md)  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3798 generiert:  
  
```  
// C3798.cpp  
// compile with: /clr /c  
ref struct A {  
   property int Prop_1 abstract;   // C3798  
   property int Prop_2 sealed;   // C3798  
  
   // OK  
   property int Prop_3 {  
      virtual int get() abstract;  
      virtual void set(int i) abstract;  
   }  
  
   property int Prop_4 {  
      virtual int get() sealed;  
      virtual void set(int i) sealed;  
   }  
};  
```