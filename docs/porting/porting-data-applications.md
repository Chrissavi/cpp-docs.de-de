---
title: Portieren von Datenanwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/12/2017
ms.technology:
- devlang-cpp
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], data access applications
- databases [C++], MFC
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: 8d10c285-c13f-4e6e-a09e-5ee0f2666b44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c20b9b6e8c1e96736485f302203156f627ef6794
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2018
ms.locfileid: "42578473"
---
# <a name="porting-data-applications"></a>Portieren von Datenanwendungen
Über die Jahre hinweg hat Visual C++ mehrere Möglichkeiten zum Arbeiten mit Datenbanken bereitgestellt. 2011 kündigte Microsoft an, dass das Ausrichten auf ODBC als bevorzugte Technologie für den Zugriff auf SQL Server-Produkte über nativen Code angewendet wird. ODBC ist ein Branchenstandard, durch dessen Verwendung Sie die maximale Portabilität Ihres Codes über mehrere Plattformen und Datenquellen erreichen. Die meisten SQL-Datenbankprodukte und viele NoSQL-Produkte unterstützen ODBC. Sie können ODBC direkt verwenden, indem Sie die ODBC-APIs auf niedriger Ebene aufrufen, oder Sie können die MFC-ODBC-Wrapperklassen oder eine C++-Wrapperbibliothek eines Drittanbieters verwenden. 

OLE DB ist eine leistungsstarke API auf niedriger Ebene, die auf der COM-Spezifikation basiert und nur unter Windows unterstützt wird. Verwenden Sie OLE DB, wenn Ihr Programm auf [Verbindungsserver](/sql/relational-databases/linked-servers/linked-servers-database-engine) zugreift. ATL stellt OLE DB-Vorlagen bereit, die das Erstellen von benutzerdefinierten OLE DB-Anbietern und -Consumern vereinfachen. Die neueste Version von OLE DB wird mit SQL Native Client 11 bereitgestellt.  

Wenn Ihre ältere Anwendung OLE DB oder die ADO-Schnittstelle auf höherer Ebene verwendet, um eine Verbindung mit SQL Server herzustellen, und Sie nicht auf Verbindungsserver zugreifen, sollten Sie eine Migration zu ODBC in naher Zukunft in Betracht ziehen. Wenn Sie keine plattformübergreifende Portabilität oder keine der neuesten SQL Server-Funktionen benötigen, können Sie wahrscheinlich den Microsoft OLE DB-Anbieter für ODBC (MSDASQL) verwenden.  MSDASQL ermöglicht Anwendungen, die auf OLE DB und ADO (das OLE DB intern verwendet) erstellt wurden, den Zugriff auf Datenquellen über einen ODBC-Treiber. Wie bei jeder Translationsebene kann sich MSDASQL auf die Datenbankleistung auswirken. Sie sollten testen, ob die Auswirkung für Ihre Anwendung erheblich ist. MSDASQL ist im Lieferumfang des Windows-Betriebssystems enthalten, und Windows Server 2008 sowie Windows Vista SP1 sind die ersten Windows-Releases, in denen eine 64-Bit-Version der Technologie enthalten ist.

Die SQL Native Client-Komponente (SNAC), die OLE DB- und ODBC-Treiber in eine einzelne DLL packt, wird in ODBC-Anwendungen nicht mehr unterstützt. Die SQL Server 2012-Version von SNAC (SQLNCLI11.DLL) wird mit SQL Server 2016 geliefert, da andere SQL Server-Komponenten davon abhängig sind. Allerdings sollten neue C++-Anwendungen, die über ODBC eine Verbindung mit SQL Server oder Azure SQL-Datenbank herstellen, [den neuesten ODBC-Treiber](https://docs.microsoft.com/en-us/sql/connect/odbc/download-odbc-driver-for-sql-server) verwenden. Weitere Informationen finden Sie unter [SQL Server Native Client Programming (SQL Server Native Client-Programmierung)](/sql/relational-databases/native-client/sql-server-native-client-programming)

Wenn Sie C++/CLI verwenden, können Sie weiterhin wie gewohnt ADO.NET verwenden. Weitere Informationen finden Sie unter [Datenzugriff mit ADO.NET (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md) und [Zugreifen auf Daten in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).  
  
- Zusätzlich zu den ODBC-Wrapperklassen stellt MFC auch Datenzugriffsobjekt-Wrapperklassen (Data Access Object, DAO) zum Herstellen einer Verbindung mit Access-Datenbanken bereit.  DAO ist jedoch veraltet. Jeder Code, der auf `CDaoDatabase` oder `CDaoRecordset` basiert sollte aktualisiert werden. 

Weitere Informationen zur Geschichte von Datenzugriffstechnologien unter Windows finden Sie unter [Microsoft Data Access Components (Wikipedia) (Microsoft-Datenzugriffskomponenten)](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components).  

## <a name="see-also"></a>Siehe auch  
 
[Datenzugriff in Visual C++](../data/data-access-in-cpp.md)  
[Microsoft Open Database Connectivity (ODBC)](https://docs.microsoft.com/sql/odbc/microsoft-open-database-connectivity-odbc)  
[Data Access Technologies Road Map (Überblick über Datenzugriffstechnologien)](https://msdn.microsoft.com/library/ms810810.aspx)  