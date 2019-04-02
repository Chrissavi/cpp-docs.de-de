---
title: Compilerfehler C3919
ms.date: 11/04/2016
f1_keywords:
- C3919
helpviewer_keywords:
- C3919
ms.assetid: 5f8eddda-d751-478b-930d-e18f7191ddfb
ms.openlocfilehash: 05ac2fc9258a078f352b6012e64e86fe4b70c3f0
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58771473"
---
# <a name="compiler-error-c3919"></a>Compilerfehler C3919

'Event_method': Funktion muss den Typ 'Typ' aufweisen

Eine Ereignis-Accessormethode wurde nicht ordnungsgemäß deklariert.

Weitere Informationen zu Ereignissen finden Sie unter [Ereignis](../../extensions/event-cpp-component-extensions.md).

Im folgende Beispiel wird die C3919 generiert:

```
// C3919.cpp
// compile with: /clr /c
using namespace System;
delegate void D(String^);
ref class R {
   event D^ e {
      int add(int);   // C3919
      int remove(int);   // C3919

      void add(D^);   // OK
      void remove(D^);   // OK
   }
};
```