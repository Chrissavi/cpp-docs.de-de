---
title: '&lt;Thread&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <thread>
dev_langs:
- C++
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef5470d7c7e83c260f44d723665d5d9c0a5ad061
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953028"
---
# <a name="ltthreadgt"></a>&lt;thread&gt;

Schließen Sie den Standardheader \<Thread > zum Definieren der Klasse **Thread** und verschiedene unterstützende Funktionen.

## <a name="syntax"></a>Syntax

```cpp
#include <thread>
```

## <a name="remarks"></a>Hinweise

> [!NOTE]
> Im Code, der kompiliert wird **"/ CLR"**, dieser Header blockiert.

Die `__STDCPP_THREADS__` -Makro ist definiert als einen Wert ungleich NULL, um anzugeben, dass Threads, die von dieser Header unterstützt werden.

## <a name="members"></a>Member

### <a name="public-classes"></a>Öffentliche Klassen

|Name|Beschreibung|
|----------|-----------------|
|[thread-Klasse](../standard-library/thread-class.md)|Definiert ein Objekt, das zum Überwachen und Verwalten eines Ausführungsthreads in einer Anwendung verwendet wird.|

### <a name="public-structures"></a>Öffentliche Strukturen

|name|Beschreibung|
|----------|-----------------|
|[Hash-Struktur (C++-Standardbibliothek)](../standard-library/hash-structure-stl.md)|Definiert eine Memberfunktion, die einen Wert, die eindeutig zurückgibt nach richtet eine `thread::id`. Das Funktionsobjekt definiert eine [Hash](../standard-library/hash-class.md) -Funktion, die für Werte des Typs eignet `thread::id` einer Verteilung von Indexwerten.|

### <a name="public-functions"></a>Öffentliche Funktionen

|name|Beschreibung|
|----------|-----------------|
|[get_id](../standard-library/thread-functions.md#get_id)|Weist den aktuellen Ausführungsthread eindeutig aus.|
|[sleep_for](../standard-library/thread-functions.md#sleep_for)|Blockiert den aufrufenden Thread.|
|[sleep_until](../standard-library/thread-functions.md#sleep_until)|Blockiert den aufrufenden Thread mindestens bis zum angegebenen Zeitpunkt.|
|[swap](../standard-library/thread-functions.md#swap)|Vertauscht die Zustände von zwei **Thread** Objekte.|
|[yield](../standard-library/thread-functions.md#yield)|Signalisiert dem Betriebssystem, andere Threads auszuführen, auch wenn der aktuelle Thread normalerweise weiterhin ausgeführt werden würde.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Operator > =-Operator](../standard-library/thread-operators.md#op_gt_eq)|Bestimmt, ob ein `thread::id`-Objekt größer als oder gleich einem anderen Objekt ist.|
|[Operator >-Operator](../standard-library/thread-operators.md#op_gt)|Bestimmt, ob ein `thread::id`-Objekt größer als ein anderes Objekt ist.|
|[Operator < =-Operator](../standard-library/thread-operators.md#op_lt_eq)|Bestimmt, ob ein `thread::id`-Objekt kleiner als oder gleich einem anderen Objekt ist.|
|[Operator <-Operator](../standard-library/thread-operators.md#op_lt)|Bestimmt, ob ein `thread::id`-Objekt kleiner als ein anderes Objekt ist.|
|[Operator! =-Operator](../standard-library/thread-operators.md#op_neq)|Überprüft zwei `thread::id`-Objekte auf Ungleichheit.|
|[Operator ==-Operator](../standard-library/thread-operators.md#op_eq_eq)|Überprüft zwei `thread::id`-Objekte auf Gleichheit.|
|[Operator << Operator](../standard-library/thread-operators.md#op_lt_lt)|Fügt eine Textdarstellung eines `thread::id`-Objekts in einen Stream ein.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
