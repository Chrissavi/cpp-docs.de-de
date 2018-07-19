---
title: 'CDynamicAccessor:: GetLength | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
dev_langs:
- C++
helpviewer_keywords:
- GetLength method
ms.assetid: 3ae8983b-b267-4cf9-bfc0-3e191f79e646
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cc7203f030fc3a9ca00839bc9955c85eaa770935
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090737"
---
# <a name="cdynamicaccessorgetlength"></a>CDynamicAccessor::GetLength
Ruft die Länge der angegebenen Spalte ab.  
  
## <a name="syntax"></a>Syntax  
  
```
bool GetLength(DBORDINAL nColumn,   
  DBLENGTH* pLength) const throw();  

bool GetLength(const CHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  

bool GetLength(const WCHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nColumn`  
 [in] Die Nummer der Spalte. Die spaltenzählung beginnt mit 1. Der Wert 0 verweist auf die Lesezeichenspalte, sofern vorhanden.  
  
 `pColumnName`  
 [in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.  
  
 `pLength`  
 [out] Ein Zeiger auf die ganze Zahl, die die Länge der Spalte in Bytes enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn die angegebene Spalte gefunden wird. Andernfalls, gibt diese Funktion **"false"**.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Außerkraftsetzung nimmt die Nummer der Spalte und die zweiten und dritten Außerkraftsetzungen schalten Sie den Spaltennamen im ANSI- oder Unicode-Format, bzw. aus.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetLength](../../data/oledb/cdynamicaccessor-setlength.md)