---
title: _cgets_s, _cgetws_s
ms.date: 11/04/2016
apiname:
- _cgetws_s
- _cgets_s
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
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cgets_s
- cgets_s
- cgetws_s
- _cgetws_s
helpviewer_keywords:
- strings [C++], getting from console
- console, getting strings from
- _cgets_s function
- cget_s function
- _cgetws_s function
- cgetws_s function
ms.assetid: 38b74897-afe6-4dd9-a43f-36a3c0d72c5c
ms.openlocfilehash: 8341b775df3b9cbaececdfaa1f17e075d7c7416c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588538"
---
# <a name="cgetss-cgetwss"></a>_cgets_s, _cgetws_s

Ruft eine Zeichenfolge aus der Konsole ab. Diese Versionen von [_cgets und _cgetws](../../c-runtime-library/cgets-cgetws.md) enthalten Sicherheitserweiterungen, wie dies unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
errno_t _cgets_s(
   char *buffer,
   size_t numberOfElements,
   size_t *pSizeRead
);
errno_t _cgetws_s(
   wchar_t *buffer
   size_t numberOfElements,
   size_t *pSizeRead
);
template <size_t size>
errno_t _cgets_s(
   char (&buffer)[size],
   size_t *pSizeRead
); // C++ only
template <size_t size>
errno_t _cgetws_s(
   wchar_t (&buffer)[size],
   size_t *pSizeRead
); // C++ only
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Speicherort für Daten.

*numberOfElements*<br/>
Die Größe des Puffers in Einzelbyte- oder Breitzeichen. Hierbei handelt es sich auch um die maximale Anzahl der zu lesenden Zeichen.

*pSizeRead*<br/>
Die Anzahl der tatsächlich gelesenen Zeichen.

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert ist im Erfolgsfall „0“, andernfalls wird ein Fehlercode ausgegeben, wenn ein Fehler auftritt.

### <a name="error-conditions"></a>Fehlerbedingungen

|*buffer*|*numberOfElements*|*pSizeRead*|Zurück|Inhalt der *Puffer*|
|--------------|------------------------|-----------------|------------|--------------------------|
|**NULL**|any|any|**EINVAL**|n/v|
|Nicht **NULL**|Null|any|**EINVAL**|nicht geändert|
|Nicht **NULL**|any|**NULL**|**EINVAL**|Zeichenfolge mit der Länge 0|

## <a name="remarks"></a>Hinweise

**_cgets_s** und **_cgetws_s** lesen eine Zeichenfolge aus der Konsole, und kopieren Sie die Zeichenfolge (mit einem null-Terminator) in *Puffer*. **_cgetws_s** ist die breitzeichenversion der Funktion; andere als die Zeichengröße, das Verhalten dieser zwei Funktionen identisch ist. Die maximale Größe der zu lesenden Zeichenfolge wird als übergeben die *NumberOfElements* Parameter. Diese Größe sollte ein zusätzliches Zeichen für das abschließende Nullzeichen enthalten. Die tatsächliche Anzahl der gelesenen Zeichen befindet sich im *pSizeRead*.

Wenn während des Vorgangs oder im Zuge der Validierung der Parameter ein Fehler auftritt, wird der Handler für ungültige Parameter aufgerufen, wie dies unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und **EINVAL** zurückgegeben wird.

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht. Die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein „size“-Argument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_cgetts_s**|**_cgets_s**|**_cgets_s**|**_cgetws_s**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_cgets_s**|\<conio.h>|
|**_cgetws_s**|\<conio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Konsole und Port-E/A](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
