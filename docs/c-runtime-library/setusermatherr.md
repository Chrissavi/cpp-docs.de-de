---
title: __setusermatherr
ms.date: 11/04/2016
api_name:
- __setusermatherr
api_location:
- msvcr80.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __setusermatherr
helpviewer_keywords:
- __setusermatherr
ms.assetid: f306818d-381a-4d68-8739-71b92bacb5ea
ms.openlocfilehash: 1dc20be40614aaeda72040496a61a6ea9df99383
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957738"
---
# <a name="__setusermatherr"></a>__setusermatherr

Gibt eine benutzerdefinierte Routine an, die anstelle der [_matherr](../c-runtime-library/reference/matherr.md)-Routine verwendet wird, um Mathematikfehler zu behandeln.

## <a name="syntax"></a>Syntax

```cpp
void __setusermatherr(
   _HANDLE_MATH_ERROR pf
   )
```

#### <a name="parameters"></a>Parameter

*pf*<br/>
Zeiger zu einer Implementierung von `_matherr`, die vom Benutzer bereitgestellt wird.

Der Typ des *pf*-Parameters ist als `typedef int (__cdecl * _HANDLE_MATH_ERROR)(struct _exception *)` deklariert.

## <a name="remarks"></a>Anmerkungen

## <a name="requirements"></a>Requirements (Anforderungen)

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__setusermatherr|matherr.c|