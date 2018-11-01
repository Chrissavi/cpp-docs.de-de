---
title: 'Gewusst wie: Anheften von Zeigern und Arrays'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- pointers, pinning
- arrays [C++], pinning
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
ms.openlocfilehash: 54897253b93c97eb2d1ef94b6922c99fb75fdae9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641858"
---
# <a name="how-to-pin-pointers-and-arrays"></a>Gewusst wie: Anheften von Zeigern und Arrays

Anheften von einem untergeordneten Objekt in ein verwaltetes Objekt definiert, hat die Auswirkung der Verknüpfung mit dem das gesamte Objekt.  Z. B. wenn jedes Element eines Arrays verknüpft ist, ist Klicken Sie dann das gesamte Array auch fixiert. Es gibt keine Erweiterungen für die Sprache für eine angeheftete Array zu deklarieren. Um ein Array anzuheften, deklarieren Sie einen festen Zeiger, dessen Elementtyp und der Pin eines seiner Elemente.

## <a name="example"></a>Beispiel

### <a name="code"></a>Code

```cpp
// pin_ptr_array.cpp
// compile with: /clr
#include <stdio.h>
using namespace System;

int main() {
   array<Byte>^ arr = gcnew array<Byte>(4);
   arr[0] = 'C';
   arr[1] = '+';
   arr[2] = '+';
   arr[3] = '\0';
   pin_ptr<Byte> p = &arr[1];   // entire array is now pinned
   unsigned char * cp = p;

   printf_s("%s\n", cp); // bytes pointed at by cp
                         // will not move during call
}
```

```Output
++
```

## <a name="see-also"></a>Siehe auch

[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)