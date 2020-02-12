---
title: 'Gewusst wie: Konvertieren einer OpenMP-Schleife, in der eine reduction-Variable verwendet wird, zur Verwendung der Concurrency Runtime'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, reduction variables
- reduction variables, converting from OpenMP to the Concurrency Runtime
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
ms.openlocfilehash: ee0a600f4234c3ebf4681ad92b5e3623be5665c3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141264"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime"></a>Gewusst wie: Konvertieren einer OpenMP-Schleife, in der eine reduction-Variable verwendet wird, zur Verwendung der Concurrency Runtime

In diesem Beispiel wird veranschaulicht, wie eine [parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)OpenMP-[for](../../parallel/openmp/reference/for-openmp.md) -Schleife konvertiert wird, die mithilfe der [Reduction](../../parallel/openmp/reference/reduction.md) -Klausel die Concurrency Runtime verwendet.

Mit der OpenMP-`reduction`-Klausel können Sie eine oder mehrere private Variablen im Thread angeben, auf die am Ende des parallelen Bereichs ein Reduzierungsvorgang angewendet wird. OpenMP enthält einen Satz vordefinierter Reduzierungsoperatoren. Jede Reduzierungsvariable muss ein Skalar sein (z. B. `int`, `long` und `float`). OpenMP definiert außerdem einige Einschränkungen für die Verwendung von Reduzierungsvariablen in einem parallelen Bereich.

Die Parallel Patterns Library (PPL) stellt die [parallelcurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) -Klasse bereit, die wiederverwendbaren, Thread lokalen Speicher bereitstellt, mit dem Sie differenzierte Berechnungen ausführen und diese Berechnungen anschließend in ein Endergebnis zusammenführen können. Die `combinable`-Klasse ist eine Vorlage, die sowohl auf skalare als auch auf komplexe Typen angewendet wird. Um die `combinable`-Klasse zu verwenden, führen Sie unter Berechnungen im Text eines parallelen Konstrukts aus, und rufen Sie dann die Methode " [parallelcurrency:: combinable:: Combine](reference/combinable-class.md#combine) " oder " [parallelcurrency:: combinable:: combine_each](reference/combinable-class.md#combine_each) " auf, um das Endergebnis zu erzeugen. Die Methoden `combine` und `combine_each` verwenden jeweils eine *Combine-Funktion* , die angibt, wie jedes Element paar kombiniert werden soll. Daher ist die `combinable`-Klasse nicht auf einen festen Satz von Reduzierungsoperatoren beschränkt.

## <a name="example"></a>Beispiel

In diesem Beispiel wird mit OpenMP und der Concurrency Runtime die Summe der ersten 35 Fibonacci-Zahlen berechnet.

[!code-cpp[concrt-openmp#7](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-a-reduction-variable_1.cpp)]

Folgende Ergebnisse werden zurückgegeben:

```Output
Using OpenMP...
The sum of the first 35 Fibonacci numbers is 14930351.
Using the Concurrency Runtime...
The sum of the first 35 Fibonacci numbers is 14930351.
```

Weitere Informationen zum `combinable`-Klasse finden Sie unter [parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `concrt-omp-fibonacci-reduction.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc/OpenMP ConcRT-OMP-Fibonacci-Reduction. cpp**

## <a name="see-also"></a>Weitere Informationen

[Migrieren von OpenMP zur Concurrency Runtime](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)
