---
title: 'SyncLockT:: ~ SyncLockT-Destruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- ~SyncLockT, destructor
ms.assetid: 9e14870d-017d-45fe-a3dc-cd86b6fa1c3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 85ff68b4a3739c9a258e8664f261c61bb47971db
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018519"
---
# <a name="synclocktsynclockt-destructor"></a>SyncLockT::~SyncLockT-Destruktor
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
~SyncLockT();  
```  
  
## <a name="remarks"></a>Hinweise  
 Hebt die Initialisierung einer Instanz von der **SyncLockT** Klasse.  
  
 Dieser Destruktor entsperrt auch die aktuelle **SyncLockT** Instanz.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Siehe auch  
 [SyncLockT-Klasse](../windows/synclockt-class.md)