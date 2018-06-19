---
title: Message_processor-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- message_processor
- AGENTS/concurrency::message_processor
- AGENTS/concurrency::message_processor::async_send
- AGENTS/concurrency::message_processor::sync_send
- AGENTS/concurrency::message_processor::wait
- AGENTS/concurrency::message_processor::process_incoming_message
dev_langs:
- C++
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95e95cc84ca999402e0d64c0699750bb92203cef
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689388"
---
# <a name="messageprocessor-class"></a>message_processor-Klasse
Die `message_processor`-Klasse ist die abstrakte Basisklasse für die Verarbeitung von `message`-Objekten. Für die Reihenfolge der Meldungen besteht keine Garantie.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class message_processor;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp der Nutzlast in Nachrichten von diesem verarbeitet `message_processor` Objekt.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`type`|Ein Typalias für `T`.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[async_send](#async_send)|Ruft beim Überschreiben in einer abgeleiteten Klasse legt Nachrichten asynchron in den Block.|  
|[sync_send](#sync_send)|Ruft beim Überschreiben in einer abgeleiteten Klasse legt Nachrichten synchron in den Block.|  
|[wait](#wait)|Ruft beim Überschreiben in einer abgeleiteten Klasse wartet, bis alle asynchronen Vorgänge abgeschlossen.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[process_incoming_message](#process_incoming_message)|Führt beim Überschreiben in einer abgeleiteten Klasse die forward-Verarbeitung von Nachrichten in den Block aus. Wird einmal aufgerufen, sobald eine neue Nachricht hinzugefügt wird und die Warteschlange ist eine leere Zeichenfolge gefunden.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `message_processor`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="async_send"></a> async_send 

 Ruft beim Überschreiben in einer abgeleiteten Klasse legt Nachrichten asynchron in den Block.  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Msg`  
 Ein `message` Objekt asynchron gesendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Prozessor-Implementierungen sollten diese Methode überschreiben.  
  
##  <a name="process_incoming_message"></a> process_incoming_message 

 Führt beim Überschreiben in einer abgeleiteten Klasse die forward-Verarbeitung von Nachrichten in den Block aus. Wird einmal aufgerufen, sobald eine neue Nachricht hinzugefügt wird und die Warteschlange ist eine leere Zeichenfolge gefunden.  
  
```
virtual void process_incoming_message() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Message-Block-Implementierungen sollten diese Methode überschreiben.  
  
##  <a name="sync_send"></a> sync_send 

 Ruft beim Überschreiben in einer abgeleiteten Klasse legt Nachrichten synchron in den Block.  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Msg`  
 Ein `message` Objekt, das synchron gesendet.  
  
### <a name="remarks"></a>Hinweise  
 Prozessor-Implementierungen sollten diese Methode überschreiben.  
  
##  <a name="wait"></a> Warte 

 Ruft beim Überschreiben in einer abgeleiteten Klasse wartet, bis alle asynchronen Vorgänge abgeschlossen.  
  
```
virtual void wait() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Prozessor-Implementierungen sollten diese Methode überschreiben.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [ordered_message_processor-Klasse](ordered-message-processor-class.md)
