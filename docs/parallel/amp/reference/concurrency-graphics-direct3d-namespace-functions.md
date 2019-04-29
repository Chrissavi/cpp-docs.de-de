---
title: Concurrency::Graphics::Direct3D Namespace-Funktionen
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d::get_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_texture
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
ms.openlocfilehash: 18fb409b033ea14c3a140ea6600fc43cf3a8d603
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405546"
---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Concurrency::Graphics::Direct3D Namespace-Funktionen

||||
|-|-|-|
|[get_sampler](#get_sampler)|[get_texture](#get_texture)|[make_sampler](#make_sampler)|
|[make_texture](#make_texture)|[msad4](#msad4)|

##  <a name="get_sampler"></a>  get_sampler

Rufen Sie die D3D-Samplerstatus-Schnittstelle für die angegebene Zugriffstastenansicht ab, die das angegebene Samplerobjekt darstellt.

```
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,
    const sampler& _Sampler) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_Av*<br/>
Eine D3D-Zugriffstastenansicht, auf der der D3D-Samplerstatus erstellt werden soll.

*_Sampler*<br/>
Ein Samplerobjekt, für das die zugrunde liegende D3D-Samplerstatus-Schnittstelle erstellt wird.

### <a name="return-value"></a>Rückgabewert

Der IUnknown-Schnittstellenzeiger, der dem D3D-Samplerstatus entspricht, der den angegebenen Sampler darstellt.

##  <a name="get_texture"></a>  get_texture

Ruft die zugrunde liegende angegebenen Direct3D-texturschnittstelle [Textur](texture-class.md) Objekt.

```
template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const writeonly_texture_view<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture_view<value_type, _Rank>& _Texture) restrict(cpu);
```

### <a name="parameters"></a>Parameter

*value_type*<br/>
Der Elementtyp der Textur.

*_Rank*<br/>
Der Rang der Textur.

*_Texture*<br/>
Eine Textur oder Texturansicht, die mit dem accelerator_view-Objekt verknüpft ist, für das die zugrunde liegende Direct3D-Texturschnittstelle zurückgegeben wird.

### <a name="return-value"></a>Rückgabewert

Der IUnknown-Schnittstellenzeiger, der der Direct3D-Textur entspricht, die der Textur zugrunde liegt.

##  <a name="make_sampler"></a>  make_sampler

Erstellen Sie einen Sampler aus einem D3D-Samplerstatusschnittstellenzeiger.

```
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_D3D_sampler*<br/>
IUnknown-Schnittstellenzeiger des D3D-Samplerstatus zum Erstellen des Samplers.

### <a name="return-value"></a>Rückgabewert

Ein Sampler stellt den bereitgestellten D3D-Samplerstatus dar.

##  <a name="make_texture"></a>  make_texture

Erstellt eine [Textur](texture-class.md) Objekt mit den angegebenen Parametern.

```
template<
    typename value_type,
    int _Rank
>
texture<value_type, _Rank> make_texture(
    const Concurrency::accelerator_view& _Av,
    _In_ IUnknown* _D3D_texture,
    DXGI_FORMAT _View_format = DXGI_FORMAT_UNKNOWN) restrict(cpu);
```

### <a name="parameters"></a>Parameter

*value_type*<br/>
Der Typ der Elemente in der Textur.

*_Rank*<br/>
Der Rang der Textur.

*_Av*<br/>
Eine D3D-Zugriffstastenansicht, in der die Textur erstellt werden soll.

*_D3D_texture*<br/>
IUnknown-Schnittstellenzeiger der D3D-Textur zum Erstellen der Textur.

*_View_format*<br/>
Das DXGI-Format, das für Ansichten verwendet werden soll, die mit dieser Textur erstellt werden. Übergeben Sie DXGI_FORMAT_UNKNOWN (Standardeinstellung), um das Format von der zugrunde liegenden Formats von _D3D_texture und die Value_type dieser Vorlage abgeleitet werden. Das bereitgestellte Format muss mit dem zugrunde liegenden Format von _D3D_texture kompatibel sein.

### <a name="return-value"></a>Rückgabewert

Eine Textur, die die bereitgestellte D3D-Textur verwendet.

##  <a name="msad4"></a>  msad4

Vergleicht einen 4-Byte-Verweiswert und einen 8-Byte-Quellwert und sammelt einen Vektor von 4 Summen. Jede Summe entspricht der maskierten Summe von absoluten Differenzen von verschiedenen Byteausrichtungen zwischen Verweiswert und Quellwert.

```
inline uint4 msad4(
    uint _Reference,
    uint2 _Source,
    uint4 _Accum) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_Reference*<br/>
Das Verweisarray von 4 Bytes in einem UINT-Wert

*_Source*<br/>
Das Quellarray von 8 Bytes in einen Vektor von zwei UINT-Werten.

*_Accum*<br/>
Ein Vektor von 4 Werten, die der maskierten Summe von absoluten Differenzen der verschiedenen Byteausrichtungen zwischen Verweiswert und Quellwert hinzugefügt werden müssen.

### <a name="return-value"></a>Rückgabewert

Gibt einen Vektor von 4 Summen zurück. Jede Summe entspricht der maskierten Summe von absoluten Differenzen von verschiedenen Byteausrichtungen zwischen Verweiswert und Quellwert.

## <a name="requirements"></a>Anforderungen

**Header:** amp_graphics.h

**Namespace:** Concurrency::graphics::direct3d

## <a name="see-also"></a>Siehe auch

[Concurrency::graphics::direct3d Namespace](concurrency-graphics-direct3d-namespace.md)
