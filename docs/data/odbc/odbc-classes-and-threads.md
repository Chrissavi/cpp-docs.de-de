---
title: ODBC-Klassen und Threads | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dedd1f03bf14e0513f9f76a1e292b9180e4d60db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090587"
---
# <a name="odbc-classes-and-threads"></a>ODBC-Klassen und Threads
Ab MFC 4.2 ist Multithreadingunterstützung für die MFC-ODBC-Klassen. Beachten Sie jedoch, dass MFC keine Multithreadingunterstützung für den DAO-Klassen.  
  
 Die Multithreadingunterstützung für die ODBC-Klassen gelten einige Einschränkungen. Da diese Klassen die ODBC-API umschließen, sind sie beschränkt auf die Multithreadingunterstützung der Komponenten auf denen sie erstellt werden. Beispielsweise sind viele ODBC-Treiber nicht threadsichere; Daher sind die MFC-ODBC-Klassen nicht threadsicher, wenn Sie diese mit einem dieser Treiber verwenden. Überprüfen Sie, ob Ihre bestimmte Treiber threadsicher ist.  
  
 Wenn Sie eine Multithreadanwendung zu erstellen, sollten Sie vorsichtig mithilfe mehrerer Threads dasselbe Objekt bearbeiten können. Beispielsweise unter Verwendung des gleichen `CRecordset` Objekt in zwei Threads möglicherweise Probleme verursachen, beim Abrufen von Daten; ein Fetch-Vorgang in einem Thread möglicherweise die Daten abgerufen, in dem anderen Thread zu überschreiben. Eine gemeinsame Verwendung der MFC-ODBC-Klassen in separaten Threads ist ein offenes freigeben `CDatabase` -Objekt threadübergreifend verwenden dieselbe ODBC-Verbindung mit einem separaten `CRecordset` Objekt in jedem Thread. Beachten Sie, dass Sie keine geöffnete übergeben soll `CDatabase` -Objekt an eine `CRecordset` Objekt in einem anderen Thread.  
  
> [!NOTE]
>  Wenn Sie mehrere Threads dasselbe Objekt bearbeiten benötigen, sollten Sie die entsprechenden Synchronisierungsmechanismen, z. B. kritische Abschnitte implementieren. Beachten Sie, dass bestimmte Vorgänge, wie z. B. **öffnen**, sind nicht geschützt. Sie sollten sicher sein, dass diese Vorgänge nicht aus verschiedenen Threads gleichzeitig aufgerufen werden.  
  
 Weitere Informationen zum Erstellen von Multithreadanwendungen verwendet werden können, finden Sie unter [Themen zu Multithreading](../../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Open Sie Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Datenzugriffsprogrammierung (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)