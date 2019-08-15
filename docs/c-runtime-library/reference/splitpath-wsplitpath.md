---
title: _splitpath, _wsplitpath
ms.date: 11/04/2016
apiname:
- _wsplitpath
- _splitpath
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
helpviewer_keywords:
- _splitpath function
- pathnames
- wsplitpath function
- splitpath function
- _wsplitpath function
- tsplitpath function
- path names
- _tsplitpath function
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
ms.openlocfilehash: d5aab68524c0833bff0e09927587c0362c5194f9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500995"
---
# <a name="_splitpath-_wsplitpath"></a>_splitpath, _wsplitpath

Unterteilen Sie einen Pfadnamen in Komponenten. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

## <a name="syntax"></a>Syntax

```C
void _splitpath(
   const char *path,
   char *drive,
   char *dir,
   char *fname,
   char *ext
);
void _wsplitpath(
   const wchar_t *path,
   wchar_t *drive,
   wchar_t *dir,
   wchar_t *fname,
   wchar_t *ext
);
```

### <a name="parameters"></a>Parameter

*path*<br/>
Vollständiger Pfad

*Antrie*<br/>
Laufwerk Buchstabe, gefolgt von einem Doppelpunkt ( **:** ). Sie können **null** für diesen Parameter übergeben, wenn Sie den Laufwerk Buchstaben nicht benötigen.

*dir*<br/>
Verzeichnispfad, einschl. nachstehender Schrägstrich. Schrägstriche ( **/** ), umgekehrte Schrägstriche ( **\\** ) oder beides können verwendet werden. Sie können **null** für diesen Parameter übergeben, wenn Sie den Verzeichnispfad nicht benötigen.

*fname*<br/>
Basisdateiname (ohne Erweiterung). Sie können **null** für diesen Parameter übergeben, wenn Sie den Dateinamen nicht benötigen.

*Antrags*<br/>
Erweiterung des Datei namens, einschließlich des führenden Zeitraums ( **.** ). Sie können **null** für diesen Parameter übergeben, wenn Sie die Dateinamenerweiterung nicht benötigen.

## <a name="remarks"></a>Hinweise

Die **_splitpath** -Funktion unterteilt einen Pfad in seine vier Komponenten. **_splitpath** verarbeitet nach Bedarf automatisch Multibytezeichen-Zeichen folgen Argumente und erkennt multibytezeichensequenzen gemäß der derzeit verwendeten Multibytezeichen-Codepage. **_wsplitpath** ist eine breit Zeichen Version von **_splitpath**. die Argumente für **_wsplitpath** sind Zeichen folgen mit breit Zeichen. Anderenfalls verhalten sich diese Funktionen identisch.

**Sicherheitshinweis:** Diese Funktionen stellen eine mögliche Bedrohung aufgrund eines Pufferüberlaufproblems dar. Pufferüberlaufprobleme werden häufig bei Systemangriffen eingesetzt, da sie zu einer unbefugten Ausweitung der Berechtigungen führen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/win32/SecBP/avoiding-buffer-overruns). Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath**|**_splitpath**|**_splitpath**|**_wsplitpath**|

Jede Komponente des vollständigen Pfads wird in einem separaten Puffer gespeichert. Die Manifest-Konstanten **_MAX_DRIVE**, **_MAX_DIR**, **_MAX_FNAME**und **_MAX_EXT** (in stdlib definiert). H) geben Sie die maximale Größe für jede Datei Komponente an. Dateikomponenten, die größer als die entsprechenden Manifestkonstanten sind, können zur Beschädigung des Heaps führen.

Jeder Puffer muss so groß wie die entsprechende Manifestkonstante sein, damit ein potenzieller Pufferüberlauf vermieden werden kann.

In der folgenden Tabelle werden die Werte der Manifestkonstanten aufgelistet.

|Name|Wert|
|----------|-----------|
|**_MAX_DRIVE**|3|
|**_MAX_DIR**|256|
|**_MAX_FNAME**|256|
|**_MAX_EXT**|256|

Wenn der vollständige Pfad keine Komponente (z. b. ein Dateiname) enthält, weist **_splitpath** den entsprechenden Puffern leere Zeichen folgen zu.

Sie können **null** an **_splitpath** übergeben, wenn Sie nicht über den *Pfad* verfügen, den Sie nicht benötigen.

Wenn *path* **null**ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird **errno** auf **EINVAL** festgelegt, und die Funktion gibt **EINVAL**zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_splitpath**|\<stdlib.h>|
|**_wsplitpath**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe Beispiel für [_makepath](makepath-wmakepath.md).

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
