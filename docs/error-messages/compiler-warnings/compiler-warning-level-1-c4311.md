---
title: Compilerwarnung (Stufe 1) C4311
ms.date: 11/04/2016
f1_keywords:
- C4311
helpviewer_keywords:
- C4311
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
ms.openlocfilehash: bcb3650ca98922559f23c6c2536c3076cc522ad0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233274"
---
# <a name="compiler-warning-level-1-c4311"></a>Compilerwarnung (Stufe 1) C4311

'Variable': Zeigerverkürzung von 'Typ' zu 'Typ'

Diese Warnung erkennt Abschneidefehler bei 64-Bit-Zeigern. Wenn z. b. Code für eine 64-Bit-Architektur kompiliert wird, wird der Wert eines Zeigers (64 Bits) abgeschnitten, wenn er einem **`int`** (32 Bits) zugewiesen wird. Weitere Informationen finden Sie unter [Regeln für die Verwendung von Zeigern](/windows/win32/WinProg64/rules-for-using-pointers).

Weitere Informationen zu häufigen Gründen der Warnung C4311 finden Sie unter [Häufige Compilerfehler](/windows/win32/WinProg64/common-compiler-errors).

Im folgenden Codebeispiel wird C4311 beim Kompilieren für ein 64-Bit-Ziel generiert und dann veranschaulicht, wie Sie dieses Problem beheben können:

```cpp
// C4311.cpp
// compile by using: cl /W1 C4311.cpp
int main() {
   void* p = &p;
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets
   unsigned long long j = (unsigned long long) p;   // OK
}
```
