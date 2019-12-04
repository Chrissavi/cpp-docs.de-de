---
title: Compilerfehler C3537
ms.date: 11/04/2016
f1_keywords:
- C3537
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
ms.openlocfilehash: ef3e954987b84ea128342b38307769903df4b346
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740480"
---
# <a name="compiler-error-c3537"></a>Compilerfehler C3537

"Typ": Sie können nicht in einen Typ umwandeln, der "Auto" enthält.

Sie können eine Variable nicht in den entsprechenden Typ umwandeln, da der Typ das `auto`-Schlüsselwort enthält und die standardmäßige [/Zc: Auto](../../build/reference/zc-auto-deduce-variable-type.md) -Compileroption aktiviert ist.

## <a name="example"></a>Beispiel

Der folgende Code ergibt C3537, da die Variablen in einen Typ umgewandelt werden, der das `auto`-Schlüsselwort enthält.

```cpp
// C3537.cpp
// Compile with /Zc:auto
int main()
{
   int value = 123;
   auto(value);                        // C3537
   (auto)value;                        // C3537
   auto x1 = auto(value);              // C3537
   auto x2 = (auto)value;              // C3537
   auto x3 = static_cast<auto>(value); // C3537
   return 0;
}
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)
