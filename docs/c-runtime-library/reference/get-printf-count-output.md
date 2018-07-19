---
title: _get_printf_count_output | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_printf_count_output
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_printf_count_output
- _get_printf_count_output
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 216df8d973f391db2b6114d9bbcb50dcf509c5b5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398365"
---
# <a name="getprintfcountoutput"></a>_get_printf_count_output

Gibt an, ob [Printf, _printf_l, Wprintf _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-Familie Funktionen unterstützen die **%n** Format.

## <a name="syntax"></a>Syntax

```C
int _get_printf_count_output();
```

## <a name="return-value"></a>Rückgabewert

Ungleich 0, If **%n** wird unterstützt, 0, wenn **%n** wird nicht unterstützt.

## <a name="remarks"></a>Hinweise

Wenn **%n** wird nicht unterstützt (Standard), auftreten **%n** in der Formatzeichenfolge eines der **Printf** Funktionen werden der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn **%n** -Unterstützung aktiviert ist (finden Sie unter [_set_printf_count_output](set-printf-count-output.md)) dann **%n** verhält sich wie beschrieben in [Syntax der Formatangabe: Printf und Wprintf Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_get_printf_count_output**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [_set_printf_count_output](set-printf-count-output.md).

## <a name="see-also"></a>Siehe auch

[_set_printf_count_output](set-printf-count-output.md)<br/>
