---
title: CD2DBrushProperties-Klasse
ms.date: 11/04/2016
f1_keywords:
- CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CommonInit
helpviewer_keywords:
- CD2DBrushProperties [MFC], CD2DBrushProperties
- CD2DBrushProperties [MFC], CommonInit
ms.assetid: c77d717f-0a16-4d74-b2ce-0ae1766ed6f9
ms.openlocfilehash: 5ca791af658ee719b2e6d6ea78f82e23a66edc98
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270863"
---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties-Klasse

Ein Wrapper für `D2D1_BRUSH_PROPERTIES`.

## <a name="syntax"></a>Syntax

```
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DBrushProperties::CD2DBrushProperties](#cd2dbrushproperties)|Überladen. Erstellt eine `CD2D_BRUSH_PROPERTIES` Struktur|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DBrushProperties::CommonInit](#commoninit)|Initialisiert das Objekt|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`D2D1_BRUSH_PROPERTIES`

`CD2DBrushProperties`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="cd2dbrushproperties"></a>  CD2DBrushProperties::CD2DBrushProperties

Erstellt eine CD2D_BRUSH_PROPERTIES-Struktur

```
CD2DBrushProperties();
CD2DBrushProperties(FLOAT _opacity);

CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,
    FLOAT _opacity = 1.);
```

### <a name="parameters"></a>Parameter

*_opacity*<br/>
Die Basis Durchlässigkeit des Pinsels. Der Standardwert ist 1,0.

*_transform*<br/>
Die Transformation, auf den Pinsel angewendet.

##  <a name="commoninit"></a>  CD2DBrushProperties::CommonInit

Initialisiert das Objekt

```
void CommonInit();
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
