---
title: systeminterne | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/11/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- intrinsic_CPP
- vc-pragma.intrinsic
dev_langs:
- C++
helpviewer_keywords:
- intrinsic pragma
- pragmas, intrinsic
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c222a939ccb00dc3b7466a1cb1a83abe7ea4036
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539602"
---
# <a name="intrinsic"></a>intrinsic

Gibt an, dass Funktionsaufrufe, die in der Argumentliste des Pragmas angegeben sind, systemintern sind.

## <a name="syntax"></a>Syntax

```cpp
#pragma intrinsic( function1 [, function2, ...] )
```

## <a name="remarks"></a>Hinweise

Die **systeminterne** Pragma informiert den Compiler an, dass eine Funktion ein bekanntes Verhalten aufweist.  Der Compiler kann die Funktion aufrufen und den Funktionsaufruf nicht durch Inlineanweisungen ersetzen, wenn dies zu einer besseren Leistung führt.

Die Bibliotheksfunktionen mit systeminternen Formularen werden nachfolgend aufgeführt. Sobald ein **systeminterne** Pragma angezeigt wird, er wird wirksam, mit der ersten Funktionsdefinition, die eine bestimmte intrinsische Funktion enthält. Die Wirkung dauert bis an das Ende der Quelldatei oder bis zum Auftreten einer `function` Pragmas, die gleiche intrinsische Funktion angibt. Die **systeminterne** Pragma kann nur außerhalb einer Funktionsdefinition verwendet werden – auf globaler Ebene.

Die folgenden Funktionen haben systeminterne Formen und die systeminternen Formen werden verwendet, bei der Angabe [/Oi](../build/reference/oi-generate-intrinsic-functions.md):

|||||
|-|-|-|-|
|[_disable](../intrinsics/disable.md)|[_outp](../c-runtime-library/outp-outpw-outpd.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|
|[_enable](../intrinsics/enable.md)|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|[labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|[_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|[_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)||
|[_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|[_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[memset](../c-runtime-library/reference/memset-wmemset.md)||
|[_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)||

Programme, die intrinsische Funktionen verwenden, sind schneller, da sie nicht den Mehraufwand der Funktionsaufrufe haben, sie können aufgrund des zusätzlich erstellten Codes jedoch größer sein.

**X86 bestimmte**

Die `_disable` und `_enable` systeminterne Funktionen generieren kernelmodusanweisungen zu deaktivieren bzw. aktivieren und kann in Kernelmodustreibern hilfreich sein.

### <a name="example"></a>Beispiel

Kompilieren Sie den folgenden Code über die Befehlszeile mit `cl -c -FAs sample.c` und überprüfen Sie Sample.asm zu erkennen, dass sie in X86 umwandeln Anweisungen CLI und Sti umgewandelt werden:

```cpp
// pragma_directive_intrinsic.cpp
// processor: x86
#include <dos.h>   // definitions for _disable, _enable
#pragma intrinsic(_disable)
#pragma intrinsic(_enable)
void f1(void) {
   _disable();
   // do some work here that should not be interrupted
   _enable();
}
int main() {
}
```

**Ende X86-spezifisch**

Die unten aufgeführten Gleitkommafunktionen haben keine echten systeminternen Formen. Stattdessen verfügen sie über Versionen, die Argumente direkt an den Gleitkommachip übergeben, anstatt sie auf dem Programmstapel abzulegen:

|||||
|-|-|-|-|
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[cosh](../c-runtime-library/reference/cosh-coshf-coshl.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|[tanh](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[sinh](../c-runtime-library/reference/sinh-sinhf-sinhl.md)||

 Die unten aufgeführten Gleitkommafunktionen haben echte systeminterne Formen, bei der Angabe [/Oi](../build/reference/oi-generate-intrinsic-functions.md), ["/ Og"](../build/reference/og-global-optimizations.md), und [fast](../build/reference/fp-specify-floating-point-behavior.md) (oder eine Option, die "/ Og" enthält: [/ Ox](../build/reference/ox-full-optimization.md), ["/ O1"](../build/reference/o1-o2-minimize-size-maximize-speed.md), und "/ O2"):

|||||
|-|-|-|-|
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl.md)|
|[cos](../c-runtime-library/reference/cos-cosf-cosl.md)||||

Sie können [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) oder [/Za](../build/reference/za-ze-disable-language-extensions.md) Generierung von echten systeminternen Gleitkommaoptionen zu überschreiben. In diesem Fall werden die Funktionen als Bibliotheksroutinen erzeugt, die Argumente direkt an den Gleitkommachip übergeben, statt sie auf dem Programmstapel abzulegen.

Finden Sie unter [#pragma-funhtion](../preprocessor/function-c-cpp.md) Informationen und ein Beispiel zum Aktivieren/Deaktivieren von systeminternen Funktionen für einen Block an Quelltext.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)  
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)  