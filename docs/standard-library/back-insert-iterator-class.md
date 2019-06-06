---
title: back_insert_iterator-Klasse
ms.date: 11/04/2016
f1_keywords:
- iterator/std::back_insert_iterator
- iterator/std::back_insert_iterator::container_type
- iterator/std::back_insert_iterator::reference
helpviewer_keywords:
- std::back_insert_iterator [C++]
- std::back_insert_iterator [C++], container_type
- std::back_insert_iterator [C++], reference
ms.assetid: a1ee07f2-cf9f-46a1-8608-cfaf207f9713
ms.openlocfilehash: 2a0510b6df656b7925fd42a4c97d768336537424
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376444"
---
# <a name="backinsertiterator-class"></a>back_insert_iterator-Klasse

Beschreibt einen Iteratoradapter, der den Anforderungen eines Ausgabeiterators entspricht. Er fügt Elemente in das Ende einer Sequenz ein, anstatt sie zu überschreiben, und bietet somit Semantik, die sich von der Semantik zum Überschreiben unterscheidet, die von den Iteratoren der C++-Sequenzcontainer bereitgestellt wird. Die `back_insert_iterator`-Klasse ist für den Typ des Containers vorlagenbasiert.

## <a name="syntax"></a>Syntax

```cpp
template <class Container>
class back_insert_iterator;
```

### <a name="parameters"></a>Parameter

*Container*<br/>
Der Typ des Containers, an dessen Ende Elemente von einem `back_insert_iterator` eingefügt werden sollen.

## <a name="remarks"></a>Hinweise

Der Container muss den Anforderungen einer Sequenz zum Einfügen am Ende entsprechen, in der es möglich ist, die Elemente am Ende der Sequenz in amortisierter konstanter Zeit einzufügen. Die C++-Standardbibliothek-Sequenzcontainer, die von der [deque](../standard-library/deque-class.md)-Klasse, der [list](../standard-library/list-class.md)-Klasse und der [vector](../standard-library/vector-class.md)-Klasse definiert werden, stellen die erforderliche `push_back`-Memberfunktion bereit, und erfüllen diese Anforderungen. Diese drei Container sowie Zeichenfolgen werden jeweils für die Verwendung mit `back_insert_iterator` angepasst. Ein `back_insert_iterator` muss immer mit seinem Container initialisiert werden.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[back_insert_iterator](#back_insert_iterator)|Erstellt einen `back_insert_iterator`, der Elemente nach dem letzten Element in einen Container einfügt.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[container_type](#container_type)|Ein Typ, der einen Container für den `back_insert_iterator` bereitstellt.|
|[Verweis](#reference)|Ein Typ, der einen Verweis für den `back_insert_iterator` bereitstellt.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator*](#op_star)|Der Dereferenzierungsoperator, der zum Implementieren des ausgabeiteratorausdrucks \* `i`  =  `x` für eine Einfügung.|
|[operator++](#op_add_add)|Inkrementiert `back_insert_iterator` zum folgenden Speicherort, an dem ein Wert gespeichert werden kann.|
|[operator=](#op_eq)|Zuweisungsoperator, der zum Implementieren des ausgabeiteratorausdrucks \* `i`  =  `x` für eine Einfügung.|

## <a name="requirements"></a>Anforderungen

**Header**: \<iterator>

**Namespace:** std

## <a name="back_insert_iterator"></a> back_insert_iterator::back_insert_iterator

Erstellt einen `back_insert_iterator`, der Elemente nach dem letzten Element in einen Container einfügt.

```cpp
explicit back_insert_iterator(Container& _Cont);
```

### <a name="parameters"></a>Parameter

*_Cont*<br/>
Der Container, in den `back_insert_iterator` ein Element einfügen soll.

### <a name="return-value"></a>Rückgabewert

Ein `back_insert_iterator` für den Parametercontainer.

### <a name="example"></a>Beispiel

```cpp
// back_insert_iterator_back_insert_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 1 ; i < 4 ; ++i )
   {
      vec.push_back ( i );
   }

   vector <int>::iterator vIter;
   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   // Insertions with member function
   back_inserter ( vec ) = 40;
   back_inserter ( vec ) = 50;

   // Alternatively, insertions can be done with template function
   back_insert_iterator<vector<int> > backiter ( vec );
*backiter = 600;
   backiter++;
*backiter = 700;

   cout << "After the insertions, the vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;
}
```

```Output
The initial vector vec is: ( 1 2 3 ).
After the insertions, the vector vec is: ( 1 2 3 40 50 600 700 ).
```

## <a name="container_type"></a> back_insert_iterator::container_type

Ein Typ, der einen Container für den `back_insert_iterator` bereitstellt.

```cpp
typedef Container
container_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist synonym mit dem Vorlagenparameter **Container**.

### <a name="example"></a>Beispiel

```cpp
// back_insert_iterator_container_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 4 ; ++i )
   {
      vec.push_back (  i );
   }

   vector <int>::iterator vIter;
   cout << "The original vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   back_insert_iterator<vector<int> >::container_type vec1 = vec;
   back_inserter ( vec1 ) = 40;

   cout << "After the insertion, the vector is: ( ";
   for ( vIter = vec1.begin ( ) ; vIter != vec1.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;
}
```

```Output
The original vector vec is: ( 1 2 3 ).
After the insertion, the vector is: ( 1 2 3 40 ).
```

## <a name="op_star"></a>  back_insert_iterator:: Operator\*

Der Dereferenzierungsoperator, der zum Implementieren des Ausgabeiteratorausdrucks \* *i* = *x* verwendet wird.

```cpp
back_insert_iterator<Container>& operator*();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das am Ende des Containers eingefügte Element.

### <a name="remarks"></a>Hinweise

Wird zum Implementieren des Ausgabeiteratorausdrucks **\*Iter** = **value** verwendet. Wenn **Iter** ein Iterator ist, der ein Element in einer Sequenz adressiert, dann ersetzt **\*Iter** = **value** das Element mit Wert, ohne dass die Gesamtzahl von Elementen in der Zeichenfolge geändert wird.

### <a name="example"></a>Beispiel

```cpp
// back_insert_iterator_back_insert.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 4 ; ++i )
   {
      vec.push_back ( i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   back_insert_iterator<vector<int> > backiter ( vec );
*backiter = 10;
   backiter++;      // Increment to the next element
*backiter = 20;
   backiter++;

   cout << "After the insertions, the vector vec becomes: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;
}
```

```Output
The vector vec is: ( 1 2 3 ).
After the insertions, the vector vec becomes: ( 1 2 3 10 20 ).
```

## <a name="op_add_add"></a> back_insert_iterator::operator++

Inkrementiert `back_insert_iterator` zum folgenden Speicherort, an dem ein Wert gespeichert werden kann.

```cpp
back_insert_iterator<Container>& operator++();
back_insert_iterator<Container> operator++(int);
```

### <a name="return-value"></a>Rückgabewert

Ein `back_insert_iterator`, der den nächsten Speicherort adressiert, an dem ein Wert gespeichert werden kann

### <a name="remarks"></a>Hinweise

Sowohl der Prä- als auch der Postinkrement-Operator geben das gleichen Ergebnis zurück.

### <a name="example"></a>Beispiel

```cpp
// back_insert_iterator_op_incre.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 3 ; ++i )
   {
      vec.push_back ( 10 * i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   back_insert_iterator<vector<int> > backiter ( vec );
*backiter = 30;
   backiter++;      // Increment to the next element
*backiter = 40;
   backiter++;

   cout << "After the insertions, the vector vec becomes: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;
}
```

```Output
The vector vec is: ( 10 20 ).
After the insertions, the vector vec becomes: ( 10 20 30 40 ).
```

## <a name="op_eq"></a> back_insert_iterator::operator=

Fügt einen Wert am Ende eines Containers ein, oder überträgt einen Wert dorthin.

```cpp
back_insert_iterator<Container>& operator=(typename Container::const_reference val);
back_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```

### <a name="parameters"></a>Parameter

*val*<br/>
Der Wert, der in den Container eingefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das letzte am Ende des Containers eingefügte Element.

### <a name="remarks"></a>Hinweise

Der erste Memberoperator wertet `Container.push_back( val)` aus

und gibt danach `*this` zurück. Der zweite Memberoperator wertet Folgendes aus:

`container->push_back((typename Container::value_type&&)val)`,

Danach gibt er `*this` zurück.

### <a name="example"></a>Beispiel

```cpp
// back_insert_iterator_op_assign.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 4 ; ++i )
   {
      vec.push_back ( i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   back_insert_iterator<vector<int> > backiter ( vec );
*backiter = 10;
   backiter++;      // Increment to the next element
*backiter = 20;
   backiter++;

   cout << "After the insertions, the vector vec becomes: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;
}
```

## <a name="reference"></a> back_insert_iterator::reference

Ein Typ, der einen Verweis für den `back_insert_iterator` bereitstellt.

```cpp
typedef typename Container::reference reference;
```

### <a name="remarks"></a>Hinweise

Ein Typ beschreibt den Verweis auf ein Element in der Sequenz, die durch den zugehörigen Container gesteuert wird.

### <a name="example"></a>Beispiel

```cpp
// back_insert_iterator_reference.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 4 ; ++i )
   {
      vec.push_back ( i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   back_insert_iterator<vector<int> >::reference
        RefLast = *(vec.end ( ) - 1 );
   cout << "The last element in the vector vec is: "
        << RefLast << "." << endl;
}
```

```Output
The vector vec is: ( 1 2 3 ).
The last element in the vector vec is: 3.
```

## <a name="see-also"></a>Siehe auch

[\<iterator>](../standard-library/iterator.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
