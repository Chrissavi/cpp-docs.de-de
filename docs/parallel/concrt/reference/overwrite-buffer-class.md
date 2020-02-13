---
title: overwrite_buffer-Klasse
ms.date: 11/04/2016
f1_keywords:
- overwrite_buffer
- AGENTS/concurrency::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::has_value
- AGENTS/concurrency::overwrite_buffer::value
- AGENTS/concurrency::overwrite_buffer::accept_message
- AGENTS/concurrency::overwrite_buffer::consume_message
- AGENTS/concurrency::overwrite_buffer::link_target_notification
- AGENTS/concurrency::overwrite_buffer::propagate_message
- AGENTS/concurrency::overwrite_buffer::propagate_to_any_targets
- AGENTS/concurrency::overwrite_buffer::release_message
- AGENTS/concurrency::overwrite_buffer::reserve_message
- AGENTS/concurrency::overwrite_buffer::resume_propagation
- AGENTS/concurrency::overwrite_buffer::send_message
- AGENTS/concurrency::overwrite_buffer::supports_anonymous_source
helpviewer_keywords:
- overwrite_buffer class
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
ms.openlocfilehash: 5b222170112f43ae9700054f42e1368545612d00
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138798"
---
# <a name="overwrite_buffer-class"></a>overwrite_buffer-Klasse

Ein `overwrite_buffer`-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Zielen und mehreren Quellen, der jeweils eine einzelne Meldung speichern kann. Neue Meldungen überschreiben zuvor Gespeicherte.

## <a name="syntax"></a>Syntax

```cpp
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Nutz Lasttyp der Nachrichten, die vom Puffer gespeichert und weitergegeben werden.

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[overwrite_buffer](#ctor)|Ist überladen. Erstellt einen `overwrite_buffer`-Messaging-Block.|
|[~ overwrite_buffer-Dekonstruktor](#dtor)|Zerstört den `overwrite_buffer`-Messaging-Block.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[has_value](#has_value)|Überprüft, ob dieser `overwrite_buffer`-Nachrichtenblock noch einen Wert aufweist.|
|[value](#value)|Ruft einen Verweis auf die aktuelle Nutzlast der Meldung ab, die im `overwrite_buffer`-Messaging-Block gespeichert wird.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[accept_message](#accept_message)|Akzeptiert eine Meldung, die von diesem `overwrite_buffer` Messaging Block angeboten wurde, und gibt eine Kopie der Nachricht an den Aufrufer zurück.|
|[consume_message](#consume_message)|Verarbeitet eine Meldung, die zuvor vom `overwrite_buffer` Messaging Block angeboten und vom Ziel reserviert wurde. dabei wird eine Kopie der Nachricht an den Aufrufer zurückgegeben.|
|[link_target_notification](#link_target_notification)|Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem `overwrite_buffer`-Nachrichtenblock verknüpft wurde.|
|[propagate_message](#propagate_message)|Übergibt eine Nachricht asynchron von einem `ISource`-Block an diesen `overwrite_buffer`-Messaging-Block. Sie wird durch die `propagate`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Platziert die `message _PMessage` in diesem `overwrite_buffer`-Messaging-Block und bietet alle verknüpften Ziele an.|
|[release_message](#release_message)|Gibt eine vorherige Nachrichten Reservierung frei. (Überschreibt [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Reserviert eine Meldung, die zuvor von diesem `overwrite_buffer`-Nachrichtenblock angeboten wurde. (Überschreibt [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Setzt die Verteilung fort, nachdem eine Reservierung freigegeben wurde. (Überschreibt [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Übergibt eine Nachricht synchron von einem `ISource`-Block an diesen `overwrite_buffer`-Messaging-Block. Sie wird durch die `send`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.|
|[supports_anonymous_source](#supports_anonymous_source)|Überschreibt die `supports_anonymous_source`-Methode, um anzugeben, dass dieser Block Nachrichten akzeptieren kann, die ihm von einer nicht verknüpften Quelle angeboten werden. (Überschreibt [ITarget:: supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|

## <a name="remarks"></a>Bemerkungen

Ein `overwrite_buffer`-Messaging-Block gibt Kopien seiner gespeicherten Nachricht an die einzelnen Ziele weiter.

Weitere Informationen finden Sie unter [asynchrone Nachrichten Blöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`overwrite_buffer`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="accept_message"></a>accept_message

Akzeptiert eine Meldung, die von diesem `overwrite_buffer` Messaging Block angeboten wurde, und gibt eine Kopie der Nachricht an den Aufrufer zurück.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des angebotenen `message` Objekts.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das `message` Objekt, für das der Aufrufer nun den Besitz hat.

### <a name="remarks"></a>Bemerkungen

Der `overwrite_buffer` Messaging-Block gibt Kopien der Nachricht an seine Ziele zurück, anstatt den Besitz der aktuell gespeicherten Nachricht zu übertragen.

## <a name="consume_message"></a>consume_message

Verarbeitet eine Meldung, die zuvor vom `overwrite_buffer` Messaging Block angeboten und vom Ziel reserviert wurde. dabei wird eine Kopie der Nachricht an den Aufrufer zurückgegeben.

```cpp
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des verbrauchten `message` Objekts.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das `message` Objekt, für das der Aufrufer nun den Besitz hat.

### <a name="remarks"></a>Bemerkungen

Ähnlich wie bei `accept`, dem aber immer ein Aufruf`reserve`vorangestellt ist.

## <a name="has_value"></a>has_value

Überprüft, ob dieser `overwrite_buffer`-Nachrichtenblock noch einen Wert aufweist.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Rückgabewert

**true** , wenn der Block einen Wert empfangen hat, andernfalls **false** .

## <a name="link_target_notification"></a>link_target_notification

Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem `overwrite_buffer`-Nachrichtenblock verknüpft wurde.

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf das neu verknüpfte Ziel.

## <a name="dtor"></a>~ overwrite_buffer

Zerstört den `overwrite_buffer`-Messaging-Block.

```cpp
~overwrite_buffer();
```

## <a name="ctor"></a>overwrite_buffer

Erstellt einen `overwrite_buffer`-Messaging-Block.

```cpp
overwrite_buffer();

overwrite_buffer(
    filter_method const& _Filter);

overwrite_buffer(
    Scheduler& _PScheduler);

overwrite_buffer(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Parameter

*_Filter*<br/>
Eine Filterfunktion, die bestimmt, ob angebotene Nachrichten akzeptiert werden sollen.

*_PScheduler*<br/>
Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `overwrite_buffer` -Meldungsblock geplant ist.

*_PScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `overwrite_buffer` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

### <a name="remarks"></a>Bemerkungen

Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.

Der Typ `filter_method` ist ein Funktor mit Signatur `bool (T const &)` der von diesem `overwrite_buffer` Messaging Block aufgerufen wird, um zu bestimmen, ob er eine angebotene Nachricht akzeptieren soll.

## <a name="propagate_message"></a>propagate_message

Übergibt eine Nachricht asynchron von einem `ISource`-Block an diesen `overwrite_buffer`-Messaging-Block. Sie wird durch die `propagate`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.

```cpp
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quell Block, der die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Eine [Message_status](concurrency-namespace-enums.md) , die angibt, wie sich das Ziel für die Nachricht entschieden hat.

## <a name="propagate_to_any_targets"></a>propagate_to_any_targets

Platziert die `message _PMessage` in diesem `overwrite_buffer`-Messaging-Block und bietet alle verknüpften Ziele an.

```cpp
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf ein `message` Objekt, für das diese `overwrite_buffer` den Besitz übernommen hat.

### <a name="remarks"></a>Bemerkungen

Diese Methode überschreibt die aktuelle Meldung in der `overwrite_buffer` mit der neu akzeptierten Nachricht `_PMessage`.

## <a name="send_message"></a>send_message

Übergibt eine Nachricht synchron von einem `ISource`-Block an diesen `overwrite_buffer`-Messaging-Block. Sie wird durch die `send`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.

```cpp
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quell Block, der die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Eine [Message_status](concurrency-namespace-enums.md) , die angibt, wie sich das Ziel für die Nachricht entschieden hat.

## <a name="supports_anonymous_source"></a>supports_anonymous_source

Überschreibt die `supports_anonymous_source`-Methode, um anzugeben, dass dieser Block Nachrichten akzeptieren kann, die ihm von einer nicht verknüpften Quelle angeboten werden.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Rückgabewert

**true** , weil der-Block angebotene Nachrichten nicht verschiebt.

## <a name="release_message"></a>release_message

Gibt eine vorherige Nachrichten Reservierung frei.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des `message` Objekts, das freigegeben wird.

## <a name="reserve_message"></a>reserve_message

Reserviert eine Meldung, die zuvor von diesem `overwrite_buffer`-Nachrichtenblock angeboten wurde.

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des reservierten `message` Objekts.

### <a name="return-value"></a>Rückgabewert

**true** , wenn die Nachricht erfolgreich reserviert wurde, andernfalls **false** .

### <a name="remarks"></a>Bemerkungen

Wenn `reserve` aufgerufen wird, muss entweder `consume` oder `release` aufgerufen **werden, um**den Besitz der Nachricht zu übernehmen oder freizugeben.

## <a name="resume_propagation"></a>resume_propagation

Setzt die Verteilung fort, nachdem eine Reservierung freigegeben wurde.

```cpp
virtual void resume_propagation();
```

## <a name="value"></a>Wert

Ruft einen Verweis auf die aktuelle Nutzlast der Meldung ab, die im `overwrite_buffer`-Messaging-Block gespeichert wird.

```cpp
T value();
```

### <a name="return-value"></a>Rückgabewert

Die Nutzlast der aktuell gespeicherten Nachricht.

### <a name="remarks"></a>Bemerkungen

Der im `overwrite_buffer` gespeicherte Wert kann sich unmittelbar nach der Rückgabe dieser Methode ändern. Diese Methode wartet, bis eine Nachricht eingeht, wenn zurzeit keine Nachricht in der `overwrite_buffer`gespeichert ist.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[unbounded_buffer-Klasse](unbounded-buffer-class.md)<br/>
[single_assignment-Klasse](single-assignment-class.md)
