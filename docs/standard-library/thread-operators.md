---
title: '&lt;thread&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- thread/std::operator!=
- thread/std::operator&gt;
- thread/std::operator&gt;=
- thread/std::operator&lt;
- thread/std::operator&lt;&lt;
- thread/std::operator&lt;=
- thread/std::operator==
dev_langs:
- C++
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
helpviewer_keywords:
- std::operator!= (thread)
- std::operator&gt; (thread)
- std::operator&gt;= (thread)
- std::operator&lt; (thread)
- std::operator&lt;&lt; (thread)
- std::operator&lt;= (thread)
- std::operator== (thread)
ms.openlocfilehash: ac9a436637f9acf5f3818454706eb146d814b3bc
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964813"
---
# <a name="ltthreadgt-operators"></a>&lt;thread&gt;-Operatoren

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|

## <a name="op_gt_eq"></a> operator&gt;=

Bestimmt, ob ein `thread::id`-Objekt größer als oder gleich einem anderen Objekt ist.

```cpp
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parameter

*Links*  
 Das linke `thread::id`-Objekt.

*Rechts*  
 Das rechte `thread::id`-Objekt.

### <a name="return-value"></a>Rückgabewert

`!(Left < Right)`

### <a name="remarks"></a>Hinweise

Diese Funktion löst keine Ausnahmen aus.

## <a name="op_gt"></a> operator&gt;

Bestimmt, ob ein `thread::id`-Objekt größer als ein anderes Objekt ist.

```cpp
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parameter

*Links*  
 Das linke `thread::id`-Objekt.

*Rechts*  
 Das rechte `thread::id`-Objekt.

### <a name="return-value"></a>Rückgabewert

`Right < Left`

### <a name="remarks"></a>Hinweise

Diese Funktion löst keine Ausnahmen aus.

## <a name="op_lt_eq"></a> operator&lt;=

Bestimmt, ob ein `thread::id`-Objekt kleiner als oder gleich einem anderen Objekt ist.

```cpp
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parameter

*Links*  
 Das linke `thread::id`-Objekt.

*Rechts*  
 Das rechte `thread::id`-Objekt.

### <a name="return-value"></a>Rückgabewert

`!(Right < Left)`

### <a name="remarks"></a>Hinweise

Diese Funktion löst keine Ausnahmen aus.

## <a name="op_lt"></a> operator&lt;

Bestimmt, ob ein `thread::id`-Objekt kleiner als ein anderes Objekt ist.

```cpp
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parameter

*Links*  
 Das linke `thread::id`-Objekt.

*Rechts*  
 Das rechte `thread::id`-Objekt.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn *Links* vorausgeht *rechts* in der gesamten Sortierung hingegen **"false"**.

### <a name="remarks"></a>Hinweise

Der Operator definiert eine gesamte Sortierung für alle `thread::id`-Objekte. Diese Objekte können als Schlüssel in assoziativen Containern verwendet werden.

Diese Funktion löst keine Ausnahmen aus.

## <a name="op_neq"></a> operator!=

Überprüft zwei `thread::id`-Objekte auf Ungleichheit.

```cpp
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parameter

*Links*  
 Das linke `thread::id`-Objekt.

*Rechts*  
 Das rechte `thread::id`-Objekt.

### <a name="return-value"></a>Rückgabewert

`!(Left == Right)`

### <a name="remarks"></a>Hinweise

Diese Funktion löst keine Ausnahmen aus.

## <a name="op_eq_eq"></a> operator==

Überprüft zwei `thread::id`-Objekte auf Gleichheit.

```cpp
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Parameter
 
*Links*  
 Das linke `thread::id`-Objekt.

*Rechts*  
 Das rechte `thread::id`-Objekt.

### <a name="return-value"></a>Rückgabewert

**"true"** aus, wenn die beiden Objekte den gleichen Ausführungsthread darstellen oder wenn kein Objekt einen Ausführungsthread darstellt, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Diese Funktion löst keine Ausnahmen aus.

## <a name="op_lt_lt"></a> operator&lt;&lt;

Fügt eine Textdarstellung eines `thread::id`-Objekts in einen Stream ein.

```cpp
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```

### <a name="parameters"></a>Parameter

*Ostr*  
 Ein [basic_ostream](../standard-library/basic-ostream-class.md)-Objekt.

*Id*  
 Ein `thread::id`-Objekt.

### <a name="return-value"></a>Rückgabewert

*Ostr*.

### <a name="remarks"></a>Hinweise

Diese Funktion fügt *Id* in *Ostr*.

Wenn zwei `thread::id`-Objekte gleich sind, sind die eingefügten Text-Darstellungen dieser Objekte gleich.

## <a name="see-also"></a>Siehe auch

[\<thread>](../standard-library/thread.md)<br/>
