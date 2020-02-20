---
title: _setmbcp
ms.date: 11/04/2016
api_name:
- _setmbcp
api_location:
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
- api-ms-win-crt-locale-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _setmbcp
- setmbcp
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
ms.openlocfilehash: a3408f04eb60a33a84c628c989ebc9c4c4a261df
ms.sourcegitcommit: f38f770bfda1c174d2b81fabda7c893b15bd83a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77473875"
---
# <a name="_setmbcp"></a>_setmbcp

Legt eine neue Multibyte-Codepage fest.

## <a name="syntax"></a>Syntax

```C
int _setmbcp(
   int codepage
);
```

### <a name="parameters"></a>Parameter

*codepage*<br/>
Neue Codepageeinstellung für gebietsschemaunabhängige Multibyte-Routinen.

## <a name="return-value"></a>Rückgabewert

Gibt 0 zurück, wenn die Codepage erfolgreich festgelegt wurde. Wenn für *Codepage*ein ungültiger Codepage-Wert angegeben wird, wird-1 zurückgegeben, und die Codepage-Einstellung ist unverändert. Legt **errno** auf **EINVAL** fest, wenn ein Fehler bei der Speicher Belegung auftritt.

## <a name="remarks"></a>Hinweise

Die **_setmbcp** -Funktion gibt eine neue Multibytezeichen-Codepage an. Standardmäßig legt das Laufzeitsystem automatisch die Multibyte-Codepage auf die Systemstandard-ANSI-Codepage fest. Die Multibyte-Codepageeinstellung wirkt sich auf alle Multibyteroutinen auf, die nicht vom Gebietsschema abhängig sind. Es ist jedoch möglich, **_setmbcp** anzuweisen, die Codepage zu verwenden, die für das aktuelle Gebiets Schema definiert ist (Weitere Informationen finden Sie in der folgenden Liste der Manifest-Konstanten und der zugehörigen verhaltensergebnisse). Eine Liste der Multibyteroutinen, die von der Gebietsschema-Codepage und nicht von der Multibyte-Codepage abhängig sind, finden Sie unter [Interpretation von Multybite-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).

Die Multibyte-Codepage hat auch Auswirkungen auf die Multibyteverarbeitung durch die folgenden Routinen der Laufzeitbibliothek:

||||
|-|-|-|
|[_exec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[_spawn functions](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

Außerdem verarbeiten alle Lauf Zeit Bibliotheks Routinen, die Multibytezeichen- *argv* -oder *envp* -Programm Argumente als Parameter (z. b. die **_exec** -und **_spawn** Familien) empfangen, diese Zeichen folgen entsprechend der Multibytezeichen-Codepage. Aus diesem Grund werden diese Routinen auch durch einen **aufrufs_setmbcp** beeinflusst, der die Multibytezeichen-Codepage ändert.

Das *Codepage* -Argument kann auf einen der folgenden Werte festgelegt werden:

- **_MB_CP_ANSI** Verwenden Sie die ANSI-Codepage, die vom Betriebssystem beim Programmstart abgerufen wird.

- **_MB_CP_LOCALE** Verwenden Sie die Codepage des aktuellen Gebiets Schemas, die Sie aus einem vorherigen-Befehl von [setlocale](setlocale-wsetlocale.md)abgerufen haben

- **_MB_CP_OEM** OEM-Codepage verwenden, die vom Betriebssystem beim Programmstart abgerufen wird.

- **_MB_CP_SBCS** Einzel Byte-Codepage verwenden. Wenn die Codepage auf **_MB_CP_SBCS**festgelegt ist, gibt eine Routine wie [_ismbblead](ismbblead-ismbblead-l.md) immer false zurück.

- **_MB_CP_UTF8** Verwenden Sie UTF-8.  Wenn die Codepage auf **_MB_CP_UTF8**festgelegt ist, gibt eine Routine wie [_ismbblead](ismbblead-ismbblead-l.md) immer false zurück.

- Jeder andere gültige Codepage-Wert, unabhängig davon, ob der Wert eine ANSI-, OEM-oder andere vom Betriebssystem unterstützte Codepage ist (mit Ausnahme von UTF-7, die nicht unterstützt wird).

## <a name="requirements"></a>Voraussetzungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_setmbcp**|\<mbctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_getmbcp](getmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
