---
title: gslice_array-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::gslice_array
dev_langs:
- C++
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff9718a98244379fccde78b18fa70ef46c7e7a76
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845644"
---
# <a name="gslicearray-class"></a>gslice_array-Klasse

Eine interne zusätzliche Vorlagenklasse, die allgemeine slice-Objekte (Segmente) unterstützt, indem sie Vorgänge zwischen Teilmengenarrays bereitstellt, die durch das allgemeine Segment eines valarray-Objekts definiert sind.

## <a name="syntax"></a>Syntax

```cpp
template <class Type>
class gslice_array : public gsplice {
public:
    typedef Type value_type;
    void operator=(const valarray<Type>& x) const;


    void operator=(const Type& x) const;


    void operator*=(const valarray<Type>& x) const;


    void operator/=(const valarray<Type>& x) const;


    void operator%=(const valarray<Type>& x) const;


    void operator+=(const valarray<Type>& x) const;


    void operator-=(const valarray<Type>& x) const;


    void operator^=(const valarray<Type>& x) const;


    void operator&=(const valarray<Type>& x) const;


    void operator|=(const valarray<Type>& x) const;


    void operator<<=(const valarray<Type>& x) const;


    void operator>>=(const valarray<Type>& x) const;


// The rest is private or implementation defined
}
```

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt **va** der Klasse [valarray](../standard-library/valarray-class.md)**\<Type>** zusammen mit einem Objekt **gs** der Klasse [gslice](../standard-library/gslice-class.md) speichert, das die Reihenfolge der Elemente beschreibt, die im **valarray\<Type>**-Objekt ausgewählt werden sollen.

Sie erstellen ein **gslice_array\<Type>**-Objekt nur, indem Sie einen Ausdruck der Form [va&#91;gs&#93;](../standard-library/valarray-class.md#op_at) schreiben. Die Memberfunktionen der gslice_array-Klasse verhalten sich danach wie die entsprechenden Funktionssignaturen, die für **valarray\<Type>** definiert sind, mit der Ausnahme, dass nur die Reihenfolge der ausgewählten Elemente betroffen ist.

Die Vorlagenklasse wird indirekt durch bestimmte valarray-Operationen erstellt und kann nicht direkt in der Anwendung verwendet werden. Eine interne auxiliary-Vorlagenklasse wird stattdessen von dem Segment-Indexoperator verwendet:

`gslice_array`\< **Type**> `valarray`\< **Type**>:: `operator[]` (**constgslice&**).

Sie erstellen ein **gslice_array\<Type>**-Objekt für ein **gsl**-Segment des valarray **va** nur, indem Sie einen Ausdruck der Form **va[gsl]** schreiben. Die Memberfunktionen der gslice_array-Klasse verhalten sich danach wie die entsprechenden Funktionssignaturen, die für **valarray\<Type>** definiert sind, mit der Ausnahme, dass nur die Reihenfolge der ausgewählten Elemente betroffen ist. Die Sequenz, die vom gslice_array gesteuert wird, wird durch die drei Parameter des Segmentkonstruktors, den Index des ersten Elements im ersten Segment und die Anzahl der Elemente in jedem Segment und den Abstand zwischen den Elementen in jedem Segment definiert.

Im folgenden Beispiel:

```cpp
const size_t lv[] = {2, 3};
const size_t dv[] = {7, 2};
const valarray<size_t> len(lv, 2), str(dv, 2);

// va[gslice(3, len, str)] selects elements with
//   indices 3, 5, 7, 10, 12, 14
```

Die Indizes müssen für die Prozedur gültig sein, um gültig zu sein.

## <a name="example"></a>Beispiel

Im Beispiel für [gslice::gslice](../standard-library/gslice-class.md#gslice) wird verdeutlicht, wie ein slice_array deklariert und verwendet wird.

## <a name="requirements"></a>Anforderungen

**Header:** \<valarray>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
