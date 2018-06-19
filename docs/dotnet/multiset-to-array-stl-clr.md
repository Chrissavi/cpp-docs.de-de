---
title: multiset::to_array (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset::to_array
dev_langs:
- C++
helpviewer_keywords:
- to_array member [STL/CLR]
ms.assetid: 3ca4482d-2584-4a93-89b9-33ea29692de2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0cc47e2a78e49aa9eb5debeae4dc11d9b3e20c6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133099"
---
# <a name="multisettoarray-stlclr"></a>multiset::to_array (STL/CLR)
Kopiert die gesteuerte Sequenz in ein neues Array.  
  
## <a name="syntax"></a>Syntax  
  
```  
cli::array<value_type>^ to_array();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt ein Array mit der kontrollierten Sequenz zurück. Sie können sie eine Kopie der gesteuerten Sequenz im Arrayform abrufen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_multiset_to_array.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.insert(L'd');   
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
 **Header:** \<Cliext/Set >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)