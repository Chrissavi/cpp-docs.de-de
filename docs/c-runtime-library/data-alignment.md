---
title: Datenausrichtung
ms.date: 11/04/2016
f1_keywords:
- data.alignment
helpviewer_keywords:
- data alignment [C++]
ms.assetid: 35ac3d2d-a4b3-421b-954f-b7372b1f18e1
ms.openlocfilehash: 7d835545bdc1f94de56846f35d510927c06c2560
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520284"
---
# <a name="data-alignment"></a>Datenausrichtung

Die folgenden C-Laufzeitfunktionen unterstützen die Datenausrichtung.

## <a name="data-alignment-routines"></a>Routinen der Datenausrichtung

|-Routine zurückgegebener Wert|Mit|
|-------------|---------|
|[_aligned_free](../c-runtime-library/reference/aligned-free.md)|Gibt einen Speicherblock frei, der mit [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) belegt wurde.|
|[_aligned_free_dbg](../c-runtime-library/reference/aligned-free-dbg.md)|Gibt einen Speicherblock frei, der mit [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) belegt ist (nur in der Debugversion).|
|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)|Weist Speicher mit einer definierten Zuweisungsgrenze zu.|
|[_aligned_malloc_dbg](../c-runtime-library/reference/aligned-malloc-dbg.md)|Belegt einen Speicherblock in einer angegebenen Ausrichtungsgrenze mit zusätzlichem Speicherplatz für einen Debugheader und Überschreibungspuffer (nur Debugversion).|
|[_aligned_msize](../c-runtime-library/reference/aligned-msize.md)|Gibt die Größe eines im Heap belegten Speicherblocks zurück.|
|[_aligned_msize_dbg](../c-runtime-library/reference/aligned-msize-dbg.md)|Gibt die Größe eines im Heap belegten Speicherblocks zurück (nur Debugversion).|
|[_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)|Weist Speicher mit einer definierten Zuweisungsgrenze zu.|
|[_aligned_offset_malloc_dbg](../c-runtime-library/reference/aligned-offset-malloc-dbg.md)|Belegt Speicher in einer angegebenen Ausrichtungsgrenze (nur Debugversion).|
|[_aligned_offset_realloc](../c-runtime-library/reference/aligned-offset-realloc.md)|Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) belegt wurde.|
|[_aligned_offset_realloc_dbg](../c-runtime-library/reference/aligned-offset-realloc-dbg.md)|Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) belegt ist (nur in der Debugversion).|
|[_aligned_offset_recalloc](../c-runtime-library/reference/aligned-offset-recalloc.md)|Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) belegt ist und den Speicher auf 0 initialisiert.|
|[_aligned_offset_recalloc_dbg](../c-runtime-library/reference/aligned-offset-recalloc-dbg.md)|Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) belegt ist und den Speicher auf 0 initialisiert (nur Debugversion).|
|[_aligned_realloc](../c-runtime-library/reference/aligned-realloc.md)|Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) belegt wurde.|
|[_aligned_realloc_dbg](../c-runtime-library/reference/aligned-realloc-dbg.md)|Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) belegt ist (nur in der Debugversion).|
|[_aligned_recalloc](../c-runtime-library/reference/aligned-recalloc.md)|Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) belegt ist und den Speicher auf 0 initialisiert.|
|[_aligned_recalloc_dbg](../c-runtime-library/reference/aligned-recalloc-dbg.md)|Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) belegt ist und den Speicher auf 0 initialisiert (nur Debugversion).|

## <a name="see-also"></a>Siehe auch

[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>