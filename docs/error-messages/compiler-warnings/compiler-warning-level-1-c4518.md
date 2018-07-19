---
title: Compilerwarnung (Stufe 1) C4518 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4518
dev_langs:
- C++
helpviewer_keywords:
- C4518
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e9dc0c7def2819f3a882667efb073c565707712
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272158"
---
# <a name="compiler-warning-level-1-c4518"></a>Compilerwarnung (Stufe 1) C4518
"Spezifizierer": Speicher-Klasse, oder geben Sie hier; unerwartete(r) ignoriert  
  
 Im folgenden Beispiel wird C4518 generiert:  
  
```  
// C4518.cpp  
// compile with: /c /W1  
_declspec(dllexport) extern "C" void MyFunction();   // C4518  
  
extern "C" void MyFunction();   // OK  
```