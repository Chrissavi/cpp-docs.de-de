---
title: Compilerfehler C2296
ms.date: 11/04/2016
f1_keywords:
- C2296
helpviewer_keywords:
- C2296
ms.assetid: 47d270f4-13ce-4c16-81e2-7d67c6c4a540
ms.openlocfilehash: ab9c9450b6e906a47a66f6c28c42ca016c98381b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182677"
---
# <a name="compiler-error-c2296"></a>Compilerfehler C2296

'Operator': Ungültiger Linker Operand

Der linke Operand für `operator` ist ungültig.

Beispielsweise kann der Compiler eine Deklaration finden Sie unter, wenn Sie einen Funktionsaufruf bestimmt.

Im folgende Beispiel wird die C2296 generiert:

```
// C2296.cpp
struct MyStruct {
   struct Help {
      Help(float f) : m_f(f) {}
      float m_f;
   };

   MyStruct(const Help &h) : m_f(h.m_f) {}
   MyStruct(float f) : m_f(f) {}
   MyStruct operator*(const MyStruct &f1) const {
      return MyStruct(m_f * f1.m_f);
   }

private:
   float m_f;
};

int main() {
   float f1 = 1.0f;

   MyStruct m_MyStruct1 ( MyStruct::Help( f1 ) );
   // try the following line instead
   // MyStruct m_MyStruct1 = MyStruct::Help( f1 );

   MyStruct m_MyStruct2 ( MyStruct::Help( f1 ) );
   // try the following line instead
   // MyStruct m_MyStruct2 = MyStruct::Help( f1 );

   MyStruct m_MyStruct3 = m_MyStruct1 * m_MyStruct2;   // C2296
}
```