---
title: 'Vorgehensweise: Umwandeln eines STL/CLR-Containers in einer Sammlung von .NET | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, converting to .NET collections
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 111d1ab8515252d38179bd1ef9627b52fdbc0612
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403239"
---
# <a name="how-to-convert-from-a-stlclr-container-to-a-net-collection"></a>Gewusst wie: Umwandeln eines STL/CLR-Containers in eine .NET-Auflistung

In diesem Thema wird gezeigt, wie STL/CLR-Container in ihre äquivalente Sammlungen von .NET konvertiert. Beispielsweise erfahren, wie eine STL/CLR konvertieren [Vektor](../dotnet/vector-stl-clr.md) in ein .NET <xref:System.Collections.Generic.ICollection%601> und konvertieren Sie eine STL/CLR [Zuordnung](../dotnet/map-stl-clr.md) in ein .NET <xref:System.Collections.Generic.IDictionary%602>, aber das Verfahren ist für alle Sammlungen ähnlich und Container.

### <a name="to-create-a-collection-from-a-container"></a>So erstellen Sie eine Sammlung aus einem container

1. Verwenden Sie eine der folgenden Methoden:

   - Um Teil eines Containers zu konvertieren, rufen die [Make_collection](../dotnet/make-collection-stl-clr.md) Funktion, und übergeben Sie die Begin-Iterator und End-Iterator, der den STL/CLR-Container, die .NET Auflistung kopiert werden soll. Diese Vorlagenfunktion akzeptiert einen STL/CLR-Iterator als Vorlagenargument an. Das erste Beispiel veranschaulicht diese Methode.

   - Zum Konvertieren eines gesamten Containers wandeln Sie den Container an einem entsprechenden .NET sammlungsschnittstelle oder einer Schnittstelle-Auflistung. Das zweite Beispiel veranschaulicht diese Methode.

## <a name="example"></a>Beispiel

In diesem Beispiel erstellen wir eine STL/CLR `vector` , und fügen Sie 5 Elemente hinzu. Anschließend erstellen wir eine Sammlung von .NET durch Aufrufen der `make_collection` Funktion. Schließlich zeigen wir den Inhalt der neu erstellte Sammlung an.

```
// cliext_convert_vector_to_icollection.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/vector>

using namespace cliext;
using namespace System;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    cliext::vector<int> primeNumbersCont;
    primeNumbersCont.push_back(2);
    primeNumbersCont.push_back(3);
    primeNumbersCont.push_back(5);
    primeNumbersCont.push_back(7);
    primeNumbersCont.push_back(11);

    System::Collections::Generic::ICollection<int> ^iColl =
        make_collection<cliext::vector<int>::iterator>(
            primeNumbersCont.begin() + 1,
            primeNumbersCont.end() - 1);

    Console::WriteLine("The contents of the System::Collections::Generic::ICollection are:");
    for each (int i in iColl)
    {
        Console::WriteLine(i);
    }
}
```

```Output
The contents of the System::Collections::Generic::ICollection are:
3
5
7
```

## <a name="example"></a>Beispiel

In diesem Beispiel erstellen wir eine STL/CLR `map` , und fügen Sie 5 Elemente hinzu. Anschließend erstellen wir ein .NET <xref:System.Collections.Generic.IDictionary%602> und weisen Sie die `map` direkt an die Klasse. Schließlich zeigen wir den Inhalt der neu erstellte Sammlung an.

```
// cliext_convert_map_to_idictionary.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/map>

using namespace cliext;
using namespace System;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    cliext::map<float, int> ^aMap = gcnew cliext::map<float, int>;
    aMap->insert(cliext::make_pair<float, int>(42.0, 42));
    aMap->insert(cliext::make_pair<float, int>(13.0, 13));
    aMap->insert(cliext::make_pair<float, int>(74.0, 74));
    aMap->insert(cliext::make_pair<float, int>(22.0, 22));
    aMap->insert(cliext::make_pair<float, int>(0.0, 0));

    System::Collections::Generic::IDictionary<float, int> ^iDict = aMap;

    Console::WriteLine("The contents of the IDictionary are:");
    for each (KeyValuePair<float, int> ^kvp in iDict)
    {
        Console::WriteLine("Key: {0:F} Value: {1}", kvp->Key, kvp->Value);
    }
}
```

```Output
The contents of the IDictionary are:
Key: 0.00 Value: 0
Key: 13.00 Value: 13
Key: 22.00 Value: 22
Key: 42.00 Value: 42
Key: 74.00 Value: 74
```

## <a name="see-also"></a>Siehe auch

[Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)<br/>
[Vorgehensweise: Umwandeln einer .Net-Auflistung in einen STL/CLR-Container](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
[range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)