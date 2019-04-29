---
title: Compilerfehler C3831
ms.date: 11/04/2016
f1_keywords:
- C3831
helpviewer_keywords:
- C3831
ms.assetid: a125d8dc-b75a-4ea0-b6c7-fe7b119dba25
ms.openlocfilehash: d9aa703f12fd175d9f7fc00eb76e76097a32e860
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390554"
---
# <a name="compiler-error-c3831"></a>Compilerfehler C3831

'Member': 'Class' sind keine keinen festen Datenmember oder eine Memberfunktion, die einen festen Zeiger zurückgibt

[Pin_ptr (C++/CLI)](../../extensions/pin-ptr-cpp-cli.md) wurde falsch verwendet.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3831 generiert:

```
// C3831a.cpp
// compile with: /clr
ref class Y
{
public:
   int i;
};

ref class X
{
   pin_ptr<int> mbr_Y;   // C3831
   int^ mbr_Y2;   // OK
};

int main() {
   Y y;
   pin_ptr<int> p = &y.i;
}
```
