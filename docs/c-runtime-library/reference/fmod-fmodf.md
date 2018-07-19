---
title: Fmod, Fmodf, Fmodl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fmod
- fmodf
- fmodl
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fmod
- _fmodl
- fmodf
dev_langs:
- C++
helpviewer_keywords:
- calculating floating-point remainders
- fmodf function
- fmodl function
- fmod function
- floating-point numbers, calculating remainders
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f6cc8cc10c026c5ecd621657c556da883c187f5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399035"
---
# <a name="fmod-fmodf-fmodl"></a>Fmod, Fmodf, fmodl

Berechnet den Gleitkommarest.

## <a name="syntax"></a>Syntax

```C
double fmod(
   double x,
   double y
);
float fmod(
   float x,
   float y
);  // C++ only
long double fmod(
   long double x,
   long double y
);  // C++ only
float fmodf(
   float x,
   float y
);
long double fmodl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Parameter

*X*, *y*<br/>
Gleitkommawerte.

## <a name="return-value"></a>Rückgabewert

**Fmod** gibt den Gleitkommarest von *x* / *y*. Wenn der Wert der *y* ist "0,0", " **Fmod** gibt ein stilles NaN zurück. Informationen zur Darstellung einer stillen NaN durch die **Printf** Familie finden Sie unter [Printf](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Hinweise

Die **Fmod** -Funktion berechnet den Gleitkommarest *f* von *x* / *y* so, dass *x*  =  *ich* * *y* + *f*, wobei *ich* ist eine ganze Zahl *f* hat die gleichen Vorzeichen wie *x*, und den absoluten Wert des *f* ist kleiner als der Absolute Wert des *y*.

C++ das Überladen zulässt, sodass Sie Überladungen von aufrufen können **Fmod** verwenden und zurückgeben **"float"** und **lange** **doppelte** Werte. In einem C-Programm **Fmod** immer zwei **doppelte** Argumente und gibt eine **doppelte**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**Fmod**, **Fmodf**, **Fmodl**|\<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fmod.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = fmod( w, x );
   printf( "The remainder of %.2f / %.2f is %f\n", w, x, z );
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[_CIfmod](../../c-runtime-library/cifmod.md)<br/>
