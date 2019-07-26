---
title: '&lt;valarray&gt;'
ms.date: 11/04/2016
f1_keywords:
- <valarray>
helpviewer_keywords:
- valarray header
ms.assetid: 30835415-21c1-4801-8f24-6bbef7dd8ecd
ms.openlocfilehash: c18b72017e4999e377bf8575f624f8fdda5b0caf
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448338"
---
# <a name="ltvalarraygt"></a>&lt;valarray&gt;

Definiert die valarray-Vorlagenklasse sowie zahlreiche unterstützende Vorlagenklassen und Funktionen.

## <a name="requirements"></a>Anforderungen

**Header:** \<valarray>

**Namespace:** std

> [!NOTE]
> Die \<Valarray-> Bibliothek verwendet die #include < initializer_list > "-Anweisung.

## <a name="remarks"></a>Hinweise

Diese Vorlagenklassen und Funktionen haben im Interesse einer verbesserten Leistung ungewöhnliche Freiheiten. Insbesondere kann jede Funktion, die `valarray<T1>` den Typ zurückgibt, ein Objekt eines anderen Typs T2 zurückgeben. In diesem Fall muss jede Funktion, die ein oder mehrere Argumente des Typs `valarray<T2>` akzeptiert, über Ladungen haben, die beliebige Kombinationen dieser Argumente akzeptieren, die jeweils durch ein Argument des Typs T2 ersetzt werden.

## <a name="members"></a>Member

### <a name="functions"></a>Funktionen

|||
|-|-|
|[abs](../standard-library/valarray-functions.md#abs)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich dem absoluten Wert der Elemente des valarray-Eingabeobjekts sind.|
|[acos](../standard-library/valarray-functions.md#acos)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich dem Arkuskosinus der Elemente des valarray-Eingabeobjekts sind.|
|[asin](../standard-library/valarray-functions.md#asin)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich dem Arkussinus der Elemente des valarray-Eingabeobjekts sind.|
|[atan](../standard-library/valarray-functions.md#atan)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich dem Hauptwert des Arkustangens der Elemente des valarray-Eingabeobjekts sind.|
|[atan2](../standard-library/valarray-functions.md#atan2)|Gibt ein valarray-Objekt zurück, dessen Elemente gleich dem Arkustangens der kartesischen Komponenten sind, die durch eine Kombination aus Konstanten und Elementen von valarray-Objekten angegeben sind.|
|[begin](../standard-library/valarray-functions.md#begin)||
|[cos](../standard-library/valarray-functions.md#cos)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich dem Kosinus der Elemente des valarray-Eingabeobjekts sind.|
|[cosh](../standard-library/valarray-functions.md#cosh)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich dem Kosinus Hyperbolicus der Elemente des valarray-Eingabeobjekts sind.|
|[end](../standard-library/valarray-functions.md#end)||
|[exp](../standard-library/valarray-functions.md#exp)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich der natürlichen Exponentialfunktion der Elemente des valarray-Eingabeobjekts sind.|
|[log](../standard-library/valarray-functions.md#log)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich dem natürlichen Logarithmus der Elemente des valarray-Eingabeobjekts sind.|
|[log10](../standard-library/valarray-functions.md#log10)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich dem Logarithmus zur Basis 10 (dekadischer Logarithmus) der Elemente des valarray-Eingabeobjekts sind.|
|[pow](../standard-library/valarray-functions.md#pow)|Verarbeitet die Elemente von valarray-Eingabeobjekten und Konstanten und gibt ein valarray-Objekt zurück, dessen Elemente gleich einer mit einem Exponenten potenzierten Basis sind, wobei Basis und Exponent jeweils durch die Elemente eines valarray-Eingabeobjekts oder eine Konstante angegeben sind.|
|[sin](../standard-library/valarray-functions.md#sin)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich dem Sinus der Elemente des valarray-Eingabeobjekts sind.|
|[sinh](../standard-library/valarray-functions.md#sinh)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich dem Sinus Hyperbolicus der Elemente des valarray-Eingabeobjekts sind.|
|[sqrt](../standard-library/valarray-functions.md#sqrt)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich der Quadratwurzel der Elemente des valarray-Eingabeobjekts sind.|
|[swap](../standard-library/valarray-functions.md#swap)||
|[tan](../standard-library/valarray-functions.md#tan)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich dem Tangens der Elemente des valarray-Eingabeobjekts sind.|
|[tanh](../standard-library/valarray-functions.md#tanh)|Verarbeitet die Elemente eines valarray-Eingabeobjekts und gibt ein valarray-Objekt zurück, dessen Elemente gleich dem Tangens Hyperbolicus der Elemente des valarray-Eingabeobjekts sind.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[Operator!=](../standard-library/valarray-operators.md#op_neq)|Überprüft, ob die entsprechenden Elemente von zwei gleich großen valarray-Objekten ungleich sind oder ob alle Elemente eines valarray-Objekts entsprechend einem angegebenen Wert des Elementtyps des valarray-Objekts ungleich sind.|
|[operator%](../standard-library/valarray-operators.md#op_mod)|Ruft den Rest der Division der entsprechenden Elemente von zwei gleich großen valarray-Objekten oder der Division eines valarray-Objekts durch einen angegebenen Wert des valarray Elementtyps oder der Division eines angegebenen Werts durch ein valarray-Objekt ab.|
|[operator&](../standard-library/valarray-operators.md#op_amp)|Ruft das bitweise `AND` zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps ab.|
|[operator&&](../standard-library/valarray-operators.md#op_amp_amp)|Ruft das logische `AND` zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps des valarray-Objekts ab.|
|[operator>](../standard-library/valarray-operators.md#op_gt)|Überprüft, ob die Elemente eines valarray-Objekts größer sind als die Elemente eines gleich großen valarray-Objekts oder ob alle Elemente eines valarray-Objekts größer oder kleiner sind als ein angegebener Wert des Elementtyps des valarray-Objekts.|
|[operator>=](../standard-library/valarray-operators.md#op_gt_eq)|Überprüft, ob die Elemente eines valarray-Objekts größer gleich den Elementen eines gleich großen valarray-Objekts oder ob alle Elemente eines valarray-Objekts größer gleich oder kleiner gleich einem angegebenen Wert sind.|
|[operator>>](../standard-library/valarray-operators.md#op_gt_gt)|Verschiebt die Bits für jedes Element eines valarray-Objekts um eine angegebene Anzahl von Positionen oder um einen elementweisen Betrag, der durch ein zweites valarray-Objekt angegeben ist, nach rechts.|
|[operator<](../standard-library/valarray-operators.md#op_lt)|Überprüft, ob die Elemente eines valarray-Objekts kleiner sind als die Elemente eines gleich großen valarray-Objekts oder ob alle Elemente eines valarray-Objekts größer oder kleiner sind als ein angegebener Wert.|
|[operator<=](../standard-library/valarray-operators.md#op_lt_eq)|Überprüft, ob die Elemente eines valarray-Objekts kleiner gleich den Elementen eines gleich großen valarray-Objekts oder ob alle Elemente eines valarray-Objekts größer gleich oder kleiner gleich einem angegebenen Wert sind.|
|[operator<<](../standard-library/valarray-operators.md#op_lt_lt)|Verschiebt die Bits für jedes Element eines valarray-Objekts um eine angegebene Anzahl von Positionen oder um einen elementweisen Betrag, der durch ein zweites valarray-Objekt angegeben ist, nach links.|
|[operator*](../standard-library/valarray-operators.md#op_star)|Ruft das elementweise Produkt zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps des valarray-Objekts ab.|
|[operator+](../standard-library/valarray-operators.md#op_add)|Ruft die elementweise Summe zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps des valarray-Objekts ab.|
|[operator-](../standard-library/valarray-operators.md#operator-)|Ruft die elementweise Differenz zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps des valarray-Objekts ab.|
|[operator/](../standard-library/valarray-operators.md#op_div)|Ruft den elementweise Quotienten zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps des valarray-Objekts ab.|
|[operator==](../standard-library/valarray-operators.md#op_eq_eq)|Überprüft, ob die entsprechenden Elemente von zwei gleich großen valarray-Objekten gleich sind oder ob alle Elemente eines valarray-Objekts entsprechend einem angegebenen Wert des Elementtyps des valarray-Objekts gleich sind.|
|[operator^](../standard-library/valarray-operators.md#op_xor)|Ruft das bitweise exklusive `OR` zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps ab.|
|[operator|](../standard-library/valarray-operators.md#op_or)|Ruft das bitweise `OR` zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps ab.|
|[operator||](../standard-library/valarray-operators.md#op_lor)|Ruft das logische `OR` zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps des valarray-Objekts ab.|

### <a name="classes"></a>Klassen

|||
|-|-|
|[gslice-Klasse](../standard-library/gslice-class.md)|Eine Hilfsklasse der valarray-Klasse, die zum Definieren von mehrdimensionalen Segmenten eines valarray-Objekts verwendet wird.|
|[gslice_array-Klasse](../standard-library/gslice-array-class.md)|Eine interne zusätzliche Vorlagenklasse, die allgemeine slice-Objekte (Segmente) unterstützt, indem sie Vorgänge zwischen Teilmengenarrays bereitstellt, die durch das allgemeine Segment eines valarray-Objekts definiert sind.|
|[indirect_array-Klasse](../standard-library/indirect-array-class.md)|Eine interne zusätzliche Vorlagenklasse, die allgemeine Objekte, die Teilmengen von valarray-Objekten sind, unterstützt, indem sie Vorgänge zwischen Teilmengenarrays bereitstellt, die durch Angeben einer Teilmenge von Indizes eines übergeordneten valarray-Objekts definiert sind.|
|[mask_array-Klasse](../standard-library/mask-array-class.md)|Eine interne zusätzliche Vorlagenklasse, die Objekte, die Teilmengen von übergeordneten valarray-Objekten und mit einem booleschen Ausdruck angegeben sind, dadurch unterstützt, dass sie Vorgänge zwischen den Teilmengenarrays bereitstellt.|
|[slice-Klasse](../standard-library/slice-class.md)|Eine Hilfsklasse für die valarray-Klasse, die dazu verwendet wird, eindimensionale vektorähnliche Teilmengen eines valarray-Objekts zu definieren.|
|[slice_array-Klasse](../standard-library/slice-array-class.md)|Eine interne zusätzliche Vorlagenklasse, die slice-Objekte (Segmente) unterstützt, indem sie Vorgänge zwischen Teilmengenarrays bereitstellt, die durch das Segment eines valarray-Objekts definiert sind.|
|[valarray-Klasse](../standard-library/valarray-class.md)|Die Vorlagen Klasse beschreibt ein Objekt, das eine Sequenz von Elementen des Typs `Type` steuert, die als Array gespeichert werden und für die Ausführung von hoch Geschwindigkeits mathematischen Operationen entworfen wurden, die für die Rechenleistung optimiert sind.|

### <a name="specializations"></a>Spezialisierungen

|||
|-|-|
|[valarray\<bool>-Klasse](../standard-library/valarray-bool-class.md)|Eine spezialisierte Version der Vorlagen Klasse Valarray\<**Type**> auf Elemente des Typs **bool**.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
