---
title: CAnimationStoryboardEventHandler-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationStoryboardEventHandler [MFC], CAnimationStoryboardEventHandler
- CAnimationStoryboardEventHandler [MFC], CreateInstance
- CAnimationStoryboardEventHandler [MFC], OnStoryboardStatusChanged
- CAnimationStoryboardEventHandler [MFC], OnStoryboardUpdated
- CAnimationStoryboardEventHandler [MFC], SetAnimationController
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb7c89e6441379949386baecbddbb30f7c01ebff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352222"
---
# <a name="canimationstoryboardeventhandler-class"></a>CAnimationStoryboardEventHandler-Klasse
Implementiert einen Rückruf, der von der Animations-API aufgerufen wird, wenn der Status eines Drehbuchs geändert oder ein Storyboard aktualisiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler](#canimationstoryboardeventhandler)|Erstellt ein `CAnimationStoryboardEventHandler`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationStoryboardEventHandler::CreateInstance](#createinstance)|Erstellt eine Instanz des `CAnimationStoryboardEventHandler` Rückruf.|  
|[CAnimationStoryboardEventHandler::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Behandelt `OnStoryboardStatusChanged` Ereignisse, die auftreten, wenn der Status eines Drehbuchs geändert (Außerkraftsetzungen `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged`.)|  
|[CAnimationStoryboardEventHandler::OnStoryboardUpdated](#onstoryboardupdated)|Behandelt `OnStoryboardUpdated` Ereignisse, die auftreten, wenn ein Storyboard aktualisiert wird (Außerkraftsetzungen `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated`.)|  
|[CAnimationStoryboardEventHandler::SetAnimationController](#setanimationcontroller)|Speichert einen Zeiger auf den Animationscontroller, um Ereignisse weiterzuleiten.|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Ereignishandler erstellt und übergeben `IUIAnimationStoryboard::SetStoryboardEventHandler` Methode, die beim Aufrufen von `CAnimationController::EnableStoryboardEventHandler`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationStoryboardEventHandlerBase`  
  
 `CAnimationStoryboardEventHandler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="canimationstoryboardeventhandler"></a>  CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler  
 Erstellt ein CAnimationStoryboardEventHandler-Objekt.  
  
```  
CAnimationStoryboardEventHandler();
```  
  
##  <a name="createinstance"></a>  CAnimationStoryboardEventHandler::CreateInstance  
 Erstellt eine Instanz des CAnimationStoryboardEventHandler-Rückrufs.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationStoryboardEventHandler** ppHandler);
```  
  
### <a name="parameters"></a>Parameter  
 `pAnimationController`  
 Ein Zeiger auf den Animationscontroller, der Ereignisse empfängt.  
  
 `ppHandler`  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="onstoryboardstatuschanged"></a>  CAnimationStoryboardEventHandler::OnStoryboardStatusChanged  
 Behandelt OnStoryboardStatusChanged-Ereignisse treten auf, wenn der Status eines Drehbuchs geändert wird.  
  
```  
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Parameter  
 `storyboard`  
 Ein Zeiger auf Storyboard, dessen Status geändert hat.  
  
 `newStatus`  
 Gibt neue Storyboardstatus.  
  
 `previousStatus`  
 Gibt die vorherige Storyboardstatus an.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL.  
  
##  <a name="onstoryboardupdated"></a>  CAnimationStoryboardEventHandler::OnStoryboardUpdated  
 Behandelt OnStoryboardUpdated-Ereignisse, die auftreten, wenn ein Storyboard aktualisiert wird  
  
```  
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```  
  
### <a name="parameters"></a>Parameter  
 `storyboard`  
 Ein Zeiger auf storyboard, die aktualisiert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL.  
  
##  <a name="setanimationcontroller"></a>  CAnimationStoryboardEventHandler::SetAnimationController  
 Speichert einen Zeiger auf den Animationscontroller, um Ereignisse weiterzuleiten.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>Parameter  
 `pAnimationController`  
 Ein Zeiger auf den Animationscontroller, der Ereignisse empfängt.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
