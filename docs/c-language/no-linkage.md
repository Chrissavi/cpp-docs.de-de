---
title: Keine Verknüpfung
ms.date: 11/04/2016
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
ms.openlocfilehash: 9775270c5c1fb0b6758f994c432104d75e19d38d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505078"
---
# <a name="no-linkage"></a>Keine Verknüpfung

Wenn eine Deklaration für einen Bezeichner in einem Block den `extern`-Speicherklassenspezifizierer nicht enthält, hat der Bezeichner keine Bindung und ist für die Funktion eindeutig.

Die folgenden Bezeichner haben keine Verknüpfung:

- Ein Bezeichner, der als etwas anderes als ein Objekt oder eine Funktion deklariert wurde

- Ein Bezeichner, der zum Funktionsparameter deklariert wurde

- Ein Blockbereichsbezeichner für ein Objekt, das ohne den `extern`-Speicherklassenspezifizierer deklariert wurde

Wenn ein Bezeichner keine Verknüpfung aufweist, wird durch erneutes Deklarieren des gleichen Namens (in einem Deklarator oder Typspezifizierer) auf der gleichen Gültigkeitsebene einen Fehler bei der Symbolneudefinition.

## <a name="see-also"></a>Siehe auch

[Verwenden von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)