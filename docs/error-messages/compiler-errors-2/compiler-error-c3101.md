---
title: Compilerfehler C3101 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3101
dev_langs:
- C++
helpviewer_keywords:
- C3101
ms.assetid: 4f673766-d4f7-4632-94a5-d36a83f7f4b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8e10d3b22e7120789b9e1b6bb48fca097fcfddb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247455"
---
# <a name="compiler-error-c3101"></a>Compilerfehler C3101
Ungültiger Ausdruck für das benannte Attributargument 'Feld'  
  
 Wenn ein benanntes Attributargument initialisiert wird, muss der Wert eine Konstante zur Kompilierzeit.  
  
 Weitere Informationen zu Attributen finden Sie unter [benutzerdefinierte Attribute](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3101 generiert.  
  
```  
// C3101.cpp  
// compile with: /clr /c  
ref class AAttribute : System::Attribute {  
public:  
   int Field;  
};  
  
extern int i;  
  
[assembly:A(Field = i)];   // C3101  
[assembly:A(Field = 0)];   // OK  
```