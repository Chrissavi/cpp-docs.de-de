---
title: Speichern von Zeichenfolgen im OLE DB-Anbieter | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a5ba289e7e53ba1bcaca550ba84c2d871d215306
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106985"
---
# <a name="storing-strings-in-the-ole-db-provider"></a>Speichern von Zeichenfolgen im OLE DB-Anbieter
In MyProviderRS.h, der ATL-OLE DB-Anbieter-Assistent erstellt einen Standard-Benutzerdatensatz aufgerufen `CWindowsFile`. Um die beiden Zeichenfolgen zu behandeln, ändern Sie entweder `CWindowsFile` oder eigene Benutzerdatensatz hinzufügen, wie im folgenden Code gezeigt:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
class CAgentMan:   
   public WIN32_FIND_DATA  
   DWORD dwBookmark;              // Add this  
   TCHAR szCommand[256];          // Add this  
   TCHAR szText[256];             // Add this  
   TCHAR szCommand2[256];         // Add this  
   TCHAR szText2[256];            // Add this  
  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP()  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command"), 1, 256, GUID_NULL, CAgentMan, szCommand)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text"), 2, 256, GUID_NULL, CAgentMan, szText)   
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command2"), 3, 256, GUID_NULL, CAgentMan, szCommand2)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text2"),4, 256, GUID_NULL, CAgentMan, szText2)  
END_PROVIDER_COLUMN_MAP()  
   bool operator==(const CAgentMan& am) // This is optional   
   {  
      return (lstrcmpi(cFileName, wf.cFileName) == 0);  
   }  
};  
```  
  
 Die Datenmember `szCommand` und `szText` stehen für die zwei Zeichenfolgen mit `szCommand2` und `szText2` bei Bedarf zusätzliche Spalten bereitstellen. Das Datenelement `dwBookmark` ist für diesen einfachen schreibgeschützten Anbieters nicht erforderlich, jedoch wird später verwendet, um das Hinzufügen einer `IRowsetLocate` Schnittstelle; finden Sie unter [Erweitern des einfachen lesen nur Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md). Die `==` Operator vergleicht Instanzen (Implementierung dieses Operators ist optional).  
  
 Nachdem dies geschehen ist, sollte Ihr Anbieter bereit sein zu kompilieren und auszuführen. Um den Anbieter zu testen, benötigen Sie einen Consumer mit übereinstimmenden Funktionen. [Implementieren eines einfachen Consumers](../../data/oledb/implementing-a-simple-consumer.md) wird gezeigt, wie solche einen Testconsumer erstellen. Führen Sie den Testconsumer mit dem Anbieter an. Stellen Sie sicher, dass der Testconsumer Ruft die richtigen Zeichenfolgen vom Anbieter ab, wenn Sie auf die **ausführen** Schaltfläche der **Testconsumer** (Dialogfeld).  
  
 Wenn Sie Ihren Anbieter erfolgreich getestet haben, empfiehlt es sich um die Funktionalität zu erhöhen, indem Sie weitere Schnittstellen implementieren. Ein Beispiel ist dargestellt, [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren des einfachen schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md)