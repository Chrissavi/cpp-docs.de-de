---
title: Intrinsische Compilerfunktionen
ms.date: 11/04/2016
helpviewer_keywords:
- intrinsics, compiler
- compiler intrinsics
- cl.exe compiler, performance
- cl.exe compiler, intrinsics
ms.assetid: 48bb9929-7d78-4fd8-a092-ae3c9f971858
ms.openlocfilehash: f66c6247aba92a1528489dcf689239c9341b7d2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560016"
---
# <a name="compiler-intrinsics"></a>Intrinsische Compilerfunktionen

Die meisten Funktionen sind in Bibliotheken enthalten, aber einige Funktionen sind in den Compiler integriert (das heißt, sie sind systemintern). Diese werden als intrinsische Funktionen bezeichnet.

## <a name="remarks"></a>Hinweise

Wenn eine Funktion systemintern ist, wird der Code für diese Funktion normalerweise inline eingefügt, damit wird der Mehraufwand eines Funktionsaufrufs vermieden und es können äußerst effiziente Computerbefehle für diese Funktion ausgegeben werden. Eine systeminterne Funktion ist häufig schneller als die entsprechende Inlineassembly, da der Optimierer über integriertes Wissen über das Verhalten vieler systeminterner Funktionen verfügt, sodass einige Optimierungen verfügbar sein können, die bei Verwendung von Inlineassemblys nicht verfügbar sind. Außerdem kann der Optimierer die systeminterne Funktion anders erweitern, Puffer anders ausrichten oder je nach Kontext und den Argumenten des Aufrufs andere Anpassungen vornehmen.

Die Verwendung systeminterner Funktionen beeinflusst die Portabilität des Codes, da die in Visual C++ verfügbaren systeminternen Funktionen möglicherweise nicht zur Verfügung stehen, wenn der Code mit anderen Compilern und einigen systeminternen Funktionen kompiliert wird, die möglicherweise für einige aber nicht für alle Zielarchitekturen verfügbar sind. Allerdings sind systeminterne Funktionen in der Regel besser portierbar als Inlineassemblys. Systeminternen Funktionen sind auf 64-Bit-Architekturen erforderlich, auf denen Inlineassemblys nicht unterstützt werden.

Einige systeminterne Funktionen, wie `__assume` und `__ReadWriteBarrier`, stellen dem Compiler Informationen bereit, die das Verhalten des Optimierers beeinflussen.

Einige systeminterne Funktionen sind nur als systeminterne Funktionen verfügbar, und einige sind sowohl in Funktionsimplementierungen als auch in systeminternen Implementierungen verfügbar. Sie können den Compiler anweisen, die systeminterne Implementierung auf einer von zwei Arten zu verwenden, je nach dem, ob Sie nur bestimmte Funktionen aktivieren möchten, oder ob Sie alle systeminternen Funktionen aktivieren möchten. Die erste Möglichkeit ist die Verwendung `#pragma intrinsic(` *systeminterne-Funktion-Name-List*`)`. Das Pragma kann verwendet werden, um eine einzelne systeminterne Funktion oder mehrere durch Trennzeichen getrennte systeminterne Funktionen angeben. Die zweite ist die Verwendung der [/Oi (systeminterne Funktionen erstellen)](../build/reference/oi-generate-intrinsic-functions.md) Compileroption, die alle systeminternen Funktionen auf eine bestimmte Plattform zur Verfügung stellt. Klicken Sie unter **/Oi**, verwenden Sie `#pragma function(` *systeminterne-Funktion-Name-List* `)` erzwingen ein Funktionsaufrufs anstelle einer systeminternen Funktion verwendet werden. Wenn Sie die Dokumentation für einer bestimmte systeminterne Funktion darauf hingewiesen wird, dass die Routine ist nur als systeminterne Funktion verfügbar, wird die systeminterne Implementierung verwendet, unabhängig davon, ob **/Oi** oder `#pragma intrinsic` angegeben ist. In allen Fällen **/Oi** oder `#pragma intrinsic` ermöglicht, jedoch nicht erzwungen, den Optimierer die systeminterne Funktion verwendet. Die Funktion kann vom Optimierer noch immer aufgerufen werden.

Einige C bzw. C++-Standardbibliotheksfunktionen sind in den systeminternen Implementierungen einiger Architekturen verfügbar. Wenn Sie eine CRT-Funktion aufrufen, wird die systeminterne Implementierung verwendet, wenn **/Oi** in der Befehlszeile angegeben ist.

Eine Headerdatei, \<intrin.h >, ist verfügbar, die Prototypen für die gängigsten intrinsischen Funktionen deklariert. Herstellerspezifische systeminterne Funktionen stehen in der \<immintrin.h > und \<ammintrin.h > Headerdateien. Außerdem deklarieren bestimmte Windows-Header Funktionen, die auf eine systeminterne Compilerfunktion zuordnen.

In den folgenden Abschnitten werden alle systeminternen Funktionen aufgeführt, die auf verschiedenen Architekturen verfügbar sind. Weitere Informationen zu der Funktionsweise systeminterner Funktionen auf dem bestimmten Zielprozessor finden Sie in der Referenzdokumentation des Herstellers.

- [Intrinsische ARM-Funktionen](../intrinsics/arm-intrinsics.md)

- [Liste der intrinsischen Funktionen für x86](../intrinsics/x86-intrinsics-list.md)

- [Liste der intrinsischen Funktionen für x64 (amd64)](../intrinsics/x64-amd64-intrinsics-list.md)

- [Intrinsische Funktionen verfügbar für alle Architekturen](../intrinsics/intrinsics-available-on-all-architectures.md)

- [Alphabetische Liste der intrinsischen Funktionen](../intrinsics/alphabetical-listing-of-intrinsic-functions.md)

## <a name="see-also"></a>Siehe auch

[Verweis auf den ARM-Assembler](../assembler/arm/arm-assembler-reference.md)<br/>
[Referenz zum Microsoft-Makroassembler](../assembler/masm/microsoft-macro-assembler-reference.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[C-Laufzeitbibliotheksreferenz](../c-runtime-library/c-run-time-library-reference.md)