---
title: Compilerfehler C3126
ms.date: 11/04/2016
f1_keywords:
- C3126
helpviewer_keywords:
- C3126
ms.assetid: e72658a3-5d85-4a31-89a4-dbc3d475973d
ms.openlocfilehash: 2b8901ce9914f35d4cd219f4d51477582fa676a8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760724"
---
# <a name="compiler-error-c3126"></a>Compilerfehler C3126

eine Union ' Union ' kann nicht innerhalb des verwalteten Typs ' type ' definiert werden.

Eine Union kann nicht innerhalb eines verwalteten Typs definiert werden.

Im folgenden Beispiel wird C3126 generiert:

```cpp
// C3126_2.cpp
// compile with: /clr /c
ref class Test
{
   union x
   {   // C3126
      int a;
      int b;
   };
};
```
