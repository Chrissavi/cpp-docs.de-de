---
title: _locking-Konstanten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
dev_langs:
- C++
helpviewer_keywords:
- LK_UNLCK constant
- LK_NBRLCK constant
- _LK_NBRLCK constant
- _LK_NBLCK constant
- _LK_LOCK constant
- LK_NBLCK constant
- _LK_UNLCK constant
- LK_RLCK constant
- _LK_RLCK constant
- LK_LOCK constant
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abf776ab72d692be6d573803353f35946df145ec
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031930"
---
# <a name="locking-constants"></a>_locking-Konstanten

## <a name="syntax"></a>Syntax

```
#include <sys/locking.h>
```

## <a name="remarks"></a>Hinweise

Das *mode*-Argument im Aufruf der `_locking`-Funktion gibt die auszuführende Sperraktion an.

Das *mode*-Argument muss eine der folgenden Manifestkonstanten sein.

|||
|-|-|
| `_LK_LOCK`  | Sperrt die angegebenen Bytes. Wenn die Bytes nicht gesperrt werden können, führt die Funktion nach 1 Sekunde einen neuen Versuch durch. Wenn nach 10 Versuchen die Bytes nicht gesperrt werden können, gibt die Funktion einen Fehler zurück.  |
| `_LK_RLCK`  | Wie in `_LK_LOCK`.  |
|`_LK_NBLCK`  | Sperrt die angegebenen Bytes. Wenn die Bytes nicht gesperrt werden können, gibt die Funktion einen Fehler zurück.  |
| `_LK_NBRLCK`  | Wie in `_LK_NBLCK`.  |
| `_LK_UNLCK`  | Entsperrt die angegebenen Bytes. (Die Bytes müssen zuvor gesperrt worden sein.)  |

## <a name="see-also"></a>Siehe auch

[_locking](../c-runtime-library/reference/locking.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)