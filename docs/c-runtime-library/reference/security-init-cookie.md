---
title: __security_init_cookie
ms.date: 11/04/2016
apiname:
- __security_init_cookie
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
- security_init_cookie
- __security_init_cookie
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
ms.openlocfilehash: c7b25e05b4574a7b397cd07d55000a5e53db58f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573614"
---
# <a name="securityinitcookie"></a>__security_init_cookie

Initialisiert das globale Sicherheitscookie.

## <a name="syntax"></a>Syntax

```C
void __security_init_cookie(void);
```

## <a name="remarks"></a>Hinweise

Das globale Sicherheitscookie wird zum Schutz vor Pufferüberlauf in dem Code verwendet, der mit [/GS (Puffer-Sicherheitsüberprüfung)](../../build/reference/gs-buffer-security-check.md) kompiliert wurde, sowie in Code mit Ausnahmebehandlung. Beim Einstieg in eine vor Pufferüberlauf geschützte Funktion wird das Cookie auf dem Stapel abgelegt, und bei Funktionsende wird der Wert auf dem Stapel mit dem globalen Cookie verglichen. Jeglicher Unterschied zwischen diesen Werten weist darauf hin, dass ein Pufferüberlauf eingetreten ist. Das Programm wird daraufhin sofort beendet.

In der Regel **"__security_init_cookie"** wird von der CRT aufgerufen, wenn es initialisiert wird. Wenn Sie die CRT-Initialisierung umgehen, z. B. bei Verwendung von [/Entry](../../build/reference/entry-entry-point-symbol.md) zum Angeben eines einstiegpunkts – Sie aufrufen müssen **"__security_init_cookie"** selbst. Wenn **"__security_init_cookie"** nicht aufgerufen wird, das globale Sicherheitscookie auf den Standardwert festgelegt ist, und Schutz vor Pufferüberlauf ist beeinträchtigt. Da ein Angreifer diesen Cookie-Standardwert zum der pufferüberlaufprüfungen nutzen kann, es wird empfohlen, dass Sie immer Aufrufen **"__security_init_cookie"** beim Definieren Ihres eigenen Einstiegspunkts.

Der Aufruf von **"__security_init_cookie"** müssen vorgenommen werden, bevor eine vor Pufferüberlauf geschützte Funktion eingegeben wird; andernfalls wird ein unechter Pufferüberlauf erkannt. Weitere Informationen finden Sie unter [C-Laufzeitfehler R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).

## <a name="example"></a>Beispiel

Beispiele finden Sie unter [C-Laufzeitfehler R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**__security_init_cookie**|\<process.h>|

**"__security_init_cookie"** ist eine Microsoft-Erweiterung für die standard-C-Laufzeitbibliothek. Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Microsoft Security Response Center](https://www.microsoft.com/msrc?rtc=1)
