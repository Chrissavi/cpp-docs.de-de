---
title: Compilerwarnung (Stufe 1) C4109
ms.date: 11/04/2016
f1_keywords:
- C4109
helpviewer_keywords:
- C4109
ms.assetid: 9e8d95c6-e05d-47e0-bd87-78974b3cc06c
ms.openlocfilehash: 1156bbfbed7aed9524b24b046b9ce9acdbdc8b8a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539528"
---
# <a name="compiler-warning-level-1-c4109"></a>Compilerwarnung (Stufe 1) C4109

Unerwarteter Bezeichner "identifier"

Das Pragma mit dem unerwarteten Bezeichner wird ignoriert.

## <a name="example"></a>Beispiel

```
// C4109.cpp
// compile with: /W1 /LD
#pragma init_seg( abc ) // C4109
```