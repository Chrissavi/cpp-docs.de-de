---
title: Änderungen, die Sie möglicherweise, um den Standardcode (MFC-Datenzugriff vornehmen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e647f6350819fa2cccb5f8319f95fbac16ca19fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33088364"
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>Mögliche Änderungen am Standardcode (MFC-Datenzugriff)
Die [MFC-Anwendung-Assistent](../mfc/reference/database-support-mfc-application-wizard.md) schreibt eine Recordset-Klasse, die alle Datensätze in einer einzelnen Tabelle auswählt. Dieses Verhalten können Sie häufig auf eine oder mehrere der folgenden Arten ändern:  
  
-   Legen Sie einen Filter oder eine Sortierreihenfolge für das Recordset fest. Führen Sie dies in `OnInitialUpdate` , nachdem das Recordset-Objekt, jedoch bevor erstellt seine **öffnen** Memberfunktion aufgerufen wird. Weitere Informationen finden Sie unter [Recordset: Filtern von Datensätzen (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) und [Recordset: Sortieren von Datensätzen (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).  
  
-   Parametrisieren Sie das Recordset. Geben Sie den tatsächlichen Laufzeit-Parameterwert nach dem Filter an. Weitere Informationen finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
-   Übergeben Sie eine benutzerdefinierte SQL-Zeichenfolge, die [öffnen](../mfc/reference/crecordset-class.md#open) Memberfunktion. Eine Erläuterung, was Sie mit dieser Technik erzielen können, finden Sie unter [SQL: Anpassen eines Recordsets SQL-Anweisung (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)