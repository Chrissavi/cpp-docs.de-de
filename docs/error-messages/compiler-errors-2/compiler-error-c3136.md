---
title: Compiler-Fehler C3136 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3136
dev_langs:
- C++
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f892c7f3d1ca7bf2aebf3ecfe7574182b544fd01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248850"
---
# <a name="compiler-error-c3136"></a>Compiler-Fehler C3136 generiert
'Schnittstelle': eine COM-Schnittstelle kann nur von einem anderen COM-Schnittstelle erben, 'Schnittstelle' ist keine COM-Schnittstelle  
  
 Eine Schnittstelle für die Sie gilt eine [Schnittstellenattribut](../../windows/interface-attributes.md) erbt von einer Schnittstelle, die keine COM-Schnittstelle ist. Eine COM-Schnittstelle erbt letztlich von `IUnknown`. Eine beliebige Schnittstelle vorangestellt Interface-Attribut ist eine COM-Schnittstelle.  
  
 Im folgende Beispiel wird C3136 generiert:  
  
```  
// C3136.cpp  
#include "unknwn.h"  
  
__interface A   // C3136  
// try the following line instead  
// _interface A : IUnknown  
{  
   int a();  
};  
  
[object]  
__interface B : A  
{  
   int aa();  
};  
```