---
title: 'CDynamicParameterAccessor:: GetParam | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicParameterAccessor::GetParam
- ATL.CDynamicParameterAccessor.GetParam
- CDynamicParameterAccessor::GetParam<ctype>
- CDynamicParameterAccessor.GetParam
- GetParam
- ATL::CDynamicParameterAccessor::GetParam<ctype>
- ATL::CDynamicParameterAccessor::GetParam
dev_langs:
- C++
helpviewer_keywords:
- GetParam method
ms.assetid: 893a6bf8-7b55-4f6d-8a10-a43b13be7f56
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3596cf8fc445a5607c008be687c44cafb713049b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090900"
---
# <a name="cdynamicparameteraccessorgetparam"></a>CDynamicParameterAccessor::GetParam
Ruft die Zeichenfolgendaten für einen angegebenen Parameter aus dem Parameterpuffer ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
template <class ctype>bool GetParam(DBORDINAL nParam,   
  ctype* pData) const throw();  

template <class ctype> bool GetParam(TCHAR* pParamName,   
   ctype* pData) const throw();  

void* GetParam(DBORDINAL nParam) const throw();  

void* GetParam(TCHAR* pParamName) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `ctype`  
 Ein aus einer Vorlage gebildete-Parameter, der den Datentyp darstellt.  
  
 `nParam`  
 [in] Die Parameteranzahl (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Parameteranzahl ist der Index des Parameters basierend auf der Reihenfolge der SQL-oder einen Aufruf einer gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) ein Beispiel.  
  
 `pParamName`  
 [in] Der Name des Parameters.  
  
 `pData`  
 [out] Der Zeiger auf den Speicher mit den Daten aus dem Puffer abgerufen werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Für auf Vorlagen basierende Versionen abgerufen, verweist auf den Speicher mit den Daten aus dem Puffer. Für auf Vorlagen basierende Versionen gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler.  
  
 Verwendung `GetParam` abzurufenden Objektressourcen Parameterdaten aus dem Puffer. Verwendung [GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md) abzurufenden Zeichenfolge Parameterdaten aus dem Puffer.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)