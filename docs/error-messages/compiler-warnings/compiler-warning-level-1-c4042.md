---
title: Compilerwarnung (Stufe 1) C4042
ms.date: 11/04/2016
f1_keywords:
- C4042
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
ms.openlocfilehash: 99f4f45aad82aa9898dad4cffb60b8e3311ddc9f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152138"
---
# <a name="compiler-warning-level-1-c4042"></a>Compilerwarnung (Stufe 1) C4042

'Bezeichner': besitzt unzulässige Speicherklasse

Die angegebene Speicher-Klasse kann nicht mit der folgenden ID in diesem Kontext nicht verwendet werden. Der Compiler verwendet die Speicherklasse standardmäßig stattdessen:

- `extern`, wenn *Bezeichner* ist eine Funktion.

- **automatische**, wenn *Bezeichner* ist eine formale Parameter oder lokale Variable.

- Klasse, wenn kein Speicher *Bezeichner* ist eine globale Variable.

Diese Warnung kann verursacht werden, außer mit einer Speicherklasse **registrieren** in einer Parameterdeklaration.

Das folgende Beispiel generiert C4042

```
// C4042.cpp
// compile with: /W1 /LD
int func2( __declspec( thread ) int tls_i )    // C4042
// try the following line instead
// int func2( int tls_i )
{
   return tls_i;
}
```