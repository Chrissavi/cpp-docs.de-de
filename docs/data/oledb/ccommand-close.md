---
title: 'CCommand:: Close | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CCommand.Close
- CCommand::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 4da9c02c-7082-4e47-a0fa-78b546f0f7d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5723c358e0af7cf9b92952bfd843ba90577333e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089763"
---
# <a name="ccommandclose"></a>CCommand::Close
Gibt den Accessor-Rowset, das mit dem Befehl verknüpfte frei.  
  
## <a name="syntax"></a>Syntax

```cpp
void Close();  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein Befehl verwendet ein Rowset, Ergebnis Set-Accessor und (optional) Parameteraccessor (im Gegensatz zu Tabellen, bei denen unterstützen keine Parameter und Parameteraccessor ist nicht erforderlich).  
  
 Wenn Sie einen Befehl ausführen, sollten Sie beide Aufrufen `Close` und [ReleaseCommand](../../data/oledb/ccommand-releasecommand.md) nach dem Befehl.  
  
 Wenn Sie denselben Befehl wiederholt ausführen möchten, sollten Sie jedes Ergebnis Set-Accessor freigeben, durch den Aufruf `Close` vor dem Aufruf `Execute`. Sie sollten die Parameteraccessor durch Aufrufen von freigeben, am Ende der Reihe `ReleaseCommand`. Ein weiteres gängiges Szenario ist das Aufrufen einer gespeicherten Prozedur, die Output-Parameter verfügt. Auf viele Anbieter (z. B. der OLE DB-Anbieter für SQL Server) können die Werte der Ausgabeparameter nicht zugegriffen werden, bis Sie die Set-Zugriffsmethode Ergebnis schließen. Rufen Sie `Close` um das zurückgegebene Rowset und Ergebnis-Set-Accessor, jedoch nicht die Parameteraccessor zu schließen, wodurch Sie die Ausgabeparameterwerte abgerufen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie aufrufen können `Close` und `ReleaseCommand` Wenn Sie denselben Befehl wiederholt ausführen.  
  
 [!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CCommand-Klasse](../../data/oledb/ccommand-class.md)   
 [CCommand::ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)