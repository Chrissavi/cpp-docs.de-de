---
title: 'CManualAccessor:: CreateAccessor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor::CreateAccessor
- CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
dev_langs:
- C++
helpviewer_keywords:
- CreateAccessor method
ms.assetid: 594c8d6d-b49a-4818-a9a5-81c8115d4e42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 93f3094c28efe519903fcc2418d26e0111d945a4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096713"
---
# <a name="cmanualaccessorcreateaccessor"></a>CManualAccessor::CreateAccessor
Belegt Speicher für die Spalte Strukturen binden, und die spaltendatenmember initialisiert.  
  
## <a name="syntax"></a>Syntax  
  
```
HRESULT CreateAccessor(int nBindEntries,   
  void* pBuffer,   
   DBLENGTH nBufferSize) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nBindEntries`  
 [in] Anzahl der Spalten. Diese Anzahl übereinstimmen, die Anzahl der Aufrufe an die [CManualAccessor:: AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md) Funktion.  
  
 `pBuffer`  
 [in] Ein Zeiger auf den Puffer, in denen die Ausgabespalten gespeichert sind.  
  
 `nBufferSize`  
 [in] Die Größe des Puffers in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
## <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird vor dem Aufrufen der `CManualAccessor::AddBindEntry` Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)   
 [DBViewer-Beispiel](../../visual-cpp-samples.md)