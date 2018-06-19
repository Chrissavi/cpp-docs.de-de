---
title: CMFCImageEditorPaletteBar Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::GetRowHeight
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorPaletteBar [MFC], GetRowHeight
- CMFCImageEditorPaletteBar [MFC], IsButtonExtraSizeAvailable
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e377a465dd55d8940e74617130216220d03f1218
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370041"
---
# <a name="cmfcimageeditorpalettebar-class"></a>CMFCImageEditorPaletteBar-Klasse
Stellt Palette Leiste Funktionalität um ein Bild-Editor (Dialogfeld) bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCImageEditorPaletteBar : public CMFCToolBar  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCImageEditorPaletteBar::GetRowHeight](#getrowheight)|Gibt die Höhe des Symbolleistenschaltflächen zurück. (Überschreibt [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|  
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Bestimmt, ob die Symbolleiste Schaltflächen angezeigt werden kann, die Ränder erweitert haben. (Überschreibt [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse kann nicht direkt aus Ihrem Code verwendet werden.  
  
 Das Framework verwendet diese Klasse eine Palette Leiste in einem Bild-Editor (Dialogfeld) angezeigt. Weitere Informationen zu den Bild-Editor (Dialogfeld), finden Sie unter [CMFCImageEditorDialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afximageeditordialog.h  
  
##  <a name="getrowheight"></a>  CMFCImageEditorPaletteBar::GetRowHeight  
 Gibt die Höhe des Symbolleistenschaltflächen zurück.  
  
```  
virtual int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe der einzelnen Schaltflächen auf der Symbolleiste.  
  
##  <a name="isbuttonextrasizeavailable"></a>  CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable  
 Bestimmt, ob die Symbolleiste Schaltflächen angezeigt werden kann, die Ränder erweitert haben.  
  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `FALSE` zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md)
