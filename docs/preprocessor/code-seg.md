---
title: code_seg-Pragma
ms.date: 08/29/2019
f1_keywords:
- code_seg_CPP
- vc-pragma.code_seg
helpviewer_keywords:
- pragmas, code_seg
- code_seg pragma
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
ms.openlocfilehash: 0144b3ed220c39cd30aeb8e53bc2aa3c0381b668
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218314"
---
# <a name="code_seg-pragma"></a>code_seg-Pragma

Gibt den Textabschnitt (Segment) an, in dem Funktionen in der Objektdatei (obj-Datei) gespeichert werden.

## <a name="syntax"></a>Syntax

> **#pragma code_seg (** ["*section-Name*" [ **,** "*section-Class*"]] **)** \
> **#pragma code_seg (** { **Push** | **Pop** } [ **,** *Identifier* ] [ **,** "*section-Name*" [ **,** "*section-Class*"]] **)**

### <a name="parameters"></a>Parameter

**Push**\
Optionale Legt einen Datensatz auf dem internen compilerstapel ab. Ein **Push** kann einen *Bezeichner* und einen *Abschnittsnamen*aufweisen.

**Chor**\
Optionale Entfernt einen Datensatz von der obersten Position des internen Compilerstapels. Ein **Pop** kann einen *Bezeichner* und einen *Abschnittsnamen*aufweisen. Mithilfe des Bezeichners können Sie mehrere Datensätze mithilfe von nur einem **Pop** -Befehl Popups. Der *Abschnitts Name* wird zum Namen des aktiven Text Abschnitts nach dem Pop.

*Figur*\
Optionale Bei Verwendung mit **Push**weist dem Datensatz im internen compilerstapel einen Namen zu. Bei Verwendung mit **Pop**werden Datensätze vom internen Stapel, bis der *Bezeichner* entfernt wird, vom internen Stapel angeblendet. Wenn der Bezeichner im internen Stapel nicht gefunden wird, wird nichts weitergeleitet.

"*Abschnitts Name*" \
Optionale Der Name eines Abschnitts. Bei Verwendung mit **Pop**wird der Stapel per Pop und *Abschnitts Name* zum aktiven Text Abschnittsnamen.

"*section-Class*" \
Optionale Wird ignoriert, aber ist aus Kompatibilitätsgründen mit C++ früheren Versionen von Microsoft als Version 2,0 enthalten.

## <a name="remarks"></a>Hinweise

Ein *Abschnitt* in einer Objektdatei ist ein benannter Datenblock, der als Einheit in den Arbeitsspeicher geladen wird. Ein *Textabschnitt* ist ein Abschnitt, der ausführbaren Code enthält. In diesem Artikel haben die Begriffe *Segment* und *Abschnitt* dieselbe Bedeutung.

Die **code_seg** -pragma-Direktive weist den Compiler an, den gesamten nachfolgenden Objektcode aus der Übersetzungseinheit in einen Textabschnitt namens *section-Name*einzufügen. Standardmäßig wird der Textabschnitt, der für Funktionen in einer Objektdatei verwendet `.text`wird, benannt. Eine **code_seg** -pragma-Direktive ohne *section-Name-* Parameter setzt den Text Abschnittsnamen für den nachfolgenden `.text`Objektcode auf zurück.

Die **code_seg** -pragma-Direktive steuert nicht die Platzierung von Objektcode, der für instanziierte Vorlagen generiert wurde. Und steuert nicht den Code, der implizit vom Compiler generiert wird, z. b. spezielle Member-Funktionen. Um diesen Code zu steuern, empfiehlt es sich, stattdessen das [__declspec (code_seg (...))](../cpp/code-seg-declspec.md) -Attribut zu verwenden. Sie ermöglicht Ihnen die Kontrolle über die Platzierung des gesamten Objektcodes, einschließlich von compilergeneriertem Code.

Eine Liste der Namen, die nicht zum Erstellen eines Abschnitts verwendet werden sollten, finden Sie unter [/section](../build/reference/section-specify-section-attributes.md).

Sie können auch Abschnitte für initialisierte Daten ([data_seg](../preprocessor/data-seg.md)), nicht initialisierte Daten ([Bss_seg](../preprocessor/bss-seg.md)) und Konstanten Variablen ([Const_seg](../preprocessor/const-seg.md)) angeben.

Sie können den [DUMPBIN verwenden. EXE](../build/reference/dumpbin-command-line.md) -Anwendung zum Anzeigen von Objektdateien. Die Versionen von DUMPBIN für jede unterstützte Zielarchitektur sind in Visual Studio enthalten.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie die **code_seg** -pragma-Direktive verwendet wird, um zu steuern, wo der Objektcode abgelegt wird:

```cpp
// pragma_directive_code_seg.cpp
void func1() {                  // stored in .text
}

#pragma code_seg(".my_data1")
void func2() {                  // stored in my_data1
}

#pragma code_seg(push, r1, ".my_data2")
void func3() {                  // stored in my_data2
}

#pragma code_seg(pop, r1)      // stored in my_data1
void func4() {
}

int main() {
}
```

## <a name="see-also"></a>Siehe auch

[code_seg (__declspec)](../cpp/code-seg-declspec.md)\
[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
