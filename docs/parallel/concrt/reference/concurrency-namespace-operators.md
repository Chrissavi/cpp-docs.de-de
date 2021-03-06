---
title: concurrency-Namespace-Operatoren
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
ms.openlocfilehash: 97553276a7c4ff687dd8bea4627f943d5666b2e9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836010"
---
# <a name="concurrency-namespace-operators"></a>concurrency-Namespace-Operatoren

:::row:::
   :::column span="":::
      [`operator||`](#operator_lor)\
      [`operator&&`](#operator_amp_amp)
   :::column-end:::
   :::column span="":::
      [`operator==`](#operator_eq_eq)\
      [`operator!=`](#operator_neq)
   :::column-end:::
   :::column span="":::
      [`operator<`](#operator_lt)\
      [`operator<=`](#operator_lt_eq)
   :::column-end:::
   :::column span="":::
      [`operator>`](#operator_gt)\
      [`operator>=`](#operator_gt_eq)
   :::column-end:::
:::row-end:::

## <a name="operator124124-operator"></a><a name="operator_lor"></a> Operator&#124;&#124; -Operator

Erstellt eine Aufgabe, die erfolgreich abgeschlossen wird, wenn eine der als Argumente angegeben Aufgaben erfolgreich abgeschlossen wird.

```cpp
template<typename ReturnType>
task<ReturnType> operator||(
    const task<ReturnType>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>> operator||(
    const task<std::vector<ReturnType>>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>> operator||(
    const task<ReturnType>& lhs,
    const task<std::vector<ReturnType>>& rhs);

inline task<void> operator||(
    const task<void>& lhs,
    const task<void>& rhs);
```

### <a name="parameters"></a>Parameter

*ReturnType*<br/>
Der Typ der zurückgegebenen Aufgabe.

*LHS*<br/>
Die erste Aufgabe, die mit der resultierenden Aufgabe kombiniert werden soll.

*rhs*<br/>
Die zweite Aufgabe, die mit der resultierenden Aufgabe kombiniert werden soll.

### <a name="return-value"></a>Rückgabewert

Eine Aufgabe, die erfolgreich abgeschlossen wird, wenn eine der Eingabe Aufgaben erfolgreich abgeschlossen wurde. Wenn die Eingabeaufgaben vom Typ `T` sind, wird die Ausgabe dieser Funktion `task<std::vector<T>` sein. Wenn die Eingabe Aufgaben vom Typ sind, ist **`void`** die Ausgabe Aufgabe ebenfalls ein `task<void>` .

### <a name="remarks"></a>Bemerkungen

Wenn beide Tasks abgebrochen oder Ausnahmen ausgelöst werden, wird die zurückgegebene Aufgabe im Zustand "abgebrochen" vervollständigt, und eine der Ausnahmen, falls vorhanden, wird ausgelöst, wenn Sie `get()` oder `wait()` für diese Aufgabe aufruft.

## <a name="operatorampamp-operator"></a><a name="operator_amp_amp"></a>Operator &amp; &amp; Operator

Erstellt eine Aufgabe, die erfolgreich abgeschlossen wird, wenn beide Aufgaben, die als Argumente bereitgestellt werden, erfolgreich abgeschlossen werden.

```cpp
template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,
    const task<std::vector<ReturnType>>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,
    const task<std::vector<ReturnType>>& rhs);

inline task<void>  operator&&(
    const task<void>& lhs,
    const task<void>& rhs);
```

### <a name="parameters"></a>Parameter

*ReturnType*<br/>
Der Typ der zurückgegebenen Aufgabe.

*LHS*<br/>
Die erste Aufgabe, die mit der resultierenden Aufgabe kombiniert werden soll.

*rhs*<br/>
Die zweite Aufgabe, die mit der resultierenden Aufgabe kombiniert werden soll.

### <a name="return-value"></a>Rückgabewert

Eine Aufgabe, die erfolgreich abgeschlossen ist, wenn beide Eingabeaufgaben erfolgreich abgeschlossen wurden. Wenn die Eingabeaufgaben vom Typ `T` sind, wird die Ausgabe dieser Funktion `task<std::vector<T>>` sein. Wenn die Eingabe Aufgaben vom Typ sind, ist **`void`** die Ausgabe Aufgabe ebenfalls ein `task<void>` .

### <a name="remarks"></a>Bemerkungen

Wenn eine der Aufgaben abgebrochen wird oder eine Ausnahme auslöst, wird die zurückgegebene Aufgabe früh im abgebrochenen Zustand ausgeführt, und die Ausnahme, sofern Sie auftritt, wird ausgelöst, wenn Sie `get()` oder `wait()` für diese Aufgabe aufzurufen.

## <a name="operator-operator"></a><a name="operator_eq_eq"></a> Operator = =-Operator

Testet, ob das `concurrent_vector`-Objekt links vom Operator gleich dem `concurrent_vector`-Objekt rechts vom Operator ist.

```cpp
template<typename T, class A1, class A2>
inline bool operator== (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Elemente, die in den gleichzeitigen Vektoren gespeichert werden.

*A1*<br/>
Der zuordnertyp des ersten `concurrent_vector` Objekts.

*A2*<br/>
Der zuordnertyp des zweiten `concurrent_vector` Objekts.

*_A*<br/>
Ein Objekt vom Typ `concurrent_vector`.

*_B*<br/>
Ein Objekt vom Typ `concurrent_vector`.

### <a name="return-value"></a>Rückgabewert

**`true`** , wenn der gleichzeitige Vektor Links vom Operator gleich dem gleichzeitigen Vektor auf der rechten Seite des Operators ist. andernfalls **`false`** .

### <a name="remarks"></a>Bemerkungen

Zwei gleichzeitige Vektoren sind gleich, wenn Sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

Diese Methode ist nicht Parallelitäts sicher in Bezug auf andere Methoden, die einen der gleichzeitigen Vektoren oder ändern `_A` können `_B` .

## <a name="operator-operator"></a><a name="operator_neq"></a> Operator! =-Operator

Testet, ob das `concurrent_vector`-Objekt links vom Operator ungleich dem `concurrent_vector`-Objekt rechts vom Operator ist.

```cpp
template<typename T, class A1, class A2>
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Elemente, die in den gleichzeitigen Vektoren gespeichert werden.

*A1*<br/>
Der zuordnertyp des ersten `concurrent_vector` Objekts.

*A2*<br/>
Der zuordnertyp des zweiten `concurrent_vector` Objekts.

*_A*<br/>
Ein Objekt vom Typ `concurrent_vector`.

*_B*<br/>
Ein Objekt vom Typ `concurrent_vector`.

### <a name="return-value"></a>Rückgabewert

**`true`** , wenn die gleichzeitigen Vektoren nicht gleich sind. , **`false`** Wenn die gleichzeitigen Vektoren gleich sind.

### <a name="remarks"></a>Bemerkungen

Zwei gleichzeitige Vektoren sind gleich, wenn Sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

Diese Methode ist nicht Parallelitäts sicher in Bezug auf andere Methoden, die einen der gleichzeitigen Vektoren oder ändern `_A` können `_B` .

## <a name="operatorlt-operator"></a><a name="operator_lt"></a> Operator &lt; Operator

Testet, ob das `concurrent_vector`-Objekt links vom Operator kleiner als das `concurrent_vector`-Objekt auf der rechten Seite ist.

```cpp
template<typename T, class A1, class A2>
inline bool operator<(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Elemente, die in den gleichzeitigen Vektoren gespeichert werden.

*A1*<br/>
Der zuordnertyp des ersten `concurrent_vector` Objekts.

*A2*<br/>
Der zuordnertyp des zweiten `concurrent_vector` Objekts.

*_A*<br/>
Ein Objekt vom Typ `concurrent_vector`.

*_B*<br/>
Ein Objekt vom Typ `concurrent_vector`.

### <a name="return-value"></a>Rückgabewert

**`true`** , wenn der gleichzeitige Vektor Links vom Operator kleiner als der gleichzeitige Vektor auf der rechten Seite des Operators ist. andernfalls **`false`** .

### <a name="remarks"></a>Bemerkungen

Das Verhalten dieses Operators ist identisch mit dem äquivalenten Operator für die- `vector` Klasse im- `std` Namespace.

Diese Methode ist nicht Parallelitäts sicher in Bezug auf andere Methoden, die einen der gleichzeitigen Vektoren oder ändern `_A` können `_B` .

## <a name="operatorlt-operator"></a><a name="operator_lt_eq"></a> Operator &lt; =-Operator

Testet, ob das `concurrent_vector`-Objekt links vom Operator kleiner oder gleich dem `concurrent_vector`-Objekt auf der rechten Seite ist.

```cpp
template<typename T, class A1, class A2>
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Elemente, die in den gleichzeitigen Vektoren gespeichert werden.

*A1*<br/>
Der zuordnertyp des ersten `concurrent_vector` Objekts.

*A2*<br/>
Der zuordnertyp des zweiten `concurrent_vector` Objekts.

*_A*<br/>
Ein Objekt vom Typ `concurrent_vector`.

*_B*<br/>
Ein Objekt vom Typ `concurrent_vector`.

### <a name="return-value"></a>Rückgabewert

**`true`** , wenn der gleichzeitige Vektor Links vom Operator kleiner als oder gleich dem gleichzeitigen Vektor auf der rechten Seite des Operators ist. andernfalls **`false`** .

### <a name="remarks"></a>Bemerkungen

Das Verhalten dieses Operators ist identisch mit dem äquivalenten Operator für die- `vector` Klasse im- `std` Namespace.

Diese Methode ist nicht Parallelitäts sicher in Bezug auf andere Methoden, die einen der gleichzeitigen Vektoren oder ändern `_A` können `_B` .

## <a name="operatorgt-operator"></a><a name="operator_gt"></a> Operator &gt; Operator

Testet, ob das `concurrent_vector`-Objekt links vom Operator größer als das `concurrent_vector`-Objekt auf der rechten Seite ist.

```cpp
template<typename T, class A1, class A2>
inline bool operator>(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Elemente, die in den gleichzeitigen Vektoren gespeichert werden.

*A1*<br/>
Der zuordnertyp des ersten `concurrent_vector` Objekts.

*A2*<br/>
Der zuordnertyp des zweiten `concurrent_vector` Objekts.

*_A*<br/>
Ein Objekt vom Typ `concurrent_vector`.

*_B*<br/>
Ein Objekt vom Typ `concurrent_vector`.

### <a name="return-value"></a>Rückgabewert

**`true`** , wenn der gleichzeitige Vektor Links vom Operator größer als der gleichzeitige Vektor auf der rechten Seite des Operators ist. andernfalls **`false`** .

### <a name="remarks"></a>Bemerkungen

Das Verhalten dieses Operators ist identisch mit dem äquivalenten Operator für die- `vector` Klasse im- `std` Namespace.

Diese Methode ist nicht Parallelitäts sicher in Bezug auf andere Methoden, die einen der gleichzeitigen Vektoren oder ändern `_A` können `_B` .

## <a name="operatorgt-operator"></a><a name="operator_gt_eq"></a> Operator &gt; =-Operator

Testet, ob das `concurrent_vector`-Objekt links vom Operator größer oder gleich dem `concurrent_vector`-Objekt auf der rechten Seite ist.

```cpp
template<typename T, class A1, class A2>
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Elemente, die in den gleichzeitigen Vektoren gespeichert werden.

*A1*<br/>
Der zuordnertyp des ersten `concurrent_vector` Objekts.

*A2*<br/>
Der zuordnertyp des zweiten `concurrent_vector` Objekts.

*_A*<br/>
Ein Objekt vom Typ `concurrent_vector`.

*_B*<br/>
Ein Objekt vom Typ `concurrent_vector`.

### <a name="return-value"></a>Rückgabewert

**`true`** , wenn der gleichzeitige Vektor Links vom Operator größer als oder gleich dem gleichzeitigen Vektor auf der rechten Seite des Operators ist. andernfalls **`false`** .

### <a name="remarks"></a>Bemerkungen

Das Verhalten dieses Operators ist identisch mit dem äquivalenten Operator für die- `vector` Klasse im- `std` Namespace.

Diese Methode ist nicht Parallelitäts sicher in Bezug auf andere Methoden, die einen der gleichzeitigen Vektoren oder ändern `_A` können `_B` .

## <a name="see-also"></a>Weitere Informationen

[Parallelitäts Namespace](concurrency-namespace.md)
