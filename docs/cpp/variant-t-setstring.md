---
title: _variant_t::SetString | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::SetString
dev_langs:
- C++
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 52ea719a2c9296ca1e64d881ac150994c041e206
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018729"
---
# <a name="varianttsetstring"></a>_variant_t::SetString

**Microsoft-spezifisch**

Weist diesem `_variant_t`-Objekt eine Zeichenfolge zu.

## <a name="syntax"></a>Syntax

```
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>Parameter

*pSrc*<br/>
Zeiger auf die Zeichenfolge.

## <a name="remarks"></a>Hinweise

Konvertiert eine Zeichenfolge mit ANSI-Zeichen in eine Unicode-`BSTR`-Zeichenfolge und weist sie diesem `_variant_t`-Objekt zu.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_variant_t-Klasse](../cpp/variant-t-class.md)