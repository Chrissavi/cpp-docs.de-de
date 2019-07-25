---
title: system_clock-Struktur
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::system_clock
- chrono/std::chrono::system_clock::from_time_t
- chrono/std::chrono::system_clock::now
- chrono/std::chrono::system_clock::to_time_t
- chrono/std::chrono::system_clock::is_monotonic Constant
- chrono/std::chrono::system_clock::is_steady Constant
ms.assetid: a97bd46e-267a-4836-9f7d-af1f664e99ae
ms.openlocfilehash: 7a9fd83840883de5172df8b2e1e451984a95ea47
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450186"
---
# <a name="systemclock-structure"></a>system_clock-Struktur

Stellt einen auf der Echtzeituhr des Systems basierten *Uhrtyp* dar.

## <a name="syntax"></a>Syntax

```cpp
struct system_clock;
```

## <a name="remarks"></a>Hinweise

Ein *Uhrtyp* wird zum Abrufen der aktuellen Zeit (UTC) verwendet. Der Typ stellt eine Instanziierung von [duration](../standard-library/duration-class.md) und der Klassenvorlage [time_point](../standard-library/time-point-class.md) dar und definiert eine statische `now()`-Memberfunktion, mit der die Zeit zurückgegeben wird.

Eine Uhr ist *monoton*, wenn der von einem ersten Aufruf von `now()` zurückgegebene Wert immer kleiner oder gleich dem Wert ist, der über einen nachfolgenden Aufruf von `now()` zurückgegeben wird.

Eine Uhr ist *gleichmäßig*, wenn sie *monoton* und die Zeit zwischen den Teilstrichen konstant ist.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`system_clock::duration`|Ein Synonym für `duration<rep, period>`.|
|`system_clock::period`|Ein Synonym für den Typ, der zum Darstellen der Teilstrichperiode in der enthaltenden Instanziierung von `duration` verwendet wird.|
|`system_clock::rep`|Ein Synonym für den Typ zum Darstellen der Anzahl von Zeiteinheiten in der enthaltenden Instanziierung von `duration` verwendet wird.|
|`system_clock::time_point`|Ein Synonym für `time_point<Clock, duration>`, wobei `Clock` entweder ein Synonym für den Uhrtyp selbst oder einen anderen Uhrtyp ist, der auf der gleichen Epoche basiert und über den gleichen geschachtelten `duration`-Typ verfügt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[from_time_t](#from_time_t)|Statisch Gibt einen `time_point` zurück, der einer bestimmten Zeit am besten entspricht.|
|[gerade](#now)|Statisch Gibt die aktuelle Uhrzeit zurück.|
|[to_time_t](#to_time_t)|Statisch Gibt ein `time_t`-Objekt zurück, das einer bestimmten `time_point` am besten entspricht.|

### <a name="public-constants"></a>Öffentliche Konstanten

|Name|Beschreibung|
|----------|-----------------|
|[system_clock::is_monotonic-Konstante](#is_monotonic_constant)|Gibt an, ob der Uhrtyp monoton ist.|
|[system_clock::is_steady-Konstante](#is_steady_constant)|Gibt an, ob der Uhrtyp gleichmäßig ist.|

## <a name="requirements"></a>Anforderungen

**Header:** \<chrono>

**Namespace:** std::chrono

## <a name="from_time_t"></a>system_clock::from_time_t

Statische Methode, die ein [time_point](../standard-library/time-point-class.md) zurückgibt, das am ehesten der von *TM*dargestellten Zeit entspricht.

```cpp
static time_point from_time_t(time_t Tm) noexcept;
```

### <a name="parameters"></a>Parameter

*Ausnutzt*\
Ein [time_t](../c-runtime-library/standard-types.md)-Objekt.

## <a name="is_monotonic_constant"></a> system_clock::is_monotonic-Konstante

Ein statischer Wert, der angibt, ob der Uhrtyp monoton ist.

```cpp
static const bool is_monotonic = false;
```

### <a name="return-value"></a>Rückgabewert

In dieser Implementierung `system_clock::is_monotonic` gibt immer **false**zurück.

### <a name="remarks"></a>Hinweise

Eine Uhr ist *monoton*, wenn der von einem ersten Aufruf von `now()` zurückgegebene Wert immer kleiner oder gleich dem Wert ist, der über einen nachfolgenden Aufruf von `now()` zurückgegeben wird.

## <a name="is_steady_constant"></a> system_clock::is_steady-Konstante

Ein statischer Wert, der angibt, ob der Uhrtyp *gleichmäßig* ist.

```cpp
static const bool is_steady = false;
```

### <a name="return-value"></a>Rückgabewert

In dieser Implementierung `system_clock::is_steady` gibt immer **false**zurück.

### <a name="remarks"></a>Hinweise

Eine Uhr ist *gleichmäßig*, wenn sie [monoton](#is_monotonic_constant) und die Zeit zwischen den Teilstrichen konstant ist.

## <a name="now"></a>system_clock:: Now

Statische Methode, die die aktuellen Uhrzeit zurückgibt.

```cpp
static time_point now() noexcept;
```

### <a name="return-value"></a>Rückgabewert

Ein [time_point](../standard-library/time-point-class.md)-Objekt, das die aktuelle Uhrzeit darstellt.

## <a name="to_time_t"></a>system_clock::to_time_t

Statische Methode, die ein [time_t](../c-runtime-library/standard-types.md) zurückgibt, das am ehesten der Zeit entspricht, die durch die *Zeit*dargestellt wird.

```cpp
static time_t to_time_t(const time_point& Time) noexcept;
```

### <a name="parameters"></a>Parameter

*Zeit*\
Ein [time_point](../standard-library/time-point-class.md)-Objekt.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)\
[steady_clock-Struktur](../standard-library/steady-clock-struct.md)
