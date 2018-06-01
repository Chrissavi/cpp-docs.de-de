---
title: 'Vorgehensweise: Migrieren zu - Clr: safe (C + c++ / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- migration [C++], verifiable assemblies
- upgrading Visual C++ applications, verifiable assemblies
- verifiable assemblies [C++], migrating to
- /clr compiler option [C++], migrating to /clr:safe
ms.assetid: 75f9aae9-1dcc-448a-aa11-2d96f972f9d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d72be19eb893a74a17a988e8c14c6bdaba766cbc
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704513"
---
# <a name="how-to-migrate-to-clrsafe-ccli"></a>Gewusst wie: Migrieren auf /clr:safe (C++/CLI)

> [!IMPORTANT]
> Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden. Wenn Sie sichere CLR-Assemblys benötigen, empfehlen wir die Portieren von Code in c#.

Wenn Sie eine frühere Version von Visual C++-Compilertoolset aus vor Visual Studio 2017 verwenden, können Sie überprüfbare Komponenten generieren, mit **/CLR: safe**, die bewirkt, dass der Compiler generiert Fehler für jedes nicht überprüfbar Codekonstrukt.

## <a name="remarks"></a>Hinweise

Die folgenden Probleme generieren Überprüfbarkeitsfehler:

- Systemeigene Typen. Auch wenn es nicht verwendet wird, wird die Deklaration von systemeigenen Klassen, Strukturen, Zeiger oder Arrays Kompilierung verhindern.

- Globale Variablen

- Funktionsaufrufe in eine nicht verwaltete Bibliothek, einschließlich der common Language Runtime-Funktionsaufrufe

- Eine überprüfbare Funktion darf keine enthalten eine [Static_cast Operator](../cpp/static-cast-operator.md) für Down-Umwandlung. Die [Static_cast Operator](../cpp/static-cast-operator.md) kann verwendet werden, für die Umwandlung zwischen den primitiven Typen gehört, aber für Down-Umwandlung, ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md) oder eine Umwandlung im C-Format (die als implementiert eine ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md)) muss verwendet werden.

- Eine überprüfbare Funktion darf keine enthalten eine [Reinterpret_cast Operator](../cpp/reinterpret-cast-operator.md) (oder eine entsprechende Umwandlung im C-Format).

- Eine überprüfbare Funktion kann keine Arithmetik mit einem [Interior_ptr (C + c++ / CLI)](../windows/interior-ptr-cpp-cli.md). Es kann nur zuweisen und es zu dereferenzieren.

- Eine überprüfbare Funktion kann nur ausgelöst oder Zeiger auf Verweistypen abfangen, damit vor dem Auslösen Werttypen geschachtelt werden müssen.

- Eine überprüfbare Funktion kann nur überprüfbare Funktionen aufrufen (sodass Aufrufe an die common Language Runtime nicht zulässig sind, enthalten `AtEntry` / `AtExit`, weshalb globale Konstruktoren nicht zulässig sind).

- Eine überprüfbare Klasse können keine <xref:System.Runtime.InteropServices.LayoutKind>.

- Wenn eine EXE-Datei zu erstellen, eine main-Funktion keine Parameter deklariert werden, also <xref:System.Environment.GetCommandLineArgs%2A> muss verwendet werden, um Befehlszeilenargumente abzurufen.

- Eine nicht virtuelle Aufruf einer virtuellen Funktion. Zum Beispiel:

   ```cpp
   // not_verifiable.cpp
   // compile with: /clr
   ref struct A {
      virtual void Test() {}
   };

   ref struct B : A {};

   int main() {
      B^ b1 = gcnew B;
      b1->A::Test();   // Non-virtual call to virtual function
   }
   ```

Darüber hinaus können die folgenden Schlüsselwörter in überprüfbarem Code verwendet werden:

- [nicht verwaltete](../preprocessor/managed-unmanaged.md) und [Pack](../preprocessor/pack.md) Pragmas

- [naked](../cpp/naked-cpp.md) und [ausrichten](../cpp/align-cpp.md) [__declspec](../cpp/declspec.md) Modifizierer

- [__asm](../assembler/inline/asm.md)

- [__based](../cpp/based-grammar.md)

- [__try](../cpp/try-except-statement.md) und `__except`

## <a name="see-also"></a>Siehe auch

- [Reiner und überprüfbarer Code (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)
