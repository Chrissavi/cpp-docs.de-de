---
title: 'Bitweise inklusive OR-Operator: || Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/14/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bitor
- '|'
dev_langs:
- C++
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bda159ed4111bffe935d5ceb6824662159553ddc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032015"
---
# <a name="bitwise-inclusive-or-operator-"></a>Bitweise inklusive OR-Operator: |

## <a name="syntax"></a>Syntax

> *expression1* **|** *expression2*

## <a name="remarks"></a>Hinweise

Der bitweise inklusive OR-Operator (**&#124;**) vergleicht jedes Bit seines ersten Operanden mit dem entsprechenden Bit seines zweiten Operanden. Wenn jedes Bit 1 ist, wird das entsprechende Ergebnisbit auf 1 festgelegt. Andernfalls wird das entsprechende Ergebnisbit auf 0 (null) festgelegt.

Beide Operanden im bitweisen inklusiven OR-Operator müssen vom Ganzzahltyp sein. Die üblichen arithmetischen Konvertierungen finden Sie im [Standardkonvertierungen](standard-conversions.md) auf die Operanden angewendet werden.

## <a name="operator-keyword-for-124"></a>Operator-Schlüsselwort für&#124;

Die **Bitor** -Operator ist die ausgeschriebene Variante von **&#124;**. Es gibt zwei Möglichkeiten, den Zugriff auf die **Bitor** -Operator in Programmen: Fügen Sie die Headerdatei \<iso646.h >, oder Kompilieren Sie mit der [/Za](../build/reference/za-ze-disable-language-extensions.md) -Compileroption (spracherweiterungen deaktivieren).

## <a name="example"></a>Beispiel

```cpp
// expre_Bitwise_Inclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise inclusive OR
#include <iostream>
using namespace std;

int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...
}
```

## <a name="see-also"></a>Siehe auch

[C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C-Operatoren zur Bitmanipulation](../c-language/c-bitwise-operators.md)