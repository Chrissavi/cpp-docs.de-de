---
title: Compilerwarnung (Stufe 2) C4412 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4412
dev_langs:
- C++
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47659a9ba0469b8ee719dbc686ba611e876d32c1
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704012"
---
# <a name="compiler-warning-level-2-c4412"></a>Compilerwarnung (Stufe 2) C4412

> "*Funktion*': Funktionssignatur enthält Typ '*Typ*'; C++-Objekte sind nicht sicher zwischen reinem Code übergeben und gemischtem oder systemeigenem.

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** -Compileroption in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt wird. Wenn Sie über Code, die rein sein muss verfügen, wird empfohlen, dass Sie es in c# portieren.

Der Compiler hat eine potenziell unsichere Situation, die zu einem Laufzeitfehler führen konnte: erfolgt ein Aufruf von einer **/CLR: pure** Kompiliereinheit an eine Funktion, die über Dllimport und Funktionssignatur importiert wurde, enthält einen unsicheren Typ . Ein Typ ist unsicher, wenn er eine Memberfunktion enthält oder einen Datenmember, der einem unsicheren Typ oder eine Dereferenzierung zu einem unsicheren Typ ist.

Dies ist unsicher aufgrund der Unterschied in der Standard-Aufrufkonventionen zwischen reinem und systemeigenem Code (oder gemischten systemeigenen und verwalteten). Beim Importieren von (über `dllimport`) eine Funktion in einer **/CLR: pure** Kompiliereinheit, stellen Sie sicher, dass die Deklarationen der jeden Typ in der Signatur mit denjenigen in der Kompiliereinheit identisch, die die Funktion sind (Achten Sie besonders exportiert Unterschiede bei impliziten Aufrufkonventionen).

Eine virtuelle Memberfunktion ist besonders anfällig für unerwartete Ergebnisse zurückgibt.  Allerdings sollten auch eine nicht virtuelle Funktion, die getestet werden, um sicherzustellen, dass die richtigen Ergebnisse zu erhalten. Wenn Sie sicher sind, dass Sie die richtigen Ergebnisse ausgegeben werden, können Sie diese Warnung ignorieren.

C4412 ist standardmäßig deaktiviert. Finden Sie unter [Compiler deaktivierte Compilerwarnungen standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md) und [Dllexport, Dllimport](../../cpp/dllexport-dllimport.md) für Weitere Informationen.

Um diese Warnung zu beheben, entfernen Sie alle Funktionen aus dem Typ.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4412 generiert.

```cpp
// C4412.cpp
// compile with: /c /W2 /clr:pure
#pragma warning (default : 4412)

struct Unsafe {
   virtual void __cdecl Test();
};

struct Safe {
   int i;
};

__declspec(dllimport) Unsafe * __cdecl func();
__declspec(dllimport) Safe * __cdecl func2();

int main() {
   Unsafe *pUnsafe = func();   // C4412
   // pUnsafe->Test();

   Safe *pSafe = func2();   // OK
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird eine Headerdatei, die zwei Typen deklariert. Die `Unsafe` Typ ist unsicher, da sie eine Memberfunktion verfügt.

```cpp
// C4412.h
struct Unsafe {
   // will be __clrcall if #included in pure compilation
   // defaults to __cdecl in native or mixed mode compilation
   virtual void Test(int * pi);

   // try the following line instead
   // virtual void __cdecl Test(int * pi);
};

struct Safe {
   int i;
};
```

## <a name="example"></a>Beispiel

In diesem Beispiel werden Funktionen mit den in der Headerdatei definierten Typen exportiert.

```cpp
// C4412_2.cpp
// compile with: /LD
#include "C4412.h"

void Unsafe::Test(int * pi) {
   *pi++;
}

__declspec(dllexport) Unsafe * __cdecl func() { return new Unsafe; }
__declspec(dllexport) Safe * __cdecl func2() { return new Safe; }
```

## <a name="example"></a>Beispiel

Die Standardaufrufkonvention einer **/CLR: pure** Kompilierung unterscheidet sich von der systeminterne Kompilierung.  Wenn C4412.h eingeschlossen ist, wird `Test` standardmäßig `__clrcall`. Wenn Sie kompilieren und dieses Programms ausführen (verwenden Sie keine **/c**), das Programm wird eine Ausnahme ausgelöst.

Im folgenden Beispiel wird C4412 generiert.

```cpp
// C4412_3.cpp
// compile with: /W2 /clr:pure /c /link C4412_2.lib
#pragma warning (default : 4412)
#include "C4412.h"

__declspec(dllimport) Unsafe * __cdecl func();
__declspec(dllimport) Safe * __cdecl func2();

int main() {
   int n = 7;
   Unsafe *pUnsafe = func();   // C4412
   pUnsafe->Test(&n);

   Safe *pSafe = func2();   // OK
}
```