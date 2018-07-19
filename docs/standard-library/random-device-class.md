---
title: random_device-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::random_device
- random/std::random_device::min
- random/std::random_device::max
- random/std::random_device::entropy
- random/std::random_device::operator()
dev_langs:
- C++
helpviewer_keywords:
- std::random_device [C++]
- std::random_device [C++], min
- std::random_device [C++], max
- std::random_device [C++], entropy
- std::random_device [C++], entropy
ms.assetid: 4393d515-0cb6-4e0d-a2ba-c780f05dc1bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ac22e146ac305be92d0b4be214465e64e8b6873
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856110"
---
# <a name="randomdevice-class"></a>random_device-Klasse

Generiert eine zufällige Sequenz von einem externen Gerät.

## <a name="syntax"></a>Syntax

```cpp
class random_device {
public:
   typedef unsigned int result_type;

   // constructor
   explicit random_device(const std::string& token = "");

   // properties
   static result_type min();
   static result_type max();
   double entropy() const;

   // generate
   result_type operator()();

   // no-copy functions
   random_device(const random_device&) = delete;
   void operator=(const random_device&) = delete;
   };
```

## <a name="members"></a>Member

|||
|-|-|
|[random_device](#random_device)|[entropy](#entropy)|
|[random_device::operator()](#op_call)||

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt eine Quelle von Zufallszahlen und darf - aber muss nicht - nach dem ISO C++-Standard nicht-deterministisch oder kryptografisch sicher sein. In der Visual Studio-Implementierung sind die produzierten Werte nicht-deterministisch und kryptografisch sicher, aber sie läuft langsamer als aus Modulen und Moduladaptern erstellte Generatoren (wie [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md), das hochwertige und schnelle Modul für die meisten Anwendungen).

`random_device`-Ergebnisse sind gleichförmig im geschlossenen Bereich [`0, 2`<sup>32</sup>) verteilt.

Es ist nicht garantiert, dass `random_device` zu einem nicht blockierenden Aufruf führt.

Im Allgemeinen wird `random_device` verwendet, um andere mithilfe von Engines oder Engine-Adaptern erstellte Generatoren mit Startwerten auszustatten. Weitere Informationen finden Sie unter[\<random>](../standard-library/random.md).

## <a name="example"></a>Beispiel

Mit dem folgenden Code werden die grundlegende Funktion dieser Klasse und Beispielergebnisse veranschaulicht. Aufgrund der nicht-deterministischen Struktur von `random_device` entsprechen die im Abschnitt **Output** gezeigten Zufallswerte nicht Ihren Ergebnissen. Dies ist normal und zu erwarten.

```cpp
// random_device_engine.cpp
// cl.exe /W4 /nologo /EHsc /MTd
#include <random>
#include <iostream>
using namespace std;

int main()
{
    random_device gen;

    cout << "entropy == " << gen.entropy() << endl;
    cout << "min == " << gen.min() << endl;
    cout << "max == " << gen.max() << endl;

    cout << "a random value == " << gen() << endl;
    cout << "a random value == " << gen() << endl;
    cout << "a random value == " << gen() << endl;
}
```

```Output
entropy == 32
min == 0
max == 4294967295
a random value == 2378414971
a random value == 3633694716
a random value == 213725214
```

Dieses Beispiel ist vereinfacht und nicht repräsentativ für den generellen Verwendungsfall dieses Generators. Ein repräsentativeres Codebeispiel finden Sie unter [\<random>](../standard-library/random.md).

## <a name="requirements"></a>Anforderungen

**Header:** \<random>

**Namespace:** std

## <a name="random_device"></a> random_device::random_device

Konstruiert den Generator.

```cpp
random_device(const std::string& = "");
```

### <a name="remarks"></a>Hinweise

Der Konstruktor initiiert bei Bedarf den Generator und ignoriert dabei den Zeichenfolgenparameter. Löst einen Wert eines durch die Implementierung definierten Typen aus, der aus [Ausnahme](../standard-library/exception-class.md) abgeleitet wird, wenn `random_device` nicht initialisiert werden konnte.

## <a name="entropy"></a> random_device::entropy

Schätzt den Zufallscharakter der Quelle ab.

```cpp
double entropy() const noexcept;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt eine, wie in Bits gemessene, Schätzung des Zufallscharakters der Quelle zurück.

## <a name="op_call"></a> random_device::operator()

Gibt einen zufälligen Wert zurück.

```cpp
result_type operator()();
```

### <a name="remarks"></a>Hinweise

Gibt Werte zurück, die im geschlossenen Intervall [`min, max`] gleichförmig verteilt sind, wie durch die Memberfunktionen `min()` und `max()` festgelegt. Löst einen Wert eines durch die Implementierung definierten Typs aus, der aus [Auswahl](../standard-library/exception-class.md) abgeleitet wird, wenn keine Zufallszahl abgerufen werden konnte.

## <a name="see-also"></a>Siehe auch

[\<random>](../standard-library/random.md)<br/>
