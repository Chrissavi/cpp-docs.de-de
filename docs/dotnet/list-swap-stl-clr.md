---
title: 'List:: Swap (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::swap
dev_langs:
- C++
helpviewer_keywords:
- swap member [STL/CLR]
ms.assetid: 188b66c2-0a08-4001-a566-41d0955c89bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 298744c52e7cf68b8da9d1503014f72b695fe464
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132374"
---
# <a name="listswap-stlclr"></a>list::swap (STL/CLR)
Vertauscht den Inhalt von zwei Containern.  
  
## <a name="syntax"></a>Syntax  
  
```  
void swap(list<Value>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 Rechts  
 Container für den Tausch von Inhalten.  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion tauscht die kontrollierten Sequenzen zwischen `*this` und `right`aus. Dies erfolgt in konstanter Zeit, und es löst keine Ausnahmen. Sie verwenden es als eine schnelle Möglichkeit zum Austauschen von den Inhalt von zwei Containern.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_swap.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::list<wchar_t> c2(5, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
x x x x x  
x x x x x  
a b c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List:: Assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)   
 [list::operator= (STL/CLR)](../dotnet/list-operator-assign-stl-clr.md)