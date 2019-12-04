---
title: Grundlegende Typen (C++)
ms.date: 11/04/2016
f1_keywords:
- __int128_cpp
- __wchar_t_cpp
- char_cpp
- double_cpp
- float_cpp
- int_cpp
- long_cpp
- long_double_cpp
- short_cpp
- signed_cpp
- unsigned_cpp
- unsigned_int_cpp
- wchar_t_cpp
helpviewer_keywords:
- specifiers [C++], type
- float keyword [C++]
- char keyword [C++]
- __wchar_t keyword [C++]
- signed types [C++], summary of data types
- Integer data type [C++], C++ data types
- arithmetic operations [C++], types
- int data type
- unsigned types [C++], summary of data types
- short data type [C++]
- double data type [C++], summary of types
- long long keyword [C++]
- long double keyword [C++]
- unsigned types [C++]
- signed types [C++]
- void keyword [C++]
- storage [C++], basic type
- integral types, C++
- wchar_t keyword [C++]
- floating-point numbers [C++], C++ data types
- long keyword [C++]
- type specifiers [C++]
- integral types
- long keyword [C++]
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
ms.openlocfilehash: 99c30eeb942eb3ab57518cc63ce353cfeff0bec9
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810546"
---
# <a name="fundamental-types--c"></a>Grundlegende Typen (C++)

Grundlegende Typen in C++ werden in drei Kategorien unterteilt: integraler Typ, Gleitkommatyp und void. Von integralen Typen können ganze Zahlen verarbeitet werden. Von Gleitkommatypen können Werte angegeben werden, die möglicherweise Nachkommastellen aufweisen.

Der Typ [void](../cpp/void-cpp.md) beschreibt eine leere Menge von Werten. Es kann keine Variable vom Typ **void** angegeben werden – Sie wird primär verwendet, um Funktionen zu deklarieren, die keine Werte zurückgeben, oder um generische Zeiger auf nicht typisierte oder willkürlich typisierte Daten zu deklarieren. Jeder Ausdruck kann explizit konvertiert oder in den Typ " **void**" umgewandelt werden. Allerdings werden solche Ausdrücke auf folgende Anwendungsbereiche begrenzt:

- Eine Ausdrucksanweisung. (Weitere Informationen finden Sie unter [Ausdrücke](../cpp/expressions-cpp.md).)

- Der linke Operand des Komma-Operators. (Weitere Informationen finden Sie unter [Komma-Operator](../cpp/comma-operator.md) .)

- Der zweite oder dritte Operand des bedingten Operators (`? :`). (Weitere Informationen finden Sie unter [Ausdrücke mit dem bedingten Operator](../cpp/conditional-operator-q.md) .)

In der folgenden Tabelle werden die Einschränkungen für die Typgrößen erklärt. Diese Einschränkungen sind unabhängig von der Microsoft-Implementierung.

### <a name="fundamental-types-of-the-c-language"></a>Grundlegende Typen der Programmiersprache C++

|Kategorie|Typ|Inhalt|
|--------------|----------|--------------|
|Integral|**char**|Typ **char** ist ein ganzzahliger Typ, der normalerweise Member des grundlegenden Ausführungs Zeichensatzes enthält – standardmäßig C++ist dies ASCII in Microsoft.<br /><br /> Der C++ Compiler behandelt Variablen vom Typ " **char**", " **signed char**" und " **Ganzzahl ohne Vorzeichen char** " mit unterschiedlichen Typen. Variablen vom Typ **char** werden auf **int** herauf gestuft, als ob Sie standardmäßig den Typ **signed char** haben, es sei denn, die Kompilierungs Option/J wird verwendet. In diesem Fall werden Sie als Typ **Ganzzahl ohne Vorzeichen char** behandelt und ohne Vorzeichen Erweiterung zu **int** herauf gestuft.|
||**bool**|Der Typ " **bool** " ist ein ganzzahliger Typ, der einen der beiden Werte **true** oder **false**aufweisen kann. Seine Größe ist nicht angegeben.|
||**short**|Der Typ **short int** (oder einfach **Short**) ist ein ganzzahliger Typ, der größer oder gleich der Größe des Typs **char**und kürzer oder gleich der Größe des Typs **int**ist.<br /><br /> Objekte vom Typ **Short** können als " **Signed Short** " oder " **Ganzzahl ohne Vorzeichen Short**" deklariert werden. **Signed Short** ist ein Synonym für **Short**.|
||**int**|Der Typ " **int** " ist ein ganzzahliger Typ, der größer oder gleich der Größe des Typs " **short int**" und kleiner oder gleich der Größe des Typs " **Long**" ist.<br /><br /> Objekte vom Typ " **int** " können als " **signed int** " oder " **Ganzzahl ohne Vorzeichen int**" deklariert werden. **Signed int** ist ein Synonym für **int**.|
||**__int8**, **__int16**, **__int32**, **__int64**|Ganzzahl mit fester Größe `__int n`, wobei `n` in Bits die Größe der ganzzahligen Variablen ist. **__int8**, **__int16**, **__int32** und **__int64** sind Microsoft-spezifische Schlüsselwörter. Nicht alle Typen sind in allen Architekturen verfügbar. ( **__int128** wird nicht unterstützt.)|
||**long**|Der Typ **Long** (oder **long int**) ist ein ganzzahliger Typ, der größer oder gleich der Größe des Typs **int**ist. (Unter Windows **Long** ist die gleiche Größe wie **int**.)<br /><br /> Objekte vom Typ **Long** können als **Signed Long** oder **Ganzzahl ohne Vorzeichen long**deklariert werden. **Signed Long** ist ein Synonym für **Long**.|
||**langes long**|Größer als ein Ganzzahl ohne Vorzeichen **Long**.<br /><br /> Objekte vom Typ **Long Long** können als **Signed Long Long** oder **Ganzzahl ohne Vorzeichen long long**deklariert werden. **Signed Long Long** ist ein Synonym für **Long Long**.|
||**wchar_t**, **__wchar_t**|Eine Variable vom Typ **wchar_t** der einen breit Zeichen-oder multibytezeichentyp festlegt. Standardmäßig ist **wchar_t** ein System eigener Typ. Sie können jedoch [/Zc: wchar_t-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) verwenden, um **wchar_t** eine typedef für einen **Ganzzahl ohne Vorzeichen Short**-Wert zu erstellen. Der **__wchar_t** Typ ist ein Microsoft-spezifisches Synonym für den systemeigenen **wchar_t** Typ.<br /><br /> Verwenden Sie das Präfix L vor einem Zeichen oder einem Zeichenliteral, um einen Breitzeichentyp festzulegen.|
|Gleitkomma|**float**|Der Typ " **float** " ist der kleinste Gleit kommatyp.|
||**double**|Type **Double** ist ein Gleit kommatyp, der größer oder gleich dem Typ **float**ist, aber kürzer oder gleich der Größe des Typs **long Double**ist.<br /><br /> Microsoft-spezifisch: die Darstellung von **long Double** und **Double** ist identisch. **Long Double** und **Double** sind jedoch separate Typen.|
||**long double**|Der Typ **long Double** ist ein Gleit kommatyp, der größer oder gleich dem Typ **Double**ist.|

**Microsoft-spezifisch**

Die folgende Tabelle enthält den Speicherumfang, der für grundlegende Typen in Microsoft C++ erforderlich ist.

### <a name="sizes-of-fundamental-types"></a>Größen von grundlegenden Typen

|Typ|-Größe|
|----------|----------|
|**bool**, **char**, **Ganzzahl ohne Vorzeichen char**, **signed char**, **__int8**|1 Byte|
|**__int16**, **Short**, **Ganzzahl ohne Vorzeichen Short**, **wchar_t**, **__wchar_t**|2 Bytes|
|**float**, **__int32**, **int**, **Ganzzahl ohne Vorzeichen int**, **Long**, **Ganzzahl ohne Vorzeichen long**|4 Bytes|
|**Double**, **__int64**, **long Double**, **Long Long**|8 Bytes|

**Ende Microsoft-spezifisch**

Eine Zusammenfassung des Wertebereichs der einzelnen Typen erhalten Sie unter [Datentypbereiche](../cpp/data-type-ranges.md) .

Weitere Informationen zur Typkonvertierung finden Sie unter [Standardwertkonvertierungen](../cpp/standard-conversions.md).

## <a name="see-also"></a>Siehe auch

[Datentypbereiche](../cpp/data-type-ranges.md)