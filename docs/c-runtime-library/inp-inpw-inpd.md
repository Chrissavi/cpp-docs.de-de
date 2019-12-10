---
title: INP, _inp, inpw, _inpw, _inpd
description: Beschreibt die veralteten und entfernten inp-, _inp-, inpw-, _inpw-und _inpd-Funktionen der Microsoft C-Lauf Zeit Bibliothek (CRT).
ms.date: 12/09/2019
api_name:
- inp
- inpw
- _inp
- _inpw
- _inpd
api_location:
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- inp
- inpw
- _inp
- _inpw
- _inpd
helpviewer_keywords:
- inp function
- inpw function
- ports, I/O routines
- inpd function
- _inp function
- _inpd function
- I/O [CRT], port
- _inpw function
ms.assetid: 5d9c2e38-fc85-4294-86d5-7282cc02d1b3
ms.openlocfilehash: 48e0e58d2886c5a8bb90a86c81cb785d364666e8
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988712"
---
# <a name="inp-_inp-inpw-_inpw-_inpd"></a>INP, _inp, inpw, _inpw, _inpd

Eingaben, von einem Port, einem Byte (`inp``_inp`), einem Wort (`inpw`, `_inpw`) oder einem doppelten Wort (`_inpd`).

> [!IMPORTANT]
> Diese Funktionen sind veraltet. Von Visual Studio 2015 an sind sie nicht in der CRT verfügbar.  
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```cpp
int _inp(
   unsigned short port
);
unsigned short _inpw(
   unsigned short port
);
unsigned long _inpd(
   unsigned short port
);
```

### <a name="parameters"></a>Parameters

*Port*\
E/A-Portnummer.

## <a name="return-value"></a>Rückgabewert

Die Funktionen geben das aus `port`gelesene Byte, Wort oder Doppelwort zurück. Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Die Funktionen `_inp`, `_inpw`und `_inpd` lesen aus dem angegebenen Eingangsport jeweils ein Byte, ein Wort und ein Doppelwort. Der Eingabewert kann jede beliebige kurze ganze Zahl ohne Vorzeichen im Bereich von 0 bis 65.535 sein.

Da diese Funktionen direkt aus einem E/A-Port lesen, können sie nicht im Benutzercode verwendet werden.

Die `inp`-und `inpw` Namen sind älter, als veraltet markierte Namen für die Funktionen `_inp` und `_inpw`. Weitere Informationen finden Sie unter [POSIX-Funktionsnamen](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).

## <a name="requirements"></a>-Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`_inp`|\<conio.h>|
|`_inpw`|\<conio.h>|
|`_inpd`|\<conio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Compatibility](../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Console and Port I/O (Konsole und Port-E/A)](../c-runtime-library/console-and-port-i-o.md)\
[outp, outpw, _outp _outpw, _outpd](../c-runtime-library/outp-outpw-outpd.md)
