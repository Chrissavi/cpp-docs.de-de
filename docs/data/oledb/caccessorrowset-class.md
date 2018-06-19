---
title: CAccessorRowset-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CAccessorRowset
- ATL.CAccessorRowset
- ATL::CAccessorRowset
dev_langs:
- C++
helpviewer_keywords:
- CAccessorRowset class
ms.assetid: bd4f58ed-cebf-4d43-8985-1e5fcbf06953
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 27d2153c6f600c3a5c75c1218e8751baaabcf030
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090969"
---
# <a name="caccessorrowset-class"></a>CAccessorRowset-Klasse
Kapselt ein Rowset und ihre zugeordneten Accessoren in einer einzelnen Klasse.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor = CNoAccessor, 
          template <typename T> class TRowset = CRowset>  
class CAccessorRowset : public TAccessor, public TRowset<TAccessor>  
```  
  
#### <a name="parameters"></a>Parameter  
 `TAccessor`  
 Ein Accessorklasse.  
  
 `TRowset`  
 Eine Rowsetklasse.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Binden](../../data/oledb/caccessorrowset-bind.md)|Erstellt von Bindungen (wird verwendet, wenn **bBind** wird angegeben als "false" in [CCommand:: Open](../../data/oledb/ccommand-open.md)).|  
|[CAccessorRowset](../../data/oledb/caccessorrowset-caccessorrowset.md)|Konstruktor.|  
|[Schließen](../../data/oledb/caccessorrowset-close.md)|Schließt das Rowset und alle Accessoren.|  
|[FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md)|Gibt alle Spalten im aktuellen Datensatz, der freigegeben werden müssen.|  
|[GetColumnInfo](../../data/oledb/caccessorrowset-getcolumninfo.md)|Implementiert [IColumnsInfo:: GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx).|  
  
## <a name="remarks"></a>Hinweise  
 Klasse `TAccessor` verwaltet die Zugriffsmethode. Klasse *TRowset* verwaltet das Rowset.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)