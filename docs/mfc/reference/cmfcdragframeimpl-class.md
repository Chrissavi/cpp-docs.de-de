---
title: CMFCDragFrameImpl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDragFrameImpl
dev_langs:
- C++
helpviewer_keywords:
- CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 458288ecff0b457205ba1735494ad8106c3feae7
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040947"
---
# <a name="cmfcdragframeimpl-class"></a>CMFCDragFrameImpl-Klasse
Die `CMFCDragFrameImpl` Klasse zeichnet das ziehrechteck, das angezeigt wird, wenn der Benutzer einen Bereich im standarddockmodus zieht.  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
   
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDragFrameImpl  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein Objekt dieser Klasse wird in den einzelnen eingebettet [CPane-Klasse](../../mfc/reference/cpane-class.md) Objekt. Deshalb jedes Bereichs, der verwendet die `CanFloat` Methode zeigt einem Rechteck aus, wenn der Benutzer gezogen.  
  
 Sie können die Breite des Rechtecks ziehen Sie steuern, indem Sie mithilfe von [AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](afx-global-data-structure.md#m_ndragframethicknessfloat) und [AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](afx-global-data-structure.md#m_ndragframethicknessdock).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdragframeimpl.h  
  
##  <a name="enddrawdragframe"></a>  CMFCDragFrameImpl::EndDrawDragFrame  

  
```  
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bClearInternalRects*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="init"></a>  CMFCDragFrameImpl::Init  

  
```  
void Init(CWnd* pDraggedWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDraggedWnd*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="movedragframe"></a>  CMFCDragFrameImpl::MoveDragFrame  

  
```  
void MoveDragFrame(BOOL bForceMove = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bForceMove*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="placetabpredocking"></a>  CMFCDragFrameImpl::PlaceTabPreDocking  

  
```  
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,  
    BOOL bFirstTime);  
  
void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pTabbedBar*  
 [in] *bFirstTime*  
 [in] *pCBarToPlaceOn*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removetabpredocking"></a>  CMFCDragFrameImpl::RemoveTabPreDocking  

  
```  
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pOldTargetBar*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="resetstate"></a>  CMFCDragFrameImpl::ResetState  

  
```  
void ResetState();
```  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPane-Klasse](../../mfc/reference/cpane-class.md)