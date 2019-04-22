---
title: Compilerfehler C3868
ms.date: 11/04/2016
f1_keywords:
- C3868
helpviewer_keywords:
- C3868
ms.assetid: f0e45c2a-2149-4885-a03b-0d230069f03a
ms.openlocfilehash: 3d759d8e527bf38c7408f3497b27287e030d387e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776785"
---
# <a name="compiler-error-c3868"></a>Compilerfehler C3868

"Type": Einschränkungen für den generischen Parameter 'Parameter' unterscheiden sich von denen die Deklaration

Mehrere Deklarationen müssen dieselben generischen Einschränkungen verfügen.  Weitere Informationen finden Sie unter [Generics](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3868 generiert.

```
// C3868.cpp
// compile with: /clr /c
interface struct I1;

generic <typename T> ref struct MyStruct;
generic <typename U> where U : I1 ref struct MyStruct;   // C3868

// OK
generic <typename T> ref struct MyStruct2;
generic <typename U> ref struct MyStruct2;

generic <typename T> where T : I1 ref struct MyStruct3;
generic <typename U> where U : I1 ref struct MyStruct3;
```