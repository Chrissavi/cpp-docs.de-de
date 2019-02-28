---
title: binder1st-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::binder1st
helpviewer_keywords:
- binder1st class
ms.assetid: 6b8ee343-c82f-48f8-867d-06f9d1d324c0
ms.openlocfilehash: f70a1a4a0903b66edf5f42e59788b9a2d97fc967
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006629"
---
# <a name="binder1st-class"></a>binder1st-Klasse

Eine Vorlagenklasse, mit der ein Konstruktor bereitgestellt wird, der ein binäres Funktionsobjekt in ein unäres Funktionsobjekt konvertiert, indem das erste Argument der binären Funktion an einen angegebenen Wert gebunden wird. Veraltet in C ++ 11 zugunsten des [binden](functional-functions.md#bind), und klicken Sie in C ++ 17 entfernt.

## <a name="syntax"></a>Syntax

```cpp
template <class Operation>
class binder1st
    : public unaryFunction <typename Operation::second_argument_type,
                             typename Operation::result_type>
{
public:
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder1st(
        const Operation& binary_fn,
        const typename Operation::first_argument_type& left);

    result_type operator()(const argument_type& right) const;
    result_type operator()(const argument_type& right) const;

protected:
    Operation op;
    typename Operation::first_argument_type value;
};
```

### <a name="parameters"></a>Parameter

*binary_fn*<br/>
Das binäre Funktionsobjekt, das in ein unäres Funktionsobjekt konvertiert werden soll.

*left*<br/>
Der Wert, an den das erste Argument des binären Funktionsobjekts gebunden werden soll.

*right*<br/>
Der Wert des Arguments, den das angepasste binäre Objekt mit dem festen Wert des zweiten Arguments vergleicht.

## <a name="return-value"></a>Rückgabewert

Das unäre Funktionsobjekt, das Binden des ersten Arguments des binären Funktionsobjekts an den Wert ergibt *linken*.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse speichert eine Kopie eines binären Funktionsobjekts *Binary_fn* in `op`, sowie eine Kopie der *linken* in `value`. Sie definiert ihre Memberfunktion `operator()` als Rückgabewert `op( value, right )`.

Wenn *Binary_fn* ist ein Objekt des Typs `Operation` und `c` ist eine Konstante ist, dann `bind1st( binary_fn, c )` entspricht ein praktischer `binder1st<Operation>( binary_fn, c )`. Weitere Informationen finden Sie unter [bind1st](../standard-library/functional-functions.md#bind1st).

## <a name="example"></a>Beispiel

```cpp
// functional_binder1st.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1;
    result1 = count_if(v1.begin(), v1.end(),
        binder1st<less<int> >(less<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    // Compare use of binder2nd fixing 2nd argument:
    // count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(),
        binder2nd<less<int> >(less<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
/* Output:
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 less than 10 is: 2.
*/
```

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
