---
title: Compilerfehler C2316 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2316
dev_langs:
- C++
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 895db6535299a077bc32b6485a360ae450e6c87e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196843"
---
# <a name="compiler-error-c2316"></a>Compilerfehler C2316

> "*Ausnahme*": kann nicht aufgefangen werden, da der Destruktor und/oder den Kopierkonstruktor nicht zugegriffen werden kann  
  
Eine Ausnahme wurde durch einen Wert oder Verweis abgefangen, aber auf den copy-Konstruktor und/oder den Zuweisungsoperator konnte nicht zugegriffen werden.  
  
Dieser Code wurde von Versionen von Visual C++ vor Visual Studio 2003 akzeptiert, aber jetzt ein Fehler generiert.  
  
Konformitätsänderungen in Visual Studio 2015 vorgenommen, diese Fehler zuweisen ungültige Catch-Anweisungen von MFC-Ausnahmen abgeleitet wurde. `CException`. Da `CException` verfügt über eine geerbte privaten Kopierkonstruktor, die Klasse und die Ableitung nicht kopiert werden und nicht anhand des Werts bedeutet auch, dass sie können nicht aufgefangen werden, als Wert übergeben werden. Catch-Anweisungen, die MFC-Ausnahmen vom Wert, der zuvor geführt, die zur Laufzeit nicht abgefangene Ausnahmen abgefangen, aber der Compiler jetzt ordnungsgemäß identifiziert, diese Situation und meldet Fehler C2316. Um dieses Problem zu beheben, wird empfohlen, dass Sie die MFC-TRY/CATCH-Makros verwenden, anstatt eigene Ausnahmehandler schreiben, aber wenn dies nicht für Ihren Code geeignet ist, MFC-Ausnahmen als Verweis stattdessen abfangen.   
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2316 generiert:  
  
```  
// C2316.cpp  
// compile with: /EHsc  
#include <stdio.h>  
  
extern "C" int printf_s(const char*, ...);  
  
struct B   
{  
public:  
    B() {}  
    // Delete the following line to resolve.  
private:  
    // copy constructor  
    B(const B&)   
    {  
    }  
};  
  
void f(const B&)   
{  
}  
  
int main()   
{  
    try   
    {  
        B aB;  
        f(aB);  
    }  
    catch (B b) {   // C2316  
        printf_s("Caught an exception!\n");     
    }  
}  
```