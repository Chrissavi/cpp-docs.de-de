---
title: PAINTSTRUCT-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- PAINTSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75a3db6c6beb18afe2303b464fcab290b2e132fc
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338209"
---
# <a name="paintstruct-structure"></a>PAINTSTRUCT-Struktur
Die `PAINTSTRUCT` Struktur enthält Informationen, die verwendet werden kann, um den Clientbereich eines Fensters zu zeichnen.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagPAINTSTRUCT {  
    HDC hdc;  
    BOOL fErase;  
    RECT rcPaint;  
    BOOL fRestore;  
    BOOL fIncUpdate;  
    BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### <a name="parameters"></a>Parameter  
 *hdc*  
 Identifiziert den Anzeigekontext, die zum Zeichnen verwendet werden.  
  
 *fErase*  
 Gibt an, ob der Hintergrund neu gezeichnet werden muss. Es ist nicht 0, wenn die Anwendung neu Hintergrund gezeichnet werden soll. Die Anwendung ist verantwortlich für den Hintergrund zeichnen, wenn eine Windows-Fensterklasse ohne ein Hintergrundpinsel erstellt wird (finden Sie in der Beschreibung der `hbrBackground` Mitglied der [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur im Windows SDK).  
  
 *rcPaint*  
 Gibt an, der oberen linken und unteren linken Ecke des Rechtecks in dem das Zeichnen angefordert wird.  
  
 *fRestore*  
 Reservierten Member. Sie wird intern von Windows verwendet.  
  
 *fIncUpdate*  
 Reservierten Member. Sie wird intern von Windows verwendet.  
  
 *RgbReserved [16]*  
 Reservierten Member. Eine reservierte Speicherblock intern von Windows verwendet.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)

