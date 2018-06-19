---
title: 'CRowsetImpl:: Namefromdbid | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl.NameFromDBID
- CRowsetImpl::NameFromDBID
dev_langs:
- C++
helpviewer_keywords:
- NameFromDBID method
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 54ee345d4bf97c6f77398e62d1cb31614868a568
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097253"
---
# <a name="crowsetimplnamefromdbid"></a>CRowsetImpl::NameFromDBID
Extrahiert eine Zeichenfolge aus einem **DBID** und kopiert ihn auf die `bstr` übergeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CRowsetBaseImpl::NameFromDBID(DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pDBID*  
 [in] Ein Zeiger auf die **DBID** aus der Zeichenfolge extrahiert.  
  
 `bstr`  
 [in] Ein [CComBSTR](../../atl/reference/ccombstr-class.md) Verweis platziert eine Kopie der **DBID** Zeichenfolge.  
  
 `bIndex`  
 [in] **"true"** Wenn ein Index **DBID**; **"false"** Wenn eine Tabelle **DBID**.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt. Je nachdem, ob die **DBID** ist eine Tabelle oder eines Indexes (gekennzeichnet durch `bIndex`), die Methode wird entweder **DB_E_NOINDEX** oder **DB_E_NOTABLE**.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem Sie die `CRowsetImpl` Implementierungen von [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) und [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [CRowsetImpl-Klasse](../../data/oledb/crowsetimpl-class.md)