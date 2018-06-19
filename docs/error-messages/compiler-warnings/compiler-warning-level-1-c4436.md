---
title: Compilerwarnung (Stufe 1) C4436 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1da06a329a9c0bdfcff6877ce69c8e3672619bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281641"
---
# <a name="compiler-warning-level-1-c4436"></a>Compilerwarnung (Stufe 1) C4436
Dynamic_cast von virtueller Basis 'class1' zu 'class2' im Konstruktor oder Destruktor konnte mit teilweise konstruiert Objekt Kompilieren mit/vd2 fehlschlagen oder "Klasse2" mit der #pragma-vtordisp(2) faktisch definieren  
  
 Der Compiler hat eine `dynamic_cast` Operation mit den folgenden Merkmalen.  
  
-   Die Umwandlung ist von einem Zeiger Basisklasse in einer abgeleiteten Klasse Zeiger.  
  
-   Die abgeleitete Klasse erbt praktisch die Basisklasse.  
  
-   Die abgeleitete Klasse verfügt nicht über eine `vtordisp` Feld für die virtuelle Basisklasse.  
  
-   Die Umwandlung in einen Konstruktor oder Destruktor der abgeleiteten Klasse befindet, oder was Klasse erbt von der abgeleiteten Klasse.  
  
 Die Warnung gibt an, die `dynamic_cast` möglicherweise nicht ordnungsgemäß ausgeführt werden, wenn sie für eine teilweise konstruiert Objekt ausgeführt wird.  Die geschieht, wenn der abgeleitete Konstruktor/Destruktor auf ein Unterobjekt vom einige weitere abgeleitete Objekt ausgeführt wird.  Wenn die abgeleitete Klasse mit dem Namen in der Warnung keine weiteren abgeleitet ist, kann die Warnung ignoriert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4436 generiert und veranschaulicht, das Code-Generation-Problem, das aus den fehlenden `vtordisp` Feld.  
  
```cpp  
// C4436.cpp  
// To see the warning and runtime assert, compile with: /W1  
// To eliminate the warning and assert, compile with: /W1 /vd2  
//       or compile with: /W1 /DFIX  
#include <cassert>  
  
struct A  
{  
public:  
    virtual ~A() {}  
};  
  
#if defined(FIX)  
#pragma vtordisp(push, 2)  
#endif  
struct B : virtual A  
{  
    B()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4436  
        assert(this == b);              // assert unless compiled with /vd2  
    }  
};  
#if defined(FIX)  
#pragma vtordisp(pop)  
#endif  
  
struct C : B  
{  
    int i;  
};  
  
int main()  
{  
    C c;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Dynamic_cast-Operator](../../cpp/dynamic-cast-operator.md)   
 [vtordisp](../../preprocessor/vtordisp.md)   
 [Compilerwarnung (Ebene 4) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)