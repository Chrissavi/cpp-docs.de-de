---
title: SafeAdd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeAdd
dev_langs:
- C++
helpviewer_keywords:
- SafeAdd function
ms.assetid: 3f82b91d-59fe-4ee1-873b-d056182fa8be
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b0450820afdde3eb330948a65f8d052fa54017dc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892715"
---
# <a name="safeadd"></a>SafeAdd
Addiert zwei Zahlen in einer Weise, die schützt vor Ganzzahlüberlauf an.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T, typename U>  
inline bool SafeAdd (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `t`  
 Die erste zu addierende Zahl. Dies muss vom Typ t sein.  
  
 [in] `u`  
 Die zweite zu addierende Zahl. Dies muss vom Typ u sein.  
  
 [out] `result`  
 Der Parameter, in denen `SafeAdd` speichert das Ergebnis.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn kein Fehler auftritt. `false` , wenn ein Fehler auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ist Teil des [SafeInt-Bibliothek](../windows/safeint-library.md) und eignet sich für eine einzelne Hinzufügung Vorgang ohne Erstellen einer Instanz von der [SafeInt-Klasse](../windows/safeint-class.md).  
  
> [!NOTE]
>  Diese Methode sollte nur verwendet werden, wenn eine einzelne mathematische Operation, die geschützt werden muss. Wenn mehrere Vorgänge vorhanden sind, sollten Sie verwenden die `SafeInt` Klasse anstelle von den einzelnen eigenständigen Funktionen aufrufen.  
  
 Weitere Informationen zu den Vorlagentypen T "und" U, finden Sie unter [SafeInt-Funktionen](../windows/safeint-functions.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## <a name="see-also"></a>Siehe auch  
 [SafeInt-Funktionen](../windows/safeint-functions.md)   
 [SafeInt-Bibliothek](../windows/safeint-library.md)   
 [SafeInt-Klasse](../windows/safeint-class.md)   
 [SafeSubtract](../windows/safesubtract.md)