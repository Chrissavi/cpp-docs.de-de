---
title: CAtlComModule Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlComModule
- ATLBASE/ATL::CAtlComModule
- ATLBASE/ATL::CAtlComModule::CAtlComModule
- ATLBASE/ATL::CAtlComModule::RegisterServer
- ATLBASE/ATL::CAtlComModule::RegisterTypeLib
- ATLBASE/ATL::CAtlComModule::UnregisterServer
- ATLBASE/ATL::CAtlComModule::UnRegisterTypeLib
dev_langs:
- C++
helpviewer_keywords:
- CAtlComModule class
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47e85f3aab75f8fafb76977847ce36d37808af60
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364791"
---
# <a name="catlcommodule-class"></a>CAtlComModule-Klasse
Diese Klasse implementiert eine COM-Server-Modul.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlComModule : public _ATL_COM_MODULE
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlComModule::CAtlComModule](#catlcommodule)|Der Konstruktor.|  
|[CAtlComModule:: ~ CAtlComModule](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlComModule::RegisterServer](#registerserver)|Rufen Sie diese Methode, um die Registrierung für jedes Objekt in der objektzuordnung zu aktualisieren.|  
|[CAtlComModule::RegisterTypeLib](#registertypelib)|Rufen Sie diese Methode, um eine Typbibliothek zu registrieren.|  
|[CAtlComModule::UnregisterServer](#unregisterserver)|Rufen Sie diese Methode, um die Registrierung jedes Objekt in der objektzuordnung aufzuheben.|  
|[CAtlComModule::UnRegisterTypeLib](#unregistertypelib)|Rufen Sie diese Methode, um die Registrierung einer Typbibliothek aufzuheben.|  
  
## <a name="remarks"></a>Hinweise  
 `CAtlComModule` implementiert eine COM-Server-Modul ermöglicht einen Client den Zugriff auf das Modul Komponenten an.  
  
 Diese Klasse ersetzt die veraltete [CComModule](../../atl/reference/ccommodule-class.md) Klasse zur Verwendung in früheren Versionen von ATL Finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)  
  
 `CAtlComModule`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="catlcommodule"></a>  CAtlComModule::CAtlComModule  
 Der Konstruktor.  
  
```
CAtlComModule() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert das Modul an.  
  
##  <a name="dtor"></a>  CAtlComModule:: ~ CAtlComModule  
 Der Destruktor.  
  
```
~CAtlComModule();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle Klassenfactorys frei.  
  
##  <a name="registerserver"></a>  CAtlComModule::RegisterServer  
 Rufen Sie diese Methode, um die Registrierung für jedes Objekt in der objektzuordnung zu aktualisieren.  
  
```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `bRegTypeLib`  
 True, wenn die Typbibliothek registriert werden. Der Standardwert ist "false".  
  
 `pCLSID`  
 Verweist auf die CLSID des Objekts, das registriert werden. Wenn NULL (Standardwert), alle Objekte in der objektzuordnung registriert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die globale Funktion [AtlComModuleRegisterServer](server-registration-global-functions.md#atlcommoduleregisterserver).  
  
##  <a name="registertypelib"></a>  CAtlComModule::RegisterTypeLib  
 Rufen Sie diese Methode, um eine Typbibliothek zu registrieren.  
  
```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszIndex`  
 Zeichenfolge im Format "\\\N", wobei N der ganzzahlige Index, der die TYPBIBLIOTHEK-Ressource ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Fügt Informationen zu einer Typbibliothek in der systemregistrierung. Wenn die Modulinstanz mehrere Typbibliotheken enthält, verwenden Sie die erste Version dieser Methode, um anzugeben, welche Typbibliothek verwendet werden soll.  
  
##  <a name="unregisterserver"></a>  CAtlComModule::UnregisterServer  
 Rufen Sie diese Methode, um die Registrierung jedes Objekt in der objektzuordnung aufzuheben.  
  
```
HRESULT UnregisterServer(
  BOOL bRegTypeLib = FALSE,  
  const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `bRegTypeLib`  
 True, wenn die Typbibliothek nicht aufgehoben werden. Der Standardwert ist "false".  
  
 `pCLSID`  
 Verweist auf die CLSID des Objekts, das nicht aufgehoben werden. Wenn NULL (Standardwert), alle Objekte in der objektzuordnung aufgehoben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die globale Funktion [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver).  
  
##  <a name="unregistertypelib"></a>  CAtlComModule::UnRegisterTypeLib  
 Rufen Sie diese Methode, um die Registrierung einer Typbibliothek aufzuheben.  
  
```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszIndex`  
 Zeichenfolge im Format "\\\N", wobei N der ganzzahlige Index, der die TYPBIBLIOTHEK-Ressource ist.  
  
### <a name="remarks"></a>Hinweise  
 Werden Informationen zu einer Typbibliothek aus der Registrierung entfernt. Wenn die Modulinstanz mehrere Typbibliotheken enthält, verwenden Sie die erste Version dieser Methode, um anzugeben, welche Typbibliothek verwendet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
