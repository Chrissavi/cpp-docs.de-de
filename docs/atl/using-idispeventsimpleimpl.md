---
title: Verwendung von IDispEventSimpleImpl (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventSimpleImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0cdef5012288b7f5f17040f73dfac5ec1f90d4f0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361947"
---
# <a name="using-idispeventsimpleimpl"></a>Verwendung von IDispEventSimpleImpl
Bei Verwendung `IDispEventSimpleImpl` um Ereignisse zu behandeln, müssen Sie:  
  
-   Leiten Sie eine Klasse von [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md).  
  
-   Fügen Sie ein Ereignis Sink-Zuordnung der Klasse hinzu.  
  
-   Definieren Sie [Sie _ATL_FUNC_INFO](../atl/reference/atl-func-info-structure.md) Strukturen, die die Ereignisse beschreibt.  
  
-   Fügen Sie Einträge mit dem Ereignissenke Zuordnung der [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info) Makro.  
  
-   Implementieren Sie die Methoden, die Sie behandeln interessiert sind.  
  
-   Melden Sie an und die Ereignisquelle.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Behandeln der **DocumentChange** Ereignis ausgelöst wird, von Word **Anwendung** Objekt. Dieses Ereignis wird als eine Methode definiert, auf die **ApplicationEvents** Disp-Schnittstelle.  
  
 Das Beispiel stammt aus dem [ATLEventHandling-Beispiel](../visual-cpp-samples.md).  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 Im Beispiel wird `#import` zum Generieren der erforderlichen Headerdateien aus der Typbibliothek für Word. Wenn Sie dieses Beispiel mit anderen Versionen von Word verwenden möchten, müssen Sie die korrekte Mso-Dll-Datei angeben. Z. B. Office 2000 bietet mso9.dll und OfficeXP mso.dll bereit. Dieser Code wird von "stdafx.h" vereinfacht:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventsimpleimpl_1.h)]  
  
 Die einzige Informationen aus der Typbibliothek, die tatsächlich verwendeten in diesem Beispiel wird die CLSID des Worts **Anwendung** -Objekt und die IID der **ApplicationEvents** Schnittstelle. Diese Informationen werden nur zum Zeitpunkt der Kompilierung verwendet.  
  
 Im folgende Code wird im Simple.h angezeigt. Der relevante Code wird durch Kommentare aufgeführt:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/cpp/using-idispeventsimpleimpl_2.h)]  
  
 Der folgende Code stammt aus Simple.cpp:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/cpp/using-idispeventsimpleimpl_3.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisbehandlung](../atl/event-handling-and-atl.md)   
 [ATLEventHandling-Beispiel](../visual-cpp-samples.md)

