---
title: Concurrency::direct3d-Namespace
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::direct3d
- amprt/Concurrency::direct3d
- amp_short_vectors/Concurrency::direct3d
- amp_graphics/Concurrency::direct3d
- amp_math/Concurrency::direct3d
helpviewer_keywords:
- direct3d namespace
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
ms.openlocfilehash: 6afbd7b3a3f4280ad658c1cb9d8802cc3251d0ed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405481"
---
# <a name="concurrencydirect3d-namespace"></a>Concurrency::direct3d-Namespace

Der `direct3d`-Namespace enthält Funktionen, welche die D3D-Interoperabilität unterstützen. Dies ermöglicht die einfache Verwendung von D3D-Ressourcen zur Berechnung von AMP-Code sowie die Verwendung von in AMP erstellen Ressourcen in D3D-Code, ohne dass redundante Zwischenkopien erstellt werden. Sie können die berechnungsintensiven Abschnitte der Ihrer DirectX-Anwendungen inkrementell beschleunigen, indem Sie C++ AMP verwenden und die D3D-API für Daten nutzen, die aus AMP-Berechnungen resultieren.

## <a name="syntax"></a>Syntax

```
namespace direct3d;
```

## <a name="members"></a>Member

### <a name="classes"></a>Klassen

|Name|Beschreibung|
|----------|-----------------|
|[scoped_d3d_access_lock-Klasse](scoped-d3d-access-lock-class.md)|Ein RAII-Wrapper für eine D3D-Zugriffssperre auf einem `accelerator_view`-Objekt.|

### <a name="structures"></a>Strukturen

|Name|Beschreibung|
|----------|-----------------|
|[adopt_d3d_access_lock_t-Struktur](adopt-d3d-access-lock-t-structure.md)|Der Tagtyp, mit dem angegeben wird, dass die D3D-Zugriffssperre eher übernommen als abgerufen werden sollte.|

### <a name="functions"></a>Funktionen

|Name|Beschreibung|
|----------|-----------------|
|[abs](concurrency-direct3d-namespace-functions-amp.md#abs)|Gibt den absoluten Wert des Arguments zurück.|
|[clamp](concurrency-direct3d-namespace-functions-amp.md#clamp)|Überladen. Bindet _X an den angegebenen _Min- und _Max-Bereich|
|[countbits](concurrency-direct3d-namespace-functions-amp.md#countbits)|Zählt die Anzahl der festgelegten Bits in _X|
|[create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|Erstellt eine [Accelerator_view-Klasse](accelerator-view-class.md) von einem Zeiger auf die Schnittstelle eines Direct3D-Geräts|
|[d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|Ruft eine Sperre für eine accelerator_view ab, um D3D-Vorgänge in Ressourcen, die gemeinsam mit der accelerator_view genutzt werden, sicher ausführen zu können.|
|[d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|Versuch, ohne Blockierung die D3D-Zugriffssperre für eine accelerator_view abzurufen.|
|[d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|Gibt die D3D-Zugriffssperre für die angegebene accelerator_view frei.|
|[firstbithigh](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|Ruft den Speicherort des ersten festgelegten Bits in _X ab und arbeitet dabei vom höchsten Bit in der Reihenfolge nach unten.|
|[firstbitlow](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|Ruft den Speicherort des ersten festgelegten Bits in _X ab und arbeitet dabei vom niedrigsten Bit in der Reihenfolge nach oben.|
|[get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|Ruft die Schnittstelle des D3D-Puffers ab, die einem Array zugrunde liegt.|
|[imax](concurrency-direct3d-namespace-functions-amp.md#imax)|Vergleicht zwei Werte und gibt den größeren Wert zurück.|
|[imin](concurrency-direct3d-namespace-functions-amp.md#imin)|Vergleicht zwei Werte und gibt den kleineren Wert zurück.|
|[is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|Gibt ein boolesches Flag zurück, das angibt, ob Timeout für die angegebene "accelerator_view" deaktiviert ist.|
|[mad](concurrency-direct3d-namespace-functions-amp.md#mad)|Überladen. Führt eine arithmetische Multiplikation Operation für drei Argumente: _X \* _Y + _Z|
|[make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|Erstellt ein Array aus dem Schnittstellenzeiger eines D3D-Puffers.|
|[noise](concurrency-direct3d-namespace-functions-amp.md#noise)|Generiert mithilfe des Perlin-Noise-Algorithmus einen Zufallswert|
|[radians](concurrency-direct3d-namespace-functions-amp.md#radians)|Konvertiert _X von Grad in Bogenmaß|
|[rcp](concurrency-direct3d-namespace-functions-amp.md#rcp)|Berechnet einen schnellen, ungefähren Kehrwert des Arguments|
|[reversebits](concurrency-direct3d-namespace-functions-amp.md#reversebits)|Kehrt die Reihenfolge der Bits in _X um|
|[saturate](concurrency-direct3d-namespace-functions-amp.md#saturate)|Bindet _X im Bereich zwischen 0 und 1|
|[sign](concurrency-direct3d-namespace-functions-amp.md#sign)|Überladen. Gibt das Vorzeichen des Arguments zurück|
|[smoothstep](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|Gibt eine glatte Hermite-Interpolation zwischen 0 und 1 zurück, wenn _X im Bereich [_Min, _Max] liegt.|
|[step](concurrency-direct3d-namespace-functions-amp.md#step)|Vergleicht zwei Werte und gibt, je nachdem welcher Wert größer ist, 0 oder 1 zurück|
|[umax](concurrency-direct3d-namespace-functions-amp.md#umax)|Vergleicht zwei unsignierte Werte und gibt den größeren Wert zurück.|
|[umin](concurrency-direct3d-namespace-functions-amp.md#umin)|Vergleicht zwei unsignierte Werte und gibt den kleineren Wert zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** amp.h

**Namespace:** Parallelität

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
