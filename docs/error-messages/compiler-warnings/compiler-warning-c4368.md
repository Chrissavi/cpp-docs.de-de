---
title: Compilerwarnung C4368 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4368
dev_langs:
- C++
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3a7e53c979a3b13bde205a4546c486061a17110
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270495"
---
# <a name="compiler-warning-c4368"></a>Compilerwarnung C4368
'Member' kann nicht als Member des verwalteten 'Typs' definiert werden: Gemischte Typen werden nicht unterstützt  
  
 Sie können keinen systemeigenen Datenmember in einen CLR-Typ einbetten.  
  
 Sie können jedoch einen Zeiger auf einen systemeigenen Typ deklarieren und dessen Lebensdauer im Konstruktor, Destruktor und Finalizer der verwalteten Klasse steuern. Weitere Informationen finden Sie unter [Destruktoren und Finalizer](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 Diese Warnmeldung wird immer als Fehler ausgegeben. Verwenden der [Warnung](../../preprocessor/warning.md) Pragma C4368 deaktivieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4368 generiert.  
  
```  
// C4368.cpp  
// compile with: /clr /c  
struct N {};  
ref struct O {};  
ref struct R {  
    R() : m_p( new N ) {}  
    ~R() { delete m_p; }  
  
   property N prop;   // C4368  
   int i[10];   // C4368  
  
   property O ^ prop2;   // OK  
   N * m_p;   // OK  
};  
```