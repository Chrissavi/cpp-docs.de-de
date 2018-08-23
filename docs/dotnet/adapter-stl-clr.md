---
title: Adapter (STL/CLR) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/15/2018
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/adapter>
- cliext::collection_adapter
- cliext::collection_adapter::base
- cliext::collection_adapter::begin
- cliext::collection_adapter
- cliext::collection_adapter::collection_adapter
- cliext::collection_adapter::difference_type
- cliext::collection_adapter::end
- cliext::collection_adapter::iterator
- cliext::collection_adapter::key_type
- cliext::collection_adapter::mapped_type
- cliext::collection_adapter::operator=
- cliext::collection_adapter::reference
- cliext::collection_adapter::size
- cliext::collection_adapter::size_type
- cliext::collection_adapter::swap
- cliext::collection_adapter::value_type
- cliext::make_collection
- cliext::range_adapter
- cliext::operator=
- cliext::range_adapter::operator=
- cliext::range_adapter::range_adapter
dev_langs:
- C++
helpviewer_keywords:
- <adapter> header [STL/CLR]
- adapter [STL/CLR]
- <cliext/adapter> header [STL/CLR]
- collection_adapter class [STL/CLR]
- base member [STL/CLR]
- begin member [STL/CLR]
- collection_adapter member [STL/CLR]
- difference_type member [STL/CLR]
- end member [STL/CLR]
- iterator member [STL/CLR]
- key_type member [STL/CLR]
- mapped_type member [STL/CLR]
- operator= member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- value_type member [STL/CLR]
- make_collection function [STL/CLR]
- range_adapter class [STL/CLR]
- operator= member [STL/CLR]
- range_adapter member [STL/CLR]
ms.assetid: 71ce7e51-42b6-4f70-9595-303791a97677
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7023ef21258a5b93d889d02c1b586b524c8b98be
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2018
ms.locfileid: "42572246"
---
# <a name="adapter-stlclr"></a>adapter (STL/CLR)
Der STL/CLR-Header `<cliext/adapter>` gibt zwei Vorlagenklassen (`collection_adapter` und `range_adapter`), und die Vorlagenfunktion `make_collection`.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
#include <cliext/adapter>  
```  

## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Adapter >  
  
 **Namespace:** Cliext 
  
## <a name="declarations"></a>Deklarationen  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|[collection_adapter (STL/CLR)](#collection_adapter)|Dient als Wrapper für die Basisklassenbibliothek (Base Class Library, BCL)-Sammlung als Bereich.|  
|[range_adapter (STL/CLR)](#range_adapter)|Als eine BCL-Sammlung dient als Wrapper für den Bereich.|  

|Funktion|Beschreibung|  
|--------------|-----------------|  
|[make_collection (STL/CLR)](#make_collection)|Erstellt einen Bereich Adapter mit einem Iteratorpaar.|   
  
## <a name="members"></a>Member

## <a name="collection_adapter"></a> Collection_adapter (STL/CLR)
Dient als Wrapper für eine .NET Collection für die Verwendung als STL/CLR-Container. Ein `collection_adapter` ist eine Vorlagenklasse, die ein einfaches STL/CLR-Container-Objekt beschreibt. Es dient als Wrapper für eine Schnittstelle (Base Class Library, BCL) und gibt ein Iteratorpaar, die Sie verwenden, um die kontrollierte Sequenz zu bearbeiten.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Coll>  
    ref class collection_adapter;  
  
template<>  
    ref class collection_adapter<  
        System::Collections::ICollection>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IEnumerable>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IList>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IDictionary>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::ICollection<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IEnumerable<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IList<Value>>;  
template<typename Key,  
    typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IDictionary<Key, Value>>;  
```  
  
#### <a name="parameters"></a>Parameter  
 *Coll*  
 Der Typ der Wrapper-Auflistung.  
  
### <a name="specializations"></a>Spezialisierungen  
  
|Spezialisierung|Beschreibung|  
|--------------------|-----------------|  
|IEnumerable|Sequenzen durch die Elemente.|  
|ICollection|Verwaltet eine Gruppe von Elementen an.|  
|IList|Verwaltet eine geordnete Gruppe von Elementen an.|  
|IDictionary|Ein Satz von {Schlüssel, Wert} Paare.|  
|"IEnumerable"\<Wert >|Sequenzen durch die Elemente der typisierten.|  
|ICollection\<Wert >|Verwaltet eine Gruppe von typisierten Elementen an.|  
|IList\<Wert >|Verwaltet eine geordnete Menge von typisierten Elementen an.|  
|IDictionary\<Wert >|Verwaltet einen Satz von typisierten {Schlüssel, Wert} Paare.|  
  
### <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[collection_adapter::difference_type (STL/CLR)](#difference_type)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[collection_adapter::iterator (STL/CLR)](#iterator)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[collection_adapter::key_type (STL/CLR)](#key_type)|Der Typ der ein Dictionary-Schlüssel.|  
|[collection_adapter::mapped_type (STL/CLR)](#mapped_type)|Der Typ der ein Dictionary-Wert.|  
|[collection_adapter::reference (STL/CLR)](#reference)|Der Typ eines Verweises auf ein Element.|  
|[collection_adapter::size_type (STL/CLR)](#size_type)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[collection_adapter::value_type (STL/CLR)](#value_type)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[collection_adapter::base (STL/CLR)](#base)|Legt die umschlossene BCL-Schnittstelle.|  
|[collection_adapter::begin (STL/CLR)](#begin)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[collection_adapter::collection_adapter (STL/CLR)](#collection_adapter_collection_adapter)|Erstellt ein Hostnetzwerkadapter-Objekt.|  
|[collection_adapter::end (STL/CLR)](#end)|Legt das Ende der kontrollierten Sequenz fest.|  
|[collection_adapter::size (STL/CLR)](#size)|Ermittelt die Anzahl von Elementen.|  
|[collection_adapter::swap (STL/CLR)](#swap)|Vertauscht den Inhalt von zwei Containern.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[collection_adapter::operator= (STL/CLR)](#op_eq)|Ersetzt das gespeicherte BCL-Handle.|  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Vorlagenklasse, um eine BCL-Container, wie ein STL/CLR-Container zu bearbeiten. Die `collection_adapter` speichert ein Handle für eine BCL-Schnittstelle, die wiederum eine Sequenz von Elementen steuert. Ein `collection_adapter` Objekt `X` gibt ein Paar von eingabeiteratoren `X.begin()` und `X.end()` , besuchen Sie die Elemente, in der Reihenfolge zu verwenden. Einige der spezialisierungen Ihnen außerdem schreiben `X.size()` zum Bestimmen der Länge der kontrollierten Sequenz.  

## <a name="base"></a> collection_adapter::Base (STL/CLR)
Legt die umschlossene BCL-Schnittstelle.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
Coll^ base();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt das gespeicherte Handle der BCL-Schnittstelle zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp
// cliext_collection_adapter_base.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("base() same = {0}", c1.base() == %c1);   
    return (0);   
    }  
```  
  
```Output  
 x x x x x x  
base() same = True  
```  

## <a name="begin"></a> collection_adapter::begin (STL/CLR)
Legt den Anfang der kontrollierten Sequenz fest.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
iterator begin();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einen Eingabe-Iterator, der das erste Element der kontrollierten Sequenz oder direkt hinter das Ende einer leeren Sequenz bestimmt.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_collection_adapter_begin.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Mycoll::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
    return (0);   
    }  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
```  

## <a name="collection_adapter_collection_adapter"></a> collection_adapter::collection_adapter (STL/CLR)
Erstellt ein Hostnetzwerkadapter-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
collection_adapter();  
collection_adapter(collection_adapter<Coll>% right);  
collection_adapter(collection_adapter<Coll>^ right);  
collection_adapter(Coll^ collection);  
```  
  
#### <a name="parameters"></a>Parameter  
 *Auflistung*  
 BCL-Handle zu umschließen.  
  
 *right*  
 Zu kopierende Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor:  
  
 `collection_adapter();`  
  
 Initialisiert das gespeicherte Handle mit `nullptr`.  
  
 Der Konstruktor:  
  
 `collection_adapter(collection_adapter<Coll>% right);`  
  
 Initialisiert das gespeicherte Handle mit `right.` [collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)`()`.  
  
 Der Konstruktor:  
  
 `collection_adapter(collection_adapter<Coll>^ right);`  
  
 Initialisiert das gespeicherte Handle mit `right->` [collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)`()`.  
  
 Der Konstruktor:  
  
 `collection_adapter(Coll^ collection);`  
  
 Initialisiert das gespeicherte Handle mit `collection`.  
  
### <a name="example"></a>Beispiel  
  
```cpp 
// cliext_collection_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
  
// construct an empty container   
    Mycoll c1;   
    System::Console::WriteLine("base() null = {0}", c1.base() == nullptr);   
  
// construct with a handle   
    Mycoll c2(%d6x);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mycoll c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mycoll c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
```  
  
```Output  
base() null = True  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  

## <a name="difference_type"></a> collection_adapter::difference_type (STL/CLR)
Die Typen des Abstands zwischen den beiden Elementen mit Vorzeichen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine signierte Elementanzahl.  
  
### <a name="example"></a>Beispiel  
  
```cpp 
// cliext_collection_adapter_difference_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Mycoll::difference_type diff = 0;   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```  

## <a name="end"></a> collection_adapter::End (STL/CLR)
Legt das Ende der kontrollierten Sequenz fest.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
iterator end();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einem Eingabe-Iterator, der direkt hinter das Ende der kontrollierten Sequenz verweist.  
  
### <a name="example"></a>Beispiel  
  
```cpp 
// cliext_collection_adapter_end.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="iterator"></a> collection_adapter::Iterator (STL/CLR)
Der Typ eines Iterators für die gesteuerte Sequenz.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt vom nicht angegebenen Typ `T1` , die als ein Eingabe-Iterator für die gesteuerte Sequenz fungieren kann.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_collection_adapter_iterator.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="key_type"></a> collection_adapter::KEY_TYPE (STL/CLR)
Der Typ der ein Dictionary-Schlüssel.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter `Key`, in eine Spezialisierung für `IDictionary` oder `IDictionary<Value>`; andernfalls ist es nicht definiert.  
  
### <a name="example"></a>Beispiel  
  
```cpp
// cliext_collection_adapter_key_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef cliext::collection_adapter<   
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;   
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;   
int main()   
    {   
    Mymap d1;   
    d1.insert(Mymap::make_value(L'a', 1));   
    d1.insert(Mymap::make_value(L'b', 2));   
    d1.insert(Mymap::make_value(L'c', 3));   
    Mycoll c1(%d1);   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mypair elem in c1)   
        {   
        Mycoll::key_type key = elem.Key;   
        Mycoll::mapped_type value = elem.Value;   
        System::Console::Write(" [{0} {1}]", key, value);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  

## <a name="mapped_type"></a> collection_adapter::mapped_type (STL/CLR)
Der Typ der ein Dictionary-Wert.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef Value mapped_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter `Value`, in eine Spezialisierung für `IDictionary` oder `IDictionary<Value>`; andernfalls ist es nicht definiert.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_collection_adapter_mapped_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef cliext::collection_adapter<   
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;   
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;   
int main()   
    {   
    Mymap d1;   
    d1.insert(Mymap::make_value(L'a', 1));   
    d1.insert(Mymap::make_value(L'b', 2));   
    d1.insert(Mymap::make_value(L'c', 3));   
    Mycoll c1(%d1);   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mypair elem in c1)   
        {   
        Mycoll::key_type key = elem.Key;   
        Mycoll::mapped_type value = elem.Value;   
        System::Console::Write(" [{0} {1}]", key, value);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  

## <a name="op_eq"></a> collection_adapter::Operator = (STL/CLR)
Ersetzt das gespeicherte BCL-Handle.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
collection_adapter<Coll>% operator=(collection_adapter<Coll>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *right*  
 Der Adapter zu kopieren.  
  
### <a name="remarks"></a>Hinweise  
 Die Member-Operator Kopien *rechten* klicken Sie dann auf das Objekt, gibt `*this`. Damit können Sie das gespeicherte BCL-Handle durch eine Kopie des Handles in gespeicherte BCL ersetzen *rechten*.  
  
### <a name="example"></a>Beispiel  
  
```cpp 
// cliext_collection_adapter_operator_as.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mycoll c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
```  

## <a name="reference"></a> collection_adapter::Reference (STL/CLR)
Der Typ eines Verweises auf ein Element.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt einen Verweis auf ein Element.  
  
### <a name="example"></a>Beispiel  
  
```cpp 
// cliext_collection_adapter_reference.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        Mycoll::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="size"></a> collection_adapter::Size (STL/CLR)
Ermittelt die Anzahl von Elementen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
size_type size();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Länge der gesteuerten Sequenz zurück. Es ist nicht definiert, in eine Spezialisierung für `IEnumerable` oder `IEnumerable<Value>`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_collection_adapter_size.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
```  
  
```Output  
 x x x x x x  
size() = 6  
```  

## <a name="size_type"></a> collection_adapter::size_type (STL/CLR)
Der Typ eines Abstands zwischen den beiden Elementen mit Vorzeichen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine nicht Negative Elementanzahl.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_collection_adapter_size_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    Mycoll::size_type size = c1.size();   
    System::Console::WriteLine("size() = {0}", size);   
    return (0);   
    }  
```  
  
```Output  
 x x x x x x  
size() = 6  
```  

## <a name="swap"></a> collection_adapter::Swap (STL/CLR)
Vertauscht den Inhalt von zwei Containern.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
void swap(collection_adapter<Coll>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *right*  
 Container für den Tausch von Inhalten.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion tauscht den gespeicherten BCL-Handles zwischen `*this` und *rechten*.  
  
### <a name="example"></a>Beispiel  
  
```cpp
// cliext_collection_adapter_swap.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::deque<wchar_t> d2(5, L'x');   
    Mycoll c2(%d2);   
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

## <a name="value_type"></a> collection_adapter::value_type (STL/CLR)
Der Typ eines Elements.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter *Wert*, falls vorhanden, in der Spezialisierung; andernfalls ist dies ein Synonym für `System::Object^`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_collection_adapter_value_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display contents " a b c" using value_type   
    for (Mycoll::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        Mycoll::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="make_collection"></a> Make_collection (STL/CLR)
Stellen Sie eine `range_adapter` von ein Iteratorpaar.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Iter>  
    range_adapter<Iter> make_collection(Iter first, Iter last);  
```  
  
#### <a name="parameters"></a>Parameter  
 *Iter*  
 Der Typ der Wrapper-Iteratoren.  
  
 *Erste*  
 Erste Iterator zu umschließen.  
  
 *last*  
 Zweite Iterator zu umschließen.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion gibt `gcnew range_adapter<Iter>(first, last)` zurück. Damit können Sie erstellen eine `range_adapter<Iter>` Objekt in einem Paar von Iteratoren.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_make_collection.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in d1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Collections::ICollection^ p1 =   
        cliext::make_collection(d1.begin(), d1.end());   
    System::Console::WriteLine("Count = {0}", p1->Count);   
    System::Console::WriteLine("IsSynchronized = {0}",   
        p1->IsSynchronized);   
    System::Console::WriteLine("SyncRoot not nullptr = {0}",   
        p1->SyncRoot != nullptr);   
  
// copy the sequence   
    cli::array<System::Object^>^ a1 = gcnew cli::array<System::Object^>(5);   
  
    a1[0] = L'|';   
    p1->CopyTo(a1, 1);   
    a1[4] = L'|';   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
```  
  
```Output  
 a b c  
Count = 3  
IsSynchronized = False  
SyncRoot not nullptr = True  
 | a b c |  
```  

## <a name="range_adapter"></a> Range_adapter (STL/CLR)
Eine Vorlagenklasse, die ein Paar von Iteratoren, die verwendet werden umschließt, um mehrere (Base Class Library, BCL)-Schnittstellen zu implementieren. Sie verwenden die Range_adapter einen STL/CLR-Bereich bearbeiten, als handele es sich um eine BCL-Auflistung.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parameter  
 *Iter*  
 Der Typ, der die umschlossenen Iteratoren zugeordnet wird.  
  
### <a name="members"></a>Member  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[range_adapter::range_adapter (STL/CLR)](#range_adapter_range_adapter)|Erstellt ein Hostnetzwerkadapter-Objekt.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[range_adapter::operator= (STL/CLR)](#range_adapter_op_eq)|Ersetzt den gespeicherten Iterator-Paar.|  
  
### <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|<xref:System.Collections.IEnumerable>|Durchlaufen Elemente in der Auflistung ein.|  
|<xref:System.Collections.ICollection>|Verwaltet eine Gruppe von Elementen an.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Typisierter Elemente in der Auflistung wird durchlaufen...|  
|<xref:System.Collections.Generic.ICollection%601>|Verwaltet eine Gruppe von typisierten Elementen an.|  
  
### <a name="remarks"></a>Hinweise  
 Die Range_adapter speichert ein Paar von Iteratoren, die wiederum eine Sequenz von Elementen zu begrenzen. Das Objekt implementiert vier BCL-Schnittstellen, mit denen Sie die Elemente, in Reihenfolge durchlaufen. Sie verwenden diese Vorlagenklasse zum Bearbeiten von STL/CLR-Bereiche, ähnlich wie die BCL-Container.  

## <a name="range_adapter_op_eq"></a> range_adapter::Operator = (STL/CLR)
Ersetzt den gespeicherten Iterator-Paar.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
range_adapter<Iter>% operator=(range_adapter<Iter>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *right*  
 Der Adapter zu kopieren.  
  
### <a name="remarks"></a>Hinweise  
 Die Member-Operator Kopien *rechten* klicken Sie dann auf das Objekt, gibt `*this`. Damit können Sie den gespeicherten Iterator-Paar mit einer Kopie der gespeicherte Iterator-Paar im ersetzen *rechten*.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_range_adapter_operator_as.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Myrange c1(d1.begin(), d1.end());   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myrange c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
```  

## <a name="range_adapter_range_adapter"></a> range_adapter::range_adapter (STL/CLR)
Erstellt ein Hostnetzwerkadapter-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
range_adapter();  
range_adapter(range_adapter<Iter>% right);  
range_adapter(range_adapter<Iter>^ right);  
range_adapter(Iter first, Iter last);  
```  
  
#### <a name="parameters"></a>Parameter  
 *Erste*  
 Erste Iterator zu umschließen.  
  
 *last*  
 Zweite Iterator zu umschließen.  
  
 *right*  
 Zu kopierende Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor:  
  
 `range_adapter();`  
  
 Initialisiert den gespeicherten Iterator-Paar mit Standardeinstellungen erstellt Iteratoren.  
  
 Der Konstruktor:  
  
 `range_adapter(range_adapter<Iter>% right);`  
  
 Initialisiert den gespeicherten Iterator-Paar durch Kopieren des Paars in gespeicherten *rechten*.  
  
 Der Konstruktor:  
  
 `range_adapter(range_adapter<Iter>^ right);`  
  
 Initialisiert den gespeicherten Iterator-Paar durch Kopieren des Paars in gespeicherten `*right`.  
  
 Der Konstruktor:  
  
 `range_adapter(Iter^ first, last);`  
  
 Initialisiert den gespeicherten Iterator-Paar mit *erste* und *letzten*.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_range_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
  
// construct an empty adapter   
    Myrange c1;   
  
// construct with an iterator pair   
    Myrange c2(d1.begin(), d1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another adapter   
    Myrange c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying an adapter handle   
    Myrange c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
a b c  
```  