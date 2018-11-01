---
title: Schwerwiegender Fehler C1022
ms.date: 11/04/2016
f1_keywords:
- C1022
helpviewer_keywords:
- C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
ms.openlocfilehash: 044ebbbe895677acf74977e56879c292486e18cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432564"
---
# <a name="fatal-error-c1022"></a>Schwerwiegender Fehler C1022

#endif erwartet

Eine `#if`-, `#ifdef`- oder `#ifndef` -Direktive weist keine übereinstimmende `#endif` -Direktive auf. Stellen Sie sicher, dass jedes `#if`, `#ifdef`oder `#ifndef` über ein übereinstimmendes `#endif`verfügt.

Im folgenden Beispiel wird C1022 generiert:

```
// C1022.cpp
#define true 1

#if (true)
#else
#else    // C1022
```

Mögliche Lösung:

```
// C1022b.cpp
// compile with: /c
#define true 1

#if (true)
#else
#endif
```