---
title: OLE-Initialisierung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
dev_langs:
- C++
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b8224cf27313b056b95990f514e02eb9d9c08cad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374723"
---
# <a name="ole-initialization"></a>OLE-Initialisierung
Bevor eine Anwendung OLE-Systemdienste verwenden kann, muss er die OLE-System-DLLs initialisieren und stellen Sie sicher, dass die DLLs der richtigen Version vorliegen. Die **AfxOleInit** Funktion initialisiert die OLE-System-DLLs.  
  
### <a name="ole-initialization"></a>OLE-Initialisierung  
  
|||  
|-|-|  
|[AfxOleInit](#afxoleinit)|Initialisiert die OLE-Bibliotheken.| 
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|Mit dieser Funktion wird in des Anwendungsobjekts `InitInstance` Funktion zum Aktivieren der Unterstützung für die Kapselung der OLE-Steuerelemente.| 


## <a name="afxenablecontrolcontainer"></a> AfxEnableControlContainer
Mit dieser Funktion wird in des Anwendungsobjekts `InitInstance` Funktion zum Aktivieren der Unterstützung für die Kapselung der OLE-Steuerelemente.  
   
### <a name="syntax"></a>Syntax    
```
void AfxEnableControlContainer( );  
```  
   
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu OLE-Steuerelemente (jetzt als ActiveX-Steuerelemente bezeichnet), finden Sie unter [Themen zu ActiveX-Steuerelementen](../mfc-activex-controls.md).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  

  
##  <a name="afxoleinit"></a>  AfxOleInit  
 Initialisiert die OLE-Unterstützung für die Anwendung.  
  
``` 
BOOL AFXAPI AfxOleInit(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ist nicht 0 (Null), wenn erfolgreich, und 0, wenn die Initialisierung fehlschlägt, weil möglicherweise falsche Versionen der OLE-Systeme-DLLs installiert sind.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion auf, um die OLE-Unterstützung für eine MFC-Anwendung zu initialisieren. Wenn diese Funktion aufgerufen wird, werden folgende Aktionen ausgeführt:  
  
-   Initialisiert die COM-Bibliothek für das aktuelle Apartment des aufrufenden Anwendung. Weitere Informationen finden Sie unter [OleInitialize](http://msdn.microsoft.com/library/windows/desktop/ms690134).  
  
-   Erstellt ein nachrichtenfilterobjekt implementieren die [IMessageFilter](http://msdn.microsoft.com/library/windows/desktop/ms693740) Schnittstelle. Dieser Nachrichtenfilter möglich, die mit einem Aufruf von [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).  
  
> [!NOTE]
>  Wenn **AfxOleInit** heißt aus einer MFC-DLL der Aufruf fehl. Der Fehler tritt auf, weil die Funktion davon ausgeht, dass das OLE-System zuvor von der aufrufenden Anwendung initialisiert wurde, wenn sie von einer DLL aufgerufen wird.  
  
> [!NOTE]
>  MFC-Anwendungen müssen als Singlethread-Apartment (STA) initialisiert werden. Beim Aufrufen [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) in Ihrer `InitInstance` außer Kraft setzen, geben Sie `COINIT_APARTMENTTHREADED` (statt `COINIT_MULTITHREADED`). Weitere Informationen finden Sie unter PRB: MFC-Anwendung nicht mehr reagiert, wenn Sie die Anwendung als eine Multithread-Apartment (828643) am initialisieren [ http://support.microsoft.com/default.aspxscid=kb; En-us; 828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
