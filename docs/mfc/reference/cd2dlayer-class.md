---
title: CD2DLayer-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DLayer
- AFXRENDERTARGET/CD2DLayer
- AFXRENDERTARGET/CD2DLayer::CD2DLayer
- AFXRENDERTARGET/CD2DLayer::Attach
- AFXRENDERTARGET/CD2DLayer::Create
- AFXRENDERTARGET/CD2DLayer::Destroy
- AFXRENDERTARGET/CD2DLayer::Detach
- AFXRENDERTARGET/CD2DLayer::Get
- AFXRENDERTARGET/CD2DLayer::GetSize
- AFXRENDERTARGET/CD2DLayer::IsValid
- AFXRENDERTARGET/CD2DLayer::m_pLayer
dev_langs:
- C++
helpviewer_keywords:
- CD2DLayer [MFC], CD2DLayer
- CD2DLayer [MFC], Attach
- CD2DLayer [MFC], Create
- CD2DLayer [MFC], Destroy
- CD2DLayer [MFC], Detach
- CD2DLayer [MFC], Get
- CD2DLayer [MFC], GetSize
- CD2DLayer [MFC], IsValid
- CD2DLayer [MFC], m_pLayer
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d381ecaa2ac894ce7f393685e67909fea013cde
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400119"
---
# <a name="cd2dlayer-class"></a>CD2DLayer-Klasse

Ein Wrapper für ID2D1Layer.

## <a name="syntax"></a>Syntax

```
class CD2DLayer : public CD2DResource;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DLayer::CD2DLayer](#cd2dlayer)|Erstellt ein CD2DLayer-Objekt.|
|[CD2DLayer:: ~ CD2DLayer](#_dtorcd2dlayer)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Layer-Objekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DLayer::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle für das Objekt|
|[CD2DLayer::Create](#create)|Erstellt eine CD2DLayer an. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLayer::Destroy](#destroy)|Zerstört ein CD2DLayer-Objekt. (Überschreibt [CD2DResource:: Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DLayer::Detach](#detach)|Resource-Schnittstelle aus dem Objekt getrennt|
|[CD2DLayer::Get](#get)|Gibt die ID2D1Layer-Schnittstelle|
|[CD2DLayer::GetSize](#getsize)|Gibt die Größe des Renderziels in geräteunabhängigen Pixeln|
|[CD2DLayer::IsValid](#isvalid)|Überprüft die Gültigkeit der Ressource (überschreibt [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DLayer::Operator ID2D1Layer *](#operator_id2d1layer_star)|Gibt die ID2D1Layer-Schnittstelle|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CD2DLayer::m_pLayer](#m_player)|Speichert einen Zeiger auf ein ID2D1Layer-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DLayer`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="_dtorcd2dlayer"></a>  CD2DLayer:: ~ CD2DLayer

Der Destruktor. Wird aufgerufen, wenn ein D2D-Layer-Objekt zerstört wird.

```
virtual ~CD2DLayer();
```

##  <a name="attach"></a>  CD2DLayer::Attach

Hängt die vorhandene Ressourcenschnittstelle für das Objekt

```
void Attach(ID2D1Layer* pResource);
```

### <a name="parameters"></a>Parameter

*pResource*<br/>
Vorhandene Ressourcenschnittstelle. NULL darf nicht sein

##  <a name="cd2dlayer"></a>  CD2DLayer::CD2DLayer

Erstellt ein CD2DLayer-Objekt.

```
CD2DLayer(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parameter

*pParentTarget*<br/>
Ein Zeiger auf das Renderziel.

*bAutoDestroy*<br/>
Gibt an, dass vom Besitzer (pParentTarget) das Objekt zerstört wird.

##  <a name="create"></a>  CD2DLayer::Create

Erstellt eine CD2DLayer an.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parameter

*pRenderTarget*<br/>
Ein Zeiger auf das Renderziel.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="destroy"></a>  CD2DLayer::Destroy

Zerstört ein CD2DLayer-Objekt.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DLayer::Detach

Resource-Schnittstelle aus dem Objekt getrennt

```
ID2D1Layer* Detach();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf getrennten Resource-Schnittstelle.

##  <a name="get"></a>  CD2DLayer::Get

Gibt die ID2D1Layer-Schnittstelle

```
ID2D1Layer* Get();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1Layer-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="getsize"></a>  CD2DLayer::GetSize

Gibt die Größe des Renderziels in geräteunabhängigen Pixeln

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Größe des Renderziels in geräteunabhängigen Pixeln

##  <a name="isvalid"></a>  CD2DLayer::IsValid

Die Gültigkeit der Überprüfungen-Ressource

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Ressource gültig ist. andernfalls "false".

##  <a name="m_player"></a>  CD2DLayer::m_pLayer

Speichert einen Zeiger auf ein ID2D1Layer-Objekt.

```
ID2D1Layer* m_pLayer;
```

##  <a name="operator_id2d1layer_star"></a>  CD2DLayer::Operator ID2D1Layer *

Gibt die ID2D1Layer-Schnittstelle

```
operator ID2D1Layer* ();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1Layer-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
