---
title: _ASSERT-, _ASSERTE-, _ASSERT_EXPR-Makros
ms.date: 11/04/2016
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
- _ASSERTE
- ASSERTE
- _ASSERT
- _ASSERT_EXPR
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
ms.openlocfilehash: d2d83c3afa8e22c1f75480fe2afefa8bf68be858
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740016"
---
# <a name="_assert-_asserte-_assert_expr-macros"></a>_ASSERT-, _ASSERTE-, _ASSERT_EXPR-Makros

Wertet einen Ausdruck aus und generiert einen Debugbericht, wenn das Ergebnis " **false** " ist (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
// Typical usage:
_ASSERT_EXPR( booleanExpression, message );
_ASSERT( booleanExpression );
_ASSERTE( booleanExpression );
```

### <a name="parameters"></a>Parameter

*booleanExpression*<br/>
Ein skalarer Ausdruck (einschließlich Zeigerausdrücken) der zu ungleich null (true) oder „0“ (false) ausgewertet wird.

*message*<br/>
Eine Breitzeichenfolge, die als Teil des Berichts angezeigt werden soll.

## <a name="remarks"></a>Hinweise

Die Makros **_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** stellen eine Anwendung mit einem sauberen und einfachen Mechanismus für die Überprüfung von Annahmen während des Debugprozesses bereit. Sie sind sehr flexibel, da sie nicht in `#ifdef` -Anweisungen eingeschlossen werden müssen, um ihren Aufruf in der Verkaufsversion einer Anwendung zu verhindern. Diese Flexibilität wird mithilfe des [_DEBUG](../../c-runtime-library/debug.md) -Makros erreicht. **_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** sind nur verfügbar, wenn **_DEBUG** zur Kompilierzeit definiert ist. Wenn **_DEBUG** nicht definiert ist, werden Aufrufe dieser Makros während der Vorverarbeitung entfernt.

**_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** Werten Ihr *booleanExpression* -Argument aus, und wenn das Ergebnis **false** (0) ist, wird eine Diagnose Meldung ausgegeben und [_CrtDbgReportW](crtdbgreport-crtdbgreportw.md) aufgerufen, um einen Debugbericht zu generieren. Das **_ASSERT** -Makro gibt eine einfache Diagnose Meldung aus, **_ASSERTE** enthält eine Zeichen folgen Darstellung des fehlgeschlagenen Ausdrucks in der Nachricht, und **_ASSERT_EXPR** schließt die Meldungs Zeichenfolge *in* die Diagnose Meldung ein. Diese Makros führen keine Aktion aus, wenn *booleanExpression* als ungleich NULL ausgewertet wird.

**_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** rufen **_CrtDbgReportW**auf, was bewirkt, dass die gesamte Ausgabe in breit Zeichen ist. **_ASSERTE** gibt Unicode-Zeichen in *booleanExpression* ordnungsgemäß aus, und **_ASSERT_EXPR** gibt Unicode-Zeichen in der *Nachricht*aus.

Da das **_ASSERTE** -Makro den fehlgeschlagenen Ausdruck angibt und **_ASSERT_EXPR** Ihnen ermöglicht, eine Meldung im generierten Bericht anzugeben, können Benutzer das Problem identifizieren, ohne auf den Quellcode der Anwendung zu verweisen. Ein Nachteil besteht jedoch darin, dass jede von **_ASSERT_EXPR** gedruckte *Nachricht* und jeder von **_ASSERTE** ausgewertete Ausdruck in der Ausgabedatei (Debugversion) Ihrer Anwendung als Zeichen folgen Konstante enthalten ist. Wenn also eine große Anzahl von Aufrufen an **_ASSERT_EXPR** oder **_ASSERTE**vorgenommen wird, können diese Ausdrücke die Größe der Ausgabedatei erheblich vergrößern.

Sofern Sie es nicht mithilfe der Funktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md) anders festlegen, werden Meldungen in einem Popupdialogfeld angezeigt, entsprechend der Einstellung:

```C
_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);
````

**_CrtDbgReportW** generiert den Debugbericht und bestimmt sein Ziel oder seine Ziele basierend auf dem aktuellen Berichtsmodus oder den Modi und der Datei, die für den **_CRT_ASSERT** -Berichtstyp definiert sind. Standardmäßig werden Assertionsfehler und Fehler an ein Debugmeldungsfenster geleitet. Die Funktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md) werden verwendet, um das Ziel für jeden Berichtstyp zu definieren.

Wenn das Ziel ein debugmeldungsfenster ist und der Benutzer auf die Schaltfläche **wiederholen** klickt, gibt **_CrtDbgReportW** 1 zurück. Dies bewirkt, dass die Makros **_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** den Debugger starten, vorausgesetzt, dass Just-in-Time-Debuggen (JIT) ist aktiviert.

Weitere Informationen zum Berichtstellungsverfahren finden Sie bei der Funktion [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) . Weitere Informationen zum Beheben von Assertionsfehlern und zum Verwenden dieser Makros als Behandlungsmechanismus für Debugfehler finden Sie unter [Verwenden von Makros zur Überprüfung und Berichterstellung](/visualstudio/debugger/macros-for-reporting).

Zusätzlich zu den **_ASSERT** -Makros kann das [Assert](assert-macro-assert-wassert.md) -Makro zum Überprüfen der Programmlogik verwendet werden. Dieses Makro steht sowohl in der Debug- als auch in der endgültigen Version der Bibliotheken zur Verfügung. Die Debugmakros [_RPT, _RPTF](rpt-rptf-rptw-rptfw-macros.md) sind ebenfalls für die Erstellung eines Debugberichts verfügbar, werten aber keinen Ausdruck aus. Die **_RPT** -Makros generieren einen einfachen Bericht. Die **_RPTF** -Makros enthalten die Quelldatei und die Zeilennummer, in der das Berichts Makro im generierten Bericht aufgerufen wurde. Breit Zeichen Versionen dieser Makros sind verfügbar ( **_RPTW**, **_RPTFW**). Die Breitzeichenversionen sind mit den Versionen mit schmalen Zeichen identisch, mit dem Unterschied, dass für alle Zeichenfolgenparameter und Ausgaben Breitzeichen-Zeichenfolgen verwendet werden.

Obwohl **_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** Makros sind und durch einschließen \<von Crtdbg. h > verfügbar sind, muss die Anwendung mit einer Debugversion der C-Lauf Zeit Bibliothek verknüpft werden, wenn **_DEBUG** definiert ist, weil Diese Makros bezeichnen andere Lauf Zeitfunktionen.

## <a name="requirements"></a>Anforderungen

|Makro|Erforderlicher Header|
|-----------|---------------------|
|**_ASSERT_EXPR**, **_ASSERT**, **_ASSERTE**|\<crtdbg.h>|

## <a name="example"></a>Beispiel

In diesem Programm werden Aufrufe an die **_ASSERT** -und **_ASSERTE** -Makros durchgeführt, um `string1 == string2`die Bedingung zu testen. Wenn bei der Bedingung ein Fehler auftritt, geben diese Makros eine Diagnosemeldung aus. Die Gruppe " **_RPT** " und " **_RPTF** " wird in diesem Programm auch als Alternative zur **printf** -Funktion ausgeführt.

```C
// crt_ASSERT_macro.c
// compile with: /D_DEBUG /MTd /Od /Zi /link /verbose:lib /debug
//
// This program uses the _ASSERT and _ASSERTE debugging macros.
//

#include <stdio.h>
#include <string.h>
#include <malloc.h>
#include <crtdbg.h>

int main()
{
   char *p1, *p2;

   // The Reporting Mode and File must be specified
   // before generating a debug report via an assert
   // or report macro.
   // This program sends all report types to STDOUT.
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, _CRTDBG_FILE_STDOUT);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDOUT);
   _CrtSetReportMode(_CRT_ASSERT, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ASSERT, _CRTDBG_FILE_STDOUT);

   // Allocate and assign the pointer variables.
   p1 = (char *)malloc(10);
   strcpy_s(p1, 10, "I am p1");
   p2 = (char *)malloc(10);
   strcpy_s(p2, 10, "I am p2");

   // Use the report macros as a debugging
   // warning mechanism, similar to printf.
   // Use the assert macros to check if the
   // p1 and p2 variables are equivalent.
   // If the expression fails, _ASSERTE will
   // include a string representation of the
   // failed expression in the report.
   // _ASSERT does not include the
   // expression in the generated report.
   _RPT0(_CRT_WARN,
       "Use the assert macros to evaluate the expression p1 == p2.\n");
   _RPTF2(_CRT_WARN, "\n Will _ASSERT find '%s' == '%s' ?\n", p1, p2);
   _ASSERT(p1 == p2);

   _RPTF2(_CRT_WARN, "\n\n Will _ASSERTE find '%s' == '%s' ?\n",
          p1, p2);
   _ASSERTE(p1 == p2);

   _RPT2(_CRT_ERROR, "'%s' != '%s'\n", p1, p2);

   free(p2);
   free(p1);

   return 0;
}
```

```Output
Use the assert macros to evaluate the expression p1 == p2.
crt_ASSERT_macro.c(54) :
Will _ASSERT find 'I am p1' == 'I am p2' ?
crt_ASSERT_macro.c(55) : Assertion failed!
crt_ASSERT_macro.c(58) :

Will _ASSERTE find 'I am p1' == 'I am p2' ?
crt_ASSERT_macro.c(59) : Assertion failed: p1 == p2
'I am p1' != 'I am p2'
```

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[assert Macro, _assert, _wassert](assert-macro-assert-wassert.md)<br/>
[_RPT, _RPTF, _RPTW, _RPTFW Macros](rpt-rptf-rptw-rptfw-macros.md)<br/>
