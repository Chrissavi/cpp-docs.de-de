---
title: Aggregate und Unions | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- aggregates [C++], and unions
ms.assetid: 859fc211-b111-4f12-af98-de78e48f9b92
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b1afd3be89e1d18da9889d88dbbbef3fb104e02
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363258"
---
# <a name="aggregates-and-unions"></a>Aggregate und Unions
Andere Typen, z. B. Arrays, Strukturen und Unions, gelten strengere Ausrichtung, die konsistent aggregieren und union-Speicher und zum Datenabruf zu gewährleisten. Hier werden die Definitionen für Arrays, Struktur und Union:  
  
 Array  
 Enthält eine geordnete Gruppe von angrenzenden Datenobjekte. Jedes Objekt wird ein Element aufgerufen werden. Alle Elemente in einem Array haben die gleichen Größe und Datentyp.  
  
 Struktur  
 Enthält eine geordnete Gruppe von Datenobjekten an. Im Gegensatz zu der Elemente eines Arrays können die Datenobjekte in einer Struktur unterschiedliche Datentypen und Größen haben. Jedes Datenobjekt in eine Struktur ist ein Member aufgerufen werden.  
  
 Union  
 Ein Objekt, das einen Satz von benannten Elementen eines enthält. Die Elemente der benannten Menge können einen beliebigen Typ aufweisen. Der Speicher für eine Union zugeordnet ist gleich Speicher für den größten Member der Union sowie eines möglichen Abstands aus, für die Ausrichtung erforderlich.  
  
 Die folgende Tabelle zeigt die empfohlene Ausrichtung für die skalaren Member von Unions und Strukturen.  
  
||||  
|-|-|-|  
|Skalaren Typ|C-Datentyp|Erforderliche Ausrichtung|  
|**INT8**|`char`|Byte|  
|**UINT8**|`unsigned char`|Byte|  
|**INT16**|**short**|Word|  
|**UINT16**|**unsigned short**|Word|  
|**INT32**|**Int, long**|Doppelwort|  
|**UINT32**|**unsigned Int unsigned long**|Doppelwort|  
|**INT64**|`__int64`|Vierfachwort|  
|**UINT64**|**__int64 ohne Vorzeichen**|Vierfachwort|  
|**FP32 (einfache Genauigkeit)**|**float**|Doppelwort|  
|**FP64 (doppelte Genauigkeit)**|**double**|Vierfachwort|  
|**ZEIGER**|**\***|Vierfachwort|  
|`__m64`|**Struktur __m64**|Vierfachwort|  
|`__m128`|**Struktur __m128**|Octaword|  
  
 Die folgenden aggregierten Ausrichtung Regeln gelten:  
  
-   Die Ausrichtung eines Arrays ist identisch mit der Ausrichtung eines der Elemente des Arrays.  
  
-   Die Ausrichtung des Anfangs einer Struktur oder Union ist die maximale Ausrichtung eines einzelnen Member. Jedes Element innerhalb der Struktur oder Union muss an die richtige Ausrichtung eingefügt werden, wie in der vorherigen Tabelle definiert, die implizite interne Auffüllung, je nachdem das vorherige Element möglicherweise erforderlich sind.  
  
-   Die Größe der Struktur muss eine ganzzahlige Vielfache seiner Ausrichtung die Auffüllung nach dem letzten Element erfordern. Da Strukturen und Unions in Arrays gruppiert werden können, muss jedes Arrayelement einer Struktur oder Union beginnen und enden, an die richtige Ausrichtung, die zuvor bestimmt.  
  
-   Es ist möglich, zum Ausrichten von Daten in so, dass die ausrichtungsanforderungen größer sein als die oben aufgeführten Regeln verwaltet werden.  
  
-   Ein einzelne Compiler kann die Komprimierung einer Struktur aus Gründen der Größe anpassen. Z. B. [/Zp (Ausrichten des Strukturmembers)](../build/reference/zp-struct-member-alignment.md) ermöglicht das Anpassen der Komprimierung von Strukturen.  
  
## <a name="see-also"></a>Siehe auch  
 [Typen und Speicher](../build/types-and-storage.md)
