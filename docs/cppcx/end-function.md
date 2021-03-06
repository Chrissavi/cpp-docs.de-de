---
title: end-Funktion
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::end
helpviewer_keywords:
- end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
ms.openlocfilehash: c46c601be2b2ed78cf79641a7fcf5324e615a771
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375807"
---
# <a name="end-function"></a>end-Funktion

Gibt einen Iterator zurück, der über das Ende einer Auflistung hinaus zeigt, auf die über den angegebenen Schnittstellenparameter zugegriffen wird.

## <a name="syntax"></a>Syntax

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    end(
        IVector<T>^ v       );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    end(
        IVectorView<T>^ v
       );
template <typename T>
    ::Platform::Collections::InputIterator<T>
    end(
        IIterable<T>^ i
       );
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Ein Vorlagentyp-Parameter.

*v*<br/>
Eine Auflistung von Vektor\<T >- oder VectorView\<T >-Objekten, die durch eine IVector erfolgt\<T >, oder IVectorView\<T >-Schnittstelle.

*i*<br/>
Eine Auflistung von beliebigen Windows-Runtime-Objekten, die von einer IIterable erfolgt\<T >-Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der über das Ende der Auflistung hinaus zeigt.

### <a name="remarks"></a>Hinweise

Die ersten beiden Vorlagenfunktionen geben Iteratoren zurück und die dritte Vorlagenfunktion gibt einen Eingabeiterator zurück.

Das Objekt [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) , das von `end` zurückgegeben wird, ist ein Proxyiterator, der Elemente des Typs `VectorProxy<T>`speichert. Allerdings ist das Proxyobjekt fast nie für Benutzercode sichtbar. Weitere Informationen finden Sie unter [Auflistungen (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="requirements"></a>Anforderungen

**Header:** collection.h

**Namespace:** Windows::Foundation::Collections

## <a name="see-also"></a>Siehe auch

[Windows::Foundation::Collections-Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)
