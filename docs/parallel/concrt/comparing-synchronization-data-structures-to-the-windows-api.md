---
title: Vergleich der Synchronisierungsdatenstrukturen mit der Windows-API
ms.date: 11/04/2016
helpviewer_keywords:
- synchronization data structures, compared to Windows API
- event class, example
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
ms.openlocfilehash: 4fa0d3fbf3457bfafab731275584d206206161dd
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275973"
---
# <a name="comparing-synchronization-data-structures-to-the-windows-api"></a>Vergleich der Synchronisierungsdatenstrukturen mit der Windows-API

In diesem Thema wird das Verhalten der von der Concurrency Runtime bereitgestellten Synchronisierungsdatenstrukturen mit den von der Windows-API bereitgestellten Synchronisierungsdatenstrukturen verglichen.

Die von der Concurrency Runtime bereitgestellten Synchronisierungsdatenstrukturen führen Sie die *kooperativen Threadingmodell*. Im kooperativen Threadingmodell halten Synchronisierungsprimitiven ihre Verarbeitungsressourcen zugunsten von anderen Threads explizit zurück. Dies unterscheidet sich von der *präemptiven Threadingmodell*, in dem Verarbeitungsressourcen vom Planer oder Betriebssystem für andere Threads übertragen werden.

## <a name="criticalsection"></a>critical_section

Die [Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) -Klasse ähnelt der Windows `CRITICAL_SECTION` Struktur, da es nur von den Threads eines Prozesses verwendet werden kann. Weitere Informationen zu kritischen Abschnitten in der Windows-API finden Sie unter [Critical Section Objects](/windows/desktop/Sync/critical-section-objects).

## <a name="readerwriterlock"></a>reader_writer_lock

Die [Concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) ähnelt Windows slim Reader-/Writer (SRW) sperren. In der folgenden Tabelle werden die Übereinstimmungen und Unterschiede aufgelistet.

|Feature|`reader_writer_lock`|SRW-Sperre|
|-------------|--------------------------|--------------|
|Nicht wiedereintretend|Ja|Ja|
|Kann einen Reader auf einen Writer hochstufen|Nein|Nein|
|Kann einen Writer auf einen Reader tieferstufen|Nein|Nein|
|write-preference-Sperre|Ja|Nein|
|FIFO-Zugriff auf Writer|Ja|Nein|

Weitere Informationen zu SRW-sperren, finden Sie unter [Slim Reader-/Writer (SRW) Locks](https://msdn.microsoft.com/library/windows/desktop/aa904937) im Platform SDK.

## <a name="event"></a>event

Die [Concurrency:: Event](../../parallel/concrt/reference/event-class.md) ähnelt einem unbenannten, Windows-Ereignis für manuelles Zurücksetzen. Das Verhalten eines `event`-Objekts ist jedoch kooperativ, das Verhalten eines Windows-Ereignisses hingegen präemptiv. Weitere Informationen zu Windows-Ereignissen finden Sie unter [Ereignisobjekte](/windows/desktop/Sync/event-objects).

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Beispiel soll den Unterschied zwischen der `event`-Klasse und Windows-Ereignissen verdeutlichen. In diesem Beispiel wird der Planer aktiviert, um höchstens zwei gleichzeitige Aufgaben zu erstellen. Anschließend werden zwei ähnliche Funktionen aufgerufen, die die `event`-Klasse und ein Ereignis für manuelles Zurücksetzen in Windows verwenden. Beide Funktionen erstellen zunächst mehrere Aufgaben, die auf die Signalisierung eines freigegebenen Ereignisses warten. Beide Funktionen halten dann die ausgeführten Aufgaben zurück und signalisieren das Ereignis. Beide Funktionen warten dann auf das signalisierte Ereignis.

### <a name="code"></a>Code

[!code-cpp[concrt-event-comparison#1](../../parallel/concrt/codesnippet/cpp/comparing-synchronization-data-structures-to-the-windows-api_1.cpp)]

### <a name="comments"></a>Kommentare

Dieses Beispiel erzeugt die folgende Beispielausgabe:

```Output
Cooperative event:
    Context 0: waiting on an event.
    Context 1: waiting on an event.
    Context 2: waiting on an event.
    Context 3: waiting on an event.
    Context 4: waiting on an event.
    Setting the event.
    Context 5: received the event.
    Context 6: received the event.
    Context 7: received the event.
    Context 8: received the event.
    Context 9: received the event.
Windows event:
    Context 10: waiting on an event.
    Context 11: waiting on an event.
    Setting the event.
    Context 12: received the event.
    Context 14: waiting on an event.
    Context 15: received the event.
    Context 16: waiting on an event.
    Context 17: received the event.
    Context 18: waiting on an event.
    Context 19: received the event.
    Context 13: received the event.
```

Da das Verhalten der `event`-Klasse kooperativ ist, kann der Planer Verarbeitungsressourcen einem anderen Kontext zuweisen, während auf die Signalisierung eines Ereignisses gewartet wird. Aus diesem Grund bewerkstelligt die Version, die die `event`-Klasse verwendet, einen höheren Arbeitsaufwand. In der Version, die Windows-Ereignisse verwendet, muss jede wartende Aufgabe den signalisierten Zustand aufweisen, bevor die nächste Aufgabe gestartet werden kann.

Weitere Informationen zu Aufgaben, finden Sie unter [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="see-also"></a>Siehe auch

[Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md)
