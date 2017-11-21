---
title: '&lt;new&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
caps.latest.revision: 10
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 6ce4e11a41f199d4ec82a593b53c2f0b7f1c47e4
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="ltnewgt-functions"></a>&lt;new&gt;-Funktionen
|||  
|-|-|  
|[nothrow](#nothrow)|[set_new_handler](#set_new_handler)|  
  
##  <a name="nothrow"></a> nothrow  
 Stellt ein Objekt bereit, das als Argument für die `nothrow`-Versionen von **new** und **delete** verwendet werden muss.  
  
```  
extern const std::nothrow_t nothrow;  
```  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt wird als Funktionsargument verwendet, um auf den Parametertyp [std::nothrow_t](../standard-library/nothrow-t-structure.md) abzustimmen.  
  
### <a name="example"></a>Beispiel  
  Beispiele zur Verwendung von `std::nothrow_t` als Funktionsparameter finden Sie unter [operator new](../standard-library/new-operators.md#op_new) und [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr).  
  
##  <a name="set_new_handler"></a> set_new_handler  
 Installiert eine Benutzerfunktion, die aufgerufen werden muss, wenn `operator new` nicht in der Lage ist, Arbeitsspeicher zu belegen.  
  
```  
new_handler set_new_handler(new_handler Pnew) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `Pnew`  
 Der zu installierende new_handler.  
  
### <a name="return-value"></a>Rückgabewert  
 0 (null) beim ersten Aufruf und der vorherige `new_handler` bei nachfolgenden Aufrufen.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion speichert `Pnew` in einem von ihr verwalteten statischen [new handler](../standard-library/new-typedefs.md#new_handler)-Zeiger und gibt anschließend den Wert zurück, der zuvor im Zeiger gespeichert war. Der neue Handler wird von [operator new](../standard-library/new-operators.md#op_new)( **size_t**) verwendet.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// new_set_new_handler.cpp  
// compile with: /EHsc  
#include<new>  
#include<iostream>  
  
using namespace std;  
void __cdecl newhandler( )  
{  
   cout << "The new_handler is called:" << endl;  
   throw bad_alloc( );  
   return;  
}  
  
int main( )   
{  
   set_new_handler (newhandler);  
   try  
   {  
      while ( 1 )   
      {  
         new int[5000000];  
         cout << "Allocating 5000000 ints." << endl;  
      }  
   }  
   catch ( exception e )  
   {  
      cout << e.what( ) << endl;  
   }  
}  
```  
  
```Output  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
The new_handler is called:  
bad allocation  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<new>](../standard-library/new.md)

