---
title: _vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _vscprintf
- _vscprintf_l
- _vscwprintf_l
- _vscwprintf
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
apitype: DLLExport
f1_keywords:
- vscprintf_l
- vscwpeintf
- _vscwprintf
- _vsctprintf
- _vscprintf
- vscwprintf_l
- vscprintf
- _vscwprintf_l
dev_langs:
- C++
helpviewer_keywords:
- vsctprintf function
- _vscprintf_l function
- _vsctprintf_l function
- _vsctprintf function
- _vscwprintf_l function
- vscwprintf_l function
- _vscprintf function
- _vscwprintf function
- vscwprintf function
- vsctprintf_l function
- formatted text [C++]
- vscprintf function
- vscprintf_l function
ms.assetid: 1bc67d3d-21d5-49c9-ac8d-69e26b16a3c3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 959f39df33c2cdcd40a71a801ca715ab7c0eccf0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213645"
---
# <a name="vscprintf-vscprintfl-vscwprintf-vscwprintfl"></a>_vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l

Gibt die Anzahl der Zeichen in der formatierten Zeichenfolge mithilfe eines Zeigers auf eine Liste von Argumenten zurück.

## <a name="syntax"></a>Syntax

```C
int _vscprintf(
   const char *format,
   va_list argptr
);
int _vscprintf_l(
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vscwprintf(
   const wchar_t *format,
   va_list argptr
);
int _vscwprintf_l(
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>Parameter

*format*<br/>
Formatsteuerzeichenfolge.

*argptr*<br/>
Zeiger zur Liste der Argumente.

*locale*<br/>
Das zu verwendende Gebietsschema.

Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Rückgabewert

**_vscprintf** gibt die Anzahl der Zeichen, die erzeugt wird, wenn die Zeichenfolge, zeigt die Liste der Argumente, gedruckt oder an eine Datei gesendet wurde oder Puffer, die mit der angegebenen Formatierung Fehlercodes zurück. Der Rückgabewert umfasst nicht das abschließende NULL-Zeichen. **_vscwprintf** führt dieselbe Funktion für Breitzeichen.

Die Versionen dieser Funktionen mit den **_l** -Suffix sind beinahe identisch, außer dass sie den übergebenen Gebietsschemaparameter anstelle des aktuellen threadgebietsschemas Locale-Parameter verwenden.

Wenn *Format* ist ein null-Zeiger, der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, die Funktionen-1 zurück und legen Sie **Errno** zu **EINVAL**.

## <a name="remarks"></a>Hinweise

Jede *Argument* (sofern vorhanden) wird entsprechend der jeweiligen Formatangabe in konvertiert *Format*. Das Format besteht aus normalen Zeichen und hat die gleiche form und Funktion wie der *Format* Argument für [Printf](printf-printf-l-wprintf-wprintf-l.md).

> [!IMPORTANT]
> Stellen Sie sicher, dass bei *Format* eine benutzerdefinierte Zeichenfolge ist, ist es Null-Terminierung und die richtige Anzahl und Typ der Parameter. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsctprintf**|**_vscprintf**|**_vscprintf**|**_vscwprintf**|
|**_vsctprintf_l**|**_vscprintf_l**|**_vscprintf_l**|**_vscwprintf_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_vscprintf**, **_vscprintf_l**|\<stdio.h>|
|**_vscwprintf**, **_vscwprintf_l**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [vsprintf](vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md).

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf-Funktionen](../../c-runtime-library/vprintf-functions.md)<br/>
