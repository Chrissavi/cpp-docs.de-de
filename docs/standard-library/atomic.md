---
title: '&lt;atomic&gt;'
description: Beschreibt die Typen und Funktionen, die im Atomic-Header der Standard C++ Bibliothek verfügbar sind.
ms.date: 12/06/2019
f1_keywords:
- <atomic>
- atomic/std::atomic_int_least32_t
- atomic/std::atomic_ullong
- atomic/std::atomic_ptrdiff_t
- atomic/std::atomic_char16_t
- atomic/std::atomic_schar
- atomic/std::atomic_ulong
- atomic/std::atomic_uint_fast32_t
- atomic/std::atomic_uint8_t
- atomic/std::atomic_int32_t
- atomic/std::atomic_uint_fast64_t
- atomic/std::atomic_uint32_t
- atomic/std::atomic_int16_t
- atomic/std::atomic_uintmax_t
- atomic/std::atomic_intmax_t
- atomic/std::atomic_long
- atomic/std::atomic_int
- atomic/std::atomic_uint_least8_t
- atomic/std::atomic_size_t
- atomic/std::atomic_uint_fast16_t
- atomic/std::atomic_wchar_t
- atomic/std::atomic_int_fast64_t
- atomic/std::atomic_uint_fast8_t
- atomic/std::atomic_int_fast8_t
- atomic/std::atomic_intptr_t
- atomic/std::atomic_uint
- atomic/std::atomic_uint16_t
- atomic/std::atomic_char32_t
- atomic/std::atomic_uint64_t
- atomic/std::atomic_ushort
- atomic/std::atomic_int_least16_t
- atomic/std::atomic_char
- atomic/std::atomic_uint_least32_t
- atomic/std::atomic_uintptr_t
- atomic/std::atomic_short
- atomic/std::atomic_llong
- atomic/std::atomic_uint_least16_t
- atomic/std::atomic_int_fast16_t
- atomic/std::atomic_int_least8_t
- atomic/std::atomic_int_least64_t
- atomic/std::atomic_int_fast32_t
- atomic/std::atomic_uchar
- atomic/std::atomic_int8_t
- atomic/std::atomic_int64_t
- atomic/std::atomic_uint_least64_t
ms.assetid: e79a6b9f-52ff-48da-9554-654c4e1999f6
ms.openlocfilehash: d11e8bf2067c1c8525725ae74e713ac834d89ec4
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991169"
---
# <a name="ltatomicgt"></a>&lt;atomic&gt;

Definiert Klassen und Klassen Vorlagen, die zum Erstellen von Typen verwendet werden, die atomarische Vorgänge unterstützen.

## <a name="syntax"></a>Syntax

```cpp
#include <atomic>
```

## <a name="remarks"></a>Hinweise

> [!NOTE]
> In Code, der mit [/clr: pure](../build/reference/clr-common-language-runtime-compilation.md)kompiliert wird, wird dieser Header blockiert. Sowohl **/clr: pure** als auch **/clr: Safe** sind in Visual Studio 2017 und höheren Versionen veraltet.

Ein atomischer Vorgang hat zwei Schlüsseleigenschaften, die dabei helfen, mehrere Threads zu verwenden, um ein Objekt korrekt zu ändern, ohne Mutexsperren zu verwenden.

- Da eine atomarische Operation unteilbar ist, kann eine zweite atomarische Operation für dasselbe Objekt aus einem anderen Thread den Zustand des Objekts nur vor oder nach dem ersten atomaren Vorgang abrufen.

- Basierend auf dem Argument [memory_order](../standard-library/atomic-enums.md#memory_order_enum), richtet ein atomischer Vorgang Anforderungen für die Sortierung für die Sichtbarkeit der Effekte anderer atomischer Vorgänge im gleichen Thread ein. Daher unterbindet dieser Vorgang Compileroptimierungen, die die Anforderungen für die Sortierung verletzen.

Auf manchen Plattformen ist es möglicherweise nicht möglich, atomische Vorgänge für bestimme Typen effizient zu implementieren, ohne `mutex`-Sperren zu verwenden. Ein atomischer Typ ist *sperrfrei*, wenn für keine der atomischen Vorgänge auf diesem Typ Sperren verwendet werden.

**C++ 11**: in Signal Handlern können Sie atomarische Vorgänge für ein Objekt ausführen `obj` wenn `obj.is_lock_free()` oder `atomic_is_lock_free(x)` true sind.

Die Klasse [atomic_flag](../standard-library/atomic-flag-structure.md) stellt einen minimalen atomaren Typ bereit, der ein **Boolesches** Flag enthält. Die Vorgänge sind immer sperrfrei.

Die Klassen Vorlage `atomic<T>` speichert ein Objekt seines Argument Typs `T` und ermöglicht atomarischen Zugriff auf den gespeicherten Wert. Sie können das Objekt durch Verwendung jedes Typs instanziieren, der mithilfe von [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) kopiert und mithilfe von [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) auf Gleichheit getestet werden kann. Sie können es insbesondere mit benutzerdefinierten Typen, die diese Anforderungen erfüllen, und oftmals auch mit Gleitkommatypen verwenden.

Die Vorlage verfügt über eine Reihe von Spezialisierungen für integrale Typen und eine Teilspezialisierung für Zeiger. Diese Spezialisierungsmöglichkeiten stellen zusätzliche Vorgänge bereit, die über die primäre Vorlage nicht verfügbar sind.

## <a name="pointer-specializations"></a>Zeigerspezialisierungen

Die Teilspezialisierung `atomic<T *>` gilt für alle Zeigertypen. Sie stellen Methoden für Zeigerarithmetik bereit.

## <a name="integral-specializations"></a>Integrale Spezialisierungen

Die `atomic<integral>`-Spezialisierungen sind auf alle integralen Typen anwendbar. Sie stellen zusätzliche Vorgänge bereit, die über die primäre Vorlage nicht verfügbar sind.

Jeder `atomic<integral>`-Typ hat ein entsprechendes Makro, das Sie in `if directive` verwenden können, um beim Kompilieren festzustellen, ob Vorgänge für diesen Typ sperrfrei sind. Wenn der Wert des Makros 0 (null) ist, sind Vorgänge für den Typ nicht sperrenfrei. Wenn der Wert 1 ist, sind Vorgänge möglicherweise sperrfrei. Dadurch ist eine Überprüfung der Laufzeit erforderlich. Wenn der Wert 2 ist, sind Vorgänge sperrfrei. Sie können mithilfe der Funktion `atomic_is_lock_free` zur Laufzeit bestimmen, ob Vorgänge für diesen Typ sperrfrei sind.

Für jeden ganzzahligen Typ gibt es einen entsprechenden benannten atomaren Typ, der ein Objekt dieses ganzzahligen Typs verwaltet. Jeder `atomic_integral`-Typ hat den gleichen Satz von Memberfunktionen wie die entsprechende Instanziierung `atomic<T>`, und kann an die atomischen Funktionen übergeben werden, die nicht-Memberfunktionen sind.

|`atomic_integral`-Typ|Integrale Typen|`atomic_is_lock_free`-Makro|
|----------------------------|-------------------|---------------------------------|
|`atomic_char`|**char**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_schar`|**signed char**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_uchar`|**unsigned char**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_char16_t`|`char16_t`|ATOMIC_CHAR16_T_LOCK_FREE|
|`atomic_char32_t`|`char32_t`|ATOMIC_CHAR32_T_LOCK_FREE|
|`atomic_wchar_t`|**wchar_t**|ATOMIC_WCHAR_T_LOCK_FREE|
|`atomic_short`|**short**|ATOMIC_SHORT_LOCK_FREE|
|`atomic_ushort`|**unsigned short**|ATOMIC_SHORT_LOCK_FREE|
|`atomic_int`|**int**|ATOMIC_INT_LOCK_FREE|
|`atomic_uint`|**unsigned int**|ATOMIC_INT_LOCK_FREE|
|`atomic_long`|**long**|ATOMIC_LONG_LOCK_FREE|
|`atomic_ulong`|**unsigned long**|ATOMIC_LONG_LOCK_FREE|
|`atomic_llong`|**langes long**|ATOMIC_LLONG_LOCK_FREE|
|`atomic_ullong`|**Ganzzahl ohne Vorzeichen long long**|ATOMIC_LLONG_LOCK_FREE|

Typedef-Namen bestehen für Spezialisierungen der atomischen Vorlage für einige der Typen, die im Header \<inttypes.h> definiert sind.

|Atomischer Typ|Typedef-Name|
|-----------------|------------------|
|`atomic_int8_t`|`atomic<int8_t>`|
|`atomic_uint8_t`|`atomic<uint8_t>`|
|`atomic_int16_t`|`atomic<int16_t>`|
|`atomic_uint16_t`|`atomic<uint16_t>`|
|`atomic_int32_t`|`atomic<int32_t>`|
|`atomic_uint32_t`|`atomic<uint32_t>`|
|`atomic_int64_t`|`atomic<int64_t>`|
|`atomic_uint64_t`|`atomic<uint64_t>`|
|`atomic_int_least8_t`|`atomic<int_least8_t>`|
|`atomic_uint_least8_t`|`atomic<uint_least8_t>`|
|`atomic_int_least16_t`|`atomic<int_least16_t>`|
|`atomic_uint_least16_t`|`atomic<uint_least16_t>`|
|`atomic_int_least32_t`|`atomic<int_least32_t>`|
|`atomic_uint_least32_t`|`atomic<uint_least32_t>`|
|`atomic_int_least64_t`|`atomic<int_least64_t>`|
|`atomic_uint_least64_t`|`atomic<uint_least64_t>`|
|`atomic_int_fast8_t`|`atomic<int_fast8_t>`|
|`atomic_uint_fast8_t`|`atomic<uint_fast8_t>`|
|`atomic_int_fast16_t`|`atomic<int_fast16_t>`|
|`atomic_uint_fast16_`|`atomic<uint_fast16_t>`|
|`atomic_int_fast32_t`|`atomic<int_fast32_t>`|
|`atomic_uint_fast32_t`|`atomic<uint_fast32_t>`|
|`atomic_int_fast64_t`|`atomic<int_fast64_t>`|
|`atomic_uint_fast64_t`|`atomic<uint_fast64_t>`|
|`atomic_intptr_t`|`atomic<intptr_t>`|
|`atomic_uintptr_t`|`atomic<uintptr_t>`|
|`atomic_size_t`|`atomic<size_t>`|
|`atomic_ptrdiff_t`|`atomic<ptrdiff_t>`|
|`atomic_intmax_t`|`atomic<intmax_t>`|
|`atomic_uintmax_t`|`atomic<uintmax_t>`|

## <a name="structs"></a>Strukturen

|-Name|Beschreibung|
|----------|-----------------|
|[atomic-Struktur](../standard-library/atomic-structure.md)|Beschreibt ein Objekt, das auf einem gespeicherten Wert atomische Vorgänge ausführt.|
|[atomic_flag-Struktur](../standard-library/atomic-flag-structure.md)|Beschreibt ein Objekt, das ein **bool** -Flag atomisch festlegt und löscht.|

## <a name="enums"></a>Enumerationen

|-Name|Beschreibung|
|----------|-----------------|
|[memory_order-Enumeration](../standard-library/atomic-enums.md#memory_order_enum)|Stellt symbolische Namen für Synchronisierungsvorgänge auf Speicheradressen bereit. Diese Vorgänge wirken sich auf das Sichtbarwerden der Zuweisung eines Thread in einem anderen aus.|

## <a name="functions"></a>Funktionen

In der folgenden Liste verfügen die Funktionen, die nicht auf `_explicit` enden, über die Semantik des entsprechenden `_explicit`, mit dem Unterschied, dass Sie über die impliziten [memory_order](../standard-library/atomic-enums.md#memory_order_enum) Argumente `memory_order_seq_cst`verfügen.

|-Name|Beschreibung|
|----------|-----------------|
|[atomic_compare_exchange_strong](../standard-library/atomic-functions.md#atomic_compare_exchange_strong)|Führt einen *atomischen Vergleichs- und Austauschvorgang* aus.|
|[atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit)|Führt einen *atomischen Vergleichs- und Austauschvorgang* aus.|
|[atomic_compare_exchange_weak](../standard-library/atomic-functions.md#atomic_compare_exchange_weak)|Führt einen *schwachen atomischen Vergleichs- und Austauschvorgang* aus.|
|[atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit)|Führt einen *schwachen atomischen Vergleichs- und Austauschvorgang* aus.|
|[atomic_exchange](../standard-library/atomic-functions.md#atomic_exchange)|Ersetzt einen gespeicherten Wert.|
|[atomic_exchange_explicit](../standard-library/atomic-functions.md#atomic_exchange_explicit)|Ersetzt einen gespeicherten Wert.|
|[atomic_fetch_add](../standard-library/atomic-functions.md#atomic_fetch_add)|Fügt einem vorhandenen gespeicherten Wert einen angegebenen Wert hinzu.|
|[atomic_fetch_add_explicit](../standard-library/atomic-functions.md#atomic_fetch_add_explicit)|Fügt einem vorhandenen gespeicherten Wert einen angegebenen Wert hinzu.|
|[atomic_fetch_and](../standard-library/atomic-functions.md#atomic_fetch_and)|Führt ein bitweises `and` auf einem angegebenen Wert und einem vorhandenen gespeicherten Wert aus.|
|[atomic_fetch_and_explicit](../standard-library/atomic-functions.md#atomic_fetch_and_explicit)|Führt ein bitweises `and` auf einem angegebenen Wert und einem vorhandenen gespeicherten Wert aus.|
|[atomic_fetch_or](../standard-library/atomic-functions.md#atomic_fetch_or)|Führt ein bitweises `or` auf einem angegebenen Wert und einem vorhandenen gespeicherten Wert aus.|
|[atomic_fetch_or_explicit](../standard-library/atomic-functions.md#atomic_fetch_or_explicit)|Führt ein bitweises `or` auf einem angegebenen Wert und einem vorhandenen gespeicherten Wert aus.|
|[atomic_fetch_sub](../standard-library/atomic-functions.md#atomic_fetch_sub)|Subtrahiert einen angegebenen Wert von einem vorhandenen gespeicherten Wert.|
|[atomic_fetch_sub_explicit](../standard-library/atomic-functions.md#atomic_fetch_sub_explicit)|Subtrahiert einen angegebenen Wert von einem vorhandenen gespeicherten Wert.|
|[atomic_fetch_xor](../standard-library/atomic-functions.md#atomic_fetch_xor)|Führt ein bitweises `exclusive or` auf einem angegebenen Wert und einem vorhandenen gespeicherten Wert aus.|
|[atomic_fetch_xor_explicit](../standard-library/atomic-functions.md#atomic_fetch_xor_explicit)|Führt ein bitweises `exclusive or` auf einem angegebenen Wert und einem vorhandenen gespeicherten Wert aus.|
|[atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear)|Legt das-Flag in einem `atomic_flag`-Objekt auf **false**fest.|
|[atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit)|Legt das-Flag in einem `atomic_flag`-Objekt auf **false**fest.|
|[atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)|Legt das-Flag in einem `atomic_flag`-Objekt auf **true**fest.|
|[atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit)|Legt das-Flag in einem `atomic_flag`-Objekt auf **true**fest.|
|[atomic_init](../standard-library/atomic-functions.md#atomic_init)|Legt den gespeicherten Wert in einem `atomic`-Objekt fest.|
|[atomic_is_lock_free](../standard-library/atomic-functions.md#atomic_is_lock_free)|Gibt an, ob die atomischen Vorgänge auf einem bestimmten Objekt sperrfrei sind.|
|[atomic_load](../standard-library/atomic-functions.md#atomic_load)|Ruft atomisch einen Wert ab.|
|[atomic_load_explicit](../standard-library/atomic-functions.md#atomic_load_explicit)|Ruft atomisch einen Wert ab.|
|[atomic_signal_fence](../standard-library/atomic-functions.md#atomic_signal_fence)|Fungiert als *Umgrenzung*, die Anforderungen für die Speichersortierung zwischen Umgrenzungen in einem aufrufenden Thread einrichtet, in dem gleichzeitig Signalhandler ausgeführt werden.|
|[atomic_store](../standard-library/atomic-functions.md#atomic_store)|Speichert einen Wert atomisch.|
|[atomic_store_explicit](../standard-library/atomic-functions.md#atomic_store_explicit)|Speichert einen Wert atomisch.|
|[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)|Fungiert als *Umgrenzung*, die Anforderungen an die Speichersortierung in Bezug auf andere Umgrenzungen einrichtet.|
|[kill_dependency](../standard-library/atomic-functions.md#kill_dependency)|Unterbricht eine mögliche Abhängigkeitskette.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
