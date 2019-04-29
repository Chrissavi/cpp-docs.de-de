---
title: Compilerwarnung (Stufe 1) C4312
ms.date: 11/04/2016
f1_keywords:
- C4312
helpviewer_keywords:
- C4312
ms.assetid: 541906ed-4f62-4bcb-947f-cf9ae7411bcb
ms.openlocfilehash: 666df7904a7aac88983af40d31a67271beaa0b1f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408315"
---
# <a name="compiler-warning-level-1-c4312"></a>Compilerwarnung (Stufe 1) C4312

'Operation': Konvertierung von 'Typ1' in größeren Typ 'Typ2'

Diese Warnung erkennt den Versuch, einen 32-Bit-Wert einem 64-Bit-Zeigertyp zuzuweisen, z. B. die Umwandlung eines 32-Bit-`int` oder `long` in einen 64-Bit-Zeiger.

Dabei kann es sich um eine unsichere Konvertierung auch für Zeigerwerte handeln, die in 32 Bits passen, wenn die Vorzeichenerweiterung vorhanden ist. Wenn eine negative 32-Bit-Ganzzahl einem 64-Bit-Zeigertyp zugeordnet wird, verweist der Zeigerwert aufgrund der Vorzeichenerweiterung auf eine Speicheradresse, die sich vom Wert der Ganzzahl unterscheidet.

Diese Warnung wird nur für 64-Bit-Kompilierungsziele ausgegeben. Weitere Informationen finden Sie unter [Regeln für die Verwendung von Zeigern](/windows/desktop/WinProg64/rules-for-using-pointers).

Im folgenden Codebeispiel wird C4312 generiert, wenn dies für 64-Bit-Ziele kompiliert wird:

```
// C4312.cpp
// compile by using: cl /W1 /LD C4312.cpp
void* f(int i) {
   return (void*)i;   // C4312 for 64-bit targets
}

void* f2(__int64 i) {
   return (void*)i;   // OK
}
```