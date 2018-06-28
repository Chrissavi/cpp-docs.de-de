---
title: CLinearTransition-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::Create
- AFXANIMATIONCONTROLLER/CLinearTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CLinearTransition::m_duration
dev_langs:
- C++
helpviewer_keywords:
- CLinearTransition [MFC], CLinearTransition
- CLinearTransition [MFC], Create
- CLinearTransition [MFC], m_dblFinalValue
- CLinearTransition [MFC], m_duration
ms.assetid: 7fcb2dba-beb8-4933-9f5d-3b7fb1585ef0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1412a65ce7afaab5421d49c22a9cd8ece5b283b1
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040885"
---
# <a name="clineartransition-class"></a>CLinearTransition-Klasse
Kapselt einen linearen Übergang.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CLinearTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CLinearTransition::CLinearTransition](#clineartransition)|Erstellt einen linearen Übergang-Objekt, und mit der Dauer und den endgültigen Wert initialisiert.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CLinearTransition::Create](#create)|Ruft den Übergangsbibliothek, um die gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CLinearTransition::m_dblFinalValue](#m_dblfinalvalue)|Der Wert der Animationsvariablen am Ende des Übergangs.|  
|[CLinearTransition::m_duration](#m_duration)|Die Dauer des Übergangs.|  
  
## <a name="remarks"></a>Hinweise  
 Während einen linearen Übergang geht der Wert der Animationsvariablen linear aus ihrem ursprünglichen Wert in einem angegebenen Endwert. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, belegt sie mit dem Operator new. Das gekapselte IUIAnimationTransition-COM-Objekt wird von CAnimationController:: erst erstellt, ist es auf NULL. Ändern Membervariablen, nach der Erstellung dieses COM-Objekt hat keine Auswirkung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransition](../../mfc/reference/clineartransition-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="clineartransition"></a>  CLinearTransition::CLinearTransition  
 Erstellt einen linearen Übergang-Objekt, und mit der Dauer und den endgültigen Wert initialisiert.  
  
```  
CLinearTransition(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE dblFinalValue);
```  
  
### <a name="parameters"></a>Parameter  
 *Dauer*  
 Die Dauer des Übergangs.  
  
 *dblFinalValue*  
 Der Wert der Animationsvariablen am Ende des Übergangs.  
  
##  <a name="create"></a>  CLinearTransition::Create  
 Ruft den Übergangsbibliothek, um die gekapselte COM-Übergangsobjekt zu erstellen.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Parameter  
*pLibrary*  
 Ein Zeiger auf ein [IUIAnimationTransitionLibrary-Schnittstelle](https://msdn.microsoft.com/library/windows/desktop/dd371897), die eine Bibliothek mit standard-Übergänge definiert.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Übergang erfolgreich erstellt wurde. andernfalls "false".  
  
##  <a name="m_dblfinalvalue"></a>  CLinearTransition::m_dblFinalValue  
 Der Wert der Animationsvariablen am Ende des Übergangs.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_duration"></a>  CLinearTransition::m_duration  
 Die Dauer des Übergangs.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
