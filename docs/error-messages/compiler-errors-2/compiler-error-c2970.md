---
title: Compilerfehler C2970 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2970
dev_langs:
- C++
helpviewer_keywords:
- C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0775f9d771b2c9497b3dc731e26c6a3b4e6ab30c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246538"
---
# <a name="compiler-error-c2970"></a>Compilerfehler C2970
'Klasse': Template-Parameter 'Param': 'Arg': ein Ausdruck, der Objekte mit interner Verknüpfung kann nicht als Nichttyp-Argument verwendet werden  
  
 Sie können nicht den Namen oder die Adresse einer statischen Variablen als Vorlagenargument verwenden. Die Vorlagenklasse erwartet einen konstanten Wert, der zur Kompilierzeit ausgewertet werden kann.  
  
 Im folgende Beispiel wird C2970 generiert:  
  
```  
// C2970.cpp  
// compile with: /c  
static int si;  
// could declare nonstatic to resolve all errors  
// int si;  
  
template <int i>   
class X {};  
  
template <int *pi>   
class Y {};  
  
X<si> anX;   // C2970 cannot use static variable in templates  
  
// this would also work  
const int i = 10;  
X<i> anX2;  
```