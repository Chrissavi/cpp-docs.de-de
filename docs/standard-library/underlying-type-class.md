---
title: underlying_type-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::underlying_type
dev_langs:
- C++
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f45af807b37294b87920b6fabac18647f170025
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853221"
---
# <a name="underlyingtype-class"></a>underlying_type-Klasse

Erzeugt für einen Enumerationstyp den zugrunde liegenden ganzzahligen Typ.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Parameter

`T` Die zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Der typedef-Member `type` der Vorlagenklasse benennt den zugrunde liegenden ganzzahligen Typ von `T`, wenn `T` ein Enumerationstyp ist, andernfalls gibt es keinen typedef-Member `type`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
