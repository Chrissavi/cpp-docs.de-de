---
title: fma, fmaf, fmal | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- fma
- fmaf
- fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
dev_langs:
- C++
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b28009a9c3cc4edceb9032660a0c2a71916dfb2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401476"
---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal

Multipliziert zwei Werte, addiert einen dritten und rundet das Ergebnis, ohne Genauigkeit aufgrund von vorherigen Rundungen einzubüßen.

## <a name="syntax"></a>Syntax

```C
double fma(
   double x,
   double y,
   double z
);

float fma(
   float  x,
   float  y,
   float z
); //C++ only

long double fma(
   long double  x,
   long double  y,
   long double z
); //C++ only

float fmaf(
   float  x,
   float  y,
   float z
);

long double fmal(
   long double  x,
   long double  y,
   long double z
);

```

### <a name="parameters"></a>Parameter

*w*<br/>
Der erste zu multiplizierende Wert.

*y*<br/>
Der zweite zu multiplizierende Wert.

*z*<br/>
Der hinzuzufügende Wert.

## <a name="return-value"></a>Rückgabewert

Gibt `(x * y) + z`zurück. Der Rückgabewert wird dann mit dem aktuellen Rundungsformat gerundet.

Andernfalls wird möglicherweise einer der folgenden Werte zurückgeben:

|Problem|Zurück|
|-----------|------------|
|*X* = UNENDLICH, *y* = 0 oder<br /><br /> *X* = 0, *y* = UNENDLICH|NaN|
|*X* oder *y* = genaue ± UNENDLICH, *z* = UNENDLICH mit umgekehrtem Vorzeichen|NaN|
|*X* oder *y* = "NaN"|NaN|
|keine (*x* = 0, *y*= unbegrenzt) und *z* = "NaN"<br /><br /> keine (*x*= undefiniert *y*= 0) und *z* = "NaN"|NaN|
|Überlaufbereichsfehler|±HUGE_VAL, ±HUGE_VALF oder ±HUGE_VALL|
|Unterlaufbereichsfehler|Richtige Wert nach dem Runden|

Fehler werden gemäß der Angaben in [_matherr](matherr.md) gemeldet.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Fma** verwenden und zurückgeben **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Fma** immer Double und gibt eine **doppelte**.

Diese Funktion berechnet den Wert mit unendlicher Genauigkeit und rundet das endgültige Ergebnis dann.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**FMA**, **Fmaf**, **Fmal**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
