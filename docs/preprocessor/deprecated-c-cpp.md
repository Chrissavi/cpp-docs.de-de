---
title: deprecated-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.deprecated
- deprecated_CPP
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
ms.openlocfilehash: 2e76d1c53cb900c108e2839a9aad17b330143a5d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222405"
---
# <a name="deprecated-pragma"></a>deprecated-Pragma

Mit dem **veraltet** -Pragma können Sie angeben, dass eine Funktion, ein Typ oder ein anderer Bezeichner in einem zukünftigen Release möglicherweise nicht mehr unterstützt wird oder nicht mehr verwendet werden soll.

> [!NOTE]
> Weitere `[[deprecated]]` Informationen zum c++ 14-Attribut und Anleitungen dazu, wann dieses Attribut anstelle des Microsoft `__declspec(deprecated)` -Modifizierers oder des **veralteten** Pragmas verwendet werden sollte, finden Sie unter [Attribute in C++ ](../cpp/attributes.md).

## <a name="syntax"></a>Syntax

> **#pragma veraltet (** *Bezeichner1* [ **,** *Bezeichner2* ...] **)**

## <a name="remarks"></a>Hinweise

Wenn der Compiler auf einen Bezeichner stößt, der durch ein veralteter Pragma festgelegt ist, wird die Compilerwarnung [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)ausgegeben.

Sie können Makronamen als veraltet deklarieren. Platzieren Sie den Makronamen in Anführungszeichen; andernfalls tritt eine Makroerweiterung auf.

Da das **veraltet** -Pragma für alle übereinstimmenden Bezeichner funktioniert und keine Signaturen berücksichtigt, ist es nicht die beste Option, um bestimmte Versionen von überladenen Funktionen als veraltet zu kennzeichnen. Alle übereinstimmenden Funktionsnamen, die in den Bereich eingefügt werden, lösen die Warnung aus.

Es wird empfohlen, anstelle des `[[deprecated]]` **veralteten** Pragmas das c++ 14-Attribut zu verwenden, sofern möglich. Der Microsoft-spezifische __declspec-deklarationsmodifizierer [(veraltet)](../cpp/deprecated-cpp.md) ist in vielen Fällen besser als das **Veraltete** Pragma. Mit `[[deprecated]]` dem- `__declspec(deprecated)` Attribut und dem-Modifizierer können Sie den veralteten Status für bestimmte Formen überladener Funktionen angeben. Die Diagnose Warnung wird nur bei verweisen auf die spezifische überladene Funktion angezeigt, auf die das Attribut oder der Modifizierer angewendet wird.

## <a name="example"></a>Beispiel

```cpp
// pragma_directive_deprecated.cpp
// compile with: /W3
#include <stdio.h>
void func1(void) {
}

void func2(void) {
}

int main() {
   func1();
   func2();
   #pragma deprecated(func1, func2)
   func1();   // C4995
   func2();   // C4995
}
```

Das folgende Beispiel zeigt, wie Sie eine Klasse als veraltet deklarieren:

```cpp
// pragma_directive_deprecated2.cpp
// compile with: /W3
#pragma deprecated(X)
class X {  // C4995
public:
   void f(){}
};

int main() {
   X x;   // C4995
}
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)