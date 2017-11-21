---
title: time_base Class | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- locale/std::time_base
dev_langs:
- C++
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: c1c7c6c708087827c853234dcbd4519c79fba2bf
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="timebase-class"></a>time_base-Klasse
Die Klasse dient als Basisklasse für Facets der Vorlagenklasse time_get und definiert nur den Aufzählungstyp **dateorder** und mehrere Konstanten dieses Typs.  
  
## <a name="syntax"></a>Syntax  
  
```
class time_base : public locale::facet {
public:
    enum dateorder {no_order,
    dmy,
 mdy,
    ymd,
 ydm};
    time_base(
 size_t _Refs = 0)
 ~time_base();

};
```  
  
## <a name="remarks"></a>Hinweise  
 Jede Konstante kennzeichnet eine andere Möglichkeit, die Komponenten eines Datums zu ordnen. Es gibt folgende Konstanten:  
  
- **no_order** kennzeichnet keine bestimmte Reihenfolge.  
  
- **dmy** kennzeichnet die Reihenfolge Tag, Monat, Jahr wie in 2. Dezember 1979.  
  
- **mdy** kennzeichnet die Reihenfolge Monat, Tag, Jahr wie in Dezember 2, 1979.  
  
- **ymd** kennzeichnet die Reihenfolge Jahr, Monat, Tag wie in 1979/12/2.  
  
- **ydm** kennzeichnet die Reihenfolge Jahr, Tag, Monat wie in 1979: 2 Dez.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)



