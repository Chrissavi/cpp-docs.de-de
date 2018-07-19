---
title: Compilerfehler C3461 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3461
dev_langs:
- C++
helpviewer_keywords:
- C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0b9349ed9450c6d74a9311d5b9265f57cc37b81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33255979"
---
# <a name="compiler-error-c3461"></a>Compilerfehler C3461
'Typ': Nur ein verwalteter Typ kann weitergeleitet werden.  
  
 Die Typweiterleitung ist nur bei CLR-Typen möglich.  Finden Sie unter [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md) für Weitere Informationen.  
  
 Weitere Informationen finden Sie unter [Typweiterleitung (C + c++ / CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Komponente erstellt:  
  
```  
// C3461.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3461 generiert:  
  
```  
// C3461b.cpp  
// compile with: /clr /c  
#using "C3461.dll"  
class N {};  
[assembly:TypeForwardedTo(N::typeid)];   // C3461  
[assembly:TypeForwardedTo(R::typeid)];   // OK  
```