---
title: eindeutige (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::unique
dev_langs:
- C++
helpviewer_keywords:
- unique function [STL/CLR]
ms.assetid: 833cc314-b452-4659-bbb4-575c2bb63855
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 95e4ae3fe883f122f3a806dbcba017a0161c84b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164158"
---
# <a name="unique-stlclr"></a>unique (STL/CLR)
Entfernt doppelte Elemente, die in einem angegebenen Bereich nebeneinander angeordnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `unique`. Weitere Informationen finden Sie unter [eindeutige](../standard-library/algorithm-functions.md#unique).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)