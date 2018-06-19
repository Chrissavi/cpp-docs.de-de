---
title: Compilerfehler C3236 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3236
dev_langs:
- C++
helpviewer_keywords:
- C3236
ms.assetid: 4ef1871f-a348-44ae-922b-1e2081de20d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bdcbab59744fcaac88836656639a0fa777aefb6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248169"
---
# <a name="compiler-error-c3236"></a>Compilerfehler C3236
Die explizite Instanziierung von Generika ist nicht zulässig.  
  
 Der Compiler lässt keine explizite Instanziierung von generischen Klassen zu.  
  
 Im folgenden Beispiel wird C3236 generiert:  
  
```  
// C3236.cpp  
// compile with: /clr  
generic<class T>  
public ref class X {};  
  
generic ref class X<int>;   // C3236  
```  
  
 Das folgende Beispiel zeigt eine mögliche Lösung:  
  
```  
// C3236b.cpp  
// compile with: /clr /c  
generic<class T>  
public ref class X {};  
```