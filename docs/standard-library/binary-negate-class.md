---
title: binary_negate-Klasse| Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::binary_negate
dev_langs:
- C++
helpviewer_keywords:
- binary_negate class
ms.assetid: 7b86f02c-af7e-4c7f-9df1-08addae4dd65
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 58d71ef5d3b2b50ec9d51668e4420c99ef9f3b17
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108823"
---
# <a name="binarynegate-class"></a>binary_negate-Klasse

Eine Klasse, mit der eine Memberfunktion bereitgestellt wird, die den Rückgabewert einer angegebenen binären Funktion negiert.

## <a name="syntax"></a>Syntax

```cpp
template <class Operation>
class binary_negate
    : public binaryFunction <typename Operation::first_argument_type,
                              typename Operation::second_argument_type, bool>
{
public:
    explicit binary_negate(const Operation& Func);
    bool operator()(const typename Operation::first_argument_type& left,
                    const typename Operation::second_argument_type& right) const;
};
```

### <a name="parameters"></a>Parameter

*Func*<br/>
Die binäre Funktion, die negiert werden soll.

*left*<br/>
Der linke Operand der binären Funktion, die negiert werden soll.

*right*<br/>
Der rechte Operand der binären Funktion, die negiert werden soll.

## <a name="return-value"></a>Rückgabewert

Die Negation der binären Funktion.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse speichert eine Kopie eines binären Funktionsobjekts _ *Func*. Für seine Memberfunktion `operator()` definiert die Klasse **!**\_ als Rückgabewert. *Func(left, right).*

Der Konstruktor von `binary_negate` wird nur selten direkt verwendet. Die Hilfsfunktion [not2](../standard-library/functional-functions.md#not2) wird normalerweise bevorzugt für das Deklarieren verwendet und verwendet das Adapterprädikat **binary_negator**.

## <a name="example"></a>Beispiel

```cpp
// functional_binary_negate.cpp
// compile with: /EHsc
#define _CRT_RAND_S
#include <stdlib.h>

#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   vector <unsigned int> v1;
   vector <unsigned int>::iterator Iter1;

   unsigned int i;
   v1.push_back( 6262 );
   v1.push_back( 6262 );
   unsigned int randVal = 0;
   for ( i = 0 ; i < 5 ; i++ )
   {
      rand_s(&randVal);
      v1.push_back( randVal );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use default binary predicate less<unsigned int>( )
   sort( v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order,
   // use the binary_negate function
   sort( v1.begin( ), v1.end( ),
   binary_negate<less<unsigned int> >(less<unsigned int>( ) ) );

   // The helper function not2 could also have been used
   // in the above line and is usually preferred for convenience
   // sort( v1.begin( ), v1.end( ), not2(less<unsigned int>( ) ) );

   cout << "Resorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
\* Output:
Original vector v1 = ( 6262 6262 2233879413 2621500314 580942933 3715465425 3739828298 )
Sorted vector v1 = ( 6262 6262 580942933 2233879413 2621500314 3715465425 3739828298 )
Resorted vector v1 = ( 3739828298 3715465425 2621500314 2233879413 580942933 6262 6262 )
*\
```

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
