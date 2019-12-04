---
title: Compilerwarnung C4868
ms.date: 10/26/2017
f1_keywords:
- C4868
helpviewer_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
ms.openlocfilehash: c1d49eb61a5c7c47fa83dacb39ed50f42e0fb147
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810478"
---
# <a name="compiler-warning-level-4-c4868"></a>Compilerwarnung (Stufe 4) C4868

> der Compiler "_File_(*LINE_NUMBER*)" kann die Auswertungs Reihenfolge von links nach rechts in der Initialisiererliste der geschweizten Klammern nicht erzwingen.

Die Elemente einer Initialisiererliste mit geschweizten Klammern müssen in der Reihenfolge von links nach rechts ausgewertet werden. Es gibt zwei Fälle, in denen der Compiler diese Reihenfolge nicht garantieren kann: die erste ist, wenn einige der Elemente Objekte sind, die als Wert übermittelt werden. die zweite ist die Kompilierung mit `/clr` und einige Elemente sind Felder von Objekten oder sind Array Elemente. Wenn der Compiler die Auswertung von links nach rechts nicht garantieren kann, gibt er Warning C4868 aus.

Diese Warnung kann als Ergebnis einer compilerübereinstimmungs-Arbeit generiert werden, die für Visual Studio 2015 Update 2 ausgeführt wurde. Code, der vor Visual Studio 2015 Update 2 kompiliert wurde, kann nun C4868 generieren.

Diese Warnung ist standardmäßig deaktiviert. Verwenden Sie `/Wall`, um diese Warnung zu aktivieren.

Um diese Warnung zu beheben, sollten Sie zunächst überprüfen, ob die Initialisiererlisten-Elemente von links nach rechts ausgewertet werden, z. b. wenn die Auswertung der Elemente die Reihenfolge abhängiger Nebeneffekte erzeugen könnte. In vielen Fällen hat die Reihenfolge, in der Elemente ausgewertet werden, keinen wahrnehmbaren Effekt.

Wenn die Reihenfolge der Auswertung von links nach rechts erfolgen muss, sollten Sie überprüfen, ob es möglich ist, die Elemente stattdessen `const` Verweis zu übergeben. Eine Änderung, wie z. b. diese, beseitigt die Warnung im folgenden Codebeispiel.

## <a name="example"></a>Beispiel

Dieses Beispiel generiert C4868 und zeigt eine Möglichkeit, Sie zu beheben:

```cpp
// C4868.cpp
// compile with: /c /Wall
#include <cstdio>

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x): x(x) {}

    HasCopyConstructor(const HasCopyConstructor& h): x(h.x)
    {
        printf("Constructing %d\n", h.x);
    }
};

class TripWarning4868
{
public:
    // note that taking "HasCopyConstructor" parameters by-value will trigger copy-construction.
    TripWarning4868(HasCopyConstructor a, HasCopyConstructor b) {}

    // This variation will not trigger the warning:
    // TripWarning4868(const HasCopyConstructor& a, const HasCopyConstructor& b) {}
};

int main()
{
    HasCopyConstructor a{1};
    HasCopyConstructor b{2};

    // the warning will indicate the below line, the usage of the braced initializer list.
    TripWarning4868 warningOnThisLine{a, b};
};
```