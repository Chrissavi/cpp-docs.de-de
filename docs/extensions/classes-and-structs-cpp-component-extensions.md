---
title: Verweisklasse und Referenzstruktur (C++/CLI und C++/CX)
ms.date: 05/16/2019
ms.topic: reference
f1_keywords:
- ref class
helpviewer_keywords:
- ref class keyword [C++]
- value class keyword [C++]
- value struct keyword [C++]
- ref struct keyword [C++]
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
ms.openlocfilehash: 9c993b134d6d359d0bc756f5e79d2f9cc137c9cf
ms.sourcegitcommit: bc1b14f29a02685f97c7ef5c098d16db6eaf369f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2019
ms.locfileid: "65788787"
---
# <a name="ref-class-and-ref-struct--ccli-and-ccx"></a>Verweisklasse und Referenzstruktur (C++/CLI und C++/CX)

Die Erweiterungen **ref class** oder **ref struct** deklarieren eine Klasse oder Struktur, deren *Objektlebensdauer* automatisch verwaltet wird. Wenn auf das Objekt nicht mehr zugegriffen werden kann oder es den Bereich verlässt, wird der Arbeitsspeicher freigegeben.

## <a name="all-runtimes"></a>Alle Laufzeiten

### <a name="syntax"></a>Syntax

```cpp
      class_access
      ref class
      name
      modifier :  inherit_accessbase_type {};
class_accessref structnamemodifier :  inherit_accessbase_type {};
class_accessvalue classnamemodifier :  inherit_accessbase_type {};
class_accessvalue structnamemodifier :  inherit_accessbase_type {};
```

### <a name="parameters"></a>Parameter

*class_access*<br/>
(Optional) Die Möglichkeit des Zugriffs auf die Klasse oder Struktur außerhalb der Assembly. Mögliche Werte sind **public** und **private** (**private** ist der Standardwert). Geschachtelte Klassen oder Strukturen können keinen *class_access*-Bezeichner haben.

*name*<br/>
Der Name der Klasse oder Struktur.

*modifier*<br/>
(Optional) [abstract](abstract-cpp-component-extensions.md) und [sealed](sealed-cpp-component-extensions.md) sind gültige Modifizierer.

*inherit_access*<br/>
(Optional) Die Möglichkeit des Zugriffs auf *base_type*. Der einzige zulässige Zugriff ist **public** (**public** ist die Standardeinstellung).

*base_type*<br/>
(Optional) Ein Basistyp. Jedoch kann ein Werttyp nicht als Basistyp dienen.

Weitere Informationen finden Sie in den sprachspezifischen Beschreibungen für diesen Parameter in den Abschnitten „Windows-Runtime“ und „Common Language Runtime“.

### <a name="remarks"></a>Anmerkungen

Der Standardmemberzugriff auf ein mit **ref class** oder **value class** deklariertes Objekt ist **private**. Und der Standardmemberzugriff auf ein mit **ref struct** oder **value struct** deklariertes Objekt ist **public**.

Wenn ein Verweistyp von einem anderen Verweistyp erbt, dann müssen virtuelle Funktionen in der Basisklasse explizit überschrieben werden (mit [override](override-cpp-component-extensions.md)) oder ausgeblendet (mit [new (neuer Slot in vtable)](new-new-slot-in-vtable-cpp-component-extensions.md)). Die abgeleiteten Klassenfunktionen müssen auch explizit als **virtual** markiert sein.

Um zur Kompilierzeit zu erkennen, ob ein Typ eine **ref class** oder **ref struct** ist, oder eine **value class** oder **value struct**, verwenden Sie `__is_ref_class (type)`, `__is_value_class (type)` oder `__is_simple_value_class (type)`. Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](compiler-support-for-type-traits-cpp-component-extensions.md).

Weitere Informationen über Klassen und Strukturen finden Sie unter

- [Instanziieren von Klassen und Strukturen](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)

- [C++-Stack-Semantik für Referenztypen](../dotnet/cpp-stack-semantics-for-reference-types.md)

- [Klassen, Strukturen und Unions](../cpp/classes-and-structs-cpp.md)

- [„Destruktoren und Finalizer“ in „Vorgehensweise: Definieren und Verarbeiten von Klassen und Strukturen (C++/CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)

- [Benutzerdefinierte Operatoren (C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)

- [Benutzerdefinierte Konvertierungen (C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)

- [Vorgehensweise: Kapseln einer nativen Klasse zur Verwendung in C#](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

- [Generische Klassen (C++/CLI)](generic-classes-cpp-cli.md)

## <a name="windows-runtime"></a>Windows-Runtime

### <a name="remarks"></a>Anmerkungen

Weitere Informationen finden Sie unter [Verweisklassen und Strukturen](../cppcx/ref-classes-and-structs-c-cx.md) und [Wertklassen und Strukturen](https://msdn.microsoft.com/library/windows/apps/hh699861.aspx).

### <a name="parameters"></a>Parameter

*base_type*<br/>
(Optional) Ein Basistyp. Eine **ref class** oder **ref struct** kann von 0 (null) oder mehr Schnittstellen und 0 (null) oder einem **ref**-Typ erben. Eine **value class** oder **value struct** kann nur von 0 (null) oder mehr Schnittstellen erben.

Wenn Sie ein Objekt mithilfe der Schlüsselwörter **ref class** oder **ref struct** deklarieren, erfolgt der Zugriff auf das Objekt durch ein Handle für ein Objekt, d.h. einen Verweiszähler-Zeiger auf das Objekt. Wenn die deklarierte Variable den Gültigkeitsbereich verlässt, wird der Compiler automatisch das zugrunde liegende Objekt löschen. Wenn das Objekt als Parameter in einem Aufruf verwendet wird oder in einer Variablen gespeichert ist, wird ein Handle für das Objekt tatsächlich übergeben oder gespeichert.

Wenn Sie ein Objekt mithilfe der Schlüsselwörter **value class** oder **value struct** deklarieren, wird die Objektlebensdauer des deklarierten Objekts nicht überwacht. Das Objekt ist wie jede andere Standard-C++-Klasse oder -Struktur.

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="remarks"></a>Anmerkungen

Die folgende Tabelle listet die für C++/CLI spezifischen Unterschiede zu der im Abschnitt **Alle Laufzeiten** gezeigten Syntax auf.

### <a name="parameters"></a>Parameter

*base_type*<br/>
(Optional) Ein Basistyp. Eine **ref class** oder **ref struct** kann von 0 (null) oder mehr verwalteten Schnittstellen und 0 (null) oder einem ref-Typ erben. Eine **value class** oder **value struct** kann nur von 0 (null) oder mehr verwalteten Schnittstellen erben.

Die Schlüsselwörter **ref class** und **ref struct** teilen dem Compiler mit, dass die Klasse oder Struktur dem Heap zugeteilt wird. Wenn das Objekt als Parameter in einem Aufruf verwendet wird oder in einer Variablen gespeichert ist, wird eine Referenz für das Objekt tatsächlich übergeben oder gespeichert.

Die Schlüsselwörter **value class** und **value struct** teilen dem Compiler mit, dass der Wert der zugeordneten Klasse oder Struktur an Funktionen übergeben oder in Membern gespeichert wird.

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](component-extensions-for-runtime-platforms.md)