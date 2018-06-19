---
title: vector&lt;bool&gt;::reference::operator bool | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- operatorbool
- vector<bool>::reference::operatorbool
- bool
- std::vector<bool>::reference::operatorbool
dev_langs:
- C++
helpviewer_keywords:
- BOOL operator
- reference::operator bool
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0fd249dd7591caaaf62a0b8a698085efedb1f25
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854534"
---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool

Stellt eine implizite Konvertierung von `vector<bool>::reference` in `bool` bereit.

## <a name="syntax"></a>Syntax

```cpp
operator bool() const;
```

## <a name="return-value"></a>Rückgabewert

Der boolesche Wert des Elements des [vector\<bool>](../standard-library/vector-bool-class.md)-Objekts.

## <a name="remarks"></a>Hinweise

Das `vector<bool>`-Objekt kann von diesem Operator nicht geändert werden.

## <a name="requirements"></a>Anforderungen

**Header:** \<vector>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Vektor\<Bool >:: Klasse verweisen](../standard-library/vector-bool-reference-class.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
