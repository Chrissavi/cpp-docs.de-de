---
title: OLE-Initialisierung
ms.date: 11/04/2016
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
ms.openlocfilehash: 6860697dd3adbe26197dd9075e84f402029e00a5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502026"
---
# <a name="ole-initialization"></a>OLE-Initialisierung

Bevor eine Anwendung OLE-Systemdienste verwenden kann, muss Sie die OLE-System-DLLs initialisieren und sicherstellen, dass die DLLs die richtige Version aufweisen. Die `AfxOleInit` -Funktion initialisiert die OLE-System-DLLs.

### <a name="ole-initialization"></a>OLE-Initialisierung

|||
|-|-|
|[AfxOleInit](#afxoleinit)|Initialisiert die OLE-Bibliotheken.|
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|Diese Funktion wird in der-Funktion des `InitInstance` Anwendungs Objekts aufgerufen, um die Kapselung von OLE-Steuerelementen zu aktivieren.|

## <a name="afxenablecontrolcontainer"></a>AfxEnableControlContainer

Diese Funktion wird in der-Funktion des `InitInstance` Anwendungs Objekts aufgerufen, um die Kapselung von OLE-Steuerelementen zu aktivieren.

### <a name="syntax"></a>Syntax

```
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>Hinweise

Weitere Informationen zu OLE-Steuerelementen (jetzt als ActiveX-Steuerelemente bezeichnet) finden Sie unter [ActiveX-Steuerelement Themen](../mfc-activex-controls.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

##  <a name="afxoleinit"></a>AfxOLEInit

Initialisiert die OLE-Unterstützung für die Anwendung.

```
BOOL AFXAPI AfxOleInit();
```

### <a name="return-value"></a>Rückgabewert

Ist nicht 0 (Null), wenn erfolgreich, und 0, wenn die Initialisierung fehlschlägt, weil möglicherweise falsche Versionen der OLE-Systeme-DLLs installiert sind.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion auf, um die OLE-Unterstützung für eine MFC-Anwendung zu initialisieren. Wenn diese Funktion aufgerufen wird, werden folgende Aktionen ausgeführt:

- Initialisiert die COM-Bibliothek für das aktuelle Apartment des aufrufenden Anwendung. Weitere Informationen finden Sie unter [OleInitialize](/windows/win32/api/ole2/nf-ole2-oleinitialize).

- Erstellt ein Nachrichtenfilter Objekt, das die [IMessageFilter](/windows/win32/api/objidl/nn-objidl-imessagefilter) -Schnittstelle implementiert. Auf diesen Nachrichtenfilter kann mit einem Aufrufen von [afxolegetmessagefilter](application-control.md#afxolegetmessagefilter)zugegriffen werden.

> [!NOTE]
>  Wenn **AfxOLEInit** von einer MFC-DLL aufgerufen wird, schlägt der Aufruf fehl. Der Fehler tritt auf, weil die Funktion davon ausgeht, dass das OLE-System zuvor von der aufrufenden Anwendung initialisiert wurde, wenn sie von einer DLL aufgerufen wird.

> [!NOTE]
>  MFC-Anwendungen müssen als Singlethread-Apartment (STA) initialisiert werden. Wenn Sie [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) in der `InitInstance` außer Kraft Setzung aufrufen, geben Sie COINIT_APARTMENTTHREADED (anstelle von COINIT_MULTITHREADED) an.

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

## <a name="see-also"></a>Siehe auch

[Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md)
