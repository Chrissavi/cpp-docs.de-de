---
title: CProgressCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
helpviewer_keywords:
- CProgressCtrl [MFC], CProgressCtrl
- CProgressCtrl [MFC], Create
- CProgressCtrl [MFC], CreateEx
- CProgressCtrl [MFC], GetBarColor
- CProgressCtrl [MFC], GetBkColor
- CProgressCtrl [MFC], GetPos
- CProgressCtrl [MFC], GetRange
- CProgressCtrl [MFC], GetState
- CProgressCtrl [MFC], GetStep
- CProgressCtrl [MFC], OffsetPos
- CProgressCtrl [MFC], SetBarColor
- CProgressCtrl [MFC], SetBkColor
- CProgressCtrl [MFC], SetMarquee
- CProgressCtrl [MFC], SetPos
- CProgressCtrl [MFC], SetRange
- CProgressCtrl [MFC], SetState
- CProgressCtrl [MFC], SetStep
- CProgressCtrl [MFC], StepIt
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
ms.openlocfilehash: 9d63a1113e521eb73c99c47b335eb7ab00ccd753
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502850"
---
# <a name="cprogressctrl-class"></a>CProgressCtrl-Klasse

Stellt die Funktionalität des allgemeinen Windows-Statusanzeige-Steuerelements bereit.

## <a name="syntax"></a>Syntax

```
class CProgressCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|Erstellt ein `CProgressCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CProgressCtrl::Create](#create)|Erstellt ein Statusanzeige-Steuerelement und fügt es `CProgressCtrl` an ein-Objekt an.|
|[CProgressCtrl::CreateEx](#createex)|Erstellt ein Status Steuerelement mit den angegebenen erweiterten Windows-Stilen und fügt es `CProgressCtrl` an ein-Objekt an.|
|[CProgressCtrl::GetBarColor](#getbarcolor)|Ruft die Farbe der Statusanzeige Leiste für das aktuelle Statusanzeige-Steuerelement ab.|
|[CProgressCtrl::GetBkColor](#getbkcolor)|Ruft die Hintergrundfarbe der aktuellen Statusanzeige ab.|
|[CProgressCtrl::GetPos](#getpos)|Ruft die aktuelle Position der Statusanzeige ab.|
|[CProgressCtrl::GetRange](#getrange)|Ruft die unteren und oberen Begrenzungen des Bereichs des Statusanzeige-Steuer Elements ab.|
|[CProgressCtrl::GetState](#getstate)|Ruft den Status des aktuellen Statusanzeige-Steuer Elements ab.|
|[CProgressCtrl::GetStep](#getstep)|Ruft das Schritt Inkrement für die Statusanzeige des aktuellen Statusanzeige-Steuer Elements ab.|
|[CProgressCtrl::OffsetPos](#offsetpos)|Verschiebt die aktuelle Position eines Statusanzeige-Steuer Elements um ein angegebenes Inkrement und zeichnet den Balken neu, um die neue Position widerzuspiegeln.|
|[CProgressCtrl::SetBarColor](#setbarcolor)|Legt die Farbe der Statusanzeige Leiste im aktuellen Statusanzeige-Steuerelement fest.|
|[CProgressCtrl::SetBkColor](#setbkcolor)|Legt die Hintergrundfarbe für die Statusanzeige fest.|
|[CProgressCtrl::SetMarquee](#setmarquee)|Schaltet den Marquee-Modus für das aktuelle Statusanzeige-Steuerelement ein bzw. aus.|
|[CProgressCtrl::SetPos](#setpos)|Legt die aktuelle Position für ein Statusanzeige-Steuerelement fest und zeichnet den Balken neu, um die neue Position widerzuspiegeln.|
|[CProgressCtrl::SetRange](#setrange)|Legt die minimalen und maximalen Bereiche für ein Statusanzeige-Steuerelement fest und zeichnet den Balken neu, um die neuen Bereiche widerzuspiegeln.|
|[CProgressCtrl::SetState](#setstate)|Legt den Status des aktuellen Statusanzeige-Steuerelements fest.|
|[CProgressCtrl::SetStep](#setstep)|Gibt das Schritt Inkrement für ein Statusanzeige-Steuerelement an.|
|[CProgressCtrl::StepIt](#stepit)|Verschiebt die aktuelle Position für ein Statusanzeige-Steuerelement um Schritt Inkrement (siehe [SetStep](#setstep)) und zeichnet den Balken neu, um die neue Position widerzuspiegeln.|

## <a name="remarks"></a>Hinweise

Ein Statusanzeige-Steuerelement ist ein Fenster, mit dem eine Anwendung den Fortschritt eines langwierigen Vorgangs angeben kann. Er besteht aus einem Rechteck, das allmählich von links nach rechts mit der Hervorhebungs Farbe des Systems aufgefüllt wird, während ein Vorgang fortgesetzt wird.

Ein Statusanzeige-Steuerelement verfügt über einen Bereich und eine aktuelle Position. Der Bereich stellt die Gesamtdauer des Vorgangs dar, und die aktuelle Position stellt den Fortschritt dar, den die Anwendung zum Abschließen des Vorgangs durchgeführt hat. Die Fenster Prozedur verwendet den Bereich und die aktuelle Position, um den Prozentsatz der Statusanzeige zu ermitteln, der mit der Hervorhebungs Farbe aufgefüllt werden soll. Da der Bereich und die aktuellen Positionswerte als ganze Zahlen mit Vorzeichen ausgedrückt werden, liegt der mögliche Bereich der aktuellen Positionswerte zwischen-2.147.483.648 und 2.147.483.647.

Weitere Informationen zum Verwenden von `CProgressCtrl`finden Sie unter Steuer [Elemente](../../mfc/controls-mfc.md) und [Verwenden von CProgressCtrl](../../mfc/using-cprogressctrl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CProgressCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="cprogressctrl"></a>CProgressCtrl:: CProgressCtrl

Erstellt ein `CProgressCtrl`-Objekt.

```
CProgressCtrl();
```

### <a name="remarks"></a>Hinweise

`CProgressCtrl` Rufen`CProgressCtrl::Create` Sie nach dem Erstellen des Objekts auf, um das Statusanzeige-Steuerelement zu erstellen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]

##  <a name="create"></a>CProgressCtrl:: Create

Erstellt ein Statusanzeige-Steuerelement und fügt es `CProgressCtrl` an ein-Objekt an.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt den Stil des Statusanzeige-Steuer Elements an. Übernehmen Sie eine beliebige Kombination von Fenster Stilen, [die in der](/windows/win32/api/winuser/nf-winuser-createwindoww) Windows SDK, zusätzlich zu den folgenden Formatvorlagen für die Fortschrittsanzeige, auf das-Steuerelement angewendet werden:

- PBS_VERTICAL zeigt die Statusinformationen vertikal, von oben nach unten an. Ohne dieses Flag wird das Statusanzeige-Steuerelement horizontal, von links nach rechts angezeigt.

- PBS_SMOOTH zeigt ein schrittweises, nahtloses Ausfüllen des Statusanzeige-Steuer Elements an. Ohne dieses Flag wird das Steuerelement mit Blöcken gefüllt.

*Rect*<br/>
Gibt die Größe und Position des Statusanzeige-Steuer Elements an. Dabei kann es sich entweder um ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt oder um eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur handeln. Da es sich bei dem Steuerelement um ein untergeordnetes Fenster handeln muss, sind die angegebenen Koordinaten relativ zum Client Bereich des *pparameentwnd*.

*pParentWnd*<br/>
Gibt das übergeordnete Fenster des Statusanzeige-Steuer Elements `CDialog`an, in der Regel ein. Er darf nicht NULL sein.

*nID*<br/>
Gibt die ID des Statusanzeige-Steuer Elements an.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn `CProgressCtrl` das Objekt erfolgreich erstellt wurde, andernfalls false.

### <a name="remarks"></a>Hinweise

Sie erstellen ein `CProgressCtrl` -Objekt in zwei Schritten. Zuerst wird der-Konstruktor aufgerufen, der das `CProgressCtrl` -Objekt erstellt, und `Create`dann wird aufgerufen, wodurch das Statusanzeige-Steuerelement erstellt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]

##  <a name="createex"></a>CProgressCtrl:: kreateex

Erstellt ein-Steuerelement (ein untergeordnetes Fenster) und ordnet `CProgressCtrl` es dem-Objekt zu.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwExStyle*<br/>
Gibt die erweiterte Art des zu erstellenden Steuer Elements an. Eine Liste erweiterter Windows-Stile finden Sie unter dem *dwExStyle* -Parameter für " [kreatewindowex](/windows/win32/api/winuser/nf-winuser-createwindowexw) " in der Windows SDK.

*dwStyle*<br/>
Gibt den Stil des Statusanzeige-Steuer Elements an. Wenden Sie eine beliebige Kombination von Fenster [Stilen an, die in der](/windows/win32/api/winuser/nf-winuser-createwindoww) Windows SDK in der angezeigt werden.

*Rect*<br/>
Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Größe und Position des zu erstellenden Fensters in Client Koordinaten von *pparser*beschreibt.

*pParentWnd*<br/>
Ein Zeiger auf das Fenster, das das übergeordnete Element des Steuer Elements ist.

*nID*<br/>
Die ID des untergeordneten Fensters des Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Verwenden `CreateEx` Sie anstelle von [Create](#create) , um erweiterte Windows-Stile anzuwenden, die durch den erweiterten Windows-Stil **WS_EX_** angegeben werden.

##  <a name="getbarcolor"></a>CProgressCtrl:: getbarcolor

Ruft die Farbe der Statusanzeige Leiste für das aktuelle Statusanzeige-Steuerelement ab.

```
COLORREF GetBarColor() const;
```

### <a name="return-value"></a>Rückgabewert

Die Farbe der aktuellen Statusanzeige, die als [COLORREF](/windows/win32/gdi/colorref) -Wert dargestellt wird, oder CLR_DEFAULT, wenn die Statusanzeige leisten Farbe die Standardfarbe ist.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PBM_GETBARCOLOR](/windows/win32/Controls/pbm-getbarcolor) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getbkcolor"></a>CProgressCtrl:: GetBkColor

Ruft die Hintergrundfarbe der aktuellen Statusanzeige ab.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Rückgabewert

Die Hintergrundfarbe der aktuellen Statusanzeige, dargestellt als [COLORREF](/windows/win32/gdi/colorref) -Wert.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PBM_GETBKCOLOR](/windows/win32/Controls/pbm-getbkcolor) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getpos"></a>CProgressCtrl:: GetPos

Ruft die aktuelle Position der Statusanzeige ab.

```
int GetPos();
```

### <a name="return-value"></a>Rückgabewert

Die Position des Statusanzeige-Steuer Elements.

### <a name="remarks"></a>Hinweise

Die Position des Statusanzeige-Steuer Elements ist nicht die physische Position auf dem Bildschirm, sondern liegt zwischen dem oberen und unteren Bereich, [der in "](#setrange)" angegeben ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]

##  <a name="getrange"></a>CProgressCtrl:: GetRange

Ruft die aktuellen unteren und oberen Begrenzungen des Statusanzeige-Steuer Elements ab.

```
void GetRange(
    int& nLower,
    int& nUpper);
```

### <a name="parameters"></a>Parameter

*nLower*<br/>
Ein Verweis auf eine Ganzzahl, die die untere Grenze des Statusanzeige-Steuer Elements empfängt.

*nUpper*<br/>
Ein Verweis auf eine Ganzzahl, die die Obergrenze des Statusanzeige-Steuer Elements empfängt.

### <a name="remarks"></a>Hinweise

Diese Funktion kopiert die Werte der unteren und oberen Grenzen in die ganzen Zahlen, auf die von *nlower* bzw. *nupperverwiesen*wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]

##  <a name="getstate"></a>CProgressCtrl:: GetState

Ruft den Status des aktuellen Statusanzeige-Steuer Elements ab.

```
int GetState() const;
```

### <a name="return-value"></a>Rückgabewert

Der Status des aktuellen Statusanzeige-Steuer Elements, bei dem es sich um einen der folgenden Werte handelt:

|Wert|Status|
|-----------|-----------|
|PBST_NORMAL|In Bearbeitung|
|PBST_ERROR|Fehler|
|PBST_PAUSED|Paused|

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PBM_GETSTATE](/windows/win32/Controls/pbm-getstate) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird der Status des aktuellen Statusanzeige-Steuer Elements abgerufen.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]

##  <a name="getstep"></a>CProgressCtrl:: getstep

Ruft das Schritt Inkrement für die Statusanzeige des aktuellen Statusanzeige-Steuer Elements ab.

```
int GetStep() const;
```

### <a name="return-value"></a>Rückgabewert

Das Schritt Inkrement der Statusanzeige.

### <a name="remarks"></a>Hinweise

Der Schritt Inkrement ist der Betrag, um den durch einen [CProgressCtrl:: StepIt](#stepit) -Befehl die aktuelle Position der Statusanzeige erhöht wird.

Diese Methode sendet die [PBM_GETSTEP](/windows/win32/Controls/pbm-getstep) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird das Schritt Inkrement des aktuellen Statusanzeige-Steuer Elements abgerufen.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]

##  <a name="offsetpos"></a>CProgressCtrl:: OffsetPos

Verschiebt die aktuelle Position des Statusanzeige-Steuer Elements um das von *NPOs* angegebene Inkrement und zeichnet den Balken neu, um die neue Position widerzuspiegeln.

```
int OffsetPos(int nPos);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Betrag, um die Position zu verschieben.

### <a name="return-value"></a>Rückgabewert

Die vorherige Position des Statusanzeige-Steuer Elements.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]

##  <a name="setbarcolor"></a>CProgressCtrl:: setbarcolor

Legt die Farbe der Statusanzeige Leiste im aktuellen Statusanzeige-Steuerelement fest.

```
COLORREF SetBarColor(COLORREF clrBar);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*clrBar*|in Ein [COLORREF](/windows/win32/gdi/colorref) -Wert, der die neue Farbe der Statusanzeige Leiste angibt. Geben Sie CLR_DEFAULT an, damit die Statusanzeige Ihre Standardfarbe verwendet.|

### <a name="return-value"></a>Rückgabewert

Die vorherige Farbe der Status Indikator Leiste, dargestellt als [COLORREF](/windows/win32/gdi/colorref) -Wert, oder CLR_DEFAULT, wenn die Farbe der Statusanzeige Leiste die Standardfarbe ist.

### <a name="remarks"></a>Hinweise

Die `SetBarColor` -Methode legt die Statusanzeige Farbe nur dann fest, wenn ein [Windows Vista-](/windows/win32/Controls/visual-styles-overview) Design nicht wirksam ist.

Diese Methode sendet die [PBM_SETBARCOLOR](/windows/win32/Controls/pbm-setbarcolor) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die Farbe der Statusanzeige in rot, grün, blau oder den Standardwert geändert.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]

##  <a name="setbkcolor"></a>CProgressCtrl:: SetBkColor

Legt die Hintergrundfarbe für die Statusanzeige fest.

```
COLORREF SetBkColor(COLORREF clrNew);
```

### <a name="parameters"></a>Parameter

*clrNew*<br/>
Ein COLORREF-Wert, der die neue Hintergrundfarbe angibt. Geben Sie den CLR_DEFAULT-Wert an, um die Standard Hintergrundfarbe für die Statusanzeige zu verwenden.

### <a name="return-value"></a>Rückgabewert

Der [COLORREF](/windows/win32/gdi/colorref) -Wert, der die vorherige Hintergrundfarbe angibt, oder CLR_DEFAULT, wenn die Hintergrundfarbe die Standardfarbe ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]

##  <a name="setmarquee"></a>CProgressCtrl:: setmarquee

Schaltet den Marquee-Modus für das aktuelle Statusanzeige-Steuerelement ein bzw. aus.

```
BOOL SetMarquee(
    BOOL fMarqueeMode,
    int nInterval);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*fMarqueeMode*|in TRUE, wenn der Marquee-Modus aktiviert werden soll, oder false, um den Marquee-Modus zu deaktivieren.|
|*nintervall*|in Zeit in Millisekunden zwischen den Aktualisierungen der Marquee-Animation.|

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt immer true zurück.

### <a name="remarks"></a>Hinweise

Wenn der Marquee-Modus aktiviert ist, wird die Statusanzeige animiert und führt einen Bildlauf wie ein Zeichen in einem Theater-Marquee aus.

Diese Methode sendet die [PBM_SETMARQUEE](/windows/win32/Controls/pbm-setmarquee) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die Marquee-scrollanimation gestartet und beendet.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]

##  <a name="setpos"></a>CProgressCtrl:: SetPos

Legt die aktuelle Position des Statusanzeige-Steuer Elements entsprechend der Angabe durch *NPOs* fest und zeichnet den Balken neu, um die neue Position widerzuspiegeln.

```
int SetPos(int nPos);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Neue Position des Statusanzeige-Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Die vorherige Position des Statusanzeige-Steuer Elements.

### <a name="remarks"></a>Hinweise

Die Position des Statusanzeige-Steuer Elements ist nicht die physische Position auf dem Bildschirm, sondern liegt zwischen dem oberen und unteren Bereich, [der in "](#setrange)" angegeben ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]

##  <a name="setrange"></a>CProgressCtrl:: Strange

Legt die obere und untere Grenze des Bereichs des Statusanzeige-Steuer Elements fest und zeichnet den Balken neu, um die neuen Bereiche widerzuspiegeln.

```
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>Parameter

*nLower*<br/>
Gibt die untere Grenze des Bereichs an (der Standardwert ist 0 (null)).

*nUpper*<br/>
Gibt die Obergrenze des Bereichs an (der Standardwert ist 100).

### <a name="remarks"></a>Hinweise

Die Member- `SetRange32` Funktion legt den 32-Bit-Bereich für das Fortschritts Steuerelement fest.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]

##  <a name="setstate"></a>CProgressCtrl:: SetState

Legt den Status des aktuellen Statusanzeige-Steuerelements fest.

```
int SetState(int iState);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iState*|in Der Zustand, in dem die Statusanzeige festgelegt wird. Verwenden Sie einen der folgenden Werte:<br /><br /> -PBST_NORMAL-in Bearbeitung<br />-PBST_ERROR-Error<br />-PBST_PAUSED-angehalten|

### <a name="return-value"></a>Rückgabewert

Der vorherige Status des aktuellen Statusanzeige-Steuerelements.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PBM_SETSTATE](/windows/win32/Controls/pbm-setstate) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird der Status des aktuellen Statusanzeige-Steuerelements auf angehalten oder In Bearbeitung festgelegt.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]

##  <a name="setstep"></a>CProgressCtrl:: SetStep

Gibt das Schritt Inkrement für ein Statusanzeige-Steuerelement an.

```
int SetStep(int nStep);
```

### <a name="parameters"></a>Parameter

*nStep*<br/>
Neuer Schritt Inkrement.

### <a name="return-value"></a>Rückgabewert

Der vorherige Schritt Inkrement.

### <a name="remarks"></a>Hinweise

Der Schritt Inkrement ist der Betrag, um den ein `CProgressCtrl::StepIt` -Aufrufwert die aktuelle Position der Statusanzeige erhöht.

Der Standard Schritt Inkrement ist 10.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]

##  <a name="stepit"></a>CProgressCtrl:: StepIt

Verschiebt die aktuelle Position für ein Statusanzeige-Steuerelement um das Schritt Inkrement und zeichnet den Balken neu, um die neue Position widerzuspiegeln.

```
int StepIt();
```

### <a name="return-value"></a>Rückgabewert

Die vorherige Position des Statusanzeige-Steuer Elements.

### <a name="remarks"></a>Hinweise

Das Schritt Inkrement wird von der `CProgressCtrl::SetStep` Member-Funktion festgelegt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
