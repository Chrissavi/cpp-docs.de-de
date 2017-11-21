---
title: Bitmapfunktionen zu ausgrauen und Dithern | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
dev_langs: C++
helpviewer_keywords: gray and dithered bitmap functions [MFC]
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 372fd343bbca8bfac4ec31a34b3920cf29d35957
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="gray-and-dithered-bitmap-functions"></a>Bitmap-Funktionen zu Ausgrauen und Dithering
**Ausgegraute Bitmap-Funktionen**  
  
 MFC enthält zwei Funktionen, die verwendet werden können, um einer Bitmap das Aussehen eines deaktivierten Steuerelements zu verleihen.  
  
 ![Vergleich von grauen und ursprünglichen Symbolversionen](../../mfc/reference/media/vcgraybitmap.gif "Vcgraybitmap")  
  
|||  
|-|-|  
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Zeichnet eine graue Version einer Bitmap.|  
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Kopiert eine graue Version einer Bitmap.|  
  
 **Bitmap-Funktionen mit Dithering**  
  
 MFC enthält außerdem zwei Funktionen, mit denen der Hintergrund einer Bitmap durch ein gedithertes Muster ersetzt werden kann.  
  
 ![Vergleich von geditherten und ursprünglichen Symbolversionen](../../mfc/reference/media/vcditheredbitmap.gif "Vcditheredbitmap")  
  
|||  
|-|-|  
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|Zeichnet eine Bitmap mit gedithertem Hintergrund.|  
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Kopiert eine Bitmap mit gedithertem Hintergrund.|  
  
##  <a name="afxdrawgraybitmap"></a>  AfxDrawGrayBitmap  
 Zeichnet eine graue Version einer Bitmap.  
  
```   
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Zeigt auf den Ziel-DC.  
  
 *x*  
 Die X-Koordinate des Ziels.  
  
 *y*  
 Die Y-Koordinate des Ziels.  
  
 `rSrc`  
 Die Quellbitmap.  
  
 `crBackground`  
 Die neue Hintergrundfarbe (normalerweise grau, wie etwa COLOR_MENU).  
  
### <a name="remarks"></a>Hinweise  
 Eine mit `AfxDrawGrayBitmap` gezeichnete Bitmap hat das Aussehen eines deaktivierten Steuerelements.  
  
 ![Vergleich von grauen und ursprünglichen Symbolversionen](../../mfc/reference/media/vcgraybitmap.gif "Vcgraybitmap")  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  

##  <a name="afxgetgraybitmap"></a>  AfxGetGrayBitmap  
 Kopiert eine graue Version einer Bitmap.  
  
```   
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>Parameter  
 `rSrc`  
 Die Quellbitmap.  
  
 `pDest`  
 Die Zielbitmap.  
  
 `crBackground`  
 Die neue Hintergrundfarbe (normalerweise grau, wie etwa COLOR_MENU).  
  
### <a name="remarks"></a>Hinweise  
 Eine mit `AfxGetGrayBitmap` kopierte Bitmap hat das Aussehen eines deaktivierten Steuerelements.  
  
 ![Vergleich von grauen und ursprünglichen Symbolversionen](../../mfc/reference/media/vcgraybitmap.gif "Vcgraybitmap")  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="afxdrawditheredbitmap"></a>  AfxDrawDitheredBitmap  
 Zeichnet eine Bitmap, ersetzen den Hintergrund mit einem Muster Dithern (aus).  
  
```   
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Zeigt auf den Ziel-DC.  
  
 *x*  
 Die X-Koordinate des Ziels.  
  
 *y*  
 Die Y-Koordinate des Ziels.  
  
 `rSrc`  
 Die Quellbitmap.  
  
 `cr1`  
 Einer der beiden Dithering Farben ab, in der Regel weiß.  
  
 `cr2`  
 Die anderen Dithering Farbe, in der Regel hellgrau (etwa COLOR_MENU).  
  
### <a name="remarks"></a>Hinweise  
 Die Quellbitmap auf den Zieldomänencontroller mit zwei Farben gezeichnet wird ( `cr1` und `cr2`) Karomuster der Bitmap-Hintergrund ersetzt. Der Hintergrund des Quellbitmaps ist als seine weißen Pixel und alle Pixel, die die Farbe des Pixels in der linken oberen Ecke der Bitmap für die Übereinstimmung definiert.  
  
 ![Vergleich von geditherten und ursprünglichen Symbolversionen](../../mfc/reference/media/vcditheredbitmap.gif "Vcditheredbitmap")  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  


##  <a name="afxgetditheredbitmap"></a>  AfxGetDitheredBitmap  
 Kopiert eine Bitmap, ersetzen den Hintergrund mit einem Muster Dithern (aus).  
  
```   
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>Parameter  
 `rSrc`  
 Die Quellbitmap.  
  
 `pDest`  
 Die Zielbitmap.  
  
 `cr1`  
 Einer der beiden Dithering Farben ab, in der Regel weiß.  
  
 `cr2`  
 Die anderen Dithering Farbe, in der Regel hellgrau (etwa COLOR_MENU).  
  
### <a name="remarks"></a>Hinweise  
 Die Quellbitmap in das Zielbitmap mit zwei Farben kopiert ( `cr1` und `cr2`) Karomuster die Quellbitmap im Hintergrund ersetzt. Der Hintergrund des Quellbitmaps ist als seine weißen Pixel und alle Pixel, die die Farbe des Pixels in der linken oberen Ecke der Bitmap für die Übereinstimmung definiert.  
  
 ![Vergleich von geditherten und ursprünglichen Symbolversionen](../../mfc/reference/media/vcditheredbitmap.gif "Vcditheredbitmap")  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)