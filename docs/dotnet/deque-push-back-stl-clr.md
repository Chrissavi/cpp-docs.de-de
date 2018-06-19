---
title: 'deque:: push_back (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::push_back
dev_langs:
- C++
helpviewer_keywords:
- push_back member [STL/CLR]
ms.assetid: dafd5a4d-1fc7-434c-b129-a523099f8701
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: eaa2cf2889790a93b90ccf0dc4358a8415feb3fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110669"
---
# <a name="dequepushback-stlclr"></a>deque::push_back (STL/CLR)
Fügt ein neues Letztes Element hinzu.  
  
## <a name="syntax"></a>Syntax  
  
```  
void push_back(value_type val);  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion Fügt ein Element mit dem Wert `val` am Ende der kontrollierten Sequenz. Damit können sie ein anderes Element an die doppelschlange angefügt werden soll.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_deque_push_back.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/doppelschlange >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque:: pop_back (STL/CLR)](../dotnet/deque-pop-back-stl-clr.md)   
 [deque:: pop_front (STL/CLR)](../dotnet/deque-pop-front-stl-clr.md)   
 [deque::push_front (STL/CLR)](../dotnet/deque-push-front-stl-clr.md)