---
title: Compilerfehler C2433 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2433
dev_langs:
- C++
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 081e63c83909319164a2903d8277a0b26a1e6901
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059952"
---
# <a name="compiler-error-c2433"></a>Compilerfehler C2433

'Bezeichner': 'Modifizierer' Deklaration von Daten nicht zulässig.

Die `friend`, `virtual`, und `inline` Modifizierer können nicht für Datendeklarationen verwendet werden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2433 generiert.

```
// C2433.cpp
class C{};

int main() {
   inline C c;   // C2433
}
```