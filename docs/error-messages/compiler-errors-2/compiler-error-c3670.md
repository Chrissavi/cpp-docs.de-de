---
title: Compilerfehler C3670 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3670
dev_langs:
- C++
helpviewer_keywords:
- C3670
ms.assetid: d0fa9c6e-8f90-48c7-9066-31b4fa5942eb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed70f364ad72160ddc3b9e875d8b1f3b6ee67e3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266236"
---
# <a name="compiler-error-c3670"></a>Compilerfehler C3670
"override": kann nicht Basisklasse kann nicht zugegriffen werden, Methode "-Schnittstellenmethode überschreiben  
  
 Eine Außerkraftsetzung kann nur auf eine Funktion stattfinden, deren Zugriffsebene in einem abgeleiteten Typ verfügbar macht. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3670 generiert:  
  
```  
// C3670.cpp  
// compile with: /clr /c  
public ref class C {  
// Uncomment the following line to resolve.  
// public:  
   virtual void g() { }  
};  
  
public ref class D : public C {  
public:  
   virtual void f() new sealed = C::g {};   // C3670  
};  
```