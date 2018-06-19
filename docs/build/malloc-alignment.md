---
title: Malloc-Ausrichtung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d503d0dd891c651a405cb79bb5ce50996f46cff6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368664"
---
# <a name="malloc-alignment"></a>malloc-Ausrichtung
["malloc"](../c-runtime-library/reference/malloc.md) wird sichergestellt, dass Arbeitsspeicher zurückgeben, die zeigt, passend ausgerichtet ist, für das Speichern jedes Objekt, das eine grundlegende Ausrichtung und die hat hinsichtlich der Menge an Arbeitsspeicher passt konnte, der zugeordnet ist. Ein *grundlegende Ausrichtung* ist eine Ausrichtung, die kleiner oder gleich der größten Ausrichtung, die von der Implementierung ohne Ausrichtungsspezifikation unterstützt wird. (In Visual C++ ist dies die Ausrichtung, die für einen `double` oder 8 Bytes erforderlich ist. In einem Code, der auf 64-Bit-Plattformen ausgerichtet ist, sind es 16 Bytes.) Beispielsweise kann eine Vier-Byte-Speicherbelegung an einer Begrenzung ausgerichtet werden, die ein Objekt unterstützt, das maximal vier Byte groß ist.  
  
 Visual C++ unterstützt Typen mit *Erweiterte Ausrichtung*, auch bekannt als sind *ausgerichtete* Typen. Z. B. die SSE-Typen [__m128](../cpp/m128.md) und `__m256`, sowie Typen, die mithilfe von deklariert werden `__declspec(align( n ))` , in denen `n` ist größer als 8, Ausrichtung erweitert haben. Eine Speicherausrichtung an einer Grenze, die für ein Objekt geeignet ist, das eine erweiterte Ausrichtung erfordert, wird von `malloc` nicht gewährleistet. Verwenden Sie zum Reservieren von Speicher für ausgerichtetes Typen [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) und verwandte Funktionen verweisen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwendung von Stapeln](../build/stack-usage.md)   
 [Ausrichten](../cpp/align-cpp.md)   
 [__declspec](../cpp/declspec.md)