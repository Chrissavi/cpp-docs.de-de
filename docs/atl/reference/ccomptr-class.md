---
title: Klasse von CComPtr-| Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
dev_langs:
- C++
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5254e463050d685840ff90334ecbdb94372f27ef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358539"
---
# <a name="ccomptr-class"></a>Von CComPtr--Klasse
Ein intelligenter Zeiger-Klasse für die Verwaltung von COM-Schnittstellenzeiger auf.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class CComPtr
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine COM-Schnittstelle, die Angabe des Typs der Zeiger gespeichert werden soll.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPtr::CComPtr](#ccomptr)|Der Konstruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPtr::operator =](#operator_eq)|Weist einen Zeiger auf den Member-Zeiger.|  
  
## <a name="remarks"></a>Hinweise  
 ATL verwendet `CComPtr` und [CComQIPtr](../../atl/reference/ccomqiptr-class.md) zum Verwalten von COM-Schnittstellenzeiger auf. Beide abgeleitet [CComPtrBase](../../atl/reference/ccomptrbase-class.md), und führen Sie sowohl automatische verweiszählung.  
  
 Die **CComPtr** und [CComQIPtr](../../atl/reference/ccomqiptr-class.md) Klassen können helfen, Speicherverluste zu beseitigen, durch automatische verweiszählung ausführen.  Die folgenden Funktionen ausführen derselben logischen Operationen; Beachten Sie jedoch, wie die zweite Version weniger fehleranfällig mit möglicherweise die **CComPtr** Klasse:  
  
 [!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]  
  
 Verknüpfen Sie atlsd.lib für codeablaufverfolgung Debug-Builds.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 `CComPtr`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="ccomptr"></a>  CComPtr::CComPtr  
 Der Konstruktor.  
  
```
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```  
  
### <a name="parameters"></a>Parameter  
 `lp`  
 Wird verwendet, um den Schnittstellenzeiger zu initialisieren.  
  
 `T`  
 Eine COM-Schnittstelle.  
  
##  <a name="operator_eq"></a>  CComPtr::operator =  
 Zuweisungsoperator.  
  
```
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die aktualisierte `CComPtr` Objekt  
  
### <a name="remarks"></a>Hinweise  
 Dieser Vorgang AddRefs das neue Objekt und Versionen, die das vorhandene Objekt, sofern vorhanden ist.  
  
## <a name="see-also"></a>Siehe auch  
 [CComPtr::CComPtr](#ccomptr)   
 [CComQIPtr::CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
