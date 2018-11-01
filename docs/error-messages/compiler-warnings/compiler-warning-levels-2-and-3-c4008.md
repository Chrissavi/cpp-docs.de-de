---
title: Compilerwarnung (Stufen 2 und 3) C4008
ms.date: 11/04/2016
f1_keywords:
- C4008
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
ms.openlocfilehash: 99b78e1426cf1618e68ae74ae7e16dd0f08606ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604086"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Compilerwarnung (Stufen 2 und 3) C4008

'Bezeichner': 'Attribut'-Attribut wird ignoriert

Der Compiler ignoriert die Attribute `__fastcall`, **static**oder **inline** für eine Funktion (Warnstufe 3) oder für Daten (Warnstufe 2).

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. `__fastcall` -Attribute werden mit Daten.

1. Attribute**static** oder **inline** mit **main** -Funktion.