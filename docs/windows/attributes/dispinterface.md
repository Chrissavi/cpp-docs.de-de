---
title: Disp-Schnittstelle (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.dispinterface
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
ms.openlocfilehash: 6fd5010dc20d03c518206d81919e3beafbcaa9a9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038459"
---
# <a name="dispinterface"></a>dispinterface

Fügt eine Schnittstelle in die IDL-Datei als Verteilschnittstelle ein.

## <a name="syntax"></a>Syntax

```cpp
[dispinterface]
```

## <a name="remarks"></a>Hinweise

Wenn das C++-Attribut **dispinterface** einer Schnittstelle vorangeht, wird die Schnittstelle dadurch in den Bibliotheksblock in der generierten IDL-Datei eingefügt.

Solange Sie keine Basisklasse festlegen, wird eine Verteilschnittstelle von `IDispatch`abgeleitet. Sie müssen eine [ID](id.md) für die Member einer Verteilschnittstelle angeben.

Das Beispiel für die Verwendung von [dispinterface](/windows/desktop/Midl/dispinterface) in der MIDL-Dokumentation:

```cpp
dispinterface helloPro
   { interface hello; };
```

ist nicht gültig für das Attribut **dispinterface** .

## <a name="example"></a>Beispiel

Sehen Sie sich das Beispiel für [bindable](bindable.md) für ein Beispiel für die Verwendung von **dispinterface**an.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**interface**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Attribute nach Verwendung](attributes-by-usage.md)<br/>
[uuid](uuid-cpp-attributes.md)<br/>
[dual](dual.md)<br/>
[Benutzerdefiniert](custom-cpp.md)<br/>
[object](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)