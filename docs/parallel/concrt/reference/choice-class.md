---
title: choice-Klasse
ms.date: 11/04/2016
f1_keywords:
- choice
- AGENTS/concurrency::choice
- AGENTS/concurrency::choice::choice
- AGENTS/concurrency::choice::accept
- AGENTS/concurrency::choice::acquire_ref
- AGENTS/concurrency::choice::consume
- AGENTS/concurrency::choice::has_value
- AGENTS/concurrency::choice::index
- AGENTS/concurrency::choice::link_target
- AGENTS/concurrency::choice::release
- AGENTS/concurrency::choice::release_ref
- AGENTS/concurrency::choice::reserve
- AGENTS/concurrency::choice::unlink_target
- AGENTS/concurrency::choice::unlink_targets
- AGENTS/concurrency::choice::value
helpviewer_keywords:
- choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
ms.openlocfilehash: 3e718d0d34580d3bf2f13937159e431134631218
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142220"
---
# <a name="choice-class"></a>choice-Klasse

Ein `choice`-Meldungsblock ist ein Block mit mehreren Quellen und einem einzelnen Ziel, der eine Kontrollflussinteraktion zwischen mehreren Quellen darstellt. Der Auswahlblock wartet, bis eine von mehreren Quellen eine Meldung erzeugt, und gibt den Index der Quelle, von der die Meldung erzeugt wurde, weiter.

## <a name="syntax"></a>Syntax

```cpp
template<
    class T
>
class choice: public ISource<size_t>;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein `tuple`basierter Typ, der die Nutzlasten der Eingabe Quellen darstellt.

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|`type`|Ein Typalias für `T`.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Wahl](#ctor)|Ist überladen. Erstellt einen `choice` -Meldungsblock.|
|[~ Choice-Dekonstruktor](#dtor)|Zerstört den `choice`-Messaging-Block.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[erst](#accept)|Akzeptiert eine Meldung, die von diesem `choice` Block angeboten wurde, und überträgt den Besitz an den Aufrufer.|
|[acquire_ref](#acquire_ref)|Erhält einen Verweis Zähler für diesen `choice` Messaging Block, um das Löschen zu verhindern.|
|[Nutzen](#consume)|Verarbeitet eine Meldung, die zuvor von diesem `choice`-Messaging-Block angeboten und vom Ziel erfolgreich reserviert wurde, und überträgt den Besitz an den Aufrufer.|
|[has_value](#has_value)|Überprüft, ob dieser `choice`-Messaging-Block bereits mit einem Wert initialisiert wurde.|
|[Index](#index)|Gibt einen Index in die `tuple` zurück, die das vom `choice` Messaging-Block ausgewählte Element darstellt.|
|[link_target](#link_target)|Verknüpft einen Zielblock mit diesem `choice`-Messaging-Block.|
|[release](#release)|Gibt eine vorherige erfolgreiche Nachrichten Reservierung frei.|
|[release_ref](#release_ref)|Gibt einen Verweis Zähler für diesen `choice` Messaging Block frei.|
|[reserve](#reserve)|Reserviert eine Meldung, die zuvor von diesem `choice`-Nachrichtenblock angeboten wurde.|
|[unlink_target](#unlink_target)|Entfernt einen Zielblock von diesem `choice`-Messaging-Block.|
|[unlink_targets](#unlink_targets)|Entfernt die Verknüpfung aller Ziele von diesem `choice`-Messaging-Block. (Überschreibt [ISource:: unlink_targets](isource-class.md#unlink_targets).)|
|[value](#value)|Ruft die Meldung ab, deren Index vom `choice` Messaging-Block ausgewählt wurde.|

## <a name="remarks"></a>Bemerkungen

Der Auswahl Block stellt sicher, dass nur eine der eingehenden Nachrichten genutzt wird.

Weitere Informationen finden Sie unter [asynchrone Nachrichten Blöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ISource](isource-class.md)

`choice`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="accept"></a>erst

Akzeptiert eine Meldung, die von diesem `choice` Block angeboten wurde, und überträgt den Besitz an den Aufrufer.

```cpp
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des angebotenen `message` Objekts.

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der die `accept` Methode aufrufen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Nachricht, für die der Aufrufer nun den Besitz hat.

## <a name="acquire_ref"></a>acquire_ref

Erhält einen Verweis Zähler für diesen `choice` Messaging Block, um das Löschen zu verhindern.

```cpp
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der diese Methode aufgerufen hat.

### <a name="remarks"></a>Bemerkungen

Diese Methode wird von einem `ITarget` Objekt aufgerufen, das während der `link_target` Methode mit dieser Quelle verknüpft wird.

## <a name="ctor"></a>Wahl

Erstellt einen `choice` -Meldungsblock.

```cpp
explicit choice(
    T _Tuple);

choice(
    Scheduler& _PScheduler,
    T _Tuple);

choice(
    ScheduleGroup& _PScheduleGroup,
    T _Tuple);

choice(
    choice&& _Choice);
```

### <a name="parameters"></a>Parameter

*_Tuple*<br/>
Ein `tuple` von Quellen für die Auswahl.

*_PScheduler*<br/>
Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `choice` -Meldungsblock geplant ist.

*_PScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `choice` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

*_Choice*<br/>
Ein `choice` -Meldungsblock, aus dem kopiert werden soll. Beachten Sie, dass das ursprüngliche Objekt verwaist ist, sodass dies ein Bewegungskonstruktor ist.

### <a name="remarks"></a>Bemerkungen

Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.

Bewegungskonstruktion wird bei einer aktiven Sperre nicht ausgeführt, d. h., der Benutzer muss sicherstellen, dass zum Zeitpunkt der Bewegung keine einfachen Aufgaben aktiv sind. Andernfalls können zahlreiche Wettläufe auftreten, wodurch Ausnahmen oder inkonsistente Zuständen verursacht werden.

## <a name="dtor"></a>~ Auswahl

Zerstört den `choice`-Messaging-Block.

```cpp
~choice();
```

## <a name="consume"></a>Verzehr

Verarbeitet eine Meldung, die zuvor von diesem `choice`-Messaging-Block angeboten und vom Ziel erfolgreich reserviert wurde, und überträgt den Besitz an den Aufrufer.

```cpp
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des reservierten `message` Objekts.

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der die `consume` Methode aufrufen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das `message` Objekt, für das der Aufrufer nun den Besitz hat.

### <a name="remarks"></a>Bemerkungen

Die `consume`-Methode ähnelt `accept`, aber muss immer ein `reserve` aufgerufen werden, der " **true**" zurückgegeben hat.

## <a name="has_value"></a>has_value

Überprüft, ob dieser `choice`-Messaging-Block bereits mit einem Wert initialisiert wurde.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Rückgabewert

**true** , wenn der Block einen Wert empfangen hat, andernfalls **false** .

## <a name="index"></a>Sin

Gibt einen Index in die `tuple` zurück, die das vom `choice` Messaging-Block ausgewählte Element darstellt.

```cpp
size_t index();
```

### <a name="return-value"></a>Rückgabewert

Der Nachrichten Index.

### <a name="remarks"></a>Bemerkungen

Die Nachrichten Nutzlast kann mithilfe der `get`-Methode extrahiert werden.

## <a name="link_target"></a>link_target

Verknüpft einen Zielblock mit diesem `choice`-Messaging-Block.

```cpp
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf einen `ITarget` Block, der mit diesem `choice` Messaging Block verknüpft werden soll.

## <a name="release"></a>Abgabe

Gibt eine vorherige erfolgreiche Nachrichten Reservierung frei.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des `message` Objekts, das freigegeben wird.

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der die `release` Methode aufrufen.

## <a name="release_ref"></a>release_ref

Gibt einen Verweis Zähler für diesen `choice` Messaging Block frei.

```cpp
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der diese Methode aufgerufen hat.

### <a name="remarks"></a>Bemerkungen

Diese Methode wird von einem `ITarget` Objekt aufgerufen, das von dieser Quelle entfernt wird. Der Quell Block darf alle für den Zielblock reservierten Ressourcen freigeben.

## <a name="reserve"></a>Schutz

Reserviert eine Meldung, die zuvor von diesem `choice`-Nachrichtenblock angeboten wurde.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des reservierten `message` Objekts.

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der die `reserve` Methode aufrufen.

### <a name="return-value"></a>Rückgabewert

**true** , wenn die Nachricht erfolgreich reserviert wurde, andernfalls **false** . Reservierungen können aus vielen Gründen fehlschlagen, z.b.: die Nachricht wurde bereits von einem anderen Ziel reserviert oder akzeptiert, die Quelle könnte Reservierungen ablehnen usw.

### <a name="remarks"></a>Bemerkungen

Nachdem Sie `reserve`aufgerufen haben, müssen Sie bei erfolgreicher Ausführung entweder `consume` oder `release` abrufen, um die Nachricht bzw. den Besitz der Nachricht zu übernehmen.

## <a name="unlink_target"></a>unlink_target

Entfernt einen Zielblock von diesem `choice`-Messaging-Block.

```cpp
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf einen `ITarget` Block, um die Verknüpfung mit diesem `choice` Messaging Block aufzulösen.

## <a name="unlink_targets"></a>unlink_targets

Entfernt die Verknüpfung aller Ziele von diesem `choice`-Messaging-Block.

```cpp
virtual void unlink_targets();
```

### <a name="remarks"></a>Bemerkungen

Diese Methode muss nicht vom Dekonstruktor aufgerufen werden, da der Dekonstruktor für den internen `single_assignment` Block die Verknüpfung ordnungsgemäß aufführt.

## <a name="value"></a>Wert

Ruft die Meldung ab, deren Index vom `choice` Messaging-Block ausgewählt wurde.

```cpp
template <
    typename _Payload_type
>
_Payload_type const& value();
```

### <a name="parameters"></a>Parameter

*_Payload_type*<br/>
Der Typ der Nachrichten Nutzlast.

### <a name="return-value"></a>Rückgabewert

Die Nutzlast der Nachricht.

### <a name="remarks"></a>Bemerkungen

Da ein `choice`-Messaging-Block Eingaben mit unterschiedlichen Nutz Last Typen annehmen kann, müssen Sie den Typ der Nutzlast zum Zeitpunkt des Abrufs angeben. Sie können den Typ basierend auf dem Ergebnis der `index` Methode ermitteln.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[join-Klasse](join-class.md)<br/>
[single_assignment-Klasse](single-assignment-class.md)
