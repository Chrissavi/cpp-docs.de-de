---
title: _com_error-Klasse
ms.date: 11/04/2016
f1_keywords:
- _com_error
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
ms.openlocfilehash: 828a1ec68fef631700d5b64e6aeeec6660acf9a8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498743"
---
# <a name="_com_error-class"></a>_com_error-Klasse

**Microsoft-spezifisch**

Ein **_com_error** -Objekt stellt eine Ausnahme Bedingung dar, die von den Fehler Behandlungs-Wrapper Funktionen in den Header Dateien erkannt wird, die aus der Typbibliothek oder einer der com-Unterstützungs Klassen generiert wurden. Die **_com_error** -Klasse kapselt den HRESULT-Fehlercode und `IErrorInfo Interface` alle zugeordneten Objekte.

### <a name="construction"></a>Konstruktion

|||
|-|-|
|[_com_error](../cpp/com-error-com-error.md)|Erstellt ein **_com_error** -Objekt.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator =](../cpp/com-error-operator-equal.md)|Weist ein vorhandenes **_com_error** -Objekt einem anderen zu.|

### <a name="extractor-functions"></a>Funktionen des Extrahierungsprogramms

|||
|-|-|
|[Fehler](../cpp/com-error-error.md)|Ruft das HRESULT ab, das an den Konstruktor übergeben wird.|
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Ruft das `IErrorInfo`-Objekt ab, das an den Konstruktor übergeben wurde.|
|[WCode](../cpp/com-error-wcode.md)|Ruft den 16-Bit-Fehlercode ab, der dem gekapselten HRESULT zugeordnet ist.|

### <a name="ierrorinfo-functions"></a>IErrorInfo-Funktionen

|||
|-|-|
|[Beschreibung](../cpp/com-error-description.md)|Ruft die `IErrorInfo::GetDescription`-Funktion auf.|
|[HelpContext](../cpp/com-error-helpcontext.md)|Ruft die `IErrorInfo::GetHelpContext`-Funktion auf.|
|[HelpFile](../cpp/com-error-helpfile.md)|Ruft die `IErrorInfo::GetHelpFile`-Funktion auf.|
|[Quelle](../cpp/com-error-source.md)|Ruft die `IErrorInfo::GetSource`-Funktion auf.|
|[GUID](../cpp/com-error-guid.md)|Ruft die `IErrorInfo::GetGUID`-Funktion auf.|

### <a name="format-message-extractor"></a>FormatMessage-Extractor

|||
|-|-|
|[ErrorMessage](../cpp/com-error-errormessage.md)|Ruft die Zeichen folgen Meldung für HRESULT ab, die im **_com_error** -Objekt gespeichert ist.|

### <a name="exepinfowcode-to-hresult-mappers"></a>ExepInfo.wCode für HRESULT-Zuordnungen

|||
|-|-|
|[Hresulttowcode](../cpp/com-error-hresulttowcode.md)|Ordnet 32-Bit-HRESULT einem 16- `wCode`Bit-Wert zu.|
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|Ordnet ein 16- `wCode` Bit-32-Bit-HRESULT zu.|

**Ende Microsoft-spezifisch**

## <a name="requirements"></a>Anforderungen

**Header:** \<comdef.h>

`Lib:`"comsuppw. lib" oder "comsuppwd. lib" (siehe [/Zc: wchar_t (wchar_t ist](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) der systemeigene Typ), um weitere Informationen zu erhalten)

## <a name="see-also"></a>Siehe auch

[Compilerklassen für COM-Unterstützung](../cpp/compiler-com-support-classes.md)<br/>
[IErrorInfo-Schnittstelle](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)