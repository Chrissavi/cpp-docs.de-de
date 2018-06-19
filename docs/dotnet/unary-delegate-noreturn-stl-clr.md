---
title: Unary_delegate_noreturn (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::unary_delegate_noreturn
dev_langs:
- C++
helpviewer_keywords:
- unary_delegate_noreturn function [STL/CLR]
ms.assetid: 3c3fb143-f60f-4e28-a66b-690e3a7b2f9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: aad513cef26d4dcdc5f0b02ec7a22c88c629f57c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167836"
---
# <a name="unarydelegatenoreturn-stlclr"></a>unary_delegate_noreturn (STL/CLR)
Die Genereic Klasse beschreibt einen Delegaten mit nur einem Argument, die zurückgibt `void`. Sie verwenden, geben Sie einen Delegaten im Hinblick auf seine Argumenttyp.  
  
## <a name="syntax"></a>Syntax  
  
```  
generic<typename Arg>  
    delegate void unary_delegate_noreturn(Arg);  
```  
  
#### <a name="parameters"></a>Parameter  
 arg  
 Der Typ des Arguments.  
  
## <a name="remarks"></a>Hinweise  
 Der Delegat Genereic beschreibt eine Funktion von nur einem Argument, zurückgibt `void`.  
  
 Beachten Sie, dass für:  
  
 `unary_delegare_noreturn<int> Fun1;`  
  
 `unary_delegare_noreturn<int> Fun2;`  
  
 die Typen `Fun1` und `Fun2` sind Synonyme, während er sich für:  
  
 `delegate void Fun1(int);`  
  
 `delegate void Fun2(int);`  
  
 sind sie nicht den gleichen Typ.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_unary_delegate_noreturn.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
void hash_val(wchar_t val)   
    {   
    System::Console::WriteLine("hash({0}) = {1}",   
       val, (val * 17 + 31) % 67);   
    }   
  
typedef cliext::unary_delegate_noreturn<wchar_t> Mydelegate;   
int main()   
    {   
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);   
  
    myhash(L'a');   
    myhash(L'b');   
    return (0);   
    }  
  
```  
  
```Output  
hash(a) = 5  
hash(b) = 22  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/funktionale >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Binary_delegate (STL/CLR)](../dotnet/binary-delegate-stl-clr.md)   
 [Binary_delegate_noreturn (STL/CLR)](../dotnet/binary-delegate-noreturn-stl-clr.md)   
 [unary_delegate (STL/CLR)](../dotnet/unary-delegate-stl-clr.md)