---
title: Compilerfehler C3117 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3117
dev_langs:
- C++
helpviewer_keywords:
- C3117
ms.assetid: dceee392-d4c7-4599-b75e-7aaac7c36fdd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fde62b5495afa4a8a0b76502cac78117fe0575fc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090411"
---
# <a name="compiler-error-c3117"></a>Compilerfehler C3117

"%$S": eine Schnittstelle kann nur eine Basisklasse besitzen

Sie haben deklariert eine Schnittstelle, die von mehreren Basisklassen erben.

Im folgende Beispiel wird die C3117 generiert:

```
// C3117.cpp
#include <windows.h>

[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface I1
{
};

[ object, uuid("00000000-0000-0000-0000-000000000002") ]
__interface I2
{
};

[ object, uuid("00000000-0000-0000-0000-000000000003") ]
__interface I3 : I1, I2
{   // C3117
};
```