---
title: single_assignment-Klasse
ms.date: 11/04/2016
f1_keywords:
- single_assignment
- AGENTS/concurrency::single_assignment
- AGENTS/concurrency::single_assignment::single_assignment
- AGENTS/concurrency::single_assignment::has_value
- AGENTS/concurrency::single_assignment::value
- AGENTS/concurrency::single_assignment::accept_message
- AGENTS/concurrency::single_assignment::consume_message
- AGENTS/concurrency::single_assignment::link_target_notification
- AGENTS/concurrency::single_assignment::propagate_message
- AGENTS/concurrency::single_assignment::propagate_to_any_targets
- AGENTS/concurrency::single_assignment::release_message
- AGENTS/concurrency::single_assignment::reserve_message
- AGENTS/concurrency::single_assignment::resume_propagation
- AGENTS/concurrency::single_assignment::send_message
helpviewer_keywords:
- single_assignment class
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
ms.openlocfilehash: 0d302f4f7f85737d9c3b2368e3ae04d88bc1a370
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142741"
---
# <a name="single_assignment-class"></a>single_assignment-Klasse

Ein `single_assignment`-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Zielen und mehreren Quellen, der eine einzelne, einmal beschreibbare `message` speichern kann.

## <a name="syntax"></a>Syntax

```cpp
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Nutz Lasttyp der Meldung, die vom Puffer gespeichert und weitergegeben wird.

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[single_assignment](#ctor)|Ist überladen. Erstellt einen `single_assignment` -Meldungsblock.|
|[~ single_assignment-Dekonstruktor](#dtor)|Zerstört den `single_assignment`-Messaging-Block.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[has_value](#has_value)|Überprüft, ob dieser `single_assignment`-Messaging-Block bereits mit einem Wert initialisiert wurde.|
|[value](#value)|Ruft einen Verweis auf die aktuelle Nutzlast der Meldung ab, die im `single_assignment`-Messaging-Block gespeichert wird.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[accept_message](#accept_message)|Akzeptiert eine Meldung, die von diesem `single_assignment` Messaging Block angeboten wurde, und gibt eine Kopie der Nachricht an den Aufrufer zurück.|
|[consume_message](#consume_message)|Verarbeitet eine Meldung, die zuvor vom-`single_assignment` angeboten und vom Ziel reserviert wurde. dabei wird eine Kopie der Nachricht an den Aufrufer zurückgegeben.|
|[link_target_notification](#link_target_notification)|Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem `single_assignment`-Nachrichtenblock verknüpft wurde.|
|[propagate_message](#propagate_message)|Übergibt eine Nachricht asynchron von einem `ISource`-Block an diesen `single_assignment`-Messaging-Block. Sie wird durch die `propagate`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Platziert die `message _PMessage` in diesem `single_assignment`-Messaging-Block und bietet alle verknüpften Ziele an.|
|[release_message](#release_message)|Gibt eine vorherige Nachrichten Reservierung frei. (Überschreibt [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Reserviert eine Meldung, die zuvor von diesem `single_assignment`-Nachrichtenblock angeboten wurde. (Überschreibt [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Setzt die Verteilung fort, nachdem eine Reservierung freigegeben wurde. (Überschreibt [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Übergibt eine Nachricht synchron von einem `ISource`-Block an diesen `single_assignment`-Messaging-Block. Sie wird durch die `send`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.|

## <a name="remarks"></a>Bemerkungen

Ein `single_assignment`-Messaging-Block gibt Kopien seiner Nachricht an jedes Ziel weiter.

Weitere Informationen finden Sie unter [asynchrone Nachrichten Blöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`single_assignment`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="accept_message"></a>accept_message

Akzeptiert eine Meldung, die von diesem `single_assignment` Messaging Block angeboten wurde, und gibt eine Kopie der Nachricht an den Aufrufer zurück.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des angebotenen `message` Objekts.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das `message` Objekt, für das der Aufrufer nun den Besitz hat.

### <a name="remarks"></a>Bemerkungen

Der `single_assignment` Messaging-Block gibt Kopien der Nachricht an seine Ziele zurück, anstatt den Besitz der aktuell gespeicherten Nachricht zu übertragen.

## <a name="consume_message"></a>consume_message

Verarbeitet eine Meldung, die zuvor vom-`single_assignment` angeboten und vom Ziel reserviert wurde. dabei wird eine Kopie der Nachricht an den Aufrufer zurückgegeben.

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

Überprüft, ob dieser `single_assignment`-Messaging-Block bereits mit einem Wert initialisiert wurde.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Rückgabewert

**true** , wenn der Block einen Wert empfangen hat, andernfalls **false** .

## <a name="link_target_notification"></a>link_target_notification

Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem `single_assignment`-Nachrichtenblock verknüpft wurde.

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf das neu verknüpfte Ziel.

## <a name="propagate_message"></a>propagate_message

Übergibt eine Nachricht asynchron von einem `ISource`-Block an diesen `single_assignment`-Messaging-Block. Sie wird durch die `propagate`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.

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

Platziert die `message` `_PMessage` in diesem `single_assignment` Messaging Block und bietet alle verknüpften Ziele an.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf einen `message`, der von diesem `single_assignment` Messaging Block übernommen wurde.

## <a name="release_message"></a>release_message

Gibt eine vorherige Nachrichten Reservierung frei.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des `message` Objekts, das freigegeben wird.

## <a name="reserve_message"></a>reserve_message

Reserviert eine Meldung, die zuvor von diesem `single_assignment`-Nachrichtenblock angeboten wurde.

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

## <a name="send_message"></a>send_message

Übergibt eine Nachricht synchron von einem `ISource`-Block an diesen `single_assignment`-Messaging-Block. Sie wird durch die `send`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.

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

## <a name="ctor"></a>single_assignment

Erstellt einen `single_assignment` -Meldungsblock.

```cpp
single_assignment();

single_assignment(
    filter_method const& _Filter);

single_assignment(
    Scheduler& _PScheduler);

single_assignment(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

single_assignment(
    ScheduleGroup& _PScheduleGroup);

single_assignment(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Parameter

*_Filter*<br/>
Eine Filterfunktion, die bestimmt, ob angebotene Nachrichten akzeptiert werden sollen.

*_PScheduler*<br/>
Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `single_assignment` -Meldungsblock geplant ist.

*_PScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `single_assignment` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

### <a name="remarks"></a>Bemerkungen

Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.

Der Typ `filter_method` ist ein Funktor mit Signatur `bool (T const &)` der von diesem `single_assignment` Messaging Block aufgerufen wird, um zu bestimmen, ob er eine angebotene Nachricht akzeptieren soll.

## <a name="dtor"></a>~ single_assignment

Zerstört den `single_assignment`-Messaging-Block.

```cpp
~single_assignment();
```

## <a name="value"></a>Wert

Ruft einen Verweis auf die aktuelle Nutzlast der Meldung ab, die im `single_assignment`-Messaging-Block gespeichert wird.

```cpp
T const& value();
```

### <a name="return-value"></a>Rückgabewert

Die Nutzlast der gespeicherten Nachricht.

### <a name="remarks"></a>Bemerkungen

Diese Methode wartet, bis eine Nachricht eingeht, wenn derzeit keine Nachricht im `single_assignment`-Messaging-Block gespeichert wird.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[overwrite_buffer-Klasse](overwrite-buffer-class.md)<br/>
[unbounded_buffer-Klasse](unbounded-buffer-class.md)
