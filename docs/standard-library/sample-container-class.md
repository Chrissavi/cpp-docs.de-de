---
title: Sample Container-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- container classes [C++]
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a6205247a468f403357245f9b2e8d1abd558f95
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858366"
---
# <a name="sample-container-class"></a>Sample Container-Klasse

> [!NOTE]
> Dieses Thema ist in der Dokumentation zu Visual C++ als nicht funktionierendes Beispiel für Container aufgeführt, die in der C++-Standardbibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekcontainer](../standard-library/stl-containers.md).

Beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, normalerweise vom Typ **Ty**. Die Folge ist unterschiedlich gespeichert, abhängig vom tatsächlichen Container.

Ein Containerkonstruktor oder eine Memberfunktion finden möglicherweise Anlass, den Konstruktor **Ty**(**const Ty &**) oder die Funktion **Ty::operator =**(**const Ty &**) aufzurufen. Wenn solch ein Aufruf eine Ausnahme auslöst, ist das Containerobjekt verpflichtet, seine Integrität beizubehalten, und jede Ausnahme, die es entdeckt, erneut auslösen. Sie können ein Containerobjekt sicher austauschen, zuweisen, löschen oder zerstören, nachdem es eine dieser Ausnahmen auslöst. Im Allgemeinen jedoch können Sie den Zustand der vom Containerobjekt kontrollierten Sequenz andernfalls nicht vorhersagen.

Einige zusätzliche Vorsichtsmaßnahmen:

- Wenn der Ausdruck **~ Ty** eine Ausnahme auslöst, ist der resultierende Status des Containerobjekts nicht definiert.

- Wenn der Container ein Zuweisungsobjekt speichert *al*, und *al* löst eine Ausnahme außer infolge eines Aufrufs für * al ***.allocate**, der sich ergebende Zustand des Containers Objekt ist nicht definiert.

- Wenn der Container ein Funktionsobjekt *comp* speichert, um zu bestimmen, wie die kontrollierte Sequenz sortiert wird und *comp* eine beliebige Ausnahme auslöst, ist der resultierende Status des Containerobjekts nicht definiert.

Die Containerklassen, die von der C++-Standardbibliothek definiert werden, erfüllen noch weitere Anforderungen, wie in den folgenden Abschnitten beschrieben.

Die Containervorlagenklasse [list](../standard-library/list-class.md) enthält deterministisches und nützliches Verhalten, auch bei den oben beschriebenen Ausnahmen. Wenn beispielsweise eine Ausnahme während des Einfügens von einem oder mehreren Elementen ausgelöst wird, bleibt der Container unverändert, und die Ausnahme wird erneut ausgelöst.

Für *alle* die Containerklassen, die C++-Standardbibliothek definiert werden, wenn eine Ausnahme, während Aufrufe an die folgenden Memberfunktionen ausgelöst wird **einfügen**, **Push_back**, oder **Push_front**, der Container unverändert, und die Ausnahme erneut ausgelöst wird.

Für *alle* die Containerklassen, die von C++-Standardbibliothek definiert, während Aufrufe an die folgenden Memberfunktionen wird keine Ausnahme ausgelöst: **Pop_back**, **Pop_front**.

Die Memberfunktion [erase](../standard-library/container-class-erase.md) löst eine Ausnahme nur aus, wenn ein Kopiervorgang (Zuweisung oder Copy-Konstruktion) eine Ausnahme auslöst.

Darüber hinaus wird keine Ausnahme ausgelöst, während des Kopiervorgangs eines Iterators, der von einer Memberfunktion zurückgegeben wird.

Die Memberfunktion [swap](../standard-library/container-class-swap.md) macht zusätzliche Zusagen für *alle* Containerklassen, die von der C++-Standardbibliothek definiert werden:

- Die Memberfunktion löst eine Ausnahme nur dann aus, wenn der Container eine Zuweisungsobjekt al speichert und `al` löst beim Kopiervorgang eine Ausnahme aus.

- Verweise, Zeiger und Iteratoren, die getauschte Elemente der gesteuerten Sequenzen anzeigen, bleiben gültig.

Ein Objekt einer Containerklasse, die von der C++-Standardbibliothek definiert wird, reserviert Speicher und gibt ihn für die gesteuerte Sequenz frei, die sie durch ein gespeichertes Objekt vom Typ `Alloc` kontrolliert. Dieser ist gewöhnlich ein Vorlagenparameter. Ein solches Zuweisungsobjekt muss die gleiche externe Schnittstelle wie ein Objekt der Klasse **allocator\<Ty>** aufweisen. Insbesondere `Alloc` muss der gleiche Typ wie **Alloc::rebind<value_type>:: other** sein.

Für *alle* Containerklassen, die von der C++-Standardbibliothek definiert werden, gibt die Memberfunktion **Alloc get_allocator const;** eine Kopie des gespeicherten Zuordnungsobjekts zurück. Beachten Sie, dass das gespeicherte Zuweisungsobjekt *nicht* kopiert wird, wenn das Containerobjekt zugewiesen wird. Alle Konstruktoren initialisieren den in **Zuweisung** gespeicherten Wert zu `Alloc`, wenn der Konstruktor keine Zuweisungsparameter enthält.

Entsprechend dem C++-Standard kann eine Container-Klasse, die die C++-Standardbibliothek definiert, folgendes darstellen:

- Alle Objekte der Klasse `Alloc` sind beim Vergleich gleich.

- Der Typ **Alloc::const_pointer** ist derselbe wie **const Ty \***.

- Der Typ **Alloc::const_pointer** ist derselbe wie **const Ty&** .

- Der Typ **Alloc::const_pointer** ist derselbe wie **Ty \***.

- Der Typ **Alloc::const_pointer** ist derselbe wie **Ty&** .

In dieser Implementierung treffen Container jedoch nicht solche vereinfachende Annahmen. Daher arbeiten sie ordnungsgemäß mit Zuweisungsobjekten, die ehrgeiziger sind:

- Alle Objekte der `Alloc`-Klasse werden beim Vergleich nicht gleich abschneiden. (Sie können mehrere Speicherpools verwalten.)

- Der Typ **Alloc::const_pointer** braucht nicht vom selben Type wie **const Ty \***. (Ein const-Zeiger kann eine Klasse sein.)

- Der Typ **Alloc::pointer** braucht nicht vom selben Type wie **Ty \***. (Ein Zeiger kann eine Klasse sein.)

## <a name="requirements"></a>Anforderungen

**Header**: \<sample container>

## <a name="see-also"></a>Siehe auch

[\<sample container>](../standard-library/sample-container.md)<br/>
