---
title: BLOB_NAME_STATUS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BLOB_NAME_STATUS
dev_langs:
- C++
helpviewer_keywords:
- BLOB_NAME_STATUS macro
ms.assetid: 4564e4a0-8e5e-436a-bd1e-012d2a1b8642
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cadd0217c25aed21e6788b7eba7c8d0778624b9d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092857"
---
# <a name="blobnamestatus"></a>BLOB_NAME_STATUS
Mit verwendet `BEGIN_COLUMN_MAP` und `END_COLUMN_MAP` binden ein binary large Object ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). Ähnlich wie [BLOB_NAME](../../data/oledb/blob-name.md), mit dem Unterschied, dass dieses Makro auch den Status der BLOB-Spalte erhält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
BLOB_NAME_STATUS(pszName, IID, flags, data  
, status )  
```  
  
#### <a name="parameters"></a>Parameter  
 `pszName`  
 [in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies bewerkstelligen, verlegen Sie eine "L" vor dem Namen, z. B.: `L"MyColumn"`.  
  
 *IID*  
 [in] Schnittstellen-GUID, wie z. B. **IDD_ISequentialStream**, mit denen das BLOB abrufen.  
  
 `flags`  
 [in] Vom OLE Structured Storage Modell definierte Speichermodus flags (z. B. **STGM_READ**).  
  
 `data`  
 [in] Die entsprechenden Datenmember im Benutzerdatensatz.  
  
 *status*  
 [out] Der Status des BLOB-Felds.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Funktionen für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_NAME](../../data/oledb/blob-name.md)   
 [BLOB_NAME_LENGTH](../../data/oledb/blob-name-length.md)   
 [BLOB_NAME_LENGTH_STATUS](../../data/oledb/blob-name-length-status.md)