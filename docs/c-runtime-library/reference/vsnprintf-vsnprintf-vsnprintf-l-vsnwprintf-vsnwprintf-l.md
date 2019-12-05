---
title: vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l
ms.date: 11/04/2016
api_name:
- _vsnprintf
- _vsnprintf_l
- _vsnwprintf
- _vsnwprintf_l
- _vsnprintf
- _vsnprintf;
- vsnprintf; _vsnprintf
- _vsnwprintf;
- _vsnprintf_l;
- _vsnwprintf_l;
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
- ntoskrnl.exe
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _vsnprintf
- _vsnwprintf
- _vsntprintf
- vsnprintf
- stdio/vsnprintf
- stdio/_vsnprintf
- stdio/_vsnprintf_l
- stdio/_vsnwprintf
- stdio/_vsnwprintf_l
- _vsnprintf_l
- _vsnwprintf_l
helpviewer_keywords:
- vsntprintf function
- _vsnwprintf_l function
- vsnwprintf_l function
- vsntprintf_l function
- _vsntprintf function
- _vsnprintf_l function
- vsnprintf function
- _vsntprintf_l function
- vsnprintf_l function
- _vsnwprintf function
- _vsnprintf function
- formatted text [C++]
- vsnwprintf function
ms.assetid: a97f92df-c2f8-4ea0-9269-76920d2d566a
ms.openlocfilehash: abe34dc0f3baf9bdc63e0314ac70af3783d2bd9a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857709"
---
# <a name="vsnprintf-_vsnprintf-_vsnprintf_l-_vsnwprintf-_vsnwprintf_l"></a>vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l

Schreiben von formatierter Ausgabe mithilfe eines Zeigers, der auf eine Liste von Argumenten zeigt. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md).

## <a name="syntax"></a>Syntax

```C
int vsnprintf(
   char *buffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf(
   char *buffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_l(
   char *buffer,
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vsnwprintf(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   va_list argptr
);
int _vsnwprintf_l(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
template <size_t size>
int vsnprintf(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnprintf(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnprintf_l(
   char (&buffer)[size],
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf_l(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
); // C++ only
```

### <a name="parameters"></a>Parameters

*buffer*<br/>
Speicherort für die Ausgabe.

*count*<br/>
Maximale Anzahl der zu schreibenden Zeichen.

*format*<br/>
Formatangabe.

*argptr*<br/>
Zeiger zur Liste der Argumente.

*locale*<br/>
Das zu verwendende Gebietsschema.

Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Rückgabewert

Die **vsnprintf** -Funktion gibt die Anzahl der geschriebenen Zeichen zurück. das abschließende Null-Zeichen wird dabei nicht gezählt. Wenn die von *count* angegebene Puffergröße nicht ausreichend groß ist, um die durch *Format* und *argptr*angegebene Ausgabe zu enthalten, entspricht der Rückgabewert von **vsnprintf** der Anzahl der Zeichen, die geschrieben werden, ohne das NULL-Zeichen zu zählen, wenn die *Anzahl* ausreichend groß wäre. Wenn der Rückgabewert größer als *count* -1 ist, wurde die Ausgabe abgeschnitten. Der Rückgabewert „-1“ gibt an, dass ein Codierungsfehler aufgetreten ist.

Sowohl **_vsnprintf** -als auch **_vsnwprintf** -Funktion geben die Anzahl der geschriebenen Zeichen zurück, wenn die Anzahl der zu schreibenden Zeichen kleiner oder gleich *der Anzahl ist.* Wenn die Anzahl der zu schreibenden Zeichen größer als *count*ist, geben diese Funktionen-1 zurück, um anzugeben, dass die Ausgabe abgeschnitten wurde.

Der von allen diesen Funktionen zurückgegebene Wert enthält nicht das abschließende Zeichen NULL, unabhängig davon, ob es geschrieben wurde oder nicht. Wenn *count* 0 (null) ist, ist der zurückgegebene Wert die Anzahl von Zeichen, die von den Funktionen geschrieben werden, ohne abschließende NULL-Werte. Sie können dieses Ergebnis dazu verwenden, ausreichend Pufferspeicher für die Zeichenfolge und dessen abschließendes NULL-Zeichen zuzuordnen, und die Funktion dann erneut aufrufen, um den Puffer zu füllen.

Wenn *Format* **null**ist, oder wenn der Puffer **null** und *count* ungleich 0 (null) ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen-1 zurück und legen **errno** auf **EINVAL**fest.

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen nimmt einen Zeiger auf eine Argumentliste, formatiert die Daten und schreibt bis zum *zählen* von Zeichen in den Speicher, auf den von *buffer*verwiesen wird. Die **vsnprintf** -Funktion schreibt immer einen NULL-Terminator, selbst wenn die Ausgabe abgeschnitten wird. Wenn **_vsnprintf** und **_vsnwprintf**verwendet werden, wird der Puffer nur dann mit Null beendet, wenn am Ende Platz vorhanden ist (d. h., wenn die Anzahl der zu schreibenden Zeichen kleiner als *die Anzahl ist).*

> [!IMPORTANT]
> Um bestimmte Arten von Sicherheitsrisiken zu verhindern, stellen Sie sicher, dass das *Format* keine benutzerdefinierte Zeichenfolge ist. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/win32/SecBP/avoiding-buffer-overruns).

> [!NOTE]
> Um sicherzustellen, dass genügend Platz für das abschließende Null-Zeichen beim Aufrufen von **_vsnprintf**, **_vsnprintf_l**, **_vsnwprintf** und **_vsnwprintf_l**vorhanden ist, stellen Sie sicher, dass die *Anzahl* streng kleiner als die Pufferlänge ist, und initialisieren Sie den Puffer vor dem Aufrufen der Funktion auf NULL.
>
> Da **vsnprintf** immer den abschließenden NULL-Wert schreibt, kann der *count* -Parameter gleich der Größe des Puffers sein.

Beginnend mit der ucrt in Visual Studio 2015 und Windows 10 ist **vsnprintf** nicht mehr identisch mit **_vsnprintf**. Die **vsnprintf** -Funktion entspricht dem C99-Standard. **_vnsprintf** wird aus Gründen der Abwärtskompatibilität mit älteren Visual Studio-Code beibehalten.

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch den Gebiets Schema Parameter, der anstelle des aktuellen Thread Gebiets Schemas übergeben wurde.

In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsntprintf**|**_vsnprintf**|**_vsnprintf**|**_vsnwprintf**|
|**_vsntprintf_l**|**_vsnprintf_l**|**_vsnprintf_l**|**_vsnwprintf_l**|

## <a name="requirements"></a>-Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|-------------|---------------------------|-------------------------------|
|**vsnprintf**, **_vsnprintf**, **_vsnprintf_l**|\<stdio.h>|\<stdio.h> oder \<cstdio>|
|**_vsnwprintf**, **_vsnwprintf_l**|\<stdio.h> oder \<wchar.h>|\<stdio.h>, \<wchar.h>, \<cstdio> oder \<cwchar>|

Die Funktionen **_vsnprintf**, **_vsnprintf_l**, **_vsnwprintf** und **_vsnwprintf_l** sind Microsoft-spezifisch. Zusätzliche Informationen zur Kompatibilität finden Sie unter [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_vsnwprintf.c
// compile by using: cl /W3 crt_vsnwprintf.c

// To turn off error C4996, define this symbol:
#define _CRT_SECURE_NO_WARNINGS

#include <stdio.h>
#include <wtypes.h>

#define BUFFCOUNT (10)

void FormatOutput(LPCWSTR formatstring, ...)
{
    int nSize = 0;
    wchar_t buff[BUFFCOUNT];
    memset(buff, 0, sizeof(buff));
    va_list args;
    va_start(args, formatstring);
    // Note: _vsnwprintf is deprecated; consider vsnwprintf_s instead
    nSize = _vsnwprintf(buff, BUFFCOUNT - 1, formatstring, args); // C4996
    wprintf(L"nSize: %d, buff: %ls\n", nSize, buff);
    va_end(args);
}

int main() {
    FormatOutput(L"%ls %ls", L"Hi", L"there");
    FormatOutput(L"%ls %ls", L"Hi", L"there!");
    FormatOutput(L"%ls %ls", L"Hi", L"there!!");
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: -1, buff: Hi there!
```

Das Verhalten ändert sich, wenn Sie stattdessen „vsnprintf“ zusammen mit Parametern mit schmaler Zeichenfolge verwenden. Der *count* -Parameter kann die gesamte Größe des Puffers sein, und der Rückgabewert ist die Anzahl der Zeichen, die geschrieben worden wären, wenn die *Anzahl* groß genug wäre:

## <a name="example"></a>Beispiel

```C
// crt_vsnprintf.c
// compile by using: cl /W4 crt_vsnprintf.c
#include <stdio.h>
#include <stdarg.h> // for va_list, va_start
#include <string.h> // for memset

#define BUFFCOUNT (10)

void FormatOutput(char* formatstring, ...)
{
    int nSize = 0;
    char buff[BUFFCOUNT];
    memset(buff, 0, sizeof(buff));
    va_list args;
    va_start(args, formatstring);
    nSize = vsnprintf(buff, sizeof(buff), formatstring, args);
    printf("nSize: %d, buff: %s\n", nSize, buff);
    va_end(args);
}

int main() {
    FormatOutput("%s %s", "Hi", "there");   //  8 chars + null
    FormatOutput("%s %s", "Hi", "there!");  //  9 chars + null
    FormatOutput("%s %s", "Hi", "there!!"); // 10 chars + null
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: 10, buff: Hi there!
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf-Funktionen](../../c-runtime-library/vprintf-functions.md)<br/>
[Syntax der Formatangabe: printf- und wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
