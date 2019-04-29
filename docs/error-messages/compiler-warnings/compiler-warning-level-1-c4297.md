---
title: Compilerwarnung (Stufe 1) C4297
ms.date: 11/04/2016
f1_keywords:
- C4297
helpviewer_keywords:
- C4297
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
ms.openlocfilehash: 07dd6c65498ddd0d377ec3e0fbc7b44e52bec96b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408627"
---
# <a name="compiler-warning-level-1-c4297"></a>Compilerwarnung (Stufe 1) C4297

„Funktion“: Die Funktion löst eine unerwartete Ausnahme aus

Eine Funktionsdeklaration enthält einen (möglicherweise impliziten) `noexcept` Bezeichner, einen leeren `throw` -ausnahmebezeichner oder ein [__declspec(nothrow)](../../cpp/nothrow-cpp.md) -Attribut, und die Definition enthält ein oder mehrere [auslösen ](../../cpp/try-throw-and-catch-statements-cpp.md) Anweisungen. Um C4297 zu beheben, versuchen Sie nicht, Ausnahmen in Funktionen auszulösen, die als `__declspec(nothrow)`, `noexcept(true)` oder `throw()` deklariert sind. Alternativ können Sie die `noexcept`-, `throw()`- oder `__declspec(nothrow)`-Spezifikation entfernen.

Standardmäßig generiert der Compiler implizite `noexcept(true)`-Bezeichner für benutzerdefinierte Destruktoren und Deallocator-Funktionen und vom Compiler generierte spezielle Memberfunktionen. Dies entspricht dem ISO-Standard C++11. Um zu verhindern, dass Generierung impliziter Noexcept-Bezeichner und den Compiler an, das nicht standardmäßige Verhalten von Visual Studio 2013 wiederherstellen, verwenden Sie die **/Zc:implicitNoexcept-** -Compileroption. Weitere Informationen finden Sie unter [/Zc: implicitnoexcept (implizite Ausnahmespezifizierer)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md).

Weitere Informationen zu Ausnahmespezifikationen finden Sie unter [Ausnahmespezifikationen (Throw)](../../cpp/exception-specifications-throw-cpp.md). Siehe auch [/EH (Ausnahmebehandlungsmodell)](../../build/reference/eh-exception-handling-model.md) Informationen zum Standardverhalten der Ausnahmebehandlung zum Zeitpunkt der Kompilierung zu ändern.

Diese Warnung wird auch generiert, klicken Sie für __declspec ([Dllexport](../../cpp/dllexport-dllimport.md)) Funktionen "extern"C"," markiert, auch wenn sie C++ Funktionen.

Im folgenden Beispiel wird C4297 generiert:

```
// C4297.cpp
// compile with: /W1 /LD
void __declspec(nothrow) f1()   // declared nothrow
// try the following line instead
// void f1()
{
   throw 1;   // C4297
}
```