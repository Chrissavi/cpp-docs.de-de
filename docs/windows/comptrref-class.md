---
title: ComPtrRef-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef class
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aaeb641fc7b2276567edfb30fd36c46db6cfc5ae
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613688"
---
# <a name="comptrref-class"></a>ComPtrRef-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <
   typename T
>
class ComPtrRef : public ComPtrRefBase<T>;
```

#### <a name="parameters"></a>Parameter

*T*  
Ein [ComPtr\<T >](../windows/comptr-class.md) Typ oder einem Typ abgeleitet ist, nicht nur die Schnittstelle der `ComPtr`.

## <a name="remarks"></a>Hinweise

Stellt einen Verweis auf ein Objekt des Typs `ComPtr<T>`.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[ComPtrRef::ComPtrRef-Konstruktor](../windows/comptrref-comptrref-constructor.md)|Initialisiert eine neue Instanz der dem **ComPtrRef** Klasse aus dem angegebenen Zeiger auf einen anderen **ComPtrRef** Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ComPtrRef::GetAddressOf-Methode](../windows/comptrref-getaddressof-method.md)|Ruft die Adresse eines Zeigers auf die Schnittstelle, die vom aktuellen **ComPtrRef** Objekt.|
|[ComPtrRef::ReleaseAndGetAddressOf-Methode](../windows/comptrref-releaseandgetaddressof-method.md)|Löscht die aktuelle **ComPtrRef** Objekt und gibt einen Zeiger-auf-ein-Zeiger auf die Schnittstelle, die durch dargestellt wurde die **ComPtrRef** Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[ComPtrRef::operator InterfaceType**-Operator](../windows/comptrref-operator-interfacetype-star-star-operator.md)|Löscht die aktuelle **ComPtrRef** Objekt und gibt einen Zeiger-auf-ein-Zeiger auf die Schnittstelle, die durch dargestellt wurde die **ComPtrRef** Objekt.|
|[ComPtrRef::operator T*-Operator](../windows/comptrref-operator-t-star-operator.md)|Gibt den Wert des der [Ptr_](../windows/comptrrefbase-ptr-data-member.md) -Datenmember des aktuellen ComPtrRef-Objekts.|
|[ComPtrRef::operator void**-Operator](../windows/comptrref-operator-void-star-star-operator.md)|Löscht die aktuelle **ComPtrRef** Objekt, wandelt der Zeiger auf die Schnittstelle, die durch dargestellt wurde die **ComPtrRef** -Objekt als eine Zeiger-auf-Zeiger-auf **"void"**, und klicken Sie dann Gibt die Cast-Zeiger zurück.|
|[ComPtrRef::operator*-Operator](../windows/comptrref-operator-star-operator.md)|Ruft ab, der Zeiger auf die Schnittstelle, die vom aktuellen **ComPtrRef** Objekt.|
|[ComPtrRef::operator==-Operator](../windows/comptrref-operator-equality-operator.md)|Gibt an, ob zwei **ComPtrRef** Objekte gleich sind.|
|[ComPtrRef::operator!=-Operator](../windows/comptrref-operator-inequality-operator.md)|Gibt an, ob zwei **ComPtrRef** -Objekte ungleich sind.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)