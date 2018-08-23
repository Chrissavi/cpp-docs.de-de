---
title: GetModuleBase-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
dev_langs:
- C++
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 403330097f1428ee0d7650f5931aef1621f61b11
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612600"
---
# <a name="getmodulebase-function"></a>GetModuleBase-Funktion
Ruft eine [ModuleBase](../windows/modulebase-class.md) Zeiger, der inkrementiert und dekrementiert den Verweiszähler des ermöglicht eine [RuntimeClass](../windows/runtimeclass-class.md) Objekt.
  
## <a name="syntax"></a>Syntax
  
```cpp
inline Details::ModuleBase* GetModuleBase() throw()  
```
  
## <a name="return-value"></a>Rückgabewert
 Ein Zeiger auf eine `ModuleBase` Objekt.
  
## <a name="remarks"></a>Hinweise
 Diese Funktion wird intern zum Inkrementieren und Dekrementieren verwendet Verweiszähler des Objekts.
  
 Sie können diese Funktion verwenden, zum Steuern der Verweiszähler durch Aufrufen von [modulebase:: Incrementobjectcount](../windows/modulebase-incrementobjectcount-method.md) und [modulebase:: Decrementobjectcount](../windows/modulebase-decrementobjectcount-method.md).
  
## <a name="requirements"></a>Anforderungen
 **Header:** implements.h
  
 **Namespace:** Microsoft::WRL
  
## <a name="see-also"></a>Siehe auch
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)