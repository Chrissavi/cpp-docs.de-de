---
title: money_base-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/std::money_base
dev_langs:
- C++
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 805045e4ea63f153e9a35b0d4b068bd69874b93f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864085"
---
# <a name="moneybase-class"></a>money_base-Klasse

Die Klasse beschreibt eine Enumeration und eine Struktur, die für alle Spezialisierungen der Vorlagenklasse [moneypunct](../standard-library/moneypunct-class.md) gebräuchlich ist.

## <a name="syntax"></a>Syntax

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>Hinweise

Die Enumeration **part** beschreibt die möglichen Werte in Elementen des Array-Felds im Strukturmuster. Als Werte von **part** dienen:

- **none**, um auf null oder mehr Leerzeichen abzustimmen bzw. nichts zu generieren.

- **sign**, um auf ein positives bzw. negatives Vorzeichen abzustimmen oder um ein positives bzw. negatives Vorzeichen zu generieren.

- **space**, um auf null oder mehr Leerzeichen abzustimmen bzw. um ein Leerzeichen zu generieren.

- **symbol**, um auf ein Währungssymbol abzustimmen bzw. um ein Währungssymbol zu generieren.

- **value**, um auf einen monetären Wert abzustimmen bzw. um einen monetären Wert zu generieren.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
