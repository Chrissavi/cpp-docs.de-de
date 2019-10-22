---
title: time_get_byname-Klasse
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_get_byname
helpviewer_keywords:
- time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
ms.openlocfilehash: 9df3831e085f1dea1df45ff9368479fa516b944e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685757"
---
# <a name="time_get_byname-class"></a>time_get_byname-Klasse

In der abgeleiteten Klassen Vorlage wird ein Objekt beschrieben, das als Gebiets Schema-Facette vom Typ `time_get` \<CharType, InputIterator > fungieren kann.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class InputIterator =
    istreambuf_iterator<CharType, char_traits<CharType>>>
class time_get_byname : public time_get<CharType, InputIterator>
{
public:
    explicit time_get_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_get_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_get_byname()
};
```

### <a name="parameters"></a>Parameter

*_Locname* \
Ein benanntes Gebietsschema.

*_Refs* \
Eine initiale Verweisanzahl.

## <a name="requirements"></a>Anforderungen

Das Verhalten wird durch das benannte Gebiets Schema *_Locname*festgelegt. Alle Konstruktoren initialisieren ihr jeweiliges Basisobjekt mit [time_get](../standard-library/time-get-class.md#time_get)\<CharType, InputIterator>( `_Refs`).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
