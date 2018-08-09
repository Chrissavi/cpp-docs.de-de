---
title: 'Asyncbase:: Checkvalidstateforresultscall-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall
dev_langs:
- C++
helpviewer_keywords:
- CheckValidStateForResultsCall method
ms.assetid: 87ca6805-bff1-4063-b855-6dd26132deff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dfa3b7222a25ed56d014cc90dbffa5f57a2c9436
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651907"
---
# <a name="asyncbasecheckvalidstateforresultscall-method"></a>AsyncBase::CheckValidStateForResultsCall-Methode
Testet, ob die Ergebnisse eines asynchronen Vorgangs in den aktuellen asynchronen Zustand erfasst werden können.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
inline HRESULT CheckValidStateForResultsCall();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn Ergebnisse erfasst werden können; andernfalls E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)