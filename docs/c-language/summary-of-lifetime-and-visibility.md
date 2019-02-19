---
title: Zusammenfassung von Lebensdauer und Sichtbarkeit
ms.date: 11/04/2016
helpviewer_keywords:
- lifetime, and visibility
- visibility, identifiers
ms.assetid: ea05a253-7658-482c-9a6b-abd71169c42d
ms.openlocfilehash: 438dd855fbbfec01a31a8d4a1a53078e3c44658c
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56151779"
---
# <a name="summary-of-lifetime-and-visibility"></a>Zusammenfassung von Lebensdauer und Sichtbarkeit

Die folgende Tabelle ist eine Zusammenfassung der Lebensdauer- und Sichtbarkeitseigenschaften der meisten Bezeichner. Die ersten drei Spalten geben die Attribute an, die die Lebensdauer und die Sichtbarkeit definieren. Ein Bezeichner mit den Attributen, die durch die ersten drei Spalten angegeben sind, weist die Lebensdauer und Sichtbarkeit auf, die in der vierten und fünften Spalte angezeigt werden. Allerdings deckt die Tabelle nicht alle möglichen Fälle ab. Weitere Informationen finden Sie unter [Speicherklassen](../c-language/c-storage-classes.md).

### <a name="summary-of-lifetime-and-visibility"></a>Zusammenfassung von Lebensdauer und Sichtbarkeit

|Attribute:<br /><br /> Ebene|Element|Speicherklasse<br /><br /> Bezeichner|Ergebnis: <br /><br /> Lebensdauer|Sichtbarkeit|
|---------------------------|----------|----------------------------------|--------------------------|----------------|
|Dateibereich|Variablendefinition|**static**|Global|Rest der Quelldatei der Ausführung|
||Variablendeklaration|**extern**|Global|Rest der Quelldatei der Ausführung|
||Funktionsprototyp oder Definition|**static**|Global|Einzelne Quelldatei|
||Funktionsprototyp|**extern**|Global|Rest der Quelldatei|
|Blockbereich|Variablendeklaration|**extern**|Global|Block|
||Variablendefinition|**static**|Global|Block|
||Variablendefinition|**auto** oder **register**|Lokal|Block|

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Im folgenden Beispiel werden Blöcke, Verschachtelung und die Sichtbarkeit von Variablen veranschaulicht:

### <a name="code"></a>Code

```
// Lifetime_and_Visibility.c

#include <stdio.h>

int i = 1;  // i defined at external level

int main()  // main function defined at external level
{
    printf_s( "%d\n", i ); // Prints 1 (value of external level i)
    {                                 // Begin first nested block
        int i = 2, j = 3;          // i and j defined at internal level
        printf_s( "%d %d\n", i, j );  // Prints 2, 3
        {                             // Begin second nested block
            int i = 0;                // i is redefined
            printf_s( "%d %d\n", i, j ); // Prints 0, 3
        }                             // End of second nested block
        printf_s( "%d\n", i );        // Prints 2 (outer definition
                                      //  restored)
    }                                 // End of first nested block
    printf_s( "%d\n", i );            // Prints 1 (external level
                                      // definition restored)
    return 0;
}
```

### <a name="comments"></a>Kommentare

In diesem Beispiel gibt es vier Sichtbarkeitsebenen: die externe Ebene und drei Blockebenen. Die Werte werden auf dem Bildschirm gemäß den Kommentaren nach der jeweiligen Anweisung ausgegeben.

## <a name="see-also"></a>Siehe auch

[Lebensdauer, Bereich, Sichtbarkeit und Verknüpfung](../c-language/lifetime-scope-visibility-and-linkage.md)
