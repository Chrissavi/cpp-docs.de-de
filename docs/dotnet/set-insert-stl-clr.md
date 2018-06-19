---
title: 'Set:: Insert (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set::insert
dev_langs:
- C++
helpviewer_keywords:
- insert member [STL/CLR]
ms.assetid: 40472869-5c28-4658-b1d3-3ede4d8b8921
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 619dab8844920f61a19c5159fc96c688cafebfdd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33166025"
---
# <a name="setinsert-stlclr"></a>set::insert (STL/CLR)
Fügt Elemente hinzu.  
  
## <a name="syntax"></a>Syntax  
  
```  
cliext::pair<iterator, bool> insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### <a name="parameters"></a>Parameter  
 first  
 Anfang des Bereichs, der eingefügt.  
  
 last  
 Das Ende des Bereichs einfügen.  
  
 Rechts  
 Die Enumeration eingefügt.  
  
 Val  
 Schlüssel-Wert einfügen.  
  
 wo  
 Die Position, im Container (nur Hinweis) einfügen.  
  
## <a name="remarks"></a>Hinweise  
 Jede der Memberfunktionen Fügt eine Sequenz, die von den verbleibenden Operanden angegeben.  
  
 Die erste Memberfunktion zum Einfügen eines Elements mit dem Wert versucht `val`, und gibt ein Wertepaar `X`. Wenn `X.second` ist "true", `X.first` bestimmt das neu eingefügte Element; andernfalls `X.first` kennzeichnet ein Element mit entsprechender Sortierung, die bereits vorhanden ist und kein neues Element eingefügt wird. Es können Sie verwenden, um ein einzelnes Element einzufügen.  
  
 Die zweite Memberfunktion Fügt ein Element mit dem Wert `val`mit `where` als Hinweis (zur Verbesserung der Leistung), und gibt einen Iterator, der das neu eingefügte Element festlegt. Damit können sie ein einzelnes Element einfügen, das neben einem Element möglicherweise, die Sie kennen.  
  
 Die dritte Memberfunktion fügt die Sequenz [`first`, `last`). Sie verwenden ihn zum Einfügen von NULL oder mehr Elementen aus einer anderen Sequenz kopiert.  
  
 Die vierte Memberfunktion fügt die Sequenz, die vom angegebenen der `right`. Sie verwenden es, fügen Sie eine Sequenz, die durch einen Enumerator beschrieben.  
  
 Jede elementeinfügung dauert einige Zeit, die proportional zum Logarithmus der Anzahl der Elemente in der kontrollierten Sequenz. Kann in amortisierter konstanter Zeit, jedoch die Einfügung erhält einen Hinweis, der ein Element, das neben der Einfügemarke festlegt.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_set_insert.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
typedef Myset::pair_iter_bool Pairib;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    Pairib pair1 = c1.insert(L'x');   
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    pair1 = c1.insert(L'b');   
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    System::Console::WriteLine("insert(begin(), L'y') = {0}",   
        *c1.insert(c1.begin(), L'y'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myset c2;   
    Myset::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myset c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(L'x') = [x True]  
insert(L'b') = [b False]  
 a b c x  
insert(begin(), L'y') = y  
 a b c x y  
 a b c x  
 a b c x y  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Set >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [set (STL/CLR)](../dotnet/set-stl-clr.md)