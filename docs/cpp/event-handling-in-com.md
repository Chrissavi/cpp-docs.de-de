---
title: Ereignisbehandlung in COM | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- event handling [C++], COM
- event handling [C++], about event handling
- declaring events
- event handlers [C++], COM
- event handlers
- COM, events
- event receivers, in event handling
- event handling [C++]
- hooking events
- event receivers, name and signature matching
- event sources, in event handling
- declaring events, in COM
- declaring events, event handling in COM
ms.assetid: 6b4617d4-a58e-440c-a8a6-1ad1c715b2bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e55fb5c213a54b4639f5707201bfbe93bfb89668
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065282"
---
# <a name="event-handling-in-com"></a>Ereignisbehandlung in COM

In COM-Ereignisbehandlung richten Sie eine Ereignisquelle und einen Ereignisempfänger mithilfe der [Event_source](../windows/event-source.md) und [Event_receiver](../windows/event-receiver.md) -Attribute angeben `type` = `com`. Diese Attribute fügen den geeigneten Code für benutzerdefinierte Schnittstellen, Dispatchschnittstellen und duale Schnittstellen ein, damit die Klassen, auf die sie angewendet werden, Ereignisse über COM-Verbindungspunkte auslösen und behandeln können.

## <a name="declaring-events"></a>Deklarieren von Ereignissen

In einer ereignisquellklasse verwenden die [__event](../cpp/event.md) -Schlüsselwort in einer Schnittstellendeklaration, um die Methoden dieser Schnittstelle als Ereignisse zu deklarieren. Die Ereignisse der Schnittstelle werden ausgelöst, wenn Sie die Ereignisse als Schnittstellenmethoden aufrufen. Methoden für Ereignisschnittstellen können NULL oder mehr Parameter haben (die muss alle *in* Parameter). Der Rückgabetyp kann „void“ oder ein ganzzahliger Typ sein.

## <a name="defining-event-handlers"></a>Definieren von Ereignishandlern

In einer Ereignisempfängerklasse definieren Sie Ereignishandler, die Methoden mit Signaturen sind (Rückgabetypen, Argumente und Aufrufkonventionen), die mit dem Ereignis übereinstimmen, das sie behandeln. Für COM-Ereignisse müssen Aufrufkonventionen nicht übereinstimmen; finden Sie unter [Layoutabhängige COM-Ereignisse](#vcconeventhandlingincomanchorlayoutdependentcomevents) unten Weitere Informationen.

## <a name="hooking-event-handlers-to-events"></a>Verknüpfen von Ereignishandlern mit Ereignissen

In einer Ereignisempfängerklasse, verwenden Sie auch die intrinsische Funktion [__hook](../cpp/hook.md) um Ereignisse Ereignishandlern zuzuordnen und [__unhook](../cpp/unhook.md) um Ereignisse von Ereignishandlern zu trennen. Sie können mehrere Ereignisse mit einem Ereignishandler oder mehrere Ereignishandler mit einem Ereignis verknüpfen.

> [!NOTE]
>  Normalerweise gibt es zwei Möglichkeiten, um es einem COM-Ereignisempfänger zu ermöglichen, auf Schnittstellendefinitionen von Ereignisquellen zuzugreifen. Die erste Möglichkeit besteht in einer gemeinsamen Headerdatei, wie unten gezeigt. Die zweite ist die Verwendung [#import](../preprocessor/hash-import-directive-cpp.md) mit der `embedded_idl` Importqualifizierer, damit die Ereignisquellen-Typbibliothek in die TLH-Datei mit der attributgenerierte Code beibehalten geschrieben wird.

## <a name="firing-events"></a>Auslösen von Ereignissen

Um ein Ereignis auszulösen, rufen Sie einfach eine Methode in der Schnittstelle deklariert mit dem **__event** Schlüsselwort in der ereignisquellklasse. Wenn Handler an das Ereignis geknüpft wurden, werden die Handler aufgerufen.

### <a name="com-event-code"></a>COM-Ereigniscode

Das folgende Beispiel zeigt, wie ein Ereignis in einer COM-Klasse ausgelöst wird. Informationen zum Kompilieren und Ausführen des Beispiels finden Sie in den Kommentaren im Code.

```cpp
// evh_server.h
#pragma once

[ dual, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IEvents {
   [id(1)] HRESULT MyEvent([in] int value);
};

[ dual, uuid("00000000-0000-0000-0000-000000000002") ]
__interface IEventSource {
   [id(1)] HRESULT FireEvent();
};

class DECLSPEC_UUID("530DF3AD-6936-3214-A83B-27B63C7997C4") CSource;
```

Anschließend der Server:

```cpp
// evh_server.cpp
// compile with: /LD
// post-build command: Regsvr32.exe /s evh_server.dll
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include "evh_server.h"

[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];

[coclass, event_source(com), uuid("530DF3AD-6936-3214-A83B-27B63C7997C4")]
class CSource : public IEventSource {
public:
   __event __interface IEvents;

   HRESULT FireEvent() {
      __raise MyEvent(123);
      return S_OK;
   }
};
```

Und im Anschluss der Client:

```cpp
// evh_client.cpp
// compile with: /link /OPT:NOREF
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <stdio.h>
#include "evh_server.h"

[ module(name="EventReceiver") ];

[ event_receiver(com) ]
class CReceiver {
public:
   HRESULT MyHandler1(int nValue) {
      printf_s("MyHandler1 was called with value %d.\n", nValue);
      return S_OK;
   }

   HRESULT MyHandler2(int nValue) {
      printf_s("MyHandler2 was called with value %d.\n", nValue);
      return S_OK;
   }

   void HookEvent(IEventSource* pSource) {
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);
   }

   void UnhookEvent(IEventSource* pSource) {
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);
   }
};

int main() {
   // Create COM object
   CoInitialize(NULL);
   {
      IEventSource* pSource = 0;
      HRESULT hr = CoCreateInstance(__uuidof(CSource), NULL,         CLSCTX_ALL, __uuidof(IEventSource), (void **) &pSource);
      if (FAILED(hr)) {
         return -1;
      }

      // Create receiver and fire event
      CReceiver receiver;
      receiver.HookEvent(pSource);
      pSource->FireEvent();
      receiver.UnhookEvent(pSource);
   }
   CoUninitialize();
   return 0;
}
```

### <a name="output"></a>Ausgabe

```Output
MyHandler1 was called with value 123.
MyHandler2 was called with value 123.
```

##  <a name="vcconeventhandlingincomanchorlayoutdependentcomevents"></a> Layoutabhängige COM-Ereignisse

Layoutabhängigkeit ist nur bei der COM-Programmierung ein Problem. Bei nativer und verwalteter Ereignisbehandlung müssen die Signaturen (Rückgabetyp, Aufrufkonvention und Argumente) der Handler ihren Ereignissen entsprechen, aber die Handlernamen müssen nicht mit ihren Ereignissen übereinstimmen.

In COM-Ereignisbehandlung, beim Festlegen der *Layout_dependent* Parameter der `event_receiver` zu **"true"**, die Übereinstimmung von Name und Signatur erzwungen wird. Dies bedeutet, dass die Namen und Signaturen der Handler im Ereignisempfänger exakt mit den Namen und Signaturen der Ereignisse übereinstimmen müssen, mit denen sie verknüpft sind.

Bei *Layout_dependent* nastaven NA hodnotu **"false"**, die aufrufende Konvention und Speicher-Klasse (virtuellen, statisch usw.) kann gemischt und zwischen der auslösenden Ereignismethode und den hookmethoden (die Delegaten). Es ist etwas effizienter, *Layout_dependent*=**"true"**.

Nehmen Sie z. B. an, `IEventSource` wird definiert, um über die folgenden Methoden zu verfügen:

```cpp
[id(1)] HRESULT MyEvent1([in] int value);
[id(2)] HRESULT MyEvent2([in] int value);
```

Angenommen, die Ereignisquelle weist das folgende Format auf:

```cpp
[coclass, event_source(com)]
class CSource : public IEventSource {
public:
   __event __interface IEvents;

   HRESULT FireEvent() {
      MyEvent1(123);
      MyEvent2(123);
      return S_OK;
   }
};
```

Im Ereignisempfänger muss dann jeder Handler, der an eine Methode `IEventSource` gebunden ist, dem zugehörigen Namen und der zugehörigen Signatur entsprechen, wie hier gezeigt:

```cpp
[coclass, event_receiver(com, true)]
class CReceiver {
public:
   HRESULT MyEvent1(int nValue) {  // name and signature matches MyEvent1
      ...
   }
   HRESULT MyEvent2(E c, char* pc) {  // signature doesn't match MyEvent2
      ...
   }
   HRESULT MyHandler1(int nValue) {  // name doesn't match MyEvent1 (or 2)
      ...
   }
   void HookEvent(IEventSource* pSource) {
      __hook(IFace, pSource);  // Hooks up all name-matched events
                               // under layout_dependent = true
      __hook(&IFace::MyEvent1, pSource, &CReceive::MyEvent1);   // valid
      __hook(&IFace::MyEvent2, pSource, &CSink::MyEvent2);   // not valid
      __hook(&IFace::MyEvent1, pSource, &CSink:: MyHandler1); // not valid
   }
};
```

## <a name="see-also"></a>Siehe auch

[Ereignisbehandlung](../cpp/event-handling.md)