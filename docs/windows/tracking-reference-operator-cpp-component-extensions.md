---
title: Nachverfolgungsverweisoperator (C++ / CLI und C++ / CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- '%'
helpviewer_keywords:
- tracking references
- '% tracking reference [C++]'
ms.assetid: 142a7269-ab69-4b54-a6d7-833bef06228f
ms.openlocfilehash: c6fef4562545b03e212d0e4e58742a1209a6ab81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437962"
---
# <a name="tracking-reference-operator-ccli-and-ccx"></a>Nachverfolgungsverweisoperator (C++ / CLI und C++ / CX)

Ein *Nachverfolgungsverweis* (`%`) verhält sich wie ein normaler C++-Verweis (`&`) mit dem Unterschied, dass wenn ein Objekt zu einem Nachverfolgungsverweis zugewiesen wird, wird die verweiszählung des Objekts erhöht.

## <a name="all-platforms"></a>Alle Plattformen

Ein Nachverfolgungsverweis verfügt über die folgenden Eigenschaften.

- Die Zuweisung eines Objekts zu einem Nachverfolgungsverweis bewirkt, dass der Verweiszähler des Objekts erhöht wird.

- Eines systemeigenen Verweises (`&`) ist das Ergebnis, wenn Sie dereferenzieren einer `*`. Ein Nachverfolgungsverweis (`%`) ist das Ergebnis, wenn Sie dereferenzieren einer `^`. Solange Sie haben eine `%` auf ein Objekt, das Objekt im Speicher aktiv zu bleiben.

- Der Punktzugriffsoperator (`.`) für Member wird verwendet, um auf einen Member des Objekts zuzugreifen.

- Nachverfolgungsverweise gelten für Werttypen und Handles (beispielsweise `String^`).

- Ein Nachverfolgungsverweis kann ein NULL-Wert nicht zugewiesen werden oder **"nullptr"** Wert. Ein Nachverfolgungsverweis kann einem anderen gültigen Objekt so oft wie erforderlich neu zugewiesen werden.

- Ein Nachverfolgungsverweis kann nicht als unärer Adressenübernahmeoperator (Take-Address-Operator) verwendet werden.

## <a name="windows-runtime"></a>Windows-Runtime

Ein Nachverfolgungsverweis verhält sich wie ein Standard-C++-Verweis, und zwar mit Ausnahme, dass ein % per Referenzzählung behandelt wird. Der folgende Ausschnitt zeigt die Konvertierung zwischen %- und ^-Typen:

```cpp
Foo^ spFoo = ref new Foo();
Foo% srFoo = *spFoo;
Foo^ spFoo2 = %srFoo;
```

Im folgenden Beispiel wird das Übergeben einer ^-Funktion gezeigt, die ein % aufweist.

```cpp
ref class Foo sealed {};

    // internal or private
    void UseFooHelper(Foo% f)
    {
        auto x = %f;
    }

    // public method on ABI boundary
    void UseFoo(Foo^ f)
    {
        if (f != nullptr) { UseFooHelper(*f); }
    }
```

## <a name="common-language-runtime"></a>Common Language Runtime

Sie können in C++/CLI einen Nachverfolgungsverweis auf ein Handle verwenden, um eine Bindung zu einem Objekt eines CLR-Typs auf dem Heap der Garbage Collection herzustellen.

In der CLR wird der Wert einer Nachverfolgungsverweisvariablen automatisch aktualisiert, wenn der Garbage Collector das referenzierte Objekt verschiebt.

Ein Nachverfolgungsverweis kann nur auf dem Stapel deklariert werden. Ein Nachverfolgungsverweis kann kein Klassenmember sein.

Die Verwendung eines systemeigenen C++-Verweises auf ein Objekt auf dem Heap der Garbage Collection ist nicht möglich.

Weitere Informationen über Nachverfolgungsverweise in C++/CLI finden Sie unter:

- [Vorgehensweise: Verwenden von Nachverfolgungsverweisen in C++/CLI](../dotnet/how-to-use-tracking-references-in-cpp-cli.md)

### <a name="examples"></a>Beispiele

Das folgende Beispiel für C++/CLI veranschaulicht, wie ein Nachverfolgungsverweis mit systemeigenen und verwalteten Typen verwendet wird.

```cpp
// tracking_reference_1.cpp
// compile with: /clr
ref class MyClass {
public:
   int i;
};

value struct MyStruct {
   int k;
};

int main() {
   MyClass ^ x = ref new MyClass;
   MyClass ^% y = x;   // tracking reference handle to reference object

   int %ti = x->i;   // tracking reference to member of reference type

   int j = 0;
   int %tj = j;   // tracking reference to object on the stack

   int * pi = new int[2];
   int % ti2 = pi[0];   // tracking reference to object on native heap

   int *% tpi = pi;   // tracking reference to native pointer

   MyStruct ^ x2 = ref new MyStruct;
   MyStruct ^% y2 = x2;   // tracking reference to value object

   MyStruct z;
   int %tk = z.k;   // tracking reference to member of value type

   delete[] pi;
}
```

Das folgende Beispiel für C++/CLI veranschaulicht, wie ein Nachverfolgungsverweis an ein Array gebunden wird.

```cpp
// tracking_reference_2.cpp
// compile with: /clr
using namespace System;

int main() {
   array<int> ^ a = ref new array<Int32>(5);
   a[0] = 21;
   Console::WriteLine(a[0]);
   array<int> ^% arr = a;
   arr[0] = 222;
   Console::WriteLine(a[0]);
}
```

```Output
21
222
```