---
title: Compilerfehler C3609
ms.date: 11/04/2016
f1_keywords:
- C3609
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
ms.openlocfilehash: 27eba3df800c42cc53a7031e958a675c84255440
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778357"
---
# <a name="compiler-error-c3609"></a>Compilerfehler C3609

„Member“: Eine versiegelte oder endgültige Funktion muss virtuell sein.

Die [versiegelten](../../extensions/sealed-cpp-component-extensions.md) und [endgültige](../../cpp/final-specifier.md) Schlüsselwörter dürfen nur auf eine Klasse, Struktur oder Memberfunktion Funktion `virtual`.

Im folgenden Beispiel wird C3609 generiert:

```
// C3609.cpp
// compile with: /clr /c
ref class C {
   int f() sealed;   // C3609
   virtual int f2() sealed;   // OK
};
```
