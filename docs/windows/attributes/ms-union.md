---
title: Ms_union (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.ms_union
helpviewer_keywords:
- ms_union attribute
ms.assetid: bb548689-6962-457e-af56-8ffdf68987eb
ms.openlocfilehash: ae99a996cd7969da27f38ad3532f0472f389ee3d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838840"
---
# <a name="ms_union"></a>ms_union

Steuert die Ausrichtung der Netzwerkdaten Darstellung von nicht gekapselten Unions.

## <a name="syntax"></a>Syntax

```cpp
[ms_union]
```

## <a name="remarks"></a>Bemerkungen

Das **Ms_union** C++-Attribut verfügt über die gleiche Funktionalität wie das [Ms_union](/windows/win32/Midl/ms-union-attrib) -Attribut "Mittel".

## <a name="example"></a>Beispiel

Der folgende Code zeigt die Platzierung der **Ms_union**:

```cpp
// cpp_attr_ref_ms_union.cpp
// compile with: /LD
#include <unknwn.h>
[object, ms_union, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl {
   HRESULT DisplayString([in, string] char * p1);
};

[export, switch_type(short)] union _WILLIE_UNION_TYPE  {
   [case(24)]
      float fMays;
   [case(25)]
      double dMcCovey;
   [default]
      int x;
};

[public] typedef _WILLIE_UNION_TYPE WILLIE_UNION_TYPE;

[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>Requirements (Anforderungen)

| Attribut Kontext | Wert |
|-|-|
|**Zielgruppe**|Nicht gekapselt Unions|
|**REPEATABLE**|Nein|
|**Erforderliche Attribute**|Keine|
|**Ungültige Attribute**|`dispinterface`|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Weitere Informationen

[IDL-Attribute](idl-attributes.md)<br/>
[Typedef-, Aufzählungs-, Union-und struct-Attribute](typedef-enum-union-and-struct-attributes.md)
