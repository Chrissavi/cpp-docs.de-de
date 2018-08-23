---
title: Standard (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.default
dev_langs:
- C++
helpviewer_keywords:
- default attribute
- attributes [C#], default attribute
- defaults, default attribute
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe924627b0b0f4f5d02fab0040a4037085d94738
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595582"
---
# <a name="default-c"></a>default (C++)

Gibt an, dass die benutzerdefinierte Schnittstelle oder Disp-Schnittstelle innerhalb einer Co-Klasse die Standard-Programmierschnittstelle darstellt.

## <a name="syntax"></a>Syntax

```cpp
[ default(
   interface1,
   interface2
) ]
```

### <a name="parameters"></a>Parameter

*interface1*  
Die Standardschnittstelle, die für Skriptumgebungen verfügbar gemacht wird, die ein Objekt auf Grundlage der Klasse erstellen, die mit dem **default** -Attribut definiert ist.

Wenn keine Standardschnittstelle angegeben wird, wird das erste Vorkommen einer Nicht-Quellschnittstelle als Standard verwendet.

*interface2*(optional)  
Die Standard-Quellschnittstelle. Sie müssen diese Schnittstelle auch beim [source](../windows/source-cpp.md) -Attribut angeben.

Wenn keine Standard-Quellschnittstelle angegeben ist, wird die erste Quellschnittstelle als Standard verwendet.

## <a name="remarks"></a>Hinweise

Das C++-Attribut **default** hat die gleiche Funktion wie das MIDL-Attribut [default](http://msdn.microsoft.com/library/windows/desktop/aa366787) . Das **default** -Attribut wird auch mit dem [case](../windows/case-cpp.md) -Attribut verwendet.

## <a name="example"></a>Beispiel

Der folgende code zeigt, wie **Standard** werden auf der Definition einer Co-Klasse angegeben `ICustomDispatch` als Standard-Programmierschnittstelle:

```cpp
// cpp_attr_ref_default.cpp
// compile with: /LD
#include "windows.h"
[module(name="MyLibrary")];

[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
};

[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]
__interface IDual {
   HRESULT Dual([in] long l, [out, retval] long *pLong);
};

[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]
__interface ICustomDispatch : public IDispatch {
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);
};

[   coclass,
   default(ICustomDispatch),
   source(IDual),
   uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")  
]
class CClass : public ICustom, public IDual, public ICustomDispatch {
   HRESULT Custom(long l, long *pLong) { return(S_OK); }
   HRESULT Dual(long l, long *pLong) { return(S_OK); }
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }
};

int main() {
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch
   CClass *pClass = new CClass;

   long llong;

   pClass->custom(1, &llong);
   pClass->dual(1, &llong);
   pClass->dispinterface(1, &llong);
   pClass->dispatch(1, &llong);

   delete pClass;
#endif
   return(0);
}
```

Das [source](../windows/source-cpp.md) -Attribut weist außerdem ein Beispiel zum Verwenden von **default**auf.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**,-Datenmember|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**Co-Klasse** (bei Anwendung auf **Klasse** oder **Struktur**)|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Klassenattribute](../windows/class-attributes.md)  
[coclass](../windows/coclass.md)  