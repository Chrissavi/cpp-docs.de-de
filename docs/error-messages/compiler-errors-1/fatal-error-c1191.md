---
title: Schwerwiegender Fehler C1191 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1191
dev_langs:
- C++
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: daefec7c89fc98d056963c4f761b7298d6e491cc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062968"
---
# <a name="fatal-error-c1191"></a>Schwerwiegender Fehler C1191

"Dll" kann nur im globalen Gültigkeitsbereich importiert werden

Die Anweisung zur Datei "mscorlib.dll" in ein Programm zu importieren, / CLR-Programmierung verwendet, darf nicht in einem Namespace oder einer Funktion, aber Sie müssen im globalen Gültigkeitsbereich angezeigt werden.

Im folgende Beispiel wird die C1191 generiert:

```
// C1191.cpp
// compile with: /clr
namespace sample {
   #using <mscorlib.dll>   // C1191 not at global scope
}
```

Mögliche Lösung:

```
// C1191b.cpp
// compile with: /clr /c
#using <mscorlib.dll>
namespace sample {}
```