---
title: Ordered_message_processor-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ordered_message_processor
- AGENTS/concurrency::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::async_send
- AGENTS/concurrency::ordered_message_processor::initialize
- AGENTS/concurrency::ordered_message_processor::initialize_batched_processing
- AGENTS/concurrency::ordered_message_processor::sync_send
- AGENTS/concurrency::ordered_message_processor::wait
- AGENTS/concurrency::ordered_message_processor::process_incoming_message
dev_langs:
- C++
helpviewer_keywords:
- ordered_message_processor class
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27dfb6c1a64d3a4e9df24f3966ec89db1dfbe10c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688764"
---
# <a name="orderedmessageprocessor-class"></a>ordered_message_processor-Klasse
Ein `ordered_message_processor` ist ein `message_processor`, mit dem Meldungsblöcke Meldungen in der Reihenfolge verarbeiten können, in der sie empfangen wurden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class ordered_message_processor : public message_processor<T>;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Nutzlasttyp der Nachrichten, die vom Prozessor behandelt.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`type`|Ein Typalias für `T`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ordered_message_processor](#ctor)|Erstellt ein `ordered_message_processor`-Objekt.|  
|[~ Ordered_message_processor-Destruktor](#dtor)|Zerstört das `ordered_message_processor`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[async_send](#async_send)|Asynchron Warteschlangen Nachrichten und eine Verarbeitungsaufgabe beginnt, wenn dies nicht bereits ausgeführt wurde. (Überschreibt [message_processor:: async_send](message-processor-class.md#async_send).)|  
|[initialize](#initialize)|Initialisiert die `ordered_message_processor` -Objekt mit der entsprechenden Callback-Funktion, den Planer und Zeitplan.|  
|[initialize_batched_processing](#initialize_batched_processing)|Initialisieren der Verarbeitung von Nachrichten im Batchmodus|  
|[sync_send](#sync_send)|Synchrone Warteschlangen Nachrichten und eine Verarbeitungsaufgabe beginnt, wenn dies nicht bereits ausgeführt wurde. (Überschreibt [message_processor:: sync_send](message-processor-class.md#sync_send).)|  
|[wait](#wait)|Eine prozessorspezifische Drehfeld-Wartezeit in der Meldungsblöcke Destruktoren verwendet, um sicherzustellen, dass alle Aufgaben für die asynchrone Verarbeitung für die Ausführung vor dem Löschen des Blocks haben. (Überschreibt [message_processor:: wait](message-processor-class.md#wait).)|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[process_incoming_message](#process_incoming_message)|Die Verarbeitungsfunktion, die asynchron aufgerufen wird. Nachrichten entfernt, und beginnt mit der Verarbeitung werden. (Überschreibt [message_processor:: process_incoming_message](message-processor-class.md#process_incoming_message).)|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [message_processor](message-processor-class.md)  
  
 `ordered_message_processor`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="async_send"></a> async_send 

 Asynchron Warteschlangen Nachrichten und eine Verarbeitungsaufgabe beginnt, wenn dies nicht bereits ausgeführt wurde.  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>Parameter  
 `_Msg`  
 Ein Zeiger auf eine Nachricht.  
  
##  <a name="initialize"></a> Initialisieren 

 Initialisiert die `ordered_message_processor` -Objekt mit der entsprechenden Callback-Funktion, den Planer und Zeitplan.  
  
```
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```  
  
### <a name="parameters"></a>Parameter  
 `_PScheduler`  
 Ein Zeiger auf den Planer für die Planung von Lightweight-Aufgaben verwendet werden soll.  
  
 `_PScheduleGroup`  
 Ein Zeiger auf die Planungsgruppe zum Planen von Lightweight-Tasks verwendet werden soll.  
  
 `_Handler`  
 Der Handlerfunktionselement während der Rückruf aufgerufen.  
  
##  <a name="initialize_batched_processing"></a> initialize_batched_processing 

 Initialisieren der Verarbeitung von Nachrichten im Batchmodus  
  
```
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```  
  
### <a name="parameters"></a>Parameter  
 `_Processor`  
 Der Prozessor Funktionselement während der Rückruf aufgerufen.  
  
 `_Propagator`  
 Das Propagator Funktionselement während der Rückruf aufgerufen.  
  
##  <a name="ctor"></a> ordered_message_processor 

 Erstellt ein `ordered_message_processor`-Objekt.  
  
```
ordered_message_processor();
```  
  
### <a name="remarks"></a>Hinweise  
 Dies `ordered_message_processor` werde nicht planen, asynchrone oder synchrone Handler, bis die `initialize` Funktion aufgerufen wird.  
  
##  <a name="dtor"></a> ~ordered_message_processor 

 Zerstört das `ordered_message_processor`-Objekt.  
  
```
virtual ~ordered_message_processor();
```  
  
### <a name="remarks"></a>Hinweise  
 Wartet, bis alle ausstehenden asynchronen Vorgängen vor der Zerstörung des Prozessors.  
  
##  <a name="process_incoming_message"></a> process_incoming_message 

 Die Verarbeitungsfunktion, die asynchron aufgerufen wird. Nachrichten entfernt, und beginnt mit der Verarbeitung werden.  
  
```
virtual void process_incoming_message();
```  
  
##  <a name="sync_send"></a> sync_send 

 Synchrone Warteschlangen Nachrichten und eine Verarbeitungsaufgabe beginnt, wenn dies nicht bereits ausgeführt wurde.  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>Parameter  
 `_Msg`  
 Ein Zeiger auf eine Nachricht.  
  
##  <a name="wait"></a> Warte 

 Eine prozessorspezifische Drehfeld-Wartezeit in der Meldungsblöcke Destruktoren verwendet, um sicherzustellen, dass alle Aufgaben für die asynchrone Verarbeitung für die Ausführung vor dem Löschen des Blocks haben.  
  
```
virtual void wait();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
