---
title: RECT-Structure1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LPRECT
- RECT
dev_langs: C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9d3a33330ace97db19521362384356b58a6c8dca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="rect-structure1"></a>RECT-Structure1
Die `RECT`-Struktur definiert die Koordinaten der oberen linken und der unteren rechten Ecke eines Rechtecks.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagRECT {  
    LONG left;  
    LONG top;  
    LONG right;  
    LONG bottom;  
} RECT;  
```  
  
## <a name="members"></a>Member  
 `left`  
 Gibt die X-Koordinate der oberen linken Ecke eines Rechtecks an.  
  
 `top`  
 Gibt die Y-Koordinate der oberen linken Ecke eines Rechtecks an.  
  
 `right`  
 Gibt die X-Koordinate der unteren rechten Ecke eines Rechtecks an.  
  
 `bottom`  
 Gibt die Y-Koordinate der unteren rechten Ecke eines Rechtecks an.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** windef.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)