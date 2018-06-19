---
title: 'Map:: Count (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::Count
dev_langs:
- C++
helpviewer_keywords:
- count member [STL/CLR]
ms.assetid: 835f5b11-cb15-4a0b-8808-cd9b36c83e0b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8ef3497c94e45de83afc2412948b354a11e8224d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136693"
---
# <a name="mapcount-stlclr"></a>map::count (STL/CLR)
Sucht die Anzahl von Elementen, die einem angegebenen Schlüssel entsprechen.  
  
## <a name="syntax"></a>Syntax  
  
```  
size_type count(key_type key);  
```  
  
#### <a name="parameters"></a>Parameter  
 Key  
 Der zu suchende Schlüsselwert.  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Anzahl der Elemente in der kontrollierten Sequenz, die über entsprechende Sortierung mit `key`. Es können Sie verwenden, um die Anzahl der Elemente, die derzeit in der gesteuerten Sequenz zu ermitteln, die einen angegebenen Schlüssel entsprechen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_map_count.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
count(L'A') = 0  
count(L'b') = 1  
count(L'C') = 0  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Map >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Karte (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map::equal_range (STL/CLR)](../dotnet/map-equal-range-stl-clr.md)