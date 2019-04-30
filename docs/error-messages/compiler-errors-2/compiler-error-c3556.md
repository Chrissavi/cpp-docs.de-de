---
title: Compilerfehler C3556
ms.date: 11/04/2016
f1_keywords:
- C3556
helpviewer_keywords:
- C3556
ms.assetid: 9b002dcc-494e-414f-9587-20c2a0a39333
ms.openlocfilehash: 7b87f8c57b0d871a577793936ea3cb7dbab7e58d
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344541"
---
# <a name="compiler-error-c3556"></a>Compilerfehler C3556

> "*Ausdruck*": falsches Argument für "Decltype"

Der Compiler kann den Typ des Ausdrucks, der das Argument für den `decltype(`*expression*`)` -Typspezifizierer ist, nicht ableiten.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel kann der Compiler den Typ des `myFunction` -Arguments nicht ableiten, weil `myFunction` überladen ist. Um dieses Problem zu beheben, können Sie `static_cast` zum Erstellen einer Instanz eines Zeigers auf den jeweiligen überladene Funktion geben Sie in der `decltype` Ausdruck.

```cpp
// C3556.cpp
// compile with: cl /W4 /EHsc C3556.cpp
#include <iostream>

void myFunction(int);
void myFunction(float, float);

void callsMyFunction(decltype(myFunction) fn); // C3556
// One way to fix is to comment out the line above, and
// use static_cast to create specialized function pointer
// instances:
auto myFunctionInt = static_cast<void(*)(int)>(myFunction);
auto myFunctionFloatFloat = static_cast<void(*)(float,float)>(myFunction);
void callsMyFunction(decltype(myFunctionInt) fn, int n);
void callsMyFunction(decltype(myFunctionFloatFloat) fn, float f, float g);

void myFunction(int i) {
    std::cout << "called myFunction(" << i << ")" << std::endl;
}

void myFunction(float f, float g) {
    std::cout << "called myFunction(" << f << ", " << g << ")" << std::endl;
}

void callsMyFunction(decltype(myFunctionInt) fn, int n) {
    fn(n);
}

void callsMyFunction(decltype(myFunctionFloatFloat) fn, float f, float g) {
    fn(f, g);
}

int main() {
    callsMyFunction(myFunction, 42);
    callsMyFunction(myFunction, 0.1f, 2.3f);
}
```