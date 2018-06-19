---
title: ATL-Auflistungen und-Enumerationen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 537d7e8b7264beddc68805ab8b8dec2ce7883859
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356777"
---
# <a name="atl-collections-and-enumerators"></a>ATL-Auflistungen und -Enumerationen
Ein `collection` ist ein COM-Objekt, das eine Schnittstelle bereitstellt, die Zugriff auf eine Gruppe von Datenelementen (unformatierten Daten oder andere Objekte) ermöglicht. Eine Schnittstelle, die den Standards entspricht, für den Zugriff auf eine Gruppe von Objekten als bekannt ist ein *sammlungsschnittstelle*.  
  
 Collection-Schnittstellen müssen zumindest bereitstellen eine **Anzahl** Eigenschaft, die die Anzahl der Elemente in der Auflistung zurückgibt ein **Element** Eigenschaft, die Grundlage für einen Index aus der Auflistung ein Element zurückgibt und ein `_NewEnum` Eigenschaft, die einen Enumerator für die Auflistung zurückgibt. Optional können Auflistungsschnittstellen angeben **hinzufügen** und **entfernen** Methoden, um Elemente eingefügt oder aus der Auflistung gelöscht werden und ein **deaktivieren** -Methode zum Entfernen alle Elemente.  
  
 Ein `enumerator` ist ein COM-Objekt, das eine Schnittstelle zum Durchlaufen der Elemente in einer Auflistung bereitstellt. Enumeratorschnittstellen bieten die seriellen Zugriff auf die Elemente einer Auflistung über vier erforderlichen Methoden: `Next`, **Skip**, **zurücksetzen**, und `Clone`.  
  
 Sie erfahren mehr über Enumerator-Schnittstellen, lesen Sie die finden (aber vollständig imaginären) [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx) Schnittstelle.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [ATL-Auflistungen und -Enumeratorklassen](../atl/atl-collection-and-enumerator-classes.md)  
 Beschreibt kurz, und bietet Links zu den ATL-Klassen, die Ihnen helfen, Auflistungen und-Enumerationen implementieren.  
  
 [Designrichtlinien für Auflistungs- und Enumeratorschnittstellen](../atl/design-principles-for-collection-and-enumerator-interfaces.md)  
 Erläutert die unterschiedlichen Entwurfsprinzipien hinter jeden Typ der Schnittstelle an.  
  
 [Implementieren einer auf der C++-Standardbibliothek basierten Auflistung](../atl/implementing-an-stl-based-collection.md)  
 Ein umfangreicheres Beispiel, das Sie durch die Implementierung einer C++-Standardbibliothek-basierten Sammlung führt.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Enthält Links zu konzeptionellen Themen über die Programmierung mit der Active Template Library.  
  
 [-Beispiel](../visual-cpp-samples.md)  
 Ein Beispiel für die die Verwendung von `ICollectionOnSTLImpl` und `CComEnumOnSTL`, und die Implementierung von Klassen für benutzerdefinierte Richtlinie.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)

