---
title: Compilerwarnung (Stufe 1) C4091
ms.date: 11/04/2016
f1_keywords:
- C4091
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
ms.openlocfilehash: ce6dd980ef70f129a0dbae474b8f717f7573f861
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626753"
---
# <a name="compiler-warning-level-1-c4091"></a>Compilerwarnung (Stufe 1) C4091

' Schlüsselwort ': wird auf der linken Seite von ' type ' ignoriert, wenn keine Variable deklariert ist

Der Compiler hat eine Situation erkannt, in der der Benutzer wahrscheinlich eine Variable deklarieren wollte, aber der Compiler konnte die Variable nicht deklarieren.

## <a name="example"></a>Beispiel

Ein `__declspec` Attribut am Anfang einer benutzerdefinierten Typdeklaration gilt für die Variable dieses Typs. C4091 gibt an, dass keine Variable deklariert wird. Im folgenden Beispiel wird C4091 generiert.

```cpp
// C4091.cpp
// compile with: /W1 /c
__declspec(dllimport) class X {}; // C4091

// __declspec attribute applies to varX
__declspec(dllimport) class X2 {} varX;

// __declspec attribute after the class or struct keyword
// applies to user defined type
class __declspec(dllimport) X3 {};
```

## <a name="example"></a>Beispiel

Wenn ein Bezeichner eine typedef ist, kann er nicht auch ein Variablenname sein. Im folgenden Beispiel wird C4091 generiert.

```cpp
// C4091_b.cpp
// compile with: /c /W1 /WX
#define LIST 4
typedef struct _LIST {} LIST;   // C4091
```