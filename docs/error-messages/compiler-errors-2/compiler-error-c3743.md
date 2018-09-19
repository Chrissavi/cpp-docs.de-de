---
title: Compilerfehler C3743 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3743
dev_langs:
- C++
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99988a9a0fb3afb197e081c45f6f5446d55b801c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019068"
---
# <a name="compiler-error-c3743"></a>Compilerfehler C3743

Hook/unhook kann nur auf eine gesamte Schnittstelle angewendet werden, wenn der "Layout_dependent"-Parameter des Event_receiver "true" ist.

Die [__unhook](../../cpp/unhook.md) Funktion unterscheidet sich hinsichtlich der die Anzahl von Parametern, die basierend auf den übergebenen Wert die `layout_dependent` Parameter in der [Event_receiver](../../windows/event-receiver.md) Klasse.

Im folgende Beispiel wird die C3743 generiert:

```
// C3743.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[module(name="xx")];
[object] __interface I { HRESULT f(); };

[event_receiver(com, layout_dependent=true), coclass]
struct R : I {
        HRESULT f() {
      return 0;
   }
        R() {
   }

   R(I* a) {
      __hook(I, a, &R::f);   // C3743
      // The following line resolves the error.
      // __hook(I, a);
   }
};
```