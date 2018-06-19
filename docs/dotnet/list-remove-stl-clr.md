---
title: 'List:: Remove (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::remove
dev_langs:
- C++
helpviewer_keywords:
- remove member [STL/CLR]
ms.assetid: eaf598ee-e8fd-4cc0-be69-ca81a80e1d51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 785affb742b0055c0b146006d33ec0ed031c93b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33134064"
---
# <a name="listremove-stlclr"></a>list::remove (STL/CLR)
Entfernt ein Element mit einem angegebenen Wert.  
  
## <a name="syntax"></a>Syntax  
  
```  
void remove(value_type val);  
```  
  
#### <a name="parameters"></a>Parameter  
 Val  
 Der Wert des zu entfernenden Elements.  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion entfernt ein Element in der kontrollierten Sequenz an, für die `((System::Object^)val)->Equals((System::Object^)x)` ist "true" (sofern vorhanden). Sie verwenden es, um ein beliebiges Element mit dem angegebenen Wert zu löschen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_remove.cpp   
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
  
// fail to remove and redisplay   
    c1.remove(L'A');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();  
  
// remove and redisplay   
    c1.remove(L'b');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List:: Clear (STL/CLR)](../dotnet/list-clear-stl-clr.md)   
 [List:: Erase (STL/CLR)](../dotnet/list-erase-stl-clr.md)   
 [list::remove_if (STL/CLR)](../dotnet/list-remove-if-stl-clr.md)