---
title: Map::make_value (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::make_value
dev_langs:
- C++
helpviewer_keywords:
- make_value member [STL/CLR]
ms.assetid: a0bc4081-b8b7-450e-b041-a49ac42b279f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 14d238d8ecfbbff4675c3a46da8afb46561cec6b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133122"
---
# <a name="mapmakevalue-stlclr"></a>map::make_value (STL/CLR)
Erstellt ein Wertobjekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
static value_type make_value(key_type key, mapped_type mapped);  
```  
  
#### <a name="parameters"></a>Parameter  
 Key  
 Schlüsselwert verwenden.  
  
 Zugeordnet  
 Zugeordnet zu suchende Wert.  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt eine `value_type` Objekts, dessen Schlüssel `key` und dessen zugeordnete Wert ist `mapped`. Sie verwenden es, um ein Objekt, das für die Verwendung mit anderen Memberfunktionen geeignet zu verfassen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_map_make_value.cpp   
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
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Map >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Karte (STL/CLR)](../dotnet/map-stl-clr.md)   
 [Map:: KEY_TYPE (STL/CLR)](../dotnet/map-key-type-stl-clr.md)   
 [Map:: mapped_type (STL/CLR)](../dotnet/map-mapped-type-stl-clr.md)   
 [map::value_type (STL/CLR)](../dotnet/map-value-type-stl-clr.md)