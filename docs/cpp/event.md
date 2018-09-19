---
title: __event | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __event_cpp
- __event
dev_langs:
- C++
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 393e6cca6db88dc4c5545b86b3ca9e39b75a6bc9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082302"
---
# <a name="event"></a>__event

Deklariert ein Ereignis.

## <a name="syntax"></a>Syntax

```
__event method-declarator;
__event __interface interface-specifier;
__event member-declarator;
```

## <a name="remarks"></a>Hinweise

Das Schlüsselwort **__event** kann auf eine Methodendeklaration, eine Schnittstellendeklaration oder eine datenmemberdeklaration angewendet werden. Allerdings können keine der **__event** Schlüsselwort, um einen Member einer geschachtelten Klasse zu qualifizieren.

Je nachdem, ob Ereignisquelle und Empfänger systemeigenes C++, COM oder verwaltet (.NET Framework) sind, können Sie die folgenden Konstrukte als Ereignisse verwenden:

|Systemeigenes C++|COM|Verwaltet (.NET Framework)|
|------------------|---------|--------------------------------|
|Methode|—|Methode|
|—|interface|—|
|—|—|Datenmember|

Verwendung [__hook](../cpp/hook.md) in einem Ereignisempfänger, um eine Handlermethode einer Ereignismethode zuzuordnen. Beachten Sie, dass nach der Erstellung eines Ereignisses mit der **__event** -Schlüsselwort alle Ereignishandler, die anschließend zu diesem Ereignis verknüpft werden aufgerufen, wenn das Ereignis aufgerufen wird.

Ein **__event** Methodendeklaration kann keine Definition aufweisen. eine Definition wird implizit generiert, sodass die Ereignismethode aufgerufen werden kann, als handele es sich um eine normale Methode.

> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.

## <a name="native-events"></a>Systemeigene Ereignisse

Systemeigene Ereignisse sind Methoden. Der Rückgabetyp ist in der Regel HRESULT oder **"void"**, jedoch können beliebiger ganzzahliger Typ sein, einschließlich einer **Enum**. Wenn ein Ereignis einen ganzzahligen Rückgabetyp verwendet, ist für den Fall, dass ein Ereignishandler einen Wert ungleich 0 (null) zurückgibt, eine Fehlerbedingung definiert. In diesem Fall werden durch das ausgelöste Ereignis die anderen Delegaten aufgerufen.

```cpp
// Examples of native C++ events:
__event void OnDblClick();
__event HRESULT OnClick(int* b, char* s);
```

Finden Sie unter [Ereignisbehandlung in systemeigenem C++](../cpp/event-handling-in-native-cpp.md) Beispielcode.

## <a name="com-events"></a>COM-Ereignisse

COM-Ereignisse sind Schnittstellen. Die Parameter einer Methode in einer Quellschnittstelle des Ereignisses muss *in* Parameter (Dies wird jedoch nicht streng erzwungen), da ein *out* Parameter ist nicht hilfreich, wenn Sie Multicasting. Eine Warnung der Stufe 1 wird ausgegeben, wenn Sie verwenden eine *out* Parameter.

Der Rückgabetyp ist in der Regel HRESULT oder **"void"**, jedoch können beliebiger ganzzahliger Typ sein, einschließlich **Enum**. Wenn ein Ereignis einen ganzzahligen Rückgabetyp verwendet und ein Ereignishandler einen Wert ungleich 0 (null) zurückgibt, handelt es sich um eine Fehlerbedingung. In diesem Fall werden durch das ausgelöste Ereignis Aufrufe anderer Delegaten abgebrochen. Beachten Sie, dass der Compiler eine Quellschnittstelle des Ereignisses als automatisch markiert einen [Quelle](../windows/source-cpp.md) in der generierten IDL-Datei.

Die [__interface](../cpp/interface.md) -Schlüsselwort ist immer erforderlich ist, nach dem **__event** für eine COM-Ereignisquelle.

```cpp
// Example of a COM event:
__event __interface IEvent1;
```

Finden Sie unter [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md) Beispielcode.

## <a name="managed-events"></a>Verwaltete Ereignisse

Weitere Informationen über die Codierung von Ereignissen in der neuen Syntax finden Sie unter [Ereignis](../windows/event-cpp-component-extensions.md).

Verwaltete Ereignisse sind Datenmember oder Methoden. Wenn mit einem Ereignis verwendet wird, muss der Rückgabetyp eines Delegaten kompatibel mit werden die [Common Language Specification](/dotnet/standard/language-independence-and-language-independent-components). Der Rückgabetyp des Ereignishandlers muss dem Rückgabetyp des Delegaten entsprechen. Weitere Informationen zu Delegaten finden Sie unter [Delegaten und Ereignissen](../dotnet/delegates-and-events.md). Wenn ein verwaltetes Ereignis ein Datenmember ist, muss ihr Typ ein Zeiger auf einen Delegaten sein.

In .NET Framework können Sie einen Datenmember behandeln, als wäre er eine Methode selbst (d. h. die `Invoke`-Methode des entsprechenden Delegaten). Sie müssen den Delegattyp vordefinieren, um einen verwalteten Ereignisdatenmember zu deklarieren. Im Gegensatz dazu definiert eine verwaltete Ereignismethode implizit den entsprechenden verwalteten Delegaten, sofern er noch nicht definiert ist. Sie können beispielsweise einen Ereigniswert wie `OnClick` als Ereignis wie folgt angeben:

```cpp
// Examples of managed events:
__event ClickEventHandler* OnClick;  // data member as event
__event void OnClick(String* s);  // method as event
```

Wenn Sie implizit ein verwaltetes Ereignis deklarieren, können Sie add- und remove-Accessoren angeben, die aufgerufen werden, wenn Ereignishandler hinzugefügt oder entfernt werden. Sie können auch die Methode definieren, die das Ereignis außerhalb der Klasse aufruft (auslöst).

## <a name="example-native-events"></a>Beispiel: Systemeigene Ereignisse

```cpp
// EventHandling_Native_Event.cpp
// compile with: /c
[event_source(native)]
class CSource {
public:
   __event void MyEvent(int nValue);
};
```

## <a name="example-com-events"></a>Beispiel: COM-Ereignisse

```cpp
// EventHandling_COM_Event.cpp
// compile with: /c
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];

[ dual, uuid("00000000-0000-0000-0000-000000000002") ]
__interface IEventSource {
   [id(1)] HRESULT MyEvent();
};
[ coclass, uuid("00000000-0000-0000-0000-000000000003"),  event_source(com) ]
class CSource : public IEventSource {
public:
   __event __interface IEventSource;
   HRESULT FireEvent() {
      __raise MyEvent();
      return S_OK;
   }
};
```

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Ereignisbehandlung](../cpp/event-handling.md)<br/>
[event_source](../windows/event-source.md)<br/>
[event_receiver](../windows/event-receiver.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[__raise](../cpp/raise.md)