---
title: QueryInterface | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cde92ee56e51a86acbfb7e459571291bc3cae76c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356960"
---
# <a name="queryinterface"></a>QueryInterface
Es gibt, zwar Mechanismen, die mit dem express ein Objekt kann die Funktionalität bietet statisch (vor er instanziiert wird) der grundlegende Mechanismus von COM ist die Verwendung der **IUnknown** Methode mit dem Namen [QueryInterface ](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 Jede Schnittstelle abgeleitet **IUnknown**, sodass jede Schnittstelle eine Implementierung von `QueryInterface`. Unabhängig von der Implementierung fragt diese Methode ein Objekt, das über die IID der Schnittstelle, die vom Aufrufer eines Zeigers. Wenn das Objekt über diese Schnittstelle unterstützt `QueryInterface` Ruft einen Zeiger auf die Schnittstelle, während des Aufrufs auch `AddRef`. Andernfalls gibt es die **E_NOINTERFACE** Fehlercode.  
  
 Beachten Sie, die Sie befolgen müssen [Verweiszählung](../atl/reference-counting.md) Regeln jederzeit. Beim Aufrufen **Version** auf einen Schnittstellenzeiger dekrementiert den Verweiszähler auf 0 (null), sollten Sie keine verwenden diesen Zeiger erneut aus. Gelegentlich müssen Sie möglicherweise einen schwachen Verweis auf ein Objekt zu erhalten (d. h., möglicherweise möchten Sie einen Zeiger auf eine der Schnittstellen zu erhalten, ohne den Verweiszähler zu inkrementieren), aber es ist nicht zulässig hierfür durch Aufrufen von `QueryInterface` gefolgt von  **Version**. Der Zeiger auf solche Weise abgerufen ist ungültig und sollte nicht verwendet werden. Dadurch wird schneller deutlich Wenn [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) definiert ist, damit diese Makros definieren eine hilfreiche Möglichkeit suchen, verweiszählung Fehler ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [QueryInterface: Navigieren in einem Objekt](http://msdn.microsoft.com/library/windows/desktop/ms687230)

