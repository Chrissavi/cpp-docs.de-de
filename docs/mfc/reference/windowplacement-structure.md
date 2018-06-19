---
title: WINDOWPLACEMENT-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WINDOWPLACEMENT
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPLACEMENT structure [MFC]
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 829b3c90acb089bd91d71c498df5906fff919f22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379472"
---
# <a name="windowplacement-structure"></a>WINDOWPLACEMENT-Struktur
Die `WINDOWPLACEMENT` Struktur enthält Informationen über die Platzierung eines Fensters auf dem Bildschirm **.**  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagWINDOWPLACEMENT {     /* wndpl */  
    UINT length;  
    UINT flags;  
    UINT showCmd;  
    POINT ptMinPosition;  
    POINT ptMaxPosition;  
    RECT rcNormalPosition;  
} WINDOWPLACEMENT;  
```  
  
#### <a name="parameters"></a>Parameter  
 *length*  
 Gibt die Länge in Bytes, der Struktur **.**  
  
 `flags`  
 Gibt Flags an, die steuern die Position eines minimierten Fensters und die Methode mit der Fenster wiederhergestellt wird. Dieser Member kann es sich um eine oder beide der folgenden Flags sein:  
  
- **WPF_SETMINPOSITION** gibt an, dass die x und y-Positionen des minimierten Fensters angegeben werden können **.** Dieses Flag muss angegeben werden, wenn die Koordinaten, in festgelegt werden der **PtMinPosition** Member.  
  
- **WPF_RESTORETOMAXIMIZED** gibt an, dass das wiederhergestellte Fenster maximiert werden wird, unabhängig davon, ob dieses maximiert wurde, bevor er minimiert wurde. Diese Einstellung gilt nur das nächste Mal das Fenster wiederhergestellt wird. Es ändert sich nicht auf das Standardverhalten für die Wiederherstellung aus. Dieses Kennzeichen ist nur gültig, wenn die **SW_SHOWMINIMIZED** Wert wird angegeben, für die **ShowCmd** Member.  
  
 *showCmd*  
 Gibt den aktuellen Anzeigestatus des Fensters. Dieser Member kann einen der folgenden Werte sein:  
  
- **SW_HIDE** Blendet das Fenster aus und übergibt die Aktivierung zu einem anderen Fenster.  
  
- **SW_MINIMIZE** minimiert das angegebene Fenster, und aktiviert das Fenster das obersten Ebene in der System-Liste.  
  
- **SW_RESTORE** aktiviert und zeigt ein Fenster an. Wenn das Fenster minimiert oder maximiert ist, Windows wiederhergestellt werden kann, die ursprüngliche Größe und Position (identisch mit **SW_SHOWNORMAL**).  
  
- **SW_SHOW** aktiviert ein Fenster, und zeigt es in seiner aktuellen Größe und Position.  
  
- **SW_SHOWMAXIMIZED** aktiviert ein Fenster, und zeigt ihn als eines maximierten Fensters.  
  
- **SW_SHOWMINIMIZED** aktiviert ein Fenster, und zeigt ihn als ein Symbol.  
  
- **SW_SHOWMINNOACTIVE** ein Fenster als Symbol angezeigt. Das Fenster, das derzeit aktiv ist, bleibt aktiv.  
  
- **SW_SHOWNA** zeigt ein Fenster im aktuellen Zustand. Das Fenster, das derzeit aktiv ist, bleibt aktiv.  
  
- **SW_SHOWNOACTIVATE** zeigt ein Fenster in ihrer aktuellen Größe und Position. Das Fenster, das derzeit aktiv ist, bleibt aktiv.  
  
- **SW_SHOWNORMAL** aktiviert und zeigt ein Fenster an. Wenn das Fenster minimiert oder maximiert ist, Windows wiederhergestellt werden kann, die ursprüngliche Größe und Position (identisch mit **SW_RESTORE**).  
  
 *ptMinPosition*  
 Gibt die Position der linke obere Ecke des Fensters an, wenn das Fenster minimiert wird.  
  
 `ptMaxPosition`  
 Gibt die Position der linke obere Ecke des Fensters an, wenn das Fenster maximiert ist.  
  
 *rcNormalPosition*  
 Koordinaten des Fensters angibt, wenn das Fenster in der normalen (wiederhergestellt) Position befindet.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)

