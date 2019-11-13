---
title: Compilerwarnung (Stufe 1) C4532
ms.date: 11/04/2016
f1_keywords:
- C4532
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
ms.openlocfilehash: b47eb192bc01e6fe2c6c9423ed2c672f16c6818f
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966250"
---
# <a name="compiler-warning-level-1-c4532"></a>Compilerwarnung (Stufe 1) C4532

"Continue": springen aus __finally/finally-Block weist ein undefiniertes Verhalten während der Abbruch Behandlung auf.

Der Compiler hat eines der folgenden Schlüsselwörter gefunden:

- [continue](../../cpp/continue-statement-cpp.md)

- [break](../../cpp/break-statement-cpp.md)

- [goto](../../cpp/goto-statement-cpp.md)

Auslösen eines [__finally](../../cpp/try-finally-statement.md) [oder letzten](../../dotnet/finally.md) Blocks während der nicht ordnungsgemäßen Beendigung.

Wenn eine Ausnahme auftritt und der Stapel während der Ausführung der Beendigungs Handler entladen wird (die `__finally` oder schließlich blockiert) und der Code aus einem `__finally` Block springt, bevor der `__finally`-Block beendet wird, ist das Verhalten nicht definiert. Das Steuerelement wird möglicherweise nicht zum Entwicklungscode zurückgegeben, sodass die Ausnahme möglicherweise nicht ordnungsgemäß behandelt wird.

Wenn Sie von einem **__finally** -Block ausspringen müssen, überprüfen Sie zunächst, ob eine ungewöhnliche Beendigung auftritt.

Im folgenden Beispiel wird C4532 generiert. kommentieren Sie einfach die Jump-Anweisungen aus, um die Warnungen aufzulösen.

```cpp
// C4532.cpp
// compile with: /W1
// C4532 expected
int main() {
   int i;
   for (i = 0; i < 10; i++) {
      __try {
      } __finally {
         // Delete the following line to resolve.
         continue;
      }

      __try {
      } __finally {
         // Delete the following line to resolve.
         break;
      }
   }
}
```