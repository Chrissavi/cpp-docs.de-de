---
title: Typen- und Variablengrößen in der Inlineassembly
ms.date: 08/30/2018
ms.topic: reference
helpviewer_keywords:
- variables, length
- size, getting in inline assembly
- size
- LENGTH operator
- TYPE operator
- SIZE operator
- inline assembly, operators
- variables, type
- variables, size
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
ms.openlocfilehash: 3e244aaa8ea849b558b77c3f1569820079f6f76c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87191611"
---
# <a name="type-and-variable-sizes-in-inline-assembly"></a>Typen- und Variablengrößen in der Inlineassembly

**Microsoft-spezifisch**

Die Operatoren **Länge**, **Größe**und **Typ** weisen in der Inlineassembly eine begrenzte Bedeutung auf. Sie können nicht mit dem-Operator verwendet werden `DUP` (da Sie keine Daten mit MASM-Direktiven oder-Operatoren definieren können). Sie können Sie jedoch verwenden, um die Größe von C-oder C++-Variablen oder-Typen zu ermitteln:

- Der **length** -Operator kann die Anzahl der Elemente in einem Array zurückgeben. Der Wert 1 wird für nicht-Array Variablen zurückgegeben.

- Der **size** -Operator kann die Größe einer C-oder C++-Variablen zurückgeben. Die Größe einer Variablen ist das Produkt der **Länge** und des **Typs**.

- Der **typoperator** kann die Größe eines C-oder C++-Typs oder einer Variablen zurückgeben. Wenn die Variable ein Array ist, gibt **Type** die Größe eines einzelnen Elements des Arrays zurück.

Wenn das Programm z. b. über ein 8-Element- **`int`** Array verfügt,

```cpp
int arr[8];
```

die folgenden C-und assemblyausdrücke ergeben die Größe von und den zugehörigen `arr` Elementen.

|__asm|C|Size|
|-------------|-------|----------|
|**Länge** Arr|`sizeof(arr)/sizeof(arr[0])`|8|
|**Größe** Arr|`sizeof(arr)`|32|
|**Typ** Arr|`sizeof(arr[0])`|4|

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden der Assemblysprache in __asm Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
