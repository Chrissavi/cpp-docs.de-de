---
title: Ref (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.ref
dev_langs:
- C++
helpviewer_keywords:
- ref attribute
ms.assetid: 67e82d3e-07d9-4ef8-bf2b-0a4491d12557
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d420566411326b21a6d219d51ceaec476f130be4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437442"
---
# <a name="ref-c"></a>ref (C++)

Identifiziert einen Verweiszeiger an.

## <a name="syntax"></a>Syntax

```cpp
[ref]
```

## <a name="remarks"></a>Hinweise

Die **Ref** C++-Attribut hat die gleiche Funktionalität wie die [Ref](/windows/desktop/Midl/ref) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie mit der **Ref** Attribut:

```cpp
// cpp_attr_ref_ref.cpp
// compile with: /LD
#include <windows.h>
[module(name="ATLFIRELib")];
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   [id(1), unique] char * GetFirstName([in, ref] char * pszFullName );
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**TypeDef**, Schnittstellenparameter,-Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[Parameterattribute](../windows/parameter-attributes.md)  