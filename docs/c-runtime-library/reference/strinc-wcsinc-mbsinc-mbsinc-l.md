---
title: _strinc, _wcsinc, _mbsinc, _mbsinc_l
ms.date: 11/04/2016
apiname:
- _mbsinc
- _wcsinc
- _mbsinc_l
- _strinc
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsinc_l
- _strinc
- strinc
- _mbsinc
- _wcsinc
- wcsinc
- mbsinc
- _mbsinc_l
helpviewer_keywords:
- _mbsinc function
- wcsinc function
- mbsinc_l function
- _strinc function
- strinc function
- _mbsinc_l function
- mbsinc function
- _wcsinc function
- _tcsinc function
- tcsinc function
ms.assetid: 54685943-8e2c-45e9-a559-2d94930dc6b4
ms.openlocfilehash: dae14fc7b66b9be4e1016c5409a93cd172691fed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365209"
---
# <a name="strinc-wcsinc-mbsinc-mbsincl"></a>_strinc, _wcsinc, _mbsinc, _mbsinc_l

Versetzt einen Zeichenfolgenzeiger um ein Zeichen nach vorn.

> [!IMPORTANT]
> **_mbsinc** und **_mbsinc_l** kann nicht verwendet werden, in Anwendungen, die in der Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
char *_strinc(
   const char *current,
   _locale_t locale
);
wchar_t *_wcsinc(
   const wchar_t *current,
   _locale_t locale
);
unsigned char *_mbsinc(
   const unsigned char *current
);
unsigned char *_mbsinc_l(
   const unsigned char *current,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*current*<br/>
Zeichenzeiger.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen gibt einen Zeiger auf das Zeichen, die unmittelbar folgt *aktuelle*.

## <a name="remarks"></a>Hinweise

Die **_mbsinc** Funktion gibt einen Zeiger auf das erste Byte des multibytezeichens, die unmittelbar folgt *aktuelle*. **_mbsinc** erkennt multibytezeichensequenzen gemäß der [multibyte-Codepage](../../c-runtime-library/code-pages.md) , der sich derzeit in Verwendung; **_mbsinc_l** ist identisch, verwendet jedoch stattdessen den Gebietsschemaparameter, der übergeben wird. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Die Funktion für generischen Text **_tcsinc**in Tchar.h, Zuordnungen, die definierte **_mbsinc** Wenn **_MBCS** definiert wurde, oder **_wcsinc** Wenn **_UNICODE** definiert wurde. Andernfalls **_tcsinc** ordnet **_strinc**. **_strinc** und **_wcsinc** sind Single-Byte-Zeichen und Breitzeichen von **_mbsinc**. **_strinc** und **_wcsinc** werden nur für diese Zuordnung bereitgestellt und sollte nicht anderweitig verwendet werden. Weitere Informationen finden Sie unter [Verwenden von Zuordnungen für generischen Text](../../c-runtime-library/using-generic-text-mappings.md) und [Textzuordnungen für generischen Text](../../c-runtime-library/generic-text-mappings.md).

Wenn *aktuelle* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Diese Funktion gibt zurück, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **EINVAL** und **Errno** zu **EINVAL**.

> [!IMPORTANT]
> Diese Funktionen sind möglicherweise für Pufferüberlaufrisiken anfällig. Pufferüberläufe können für Systemangriffe eingesetzt werden, da sie zu einer unbefugten Ausweitung der Berechtigungen führen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/desktop/SecBP/avoiding-buffer-overruns).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_mbsinc**|\<mbstring.h>|
|**_mbsinc_l**|\<mbstring.h>|
|**_strinc**|\<tchar.h>|
|**_wcsinc**|\<tchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strdec, _wcsdec, _mbsdec, _mbsdec_l](strdec-wcsdec-mbsdec-mbsdec-l.md)<br/>
[_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)<br/>
[_strninc, _wcsninc, _mbsninc, _mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>
