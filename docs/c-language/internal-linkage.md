---
title: Interne Verknüpfung
ms.date: 11/04/2016
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
ms.openlocfilehash: 857badd1284378a066c6c19c7159c1535e313593
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452365"
---
# <a name="internal-linkage"></a>Interne Verknüpfung

Wenn die Deklaration eines Dateigültigkeitsbereichs-Bezeichners für ein Objekt oder eine Funktion den *Speicherklassenspezifizierer* **static** enthält, hat der Bezeichner eine interne Verknüpfung. Andernfalls hat der Bezeichner eine externe Bindung. Weitere Informationen erhalten Sie in der Erläuterung der *Speicherklassenspezifizierer*-Nichtterminale unter [Speicherklassen](../c-language/c-storage-classes.md).

Innerhalb einer Übersetzungseinheit kennzeichnet jede Instanz eines Bezeichners mit interner Bindung denselben Bezeichner bzw. dieselbe Funktion. Intern gebundene Bezeichner sind für eine Übersetzungseinheit eindeutig.

## <a name="see-also"></a>Siehe auch

[Verwenden von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)