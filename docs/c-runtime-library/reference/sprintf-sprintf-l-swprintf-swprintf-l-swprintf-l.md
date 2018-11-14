---
title: sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l
ms.date: 11/04/2016
apiname:
- __swprintf_l
- sprintf
- _sprintf_l
- _swprintf_l
- swprintf
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
- ntdll.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _stprintf_l
- __swprintf_l
- sprintf_l
- swprintf
- _sprintf_l
- sprintf
- _stprintf
- stprintf_l
helpviewer_keywords:
- _swprintf_l function
- _stprintf function
- __swprintf_l function
- stprintf function
- sprintf function
- _sprintf_l function
- _stprintf_l function
- swprintf function
- strings [C++], writing to
- _CRT_NON_CONFORMING_SWPRINTFS
- swprintf_l function
- stprintf_l function
- sprintf_l function
- formatted text [C++]
ms.assetid: f6efe66f-3563-4c74-9455-5411ed939b81
ms.openlocfilehash: 875cd5eca56511c2b421584766584c0c974cd775
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521868"
---
# <a name="sprintf-sprintfl-swprintf-swprintfl-swprintfl"></a>sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l

Schreiben Sie formatierte Daten in eine Zeichenfolge. Sicherere Versionen einiger dieser Funktionen sind verfügbar; siehe [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md). Die sicheren Versionen **Swprintf** und **_swprintf_l** akzeptieren keine *Anzahl* Parameter.

## <a name="syntax"></a>Syntax

```C
int sprintf(
   char *buffer,
   const char *format [,
   argument] ...
);
int _sprintf_l(
   char *buffer,
   const char *format,
   locale_t locale [,
   argument] ...
);
int swprintf(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format [,
   argument]...
);
int _swprintf_l(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
int __swprintf_l(
   wchar_t *buffer,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
template <size_t size>
int sprintf(
   char (&buffer)[size],
   const char *format [,
   argument] ...
); // C++ only
template <size_t size>
int _sprintf_l(
   char (&buffer)[size],
   const char *format,
   locale_t locale [,
   argument] ...
); // C++ only
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Speicherort für die Ausgabe

*count*<br/>
Maximale Anzahl, der in der Unicode-Version dieser Funktion zu speichernde Zeichen.

*format*<br/>
Formatsteuerzeichenfolge

*Argument*<br/>
Optionale Argumente

*locale*<br/>
Das zu verwendende Gebietsschema.

Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Rückgabewert

Die Anzahl der geschriebenen Zeichen oder -1, wenn ein Fehler aufgetreten. Wenn *Puffer* oder *Format* ist ein null-Zeiger, der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen-1 zurück und legen Sie **Errno** zu **EINVAL**.

**Sprintf** gibt die Anzahl der Bytes in einem *Puffer*, das abschließende Null-Zeichen wird dabei nicht mitgezählt. **Swprintf** gibt die Anzahl der gespeicherten Breitzeichen *Puffer*, das beendende null-Breitzeichen wird dabei nicht mitgezählt.

## <a name="remarks"></a>Hinweise

Die **Sprintf** -Funktion formatiert und speichert eine Reihe von Zeichen und Werten in *Puffer*. Jede *Argument* (sofern vorhanden) konvertiert und ausgegeben wird, entsprechend der jeweiligen Formatangabe in *Format*. Das Format besteht aus normalen Zeichen und hat die gleiche form und Funktion wie der *Format* Argument für [Printf](printf-printf-l-wprintf-wprintf-l.md). Ein NULL-Zeichen wird nach dem letzten geschriebenen Zeichen angefügt. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.

> [!IMPORTANT]
> Mithilfe von **Sprintf**, es gibt keine Möglichkeit, um die Anzahl von Zeichen geschrieben, d. h. zu beschränken, die mithilfe von code **Sprintf** für Pufferüberläufe anfällig ist. Die related-Funktion in Betracht [_snprintf](snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md), der angibt, dass einer maximale Anzahl von Zeichen an *Puffer*, oder verwenden Sie [_scprintf](scprintf-scprintf-l-scwprintf-scwprintf-l.md) um zu bestimmen, wie groß ein Puffer ist erforderlich. Stellen Sie außerdem sicher, dass *Format* ist keine benutzerdefinierte Zeichenfolge.

**Swprintf** ist eine Breitzeichen-Version von **Sprintf**; die Zeigerargumente zu **Swprintf** sind Breitzeichen Zeichenfolgen. Erkennung von Codierungsfehlern in **Swprintf** möglicherweise nicht auf die in **Sprintf**. **Swprintf** und **Fwprintf** Verhalten sich identisch, außer dass **Swprintf** schreibt die Ausgabe in eine Zeichenfolge anstatt an ein Ziel vom Typ **Datei**, und **Swprintf** erfordert die *Anzahl* Parameter, um die maximale Anzahl zu schreibender Zeichen anzugeben. Die Versionen dieser Funktionen mit den **_l** -Suffix sind beinahe identisch, außer dass sie den übergebenen Gebietsschemaparameter anstelle des aktuellen threadgebietsschemas Locale-Parameter verwenden.

**Swprintf** entspricht dem ISO C-Standard, die den zweiten Parameter erfordert, *Anzahl*, des Typs **"size_t"**. Um das alte, nicht dem Standard entsprechende Verhalten zu erzwingen, definieren **_CRT_NON_CONFORMING_SWPRINTFS**. In einer zukünftigen Version wird das alte Verhalten möglicherweise entfernt. Daher sollte Code so geändert werden, dass das neue konforme Verhalten verwendet wird.

In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stprintf**|**sprintf**|**sprintf**|**_swprintf**|
|**_stprintf_l**|**_sprintf_l**|**_sprintf_l**|**__swprintf_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**Sprintf**, **_sprintf_l**|\<stdio.h>|
|**Swprintf**, **_swprintf_l**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_sprintf.c
// compile with: /W3
// This program uses sprintf to format various
// data and place them in the string named buffer.

#include <stdio.h>

int main( void )
{
   char  buffer[200], s[] = "computer", c = 'l';
   int   i = 35, j;
   float fp = 1.7320534f;

   // Format and print various data:
   j  = sprintf( buffer,     "   String:    %s\n", s ); // C4996
   j += sprintf( buffer + j, "   Character: %c\n", c ); // C4996
   j += sprintf( buffer + j, "   Integer:   %d\n", i ); // C4996
   j += sprintf( buffer + j, "   Real:      %f\n", fp );// C4996
   // Note: sprintf is deprecated; consider using sprintf_s instead

   printf( "Output:\n%s\ncharacter count = %d\n", buffer, j );
}
```

```Output
Output:
   String:    computer
   Character: l
   Integer:   35
   Real:      1.732053

character count = 79
```

## <a name="example"></a>Beispiel

```C
// crt_swprintf.c
// wide character example
// also demonstrates swprintf returning error code
#include <stdio.h>

int main( void )
{
   wchar_t buf[100];
   int len = swprintf( buf, 100, L"%s", L"Hello world" );
   printf( "wrote %d characters\n", len );
   len = swprintf( buf, 100, L"%s", L"Hello\xffff world" );
   // swprintf fails because string contains WEOF (\xffff)
   printf( "wrote %d characters\n", len );
}
```

```Output
wrote 11 characters
wrote -1 characters
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf-Funktionen](../../c-runtime-library/vprintf-functions.md)<br/>
