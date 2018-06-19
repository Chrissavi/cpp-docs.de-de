---
title: Compilerwarnung (Stufe 3) C4538 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4538
dev_langs:
- C++
helpviewer_keywords:
- C4538
ms.assetid: 747e3d51-b6d0-41c1-a726-7af3253b59d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1d793da98b2ca4d9d86227177d3782908ef536b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33289762"
---
# <a name="compiler-warning-level-3-c4538"></a>Compilerwarnung (Stufe 3) C4538
'Typ': Const/Volatile-Qualifizierer für diesen Typ werden nicht unterstützt.  
  
 Ein Qualifiziererschlüsselwort wurde falsch in ein Array angewendet. Weitere Informationen finden Sie unter [Array](../../windows/arrays-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C4538 generiert:  
  
```  
// C4538.cpp  
// compile with: /clr /W3 /LD  
const array<int> ^f1();   // C4538  
array<const int> ^f2();   // OK  
```