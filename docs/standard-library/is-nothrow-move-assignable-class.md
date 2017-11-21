---
title: is_nothrow_move_assignable-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_nothrow_move_assignable
dev_langs: C++
helpviewer_keywords: is_nothrow_move_assignable
ms.assetid: 000baa02-cbba-49de-9870-af730033348e
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9e085e08da521f891875b2829abf17ea21614fac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="isnothrowmoveassignable-class"></a>is_nothrow_move_assignable-Klasse
Testet, ob der Typ einen **nothrow**-Bewegungszuweisungsoperator aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
struct is_nothrow_move_assignable;
```  
  
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der `Ty`-Typ einen nothrow-Verschiebungszuweisungsoperator aufweist; andernfalls „false“.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)



