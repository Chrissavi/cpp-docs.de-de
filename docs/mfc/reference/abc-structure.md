---
title: ABC-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ABC
dev_langs: C++
helpviewer_keywords: ABC structure [MFC]
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7cc04527e5fc70feffd5a5fa81dc5149a5ecc130
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="abc-structure"></a>ABC-Struktur
Die **ABC** Struktur enthält die Breite eines Zeichens in eine TrueType-Schriftart.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _ABC { /* abc */  
    int abcA;  
    UINT abcB;  
    int abcC;  
} ABC;  
```  
  
#### <a name="parameters"></a>Parameter  
 *abcA*  
 Gibt den Abstand ein des Zeichens. Der Abstand ein entspricht dem Abstand, der aktuellen Position vor dem Zeichnen des Symbols Zeichen hinzuzufügen.  
  
 *abcB*  
 Gibt den Abstand B des Zeichens. Der Abstand B ist die Breite des gezeichneten Teils des Symbols für das Zeichen an.  
  
 *abcC*  
 Gibt den Abstand C des Zeichens. Der Abstand C entspricht dem Abstand hinzufügen zu der aktuellen Position bis Leerraum auf der rechten Seite des Symbols für das Zeichen bereitzustellen.  
  
## <a name="remarks"></a>Hinweise  
 Die Gesamtbreite der ein Zeichen ist die Summe der Adressbereiche A, B und C. Die oder der C-Raum kann an Underhangs oder Überhängen negativ sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

