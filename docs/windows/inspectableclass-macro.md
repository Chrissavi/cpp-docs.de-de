---
title: InspectableClass-Makro | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
dev_langs:
- C++
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a02e20f2b87afc312c24683417f808d636c2757f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608955"
---
# <a name="inspectableclass-macro"></a>InspectableClass-Makro
Legt den Ablaufklassennamen und die Vertrauensebene fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
```  
  
### <a name="parameters"></a>Parameter  
 *runtimeClassName*  
 Der vollständige wörtliche Name der Laufzeitklasse.  
  
 *trustLevel*  
 Eines der [TrustLevel](http://msdn.microsoft.com/library/br224625.aspx) aufgelistete Werte bereitstellen.  
  
## <a name="remarks"></a>Hinweise  
 Die **InspectableClass** Makro kann nur mit Windows-Runtime-Typen verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [RuntimeClass-Klasse](../windows/runtimeclass-class.md)