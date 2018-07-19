---
title: CWindowDC Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b757da27f2b4ae79a0192df0598f833b3d1e7b9
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121541"
---
# <a name="cwindowdc-class"></a>CWindowDC-Klasse
Abgeleitet von `CDC`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CWindowDC : public CDC  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWindowDC::CWindowDC](#cwindowdc)|Erstellt ein `CWindowDC`-Objekt.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CWindowDC::m_hWnd](#m_hwnd)|Das HWND an das `CWindowDC` angefügt ist.|  
  
## <a name="remarks"></a>Hinweise  
 Ruft die Windows-Funktion [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx)bei der Konstruktion und [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx) zur zerstörungszeit. Dies bedeutet, dass eine `CWindowDC` Objekt greift auf den ganzen Bildschirmbereich eine [CWnd](../../mfc/reference/cwnd-class.md) (sowohl Client als auch nicht-Bereiche).  
  
 Weitere Informationen zur Verwendung von `CWindowDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## <a name="requirements"></a>Anforderungen  
 Header: afxwin.h  
  
##  <a name="cwindowdc"></a>  CWindowDC::CWindowDC  
 Erstellt eine `CWindowDC` -Objekt, das den ganzen Bildschirmbereich (sowohl Client als auch Größenanpassungslogik) greift auf die `CWnd` Objekt verweist *pWnd*.  
  
```  
explicit CWindowDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *pWnd*  
 Das Fenster, dessen Clientbereich das Gerätekontext Objekt zugegriffen wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor ruft die Windows-Funktion [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947).  
  
 Eine Ausnahme (vom Typ `CResourceException`) wird ausgelöst, wenn die Windows `GetWindowDC` -Aufruf fehl. Ein Gerätekontext möglicherweise nicht verfügbar, wenn Windows bereits alle verfügbaren Geräte Kontexten zugeordnet sind. Ihre Anwendung konkurriert für die fünf allgemeine Anzeige Kontexte zu einem beliebigen Zeitpunkt unter Windows verfügbar.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>  CWindowDC::m_hWnd  
 Das HWND des der `CWnd` Zeiger zum Konstruieren der `CWindowDC` Objekt.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Hinweise  
 `m_hWnd` ist eine geschützte Variable des Typs HWND.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWindowDC::CWindowDC](#cwindowdc).  
  
## <a name="see-also"></a>Siehe auch  
 [CDC-Klasse](../../mfc/reference/cdc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDC-Klasse](../../mfc/reference/cdc-class.md)
