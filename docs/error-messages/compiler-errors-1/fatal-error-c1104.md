---
title: Schwerwiegender Fehler C1104
ms.date: 11/04/2016
f1_keywords:
- C1104
helpviewer_keywords:
- C1104
ms.assetid: 45bd85c4-77d3-4d3c-b167-49c563aefb4d
ms.openlocfilehash: c10d1a89d854aaeac47a9a70f1e1e319d1662935
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174236"
---
# <a name="fatal-error-c1104"></a>Schwerwiegender Fehler C1104

Schwerwiegender Fehler beim Importieren der LibID: "Meldung"

Der Compiler hat beim Importieren einer Typbibliothek ein Problem erkannt.  Sie können beispielsweise keine Typbibliothek mit LibID und gleichzeitig `no_registry`angeben.

Weitere Informationen finden Sie unter [#import-Anweisung](../../preprocessor/hash-import-directive-cpp.md).

Im folgenden Beispiel wird C1104 generiert.

```
// C1104.cpp
#import "libid:11111111.1111.1111.1111.111111111111" version("4.0") lcid("9") no_registry auto_search   // C1104
```