---
title: system_clock-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::system_clock
- chrono/std::chrono::system_clock::from_time_t
- chrono/std::chrono::system_clock::now
- chrono/std::chrono::system_clock::to_time_t
- chrono/std::chrono::system_clock::is_monotonic Constant
- chrono/std::chrono::system_clock::is_steady Constant
dev_langs:
- C++
ms.assetid: a97bd46e-267a-4836-9f7d-af1f664e99ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b56a493ce91c6ac7f0864a1bf4e10476603d79fd
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959042"
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
|[jetzt](#now)|Statisch Gibt die aktuelle Uhrzeit zurück.|
|[to_time_t](#to_time_t)|Statisch Gibt ein `time_t`-Objekt zurück, das einer bestimmten `time_point` am besten entspricht.|

### <a name="public-constants"></a>Öffentliche Konstanten

|name|Beschreibung|
|----------|-----------------|
|[system_clock::is_monotonic-Konstante](#is_monotonic_constant)|Gibt an, ob der Uhrtyp monoton ist.|
|[system_clock::is_steady-Konstante](#is_steady_constant)|Gibt an, ob der Uhrtyp gleichmäßig ist.|

## <a name="requirements"></a>Anforderungen

**Header:** \<chrono>

**Namespace:** std::chrono

## <a name="from_time_t"></a>  system_clock:: from_time_t

Statische Methode, die gibt eine [Time_point](../standard-library/time-point-class.md) , das am ehesten der Zeit, die durch dargestellt wird *Tm*.

```cpp
static time_point from_time_t(time_t Tm) noexcept;
```

### <a name="parameters"></a>Parameter

*TM*  
 Ein [time_t](../c-runtime-library/standard-types.md)-Objekt.

## <a name="is_monotonic_constant"></a> system_clock::is_monotonic-Konstante

Ein statischer Wert, der angibt, ob der Uhrtyp monoton ist.

```cpp
static const bool is_monotonic = false;
```

### <a name="return-value"></a>Rückgabewert

In dieser Implementierung `system_clock::is_monotonic` gibt immer **"false"**.

### <a name="remarks"></a>Hinweise

Eine Uhr ist *monoton*, wenn der von einem ersten Aufruf von `now()` zurückgegebene Wert immer kleiner oder gleich dem Wert ist, der über einen nachfolgenden Aufruf von `now()` zurückgegeben wird.

## <a name="is_steady_constant"></a> system_clock::is_steady-Konstante

Ein statischer Wert, der angibt, ob der Uhrtyp *gleichmäßig* ist.

```cpp
static const bool is_steady = false;
```

### <a name="return-value"></a>Rückgabewert

In dieser Implementierung `system_clock::is_steady` gibt immer **"false"**.

### <a name="remarks"></a>Hinweise

Eine Uhr ist *gleichmäßig*, wenn sie [monoton](#is_monotonic_constant) und die Zeit zwischen den Teilstrichen konstant ist.

## <a name="now"></a>  system_clock:: Now

Statische Methode, die die aktuellen Uhrzeit zurückgibt.

```cpp
static time_point now() noexcept;
```

### <a name="return-value"></a>Rückgabewert

Ein [time_point](../standard-library/time-point-class.md)-Objekt, das die aktuelle Uhrzeit darstellt.

## <a name="to_time_t"></a>  system_clock:: to_time_t

Statische Methode, die gibt eine [Time_t](../c-runtime-library/standard-types.md) , das am ehesten der Zeit, die durch dargestellt wird *Zeit*.

```cpp
static time_t to_time_t(const time_point& Time) noexcept;
```

### <a name="parameters"></a>Parameter

*Zeit*  
 Ein [time_point](../standard-library/time-point-class.md)-Objekt.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>
[steady_clock-Struktur](../standard-library/steady-clock-struct.md)<br/>
