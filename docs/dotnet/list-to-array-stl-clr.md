---
title: List::to_array (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::to_array
dev_langs:
- C++
helpviewer_keywords:
- to_array member [STL/CLR]
ms.assetid: 3ea7b90c-127b-43cd-804b-019b86b77582
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 65e733bed845a1ad071c9ad66a043fa250812869
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130668"
---
# <a name="listtoarray-stlclr"></a>list::to_array (STL/CLR)
Kopiert die gesteuerte Sequenz in ein neues Array.  
  
## <a name="syntax"></a>Syntax  
  
```  
cli::array<Value>^ to_array();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt ein Array mit der kontrollierten Sequenz zurück. Sie können sie eine Kopie der gesteuerten Sequenz im Arrayform abrufen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_to_array.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push_back(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c d  
a b c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)