---
title: 'hash_map:: key_compare (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::key_compare
dev_langs:
- C++
helpviewer_keywords:
- key_compare member [STL/CLR]
ms.assetid: 9564d049-67fc-4293-b896-c4a96e771f86
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 289a7e80dbb5f90e6ae033d27329592d24266436
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111509"
---
# <a name="hashmapkeycompare-stlclr"></a>hash_map::key_compare (STL/CLR)
Der Delegat für zwei Schlüssel.  
  
## <a name="syntax"></a>Syntax  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>  
    key_compare;  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Delegaten, der die Reihenfolge der Schlüssel Argumente bestimmt.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_map_key_compare.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    Myhash_map::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Myhash_map c2 = cliext::greater<wchar_t>();   
    kcomp = c2.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    return (0);   
    }  
  
```  
  
```Output  
compare(L'a', L'a') = True  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
  
compare(L'a', L'a') = False  
compare(L'a', L'b') = False  
compare(L'b', L'a') = True  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_map/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_map-Element (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map:: key_comp (STL/CLR)](../dotnet/hash-map-key-comp-stl-clr.md)   
 [hash_map:: KEY_TYPE (STL/CLR)](../dotnet/hash-map-key-type-stl-clr.md)   
 [hash_map::value_compare (STL/CLR)](../dotnet/hash-map-value-compare-stl-clr.md)