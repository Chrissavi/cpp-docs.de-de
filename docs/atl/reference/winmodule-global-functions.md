---
title: Globale Funktionen WinModule | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
dev_langs:
- C++
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 514703e2c7c968035e9defc7677943377778a761
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362296"
---
# <a name="winmodule-global-functions"></a>WinModule globale Funktionen
Diese Funktionen bieten Unterstützung für `_AtlCreateWndData` Operations-Struktur.  
  
> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
|||  
|-|-|  
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|Mit dieser Funktion wird eine `_AtlCreateWndData`-Struktur initialisiert und hinzugefügt.|  
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|Mit dieser Funktion wird eine vorhandene `_AtlCreateWndData`-Struktur extrahiert.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  `            
##  <a name="atlwinmoduleaddcreatewnddata"></a>  AtlWinModuleAddCreateWndData  
 Mit dieser Funktion wird eine `_AtlCreateWndData`-Struktur initialisiert und hinzugefügt.  
   
```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```  
  
### <a name="parameters"></a>Parameter  
 `pWinModule`  
 Zeiger auf ein Modul [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) Struktur.  
  
 `pData`  
 Zeiger auf die [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) Struktur initialisiert und das aktuelle Modul hinzugefügt werden.  
  
 `pObject`  
 Zeiger auf ein Objekt **dies** Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert ein `_AtlCreateWndData` -Struktur, die zum Speichern der **dies** Zeiger verwendet, um Klasseninstanzen verweisen, und fügt es der Liste auf ein Modul verwiesen wird `_ATL_WIN_MODULE70` Struktur. Wird aufgerufen, indem [CAtlWinModule::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata).  
  
##  <a name="atlwinmoduleextractcreatewnddata"></a>  AtlWinModuleExtractCreateWndData  
 Mit dieser Funktion wird eine vorhandene `_AtlCreateWndData`-Struktur extrahiert.  
 
```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```  
  
### <a name="parameters"></a>Parameter  
 `pWinModule`  
 Zeiger auf ein Modul [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird eine vorhandene extrahieren `_AtlCreateWndData` Struktur aus der Liste auf ein Modul verweist `_ATL_WIN_MODULE70` Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)
