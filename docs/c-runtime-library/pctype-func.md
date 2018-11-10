---
title: __pctype_func
ms.date: 11/04/2016
apiname:
- __pctype_func
apilocation:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- __pctype_func
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
ms.openlocfilehash: fc0f4b0be80534744beda1fe7595293ceb002924
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444225"
---
# <a name="pctypefunc"></a>__pctype_func

Ruft einen Zeiger auf ein Array an Zeichenklassifizierungsinformationen ab.

## <a name="syntax"></a>Syntax

```cpp
const unsigned short *__pctype_func(
   )
```

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein Array an Zeichenklassifizierungsinformationen.

## <a name="remarks"></a>Hinweise

Die Informationen in der Zeichenklassifizierungstabelle sind nur zur internen Verwendung geeignet und werden von verschiedenen Funktionen verwendet, die Zeichen vom Typ `char` klassifizieren. Weitere Informationen finden Sie im `Remarks`-Abschnitt von [_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__pctype_func|ctype.h|

## <a name="see-also"></a>Siehe auch

[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)