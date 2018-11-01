---
title: transformer-Klasse
ms.date: 11/04/2016
f1_keywords:
- transformer
- AGENTS/concurrency::transformer
- AGENTS/concurrency::transformer::transformer
- AGENTS/concurrency::transformer::accept_message
- AGENTS/concurrency::transformer::consume_message
- AGENTS/concurrency::transformer::link_target_notification
- AGENTS/concurrency::transformer::propagate_message
- AGENTS/concurrency::transformer::propagate_to_any_targets
- AGENTS/concurrency::transformer::release_message
- AGENTS/concurrency::transformer::reserve_message
- AGENTS/concurrency::transformer::resume_propagation
- AGENTS/concurrency::transformer::send_message
- AGENTS/concurrency::transformer::supports_anonymous_source
helpviewer_keywords:
- transformer class
ms.assetid: eea71925-7043-4a92-bfd4-dbc0ece5d081
ms.openlocfilehash: cc35a4e2de2b29bb6d437dfcbf48ef361fefdfa3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618282"
---
# <a name="transformer-class"></a>transformer-Klasse

Ein `transformer`-Meldungsblock ist ein geordneter `propagator_block` mit einem einzelnen Ziel und mehreren Quellen, der Meldungen eines Typs akzeptieren und eine unbegrenzte Anzahl von Meldungen eines anderen Typs speichern kann.

## <a name="syntax"></a>Syntax

```
template<class _Input, class _Output>
class transformer : public propagator_block<single_link_registry<ITarget<_Output>>,
    multi_link_registry<ISource<_Input>>>;
```

#### <a name="parameters"></a>Parameter

*_Input*<br/>
Der Nutzlasttyp der Nachrichten vom Puffer akzeptiert.

*_Ausgabe*<br/>
Der Nutzlasttyp der Nachrichten gespeichert und vom Puffer übertragen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Transformer](#ctor)|Überladen. Erstellt einen `transformer` -Meldungsblock.|
|[~ Transformer-Destruktor](#dtor)|Zerstört die `transformer` Meldungsblock.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[accept_message](#accept_message)|Akzeptiert eine Meldung, die von diesem angeboten wurde `transformer` Meldungsblock, überträgt den Besitz an den Aufrufer.|
|[consume_message](#consume_message)|Nimmt eine Meldung, die zuvor von Angeboten die `transformer` und vom Ziel übertragen des Besitzes an den Aufrufer reservierte.|
|[link_target_notification](#link_target_notification)|Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit dieser verknüpft wurde `transformer` Meldungsblock.|
|[propagate_message](#propagate_message)|Übergibt asynchron eine Nachricht von einem `ISource` Block, um diese `transformer` Meldungsblock. Wird aufgerufen, indem die `propagate` Methode, wenn Sie von einem Quellblock aufgerufen.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Führt die Transformer-Funktion für die eingehende Nachrichten.|
|[release_message](#release_message)|Gibt die nachrichtenreservierung einer vorherigen frei. (Überschreibt [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Reserviert eine Meldung, die zuvor von diesem angebotenen `transformer` Meldungsblock. (Überschreibt [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Weitergabe fortgesetzt, nachdem eine Reservierung freigegeben wurde. (Überschreibt [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Übergibt synchron eine Nachricht von einem `ISource` Block, um diese `transformer` Meldungsblock. Wird aufgerufen, indem die `send` Methode, wenn Sie von einem Quellblock aufgerufen.|
|[supports_anonymous_source](#supports_anonymous_source)|Überschreibt die `supports_anonymous_source` Methode, um anzugeben, dass dieser Block annehmen kann Nachrichten angeboten, von einer Quelle, die nicht verknüpft ist. (Überschreibt [ITarget:: Supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`transformer`

## <a name="requirements"></a>Anforderungen

**Header:** agents.h

**Namespace:** Parallelität

##  <a name="accept_message"></a> accept_message

Akzeptiert eine Meldung, die von diesem angeboten wurde `transformer` Meldungsblock, überträgt den Besitz an den Aufrufer.

```
virtual message<_Output>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von den angebotenen `message` Objekt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `message` Objekt, mit der Aufrufer jetzt besitzt.

##  <a name="consume_message"></a> consume_message

Nimmt eine Meldung, die zuvor von Angeboten die `transformer` und vom Ziel übertragen des Besitzes an den Aufrufer reservierte.

```
virtual message<_Output>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von der `message` -Objekt verarbeitet.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `message` Objekt, mit der Aufrufer jetzt besitzt.

### <a name="remarks"></a>Hinweise

Ähnlich wie `accept`, steht aber immer durch einen Aufruf von ist `reserve`.

##  <a name="link_target_notification"></a> link_target_notification

Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit dieser verknüpft wurde `transformer` Meldungsblock.

```
virtual void link_target_notification(_Inout_ ITarget<_Output> *);
```

##  <a name="propagate_message"></a> propagate_message

Übergibt asynchron eine Nachricht von einem `ISource` Block, um diese `transformer` Meldungsblock. Wird aufgerufen, indem die `propagate` Methode, wenn Sie von einem Quellblock aufgerufen.

```
virtual message_status propagate_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quellblock die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, die Sie mit der Meldung.

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

Führt die Transformer-Funktion für die eingehende Nachrichten.

```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Output> *);
```

##  <a name="release_message"></a> release_message

Gibt die nachrichtenreservierung einer vorherigen frei.

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von der `message` Objekt freigegeben wird.

##  <a name="reserve_message"></a> reserve_message

Reserviert eine Meldung, die zuvor von diesem angebotenen `transformer` Meldungsblock.

```
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von der `message` Objekt reserviert wird.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Nachricht erfolgreich reserviert wurde, **"false"** andernfalls.

### <a name="remarks"></a>Hinweise

Nach dem `reserve` aufgerufen wird, wenn zurückgegeben **"true"**, entweder `consume` oder `release` aufgerufen werden, um zu übernehmen oder den Besitz der Nachricht.

##  <a name="resume_propagation"></a> resume_propagation

Weitergabe fortgesetzt, nachdem eine Reservierung freigegeben wurde.

```
virtual void resume_propagation();
```

##  <a name="send_message"></a> send_message

Übergibt synchron eine Nachricht von einem `ISource` Block, um diese `transformer` Meldungsblock. Wird aufgerufen, indem die `send` Methode, wenn Sie von einem Quellblock aufgerufen.

```
virtual message_status send_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quellblock die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, die Sie mit der Meldung.

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

Überschreibt die `supports_anonymous_source` Methode, um anzugeben, dass dieser Block annehmen kann Nachrichten angeboten, von einer Quelle, die nicht verknüpft ist.

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Rückgabewert

**"true"** , weil der Block nicht verschieben wird angeboten Nachrichten.

##  <a name="ctor"></a> Transformer

Erstellt einen `transformer` -Meldungsblock.

```
transformer(
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);

transformer(
    Scheduler& _PScheduler,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    Scheduler& _PScheduler,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);

transformer(
    ScheduleGroup& _PScheduleGroup,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    ScheduleGroup& _PScheduleGroup,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Parameter

*_Func*<br/>
Eine Funktion, die für jede akzeptierte Nachricht aufgerufen wird.

*_PTarget*<br/>
Ein Zeiger auf einem Zielblock, mit dem Transformator verknüpft.

*_Filter*<br/>
Eine Filterfunktion, die bestimmt, ob angebotene Nachrichten akzeptiert werden sollen.

*_PScheduler*<br/>
Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `transformer` -Meldungsblock geplant ist.

*_PScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `transformer` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

### <a name="remarks"></a>Hinweise

Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.

Der Typ `_Transform_method` ist ein Funktionselement mit Signatur `_Output (_Input const &)` die aufgerufen wird, von diesem `transformer` Meldungsblock, eine Nachricht nicht verarbeiten.

Der Typ `filter_method` ist ein Funktionselement mit Signatur `bool (_Input const &)` die aufgerufen wird, von diesem `transformer` Meldungsblock, um zu bestimmen, und zwar unabhängig davon, ob sie eine angebotene Nachricht akzeptiert werden sollte.

##  <a name="dtor"></a> ~ Transformer

Zerstört die `transformer` Meldungsblock.

```
~transformer();
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[call-Klasse](call-class.md)
