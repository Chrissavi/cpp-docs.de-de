---
title: Aggregate (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.aggregates
dev_langs:
- C++
helpviewer_keywords:
- aggregates attribute
- aggregation [C++]
- aggregate objects [C++], aggregates attribute
- aggregates [C++]
ms.assetid: 67a084c9-941f-474b-a029-9c93b38ebe9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5817267977ea1c8eeca00ef98357f31cb92d5bf4
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791939"
---
# <a name="aggregates"></a>Aggregate

Gibt an, dass das Objekt das von der CLSID angegebene Objekt aggregiert.

## <a name="syntax"></a>Syntax

```cpp
[ aggregates(clsid, variable_name) ]
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
Gibt die CLSID des aggregierbaren Objekts an.

*variable_name*<br/>
Der Name der Variable, die eingefügt werden soll. Diese Variable enthält die `IUnknown` des Objekts, die aggregiert wird.

## <a name="remarks"></a>Hinweise

Das C++-Attribut **aggregates** implementiert einen äußeren Wrapper für die Objekte, die aggregiert werden (angegeben von `clsid`), wenn es auf ein Objekt angewendet wird.

Dieses Attribut erfordert, dass die [Co-Klasse](coclass.md), [progid](progid.md), oder [Vi_progid](vi-progid.md) (oder ein anderes Attribut, das eines der genannten impliziert) auch angewendet werden mit dem gleichen Element. Wenn ein einzelnes Attribut verwendet wird, werden die anderen beiden automatisch angewendet. Z. B. wenn `progid` angewendet wird, `vi_progid` und `coclass` werden ebenfalls angewendet.

### <a name="atl-projects"></a>ATL-Projekte

Wenn dieses Attribut in einem Projekt verwendet wird, das ATL verwendet, ändert sich das Verhalten des Attributs. Erstens wird der folgende Eintrag der COM-Zuordnung des Zielobjekts hinzugefügt:

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(_m_spAttrXXX, clsid)  
```

Zweitens wird die [DECLARE_GET_CONTROLLING_UNKNOWN](../../atl/reference/aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) Makro wird ebenfalls hinzugefügt.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_aggregates.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

// requires 'aggregatable.dll'
// see aggregatable attribute to create 'aggregatable.dll'
class DECLSPEC_UUID("1a8369cc-1c91-42c4-befa-5a5d8c9d2529") CMyClass;

[module (name="MYObject")];
[object, uuid("ab006d85-e754-47c5-9ef4-2744ff32a20c")]
__interface IObject
{
};

[ coclass, aggregates(__uuidof(CMyClass)),
  uuid("91cb2c06-8931-432a-baac-206e55c4edfb")]
struct CObject : IObject
{
   int i;
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Ja|
|**Erforderliche Attribute**|Eine oder mehrere der folgenden: `coclass`, `progid`, oder `vi_progid`.|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[COM-Attribute](com-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Aggregation](/windows/desktop/com/aggregation)<br/>
[Aggregiert](/windows/desktop/Midl/aggregatable)<br/>
[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](../../atl/reference/com-interface-entry-macros.md#com_interface_entry_autoaggregate_blind)  