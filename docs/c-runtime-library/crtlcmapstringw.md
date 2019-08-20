---
title: __crtLCMapStringW
ms.date: 11/04/2016
apiname:
- __crtLCMapStringW
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- __crtLCMapStringW
helpviewer_keywords:
- __crtLCMapStringW
ms.assetid: 45b4ac0e-438c-4fa3-b4d1-34195f4467d9
ms.openlocfilehash: e79ac5d4072595ef1034a0483b9edc8eada916d8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500215"
---
# <a name="__crtlcmapstringw"></a>__crtLCMapStringW

Ordnet eine Zeichenfolge einer anderen zu, wobei eine angegebene Gebietsschema-abhängige Umwandlung durchgeführt wird. Mit dieser Funktion kann auch ein Sortierschlüssel für die Eingabezeichenfolge generiert werden.

## <a name="syntax"></a>Syntax

```cpp
int __crtLCMapStringW(
   LCID    Locale,
   DWORD   dwMapFlags,
   LPCWSTR lpSrcStr,
   int     cchSrc,
   LPWSTR  lpDestStr,
   int     cchDest)
```

#### <a name="parameters"></a>Parameter

*Locale*<br/>
Gebietsschemabezeichner Das Gebietsschema stellt einen Kontext für die Zeichenfolgenzuordnung oder zum Generieren des Sortierschlüssels bereit. Eine Anwendung kann mithilfe des `MAKELCID` -Makros einen Gebietsschemabezeichner generieren.

*dwMapFlags*<br/>
Der Typ der Transformation, der während der Zeichenfolgenzuordnung oder des Generierens des Sortierschlüssels verwendet werden soll.

*lpSrcStr*<br/>
Zeiger auf eine Quellzeichenfolge, die die Funktion zuordnet oder für die Sortierschlüsselgenerierung verwendet. Für diesen Parameter wird davon ausgegangen, dass es sich um eine Unicode-Zeichenfolge handelt.

*cchSrc*<br/>
Auf die Größe, in Zeichen, der Zeichenfolge wird mit dem `lpSrcStr` -Parameter verwiesen. Dieser Parameter kann den NULL-Terminator enthalten oder nicht.

Ein `cchSrc`-Wert von -1 gibt an, dass die Zeichenfolge, auf die von `lpSrcStr` verwiesen wird, NULL-terminiert ist. Wenn dies der Fall ist und diese Funktion im Zeichenfolgenzuordnungsmodus verwendet wird, berechnet die Funktion die Länge der Zeichenfolge selbst und lässt die zugeordnete Zeichenfolge, die in `*lpDestStr`gespeichert wird, auf Null enden.

*lpDestStr*<br/>
Long-Zeiger auf einen Puffer, in den die Funktion die zugeordnete Zeichenfolge oder den Sortierschlüssel speichert.

*cchDest*<br/>
Größe, in Zeichen, des Puffers, auf die von `lpDestStr`verwiesen wird.

## <a name="return-value"></a>Rückgabewert

Wenn der Wert von `cchDest` ungleich NULL ist, zeigt die Anzahl der Zeichen oder Bytes, wenn `LCMAP_SORTKEY` angegeben ist, die in den Puffer geschrieben wird, Erfolg an. Dieser Parameter bietet Platz für einen NULL-Terminator.

Wenn der Wert von `cchDest` 0 ist, gibt Größe des Puffers in Zeichen oder Bytes, wenn `LCMAP_SORTKEY` angegeben ist, Erfolg an, was erforderlich für den Empfang der übersetzten Zeichenfolge oder des Sortierschlüssels ist. Diese Größe bietet Platz für einen NULL-Terminator.

Null weist auf einen Fehler hin. Rufen Sie für erweiterte Fehlerinformationen die `GetLastError` -Funktion auf.

## <a name="remarks"></a>Anmerkungen

Wenn `cchSrc` größer als 0 (null) ist und `lpSrcStr` ist eine Null-terminierte Zeichenfolge, legt `__crtLCMapStringW` `cchSrc` auf die Länge der Zeichenfolge fest. `__crtLCMapStringW` ruft dann die Breitzeichen-Version (Unicode) der `LCMapString` -Funktion mit den angegebenen Parametern auf. Weitere Informationen zu den Parametern und Rückgabewerten dieser Funktion finden Sie unter [LCMapString](/windows/win32/api/winnls/nf-winnls-lcmapstringw).

## <a name="requirements"></a>Requirements (Anforderungen)

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__crtLCMapStringW|awint.h|