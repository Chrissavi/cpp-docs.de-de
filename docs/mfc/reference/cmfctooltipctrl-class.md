---
title: CMFCToolTipCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetIconSize
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetParams
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawBorder
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawLabel
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnFillBackground
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetFixedWidth
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetHotRibbonButton
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetLocation
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetParams
helpviewer_keywords:
- CMFCToolTipCtrl [MFC], GetIconSize
- CMFCToolTipCtrl [MFC], GetParams
- CMFCToolTipCtrl [MFC], OnDrawBorder
- CMFCToolTipCtrl [MFC], OnDrawDescription
- CMFCToolTipCtrl [MFC], OnDrawIcon
- CMFCToolTipCtrl [MFC], OnDrawLabel
- CMFCToolTipCtrl [MFC], OnDrawSeparator
- CMFCToolTipCtrl [MFC], OnFillBackground
- CMFCToolTipCtrl [MFC], SetDescription
- CMFCToolTipCtrl [MFC], SetFixedWidth
- CMFCToolTipCtrl [MFC], SetHotRibbonButton
- CMFCToolTipCtrl [MFC], SetLocation
- CMFCToolTipCtrl [MFC], SetParams
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
ms.openlocfilehash: 5376fd21f84411c86ade564d7c76d073ccb909a6
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70273692"
---
# <a name="cmfctooltipctrl-class"></a>CMFCToolTipCtrl-Klasse

Eine erweiterte QuickInfo-Implementierung auf Grundlage von [CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md). Eine QuickInfo auf Grundlage der `CMFCToolTipCtrl` -Klasse kann ein Symbol, eine Bezeichnung und eine Beschreibung anzeigen. Sie können das Aussehen anpassen, indem Sie einen Farbverlauf, einen benutzerdefinierter Text, Rahmenfarben, fetten Text, abgerundete Ecken oder ein Sprechblasenformat verwenden.

Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.

## <a name="syntax"></a>Syntax

```
class CMFCToolTipCtrl : public CToolTipCtrl
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|Standardkonstruktor|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolTipCtrl::GetIconSize](#geticonsize)|Gibt die Größe eines QuickInfo-Symbols zurück.|
|[CMFCToolTipCtrl::GetParams](#getparams)|Gibt die Anzeigeeinstellungen für QuickInfo zurück.|
|[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)|Zeichnet den QuickInfo-Rahmen.|
|[CMFCToolTipCtrl::OnDrawDescription](#ondrawdescription)||
|[CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)|Zeigt ein QuickInfo-Symbol an.|
|[CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)|Gibt die QuickInfo-Bezeichnung an oder berechnet die Bezeichnungsgröße.|
|[CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)|Zeichnet die Trennlinie zwischen der QuickInfo-Bezeichnung und -Beschreibung.|
|[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)|Füllt den QuickInfo-Hintergrund.|
|[CMFCToolTipCtrl::SetDescription](#setdescription)|Legt die von der QuickInfo angezeigte Beschreibung fest.|
|[CMFCToolTipCtrl::SetFixedWidth](#setfixedwidth)||
|[CMFCToolTipCtrl::SetHotRibbonButton](#sethotribbonbutton)||
|[CMFCToolTipCtrl::SetLocation](#setlocation)||
|[CMFCToolTipCtrl::SetParams](#setparams)|Gibt die visuelle Darstellung einer QuickInfo mit einem `CMFCToolTipInfo`-Objekt an.|

## <a name="remarks"></a>Hinweise

Verwenden `CMFCToolTipCtrl`Sie `CMFCToolTipInfo`die Klassen Objekte, und [ctooltipmanager](../../mfc/reference/ctooltipmanager-class.md) , um benutzerdefinierte Quick Infos in Ihre Anwendung zu implementieren.

Befolgen Sie die folgenden Schritte, wenn Sie beispielsweise QuickInfo-Sprechblasen verwenden möchten:

1. Verwenden Sie die Methode [CWinAppEx Class](../../mfc/reference/cwinappex-class.md) , um den QuickInfo-Manager in Ihrer Anwendung zu initialisieren.

2. Erstellen Sie eine `CMFCToolTipInfo`-Struktur, um den gewünschten visuellen Stil anzugeben:

```
CMFCToolTipInfo params;
params.m_bBoldLabel = FALSE;
params.m_bDrawDescription = FALSE;
params.m_bDrawIcon = FALSE;
params.m_bRoundedCorners = TRUE;
params.m_bDrawSeparator = FALSE;
if (m_bCustomColors)
{
    params.m_clrFill = RGB (255, 255, 255);
    params.m_clrFillGradient = RGB (228, 228, 240);
    params.m_clrText = RGB (61, 83, 80);
    params.m_clrBorder = RGB (144, 149, 168);

}
```
3. Verwenden Sie die [ctooltipmanager:: settooltipparameams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams) -Methode, um den visuellen Stil für alle Quick Infos in der Anwendung mithilfe der im `CMFCToolTipInfo` -Objekt definierten Stile festzulegen:

```
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    RUNTIME_CLASS (CMFCToolTipCtrl), &params);
```
Zum Steuern des QuickInfo-Verhaltens und -Renderings können Sie auch eine neue Klasse von `CMFCToolTipCtrl` ableiten. Verwenden Sie zum Angeben einer neuen QuickInfo-Steuerelementklasse die `CTooltipManager::SetTooltipParams`-Methode:

```
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    RUNTIME_CLASS (CMyToolTipCtrl))
```
Legen Sie zum Wiederherstellen der standardmäßigen QuickInfo-Steuerelementklasse und zum Zurücksetzen des QuickInfo-Formats auf die Standardeinstellung die Laufzeitklasse und die QuickInfo-Parameter von `SetTooltipParams` auf NULL fest.

```
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    NULL,
    NULL);
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie Sie ein `CMFCToolTipCtrl`-Objekt erstellen, die von der QuickInfo angezeigte Beschreibung und die Breite des Tooltip-Steuerelements festlegen können.

[!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/cpp/cmfctooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)

[CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxtooltipctrl. h

##  <a name="cmfctooltipctrl"></a>CMFCToolTipCtrl:: CMFCToolTipCtrl

```
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```

### <a name="parameters"></a>Parameter

in *pparser*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="geticonsize"></a>CMFCToolTipCtrl:: getikonsistze

Gibt die Größe eines QuickInfo-Symbols zurück.

```
virtual CSize GetIconSize();
```

### <a name="return-value"></a>Rückgabewert

Die Größe des Symbols in Pixel.

##  <a name="getparams"></a>CMFCToolTipCtrl:: getparameams

Gibt die Anzeigeeinstellungen für QuickInfo zurück.

```
const CMFCToolTipInfo& GetParams() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuellen QuickInfo-Anzeigeeinstellungen, die in einem [cmfctooltipinfo-Klassen](../../mfc/reference/cmfctooltipinfo-class.md) Objekt gespeichert werden.

##  <a name="ondrawborder"></a>CMFCToolTipCtrl:: ondrawborder

Zeichnet den QuickInfo-Rahmen.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect,
    COLORREF clrLine);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Zeiger auf einen Gerätekontext.

*Rect*<br/>
in Das umgebende Rechteck der QuickInfo.

*clrLine*<br/>
in Rahmenfarbe.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um die Darstellung des QuickInfo-Rahmens anzupassen.

##  <a name="ondrawdescription"></a>CMFCToolTipCtrl:: ondrawdescription

```
virtual CSize OnDrawDescription(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>
in *Rect*<br/>
in *bcally*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="ondrawicon"></a>CMFCToolTipCtrl:: ondrawicon

Zeigt ein QuickInfo-Symbol an.

```
virtual BOOL OnDrawIcon(
    CDC* pDC,
    CRect rectImage);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Ein Zeiger auf einen Gerätekontext.

*rectImage*<br/>
in Koordinaten des Symbols.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Symbol gezeichnet wurde. Andernfalls false.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um ein benutzerdefiniertes Symbol anzuzeigen. Außerdem müssen Sie [CMFCToolTipCtrl:: getikonsistze](#geticonsize) überschreiben, damit die QuickInfo das Layout von Text und Description ordnungsgemäß berechnen kann.

##  <a name="ondrawlabel"></a>CMFCToolTipCtrl:: ondrawlabel

Gibt die QuickInfo-Bezeichnung an oder berechnet die Bezeichnungsgröße.

```
virtual CSize OnDrawLabel(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Ein Zeiger auf einen Gerätekontext.

*Rect*<br/>
in Begrenzungs Rechteck des Bezeichnungs Bereichs.

*bCalcOnly*<br/>
in TRUE gibt an, dass die Bezeichnung nicht gezeichnet wird.

### <a name="return-value"></a>Rückgabewert

Größe der Bezeichnung in Pixel.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie die Darstellung der QuickInfo-Bezeichnung anpassen möchten.

##  <a name="ondrawseparator"></a>CMFCToolTipCtrl:: ondrawseparator

Zeichnet die Trennlinie zwischen der QuickInfo-Bezeichnung und -Beschreibung.

```
virtual void OnDrawSeparator(
    CDC* pDC,
    int x1,
    int x2,
    int y);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Ein Zeiger auf einen Gerätekontext.

*x1*<br/>
in Die horizontale Koordinate des linken Endes des Trenn Zeichens.

*x2*<br/>
in Die horizontale Koordinate des rechten Endes des Trenn Zeichens.

*Y*<br/>
in Vertikale Koordinate des Trenn Zeichens.

### <a name="remarks"></a>Hinweise

Die Standard Implementierung zeichnet eine Linie vom Punkt (x1, y) bis zum Punkt (x2, y).

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um die Darstellung des Trenn Zeichens anzupassen.

##  <a name="onfillbackground"></a>CMFCToolTipCtrl:: onfillbackground

Füllt den QuickInfo-Hintergrund.

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect,
    COLORREF& clrText,
    COLORREF& clrLine);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Ein Zeiger auf einen Gerätekontext.

*Rect*<br/>
in Gibt das umgebende Rechteck des aufzufüllenden Bereichs an.

*clrText*<br/>
in QuickInfo-Vordergrundfarbe.

*clrLine*<br/>
in Rahmenfarbe und Trennzeichen Linie zwischen Bezeichnung und Beschreibung.

### <a name="remarks"></a>Hinweise

Die Standard Implementierung füllt das Rechteck, das durch *Rect* angegeben wird, mit der Farbe oder dem Muster, das durch den letzten " [CMFCToolTipCtrl:: setpara](#setparams)"-Befehl angegeben wurde.

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie die Darstellung der QuickInfo anpassen möchten.

##  <a name="setdescription"></a>CMFCToolTipCtrl:: setDescription

Legt die von der QuickInfo angezeigte Beschreibung fest.

```
virtual void SetDescription(const CString strDesrciption);
```

### <a name="parameters"></a>Parameter

*strDesrciption*<br/>
in Beschreibungstext.

### <a name="remarks"></a>Hinweise

Der Beschreibungstext wird in der QuickInfo unter dem Trennzeichen angezeigt.

##  <a name="setfixedwidth"></a>CMFCToolTipCtrl:: setfixedwidth

```
void SetFixedWidth(
    int nWidthRegular,
    int nWidthLargeImage);
```

### <a name="parameters"></a>Parameter

in *nwidthregular*<br/>
in *nwidthlargeimage*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="sethotribbonbutton"></a>CMFCToolTipCtrl:: abkthotribbonbutton

```
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```

### <a name="parameters"></a>Parameter

[in] *pRibbonButton*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="setlocation"></a>CMFCToolTipCtrl:: setLocation

```
void SetLocation(CPoint pt);
```

### <a name="parameters"></a>Parameter

[in] *pt*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="setparams"></a>CMFCToolTipCtrl:: setpara

Gibt die visuelle Darstellung einer [QuickInfo mithilfe eines cmfctooltipinfo-Klassen](../../mfc/reference/cmfctooltipinfo-class.md) Objekts an.

```
void SetParams(CMFCToolTipInfo* pParams);
```

### <a name="parameters"></a>Parameter

*pParams*<br/>
in Zeiger auf ein [cmfctooltipinfo-Klassen](../../mfc/reference/cmfctooltipinfo-class.md) Objekt, das die Anzeige Parameter enthält.

### <a name="remarks"></a>Hinweise

Wenn die QuickInfo angezeigt wird, wird Sie mithilfe der Farben und visuellen Stile gezeichnet, die von *pparser* angegeben werden. Der Wert von *PPARa AMS* wird im geschützten Member `m_Params`gespeichert, auf den von einer abgeleiteten Klasse zugegriffen werden kann, die [CMFCToolTipCtrl:: ondrawborder](#ondrawborder), [CMFCToolTipCtrl:: ondrawicon](#ondrawicon), [CMFCToolTipCtrl:: ondrawlabel überschreibt. ](#ondrawlabel), [CMFCToolTipCtrl:: ondrawseparator](#ondrawseparator)oder [CMFCToolTipCtrl:: onfillbackground](#onfillbackground) , um die angegebene Darstellung beizubehalten.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CToolTipCtrl-Klasse](../../mfc/reference/ctooltipctrl-class.md)<br/>
[CTooltipManager-Klasse](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFCToolTipInfo-Klasse](../../mfc/reference/cmfctooltipinfo-class.md)<br/>
[CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)
