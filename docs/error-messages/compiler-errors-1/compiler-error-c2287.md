---
title: Compilerfehler C2287
ms.date: 11/04/2016
f1_keywords:
- C2287
helpviewer_keywords:
- C2287
ms.assetid: 64556299-4e1f-4437-88b7-2464fc0b95bb
ms.openlocfilehash: f5493220c4380d1fd67b38995414f48a2ef72a41
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514022"
---
# <a name="compiler-error-c2287"></a>Compilerfehler C2287

'Klasse': vererbungsdarstellung: 'Darstellung1' ist einfacher als die erforderliche 'Darstellung2'

Eine Klasse wird mit einer einfacheren Darstellung als deklariert.

Im folgende Beispiel wird die C2287 generiert:

```
// C2287.cpp
// compile with: /vmg /c
class __single_inheritance X;
class __single_inheritance Y;

struct A { };
struct B { };
struct X : A, B { };  // C2287  X uses multiple inheritance
struct Y : A { };  // OK
```