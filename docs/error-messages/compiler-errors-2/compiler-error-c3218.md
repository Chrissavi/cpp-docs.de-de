---
title: Compilerfehler C3218 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3218
dev_langs:
- C++
helpviewer_keywords:
- C3218
ms.assetid: 0eea19e0-503e-4e07-ae8b-2cb2e95922cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6938768211a78ca2a72c78ebb03a8972e0a86a74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248268"
---
# <a name="compiler-error-c3218"></a>Compilerfehler C3218
'Typ': Typ nicht als Einschränkung zulässig.  
  
 Für einen Typ, eine Einschränkung muss er entweder ein Werttyp oder ein Verweis auf eine verwaltete Klasse oder Schnittstelle sein.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3218 generiert.  
  
```  
// C3218.cpp  
// compile with: /clr /c  
class A {};  
ref class B {};  
  
// Delete the following 3 lines to resolve.  
generic <class T>  
where T : A   // C3218  
ref class C {};  
  
// OK  
generic <class T>  
where  T : B  
ref class D {};  
```