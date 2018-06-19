---
title: Steuerelementtypen für die Symbolleiste | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1958c83ef5a0eec5f3c7f5873451edd3839146be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373194"
---
# <a name="toolbar-control-styles"></a>Steuerelementtypen für die Symbolleiste
[CMFCToolBarButton Klasse](../../mfc/reference/cmfctoolbarbutton-class.md) verfügt über einen Satz von Style Flags, die bestimmen, die Darstellung und Verhalten der Schaltfläche. Sie können eine Kombination dieser Flags festlegen, durch den Aufruf [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle). Dieses Thema enthält die Style-Flagwerte und ihre Bedeutungen.  
  
## <a name="property-values"></a>Eigenschaftswerte  
 Die folgenden Werte bestimmen die Art der Schaltfläche, die das Steuerelement darstellt:  
  
 TBBS_BUTTON  
 Standardmäßige Pushbutton (Standard).  
  
 TBBS_CHECKBOX  
 das Kontrollkästchen.  
  
 TBBS_CHECKGROUP  
 Der Anfang einer Gruppe von Kontrollkästchen.  
  
 TBBS_GROUP  
 Der Anfang einer Gruppe von Optionsfeldern.  
  
 TBBS_SEPARATOR  
 Als Trennzeichen.  
  
 Die folgenden Werte stellen den aktuellen Status des Steuerelements dar:  
  
 TBBS_CHECKED  
 Das Kontrollkästchen aktiviert ist.  
  
 TBBS_DISABLED  
 Das Steuerelement ist deaktiviert.  
  
 TBBS_INDETERMINATE  
 Das Kontrollkästchen ist in einem unbestimmten Zustand.  
  
 TBBS_PRESSED  
 Gedrückt wird.  
  
 Der folgende Wert ändert das Layout der Schaltfläche in der Symbolleiste:  
  
 TBBS_BREAK  
 Platziert das Element in einer neuen Zeile oder in einer neuen Spalte ohne Spalten aufteilen.  
  
## <a name="remarks"></a>Hinweise  
 Das aktuelle Format befindet sich in [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle). Legen Sie einen neuen Wert nicht `m_nStyle` direkt, da einige abgeleiteten Klassen zusätzliche Verarbeitungsschritte beim Aufrufen von `SetStyles`.  
  
 Die visuelle Manager bestimmt die Darstellung der Schaltflächen in den einzelnen Zuständen. Finden Sie unter [Visualisierungs-Manager](../../mfc/visualization-manager.md) für Weitere Informationen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbarbutton.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Visualisierungs-Manager](../../mfc/visualization-manager.md)


