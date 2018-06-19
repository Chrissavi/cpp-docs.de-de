---
title: Compiler-Fehler C2718 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2718
dev_langs:
- C++
helpviewer_keywords:
- C2718
ms.assetid: 78cc71f8-c142-46fc-9aed-970635d74f0c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12ffe631f354c7aef87497e7b21e3a9cd3261c3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236324"
---
# <a name="compiler-error-c2718"></a>Compiler-Fehler C2718 generiert
"Parameter": übergebener Parameter mit __declspec(align('#')) wird nicht ausgerichtet  
  
 Die [ausrichten](../../cpp/align-cpp.md) `__declspec` Modifizierer ist in Funktionsparametern nicht zulässig.  
  
 Im folgende Beispiel wird C2718 generiert:  
  
```  
// C2718.cpp  
typedef struct __declspec(align(32)) AlignedStruct  {   
   int i;   
} AlignedStruct;  
  
void f2(int i, ...);  
  
void f4() {  
   AlignedStruct as;  
  
   f2(0, as);   // C2718, actual parameter is aligned  
}  
```