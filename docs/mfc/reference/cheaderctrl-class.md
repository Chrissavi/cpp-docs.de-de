---
title: CHeaderCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CHeaderCtrl
- AFXCMN/CHeaderCtrl
- AFXCMN/CHeaderCtrl::CHeaderCtrl
- AFXCMN/CHeaderCtrl::ClearAllFilters
- AFXCMN/CHeaderCtrl::ClearFilter
- AFXCMN/CHeaderCtrl::Create
- AFXCMN/CHeaderCtrl::CreateDragImage
- AFXCMN/CHeaderCtrl::CreateEx
- AFXCMN/CHeaderCtrl::DeleteItem
- AFXCMN/CHeaderCtrl::DrawItem
- AFXCMN/CHeaderCtrl::EditFilter
- AFXCMN/CHeaderCtrl::GetBitmapMargin
- AFXCMN/CHeaderCtrl::GetFocusedItem
- AFXCMN/CHeaderCtrl::GetImageList
- AFXCMN/CHeaderCtrl::GetItem
- AFXCMN/CHeaderCtrl::GetItemCount
- AFXCMN/CHeaderCtrl::GetItemDropDownRect
- AFXCMN/CHeaderCtrl::GetItemRect
- AFXCMN/CHeaderCtrl::GetOrderArray
- AFXCMN/CHeaderCtrl::GetOverflowRect
- AFXCMN/CHeaderCtrl::HitTest
- AFXCMN/CHeaderCtrl::InsertItem
- AFXCMN/CHeaderCtrl::Layout
- AFXCMN/CHeaderCtrl::OrderToIndex
- AFXCMN/CHeaderCtrl::SetBitmapMargin
- AFXCMN/CHeaderCtrl::SetFilterChangeTimeout
- AFXCMN/CHeaderCtrl::SetFocusedItem
- AFXCMN/CHeaderCtrl::SetHotDivider
- AFXCMN/CHeaderCtrl::SetImageList
- AFXCMN/CHeaderCtrl::SetItem
- AFXCMN/CHeaderCtrl::SetOrderArray
helpviewer_keywords:
- CHeaderCtrl [MFC], CHeaderCtrl
- CHeaderCtrl [MFC], ClearAllFilters
- CHeaderCtrl [MFC], ClearFilter
- CHeaderCtrl [MFC], Create
- CHeaderCtrl [MFC], CreateDragImage
- CHeaderCtrl [MFC], CreateEx
- CHeaderCtrl [MFC], DeleteItem
- CHeaderCtrl [MFC], DrawItem
- CHeaderCtrl [MFC], EditFilter
- CHeaderCtrl [MFC], GetBitmapMargin
- CHeaderCtrl [MFC], GetFocusedItem
- CHeaderCtrl [MFC], GetImageList
- CHeaderCtrl [MFC], GetItem
- CHeaderCtrl [MFC], GetItemCount
- CHeaderCtrl [MFC], GetItemDropDownRect
- CHeaderCtrl [MFC], GetItemRect
- CHeaderCtrl [MFC], GetOrderArray
- CHeaderCtrl [MFC], GetOverflowRect
- CHeaderCtrl [MFC], HitTest
- CHeaderCtrl [MFC], InsertItem
- CHeaderCtrl [MFC], Layout
- CHeaderCtrl [MFC], OrderToIndex
- CHeaderCtrl [MFC], SetBitmapMargin
- CHeaderCtrl [MFC], SetFilterChangeTimeout
- CHeaderCtrl [MFC], SetFocusedItem
- CHeaderCtrl [MFC], SetHotDivider
- CHeaderCtrl [MFC], SetImageList
- CHeaderCtrl [MFC], SetItem
- CHeaderCtrl [MFC], SetOrderArray
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
ms.openlocfilehash: 407ba2747ed4d6e56e56fe4ccb2ccb828240a732
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506705"
---
# <a name="cheaderctrl-class"></a>CHeaderCtrl-Klasse

Stellt die Funktionalität des allgemeinen Windows-Headersteuerelements bereit.

## <a name="syntax"></a>Syntax

```
class CHeaderCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|Erstellt ein `CHeaderCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|Löscht alle Filter für ein Header-Steuerelement.|
|[CHeaderCtrl::ClearFilter](#clearfilter)|Löscht den Filter für ein Header-Steuerelement.|
|[CHeaderCtrl::Create](#create)|Erstellt ein Header Steuerelement und fügt es an `CHeaderCtrl` ein-Objekt an.|
|[CHeaderCtrl::CreateDragImage](#createdragimage)|Erstellt eine transparente Version des Bilds eines Elements innerhalb eines Header Steuer Elements.|
|[CHeaderCtrl::CreateEx](#createex)|Erstellt ein Header Steuerelement mit den angegebenen erweiterten Windows-Stilen und fügt es `CListCtrl` an ein-Objekt an.|
|[CHeaderCtrl::DeleteItem](#deleteitem)|Löscht ein Element aus einem Header-Steuerelement.|
|[CHeaderCtrl::DrawItem](#drawitem)|Zeichnet das angegebene Element eines Header Steuer Elements.|
|[CHeaderCtrl::EditFilter](#editfilter)|Startet die Bearbeitung des angegebenen Filters eines Header Steuer Elements.|
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|Ruft die Breite des Rands einer Bitmap in einem Header Steuerelement ab.|
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|Ruft den Bezeichner des Elements im aktuellen Header Steuerelement ab, das über den Fokus verfügt.|
|[CHeaderCtrl::GetImageList](#getimagelist)|Ruft das Handle einer Bildliste ab, die zum Zeichnen von Header Elementen in einem Header-Steuerelement verwendet wird.|
|[CHeaderCtrl::GetItem](#getitem)|Ruft Informationen zu einem Element in einem Header Steuerelement ab.|
|[CHeaderCtrl::GetItemCount](#getitemcount)|Ruft die Anzahl der Elemente in einem Header Steuerelement ab.|
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|Ruft die umgebenden Rechteck Informationen für die angegebene Dropdown-Schaltfläche in einem Header-Steuerelement ab.|
|[CHeaderCtrl::GetItemRect](#getitemrect)|Ruft das umgebende Rechteck für ein angegebenes Element in einem Header Steuerelement ab.|
|[CHeaderCtrl::GetOrderArray](#getorderarray)|Ruft die Reihenfolge der Elemente in einem Header Steuerelement von links nach rechts ab.|
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|Ruft das umgebende Rechteck der Überlauf Schaltfläche für das aktuelle Header Steuerelement ab.|
|[CHeaderCtrl::HitTest](#hittest)|Bestimmt, welches Header Element, sofern vorhanden, sich an einem angegebenen Punkt befindet.|
|[CHeaderCtrl::InsertItem](#insertitem)|Fügt ein neues Element in ein Header Steuerelement ein.|
|[CHeaderCtrl::Layout](#layout)|Ruft die Größe und Position eines Header Steuer Elements innerhalb eines angegebenen Rechtecks ab.|
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|Ruft den Indexwert für ein Element auf Grundlage seiner Reihenfolge im Header Steuerelement ab.|
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|Legt die Breite des Rands einer Bitmap in einem Header Steuerelement fest.|
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|Legt das Timeout Intervall zwischen dem Zeitpunkt fest, zu dem eine Änderung in den Filter Attributen stattfindet, `HDN_FILTERCHANGE` und dem Veröffentlichen einer Benachrichtigung.|
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|Legt den Fokus auf ein angegebenes Header Element im aktuellen Header Steuerelement fest.|
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|Ändert den unter Teiler zwischen Header Elementen, um einen manuellen Drag & Drop eines Header Elements anzugeben.|
|[CHeaderCtrl::SetImageList](#setimagelist)|Weist einem Header Steuerelement eine Bildliste zu.|
|[CHeaderCtrl::SetItem](#setitem)|Legt die Attribute des angegebenen Elements in einem Header Steuerelement fest.|
|[CHeaderCtrl::SetOrderArray](#setorderarray)|Legt die Reihenfolge der Elemente in einem Header Steuerelement von links nach rechts fest.|

## <a name="remarks"></a>Hinweise

Ein Header Steuerelement ist ein Fenster, das normalerweise oberhalb eines Satzes von Text-oder Zahlen Spalten positioniert ist. Sie enthält einen Titel für jede Spalte und kann in Teile aufgeteilt werden. Der Benutzer kann die unter Teiler zum Trennen der Teile ziehen, um die Breite der einzelnen Spalten festzulegen. Eine Abbildung eines Header Steuer Elements finden Sie unter [Header](/windows/win32/Controls/header-controls)-Steuerelemente.

Dieses Steuerelement (und damit `CHeaderCtrl` auch die-Klasse) ist nur für Programme verfügbar, die unter Windows 95/98 und Windows NT, Version 3,51 und höher, ausgeführt werden.

Zu den allgemeinen Steuerelementen von Windows 95/Internet Explorer 4,0 werden folgende Funktionen hinzugefügt:

- Benutzerdefinierte Reihenfolge des Header Elements.

- Header Element Drag & Drop zum Neuordnen von Header Elementen. Verwenden Sie den HDS_DRAGDROP-Stil, wenn `CHeaderCtrl` Sie das-Objekt erstellen.

- Header Spalten Text, der während der Spaltengröße konstant angezeigt werden kann. Verwenden Sie den HDS_FULLDRAG-Stil, wenn `CHeaderCtrl` Sie ein-Objekt erstellen.

- Header-Hot-Nachverfolgung, die das Header Element hervorhebt, wenn der Mauszeiger darauf zeigt. Verwenden Sie den HDS_HOTTRACK-Stil, wenn `CHeaderCtrl` Sie das-Objekt erstellen.

- Unterstützung von Image Listen. Header Elemente können Bilder enthalten, die in `CImageList` einem-Objekt oder-Text gespeichert sind.

Weitere Informationen zum Verwenden von `CHeaderCtrl`finden Sie unter Steuer [Elemente](../../mfc/controls-mfc.md) und [Verwenden von CHeaderCtrl](../../mfc/using-cheaderctrl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHeaderCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="cheaderctrl"></a>CHeaderCtrl:: CHeaderCtrl

Erstellt ein `CHeaderCtrl`-Objekt.

```
CHeaderCtrl();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]

##  <a name="clearallfilters"></a>CHeaderCtrl:: ClearAllFilters

Löscht alle Filter für ein Header-Steuerelement.

```
BOOL ClearAllFilters();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode implementiert das Verhalten der Win32-Nachricht [HDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter) mit dem Spaltenwert-1, wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]

##  <a name="clearfilter"></a>CHeaderCtrl:: ClearFilter

Löscht den Filter für ein Header-Steuerelement.

```
BOOL ClearFilter(int nColumn);
```

### <a name="parameters"></a>Parameter

*ncolumn*<br/>
Der Spaltenwert, der den zu Lösch Ende Filter angibt.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode implementiert das Verhalten der Win32-Nachricht [HDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]

##  <a name="create"></a>CHeaderCtrl:: Create

Erstellt ein Header Steuerelement und fügt es an `CHeaderCtrl` ein-Objekt an.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt den Stil des Header Steuer Elements an. Eine Beschreibung der Header Steuerelement Stile finden Sie unter [Header-Steuerelement Stile](/windows/win32/Controls/header-control-styles) in der Windows SDK.

*Rect*<br/>
Gibt die Größe und Position des Header Steuer Elements an. Dabei kann es sich entweder um ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt oder um eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur handeln.

*pParentWnd*<br/>
Gibt das übergeordnete Fenster des Header Steuer Elements an `CDialog`, in der Regel ein. Er darf nicht NULL sein.

*nID*<br/>
Gibt die ID des Header Steuer Elements an.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Initialisierung erfolgreich war. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Sie erstellen ein `CHeaderCtrl` -Objekt in zwei Schritten. Zuerst wird der-Konstruktor aufgerufen und dann `Create`aufgerufen, wodurch das Header Steuerelement erstellt und an das `CHeaderCtrl` -Objekt angefügt wird.

Zusätzlich zu den Header Steuerelement Stilen können Sie die folgenden allgemeinen Steuerelement Stile verwenden, um zu bestimmen, wie das Header Steuerelement positioniert und seine Größe ändert (Weitere Informationen finden Sie unter [allgemeine Steuerelement Stile](/windows/win32/Controls/common-control-styles) ):

- CCS_BOTTOM bewirkt, dass sich das Steuerelement am unteren Rand des Client Bereichs des übergeordneten Fensters positioniert und die Breite auf die Breite der übergeordneten Fensterbreite festgelegt wird.

- CCS_NODIVIDER verhindert, dass eine zwei-Pixel-Hervorhebung am oberen Rand des-Steuer Elements gezeichnet wird.

- CCS_NOMOVEY bewirkt, dass die Größe des Steuer Elements in Reaktion auf eine WM_SIZE-Nachricht horizontal, aber nicht vertikal geändert wird. Wenn der CCS_NORESIZE-Stil verwendet wird, gilt dieser Stil nicht. Header Steuerelemente haben diesen Stil standardmäßig.

- CCS_NOPARENTALIGN verhindert, dass das Steuerelement automatisch an den oberen oder unteren Rand des übergeordneten Fensters wechselt. Stattdessen behält das Steuerelement die Position innerhalb des übergeordneten Fensters, trotz der Änderungen an der Größe des übergeordneten Fensters. Wenn auch der CCS_TOP-oder CCS_BOTTOM-Stil verwendet wird, wird die Höhe an den Standardwert angepasst, die Position und die Breite bleiben jedoch unverändert.

- CCS_NORESIZE verhindert, dass das Steuerelement beim Festlegen der Anfangs Größe oder einer neuen Größe die Standardbreite und-Höhe verwendet. Stattdessen verwendet das Steuerelement die Breite und die Höhe, die in der Anforderung für die Erstellung oder Größenanpassung angegeben sind.

- CCS_TOP bewirkt, dass das Steuerelement sich selbst am oberen Rand des Client Bereichs des übergeordneten Fensters positioniert und die Breite auf die Breite des übergeordneten Fensters festgelegt wird.

Sie können auch die folgenden Fenster Stile auf ein Header Steuerelement anwenden (Weitere Informationen finden Sie unter [Fenster Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) ):

- WS_CHILD erstellt ein untergeordnetes Fenster. Kann nicht mit dem WS_POPUP-Stil verwendet werden.

- WS_VISIBLE erstellt ein Fenster, das anfänglich sichtbar ist.

- WS_DISABLED erstellt ein Fenster, das anfänglich deaktiviert ist.

- WS_GROUP gibt das erste Steuerelement einer Gruppe von Steuerelementen an, in der der Benutzer mit den Pfeiltasten von einem Steuerelement zum nächsten wechseln kann. Alle Steuerelemente, die nach dem ersten Steuerelement mit dem WS_GROUP-Stil definiert sind, gehören zur selben Gruppe. Das nächste Steuerelement mit dem WS_GROUP-Stil beendet die Format Gruppe und startet die nächste Gruppe (d. h., eine Gruppe endet an der Stelle, an der der nächste beginnt).

- WS_TABSTOP gibt eine beliebige Anzahl von Steuerelementen an, über die der Benutzer mithilfe der Tab-Taste wechseln kann. Mit der Tab-Taste wird der Benutzer zum nächsten Steuerelement verschoben, das durch den WS_TABSTOP-Stil angegeben wird.

Wenn Sie erweiterte Windows-Stile mit dem Steuerelement verwenden möchten, müssen Sie anstelle von `Create`den Befehl " [kreateex](#createex) " aufrufen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]

##  <a name="createex"></a>CHeaderCtrl:: kreateex

Erstellt ein-Steuerelement (ein untergeordnetes Fenster) und ordnet `CHeaderCtrl` es dem-Objekt zu.

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
Der Stil des Header Steuer Elements. Eine Beschreibung der Header Steuerelement Stile finden Sie unter [Header-Steuerelement Stile](/windows/win32/Controls/header-control-styles) in der Windows SDK. Eine Liste der zusätzlichen Stile finden Sie unter [Erstellen](#create) .

*Rect*<br/>
Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Größe und Position des zu erstellenden Fensters in Client Koordinaten von *pparser*beschreibt.

*pParentWnd*<br/>
Ein Zeiger auf das Fenster, das das übergeordnete Element des Steuer Elements ist.

*nID*<br/>
Die ID des untergeordneten Fensters des Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Verwenden `CreateEx` Sie anstelle `Create` von, um erweiterte Windows-Stile anzuwenden, die durch den erweiterten Windows-Stil **WS_EX_** angegeben werden.

##  <a name="createdragimage"></a>CHeaderCtrl:: kreatedragimage

Erstellt eine transparente Version des Bilds eines Elements innerhalb eines Header Steuer Elements.

```
CImageList* CreateDragImage(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der null basierte Index des Elements innerhalb des Header Steuer Elements. Das diesem Element zugewiesene Bild ist die Grundlage für das transparente Bild.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, wenn erfolgreich. andernfalls NULL. Die zurückgegebene Liste enthält nur ein Bild.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [HDM_CREATEDRAGIMAGE](/windows/win32/Controls/hdm-createdragimage), wie im Windows SDK beschrieben. Er wird bereitgestellt, um das ziehen und Ablegen von Header Elementen zu unterstützen

Das `CImageList` Objekt, auf das der zurückgegebene Zeiger zeigt, ist ein temporäres Objekt und wird in der nächsten Leerlaufzeit Verarbeitung gelöscht.

##  <a name="deleteitem"></a>CHeaderCtrl::D eleteitem

Löscht ein Element aus einem Header-Steuerelement.

```
BOOL DeleteItem(int nPos);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Gibt den NULL basierten Index des zu löschenden Elements an.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]

##  <a name="drawitem"></a>CHeaderCtrl::D rawitem

Wird von Framework aufgerufen, wenn sich ein visueller Aspekt eines Header Steuer Elements mit Besitzer zeichnen ändert.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein Zeiger auf eine [drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) -Struktur, die das zu zeichnende Element beschreibt.

### <a name="remarks"></a>Hinweise

Der `itemAction` -Member `DRAWITEMSTRUCT` der-Struktur definiert die Zeichnungs Aktion, die ausgeführt werden soll.

Standardmäßig führt diese Member-Funktion keine Aktion aus. Überschreiben Sie diese Member-Funktion, um das Zeichnen für `CHeaderCtrl` ein owner-draw-Objekt zu implementieren

Die Anwendung sollte alle GDI-Objekte (Graphics Device Interface), die für den in *lpdrawitemstruct* angegebenen Anzeige Kontext ausgewählt sind, wiederherstellen, bevor diese Element Funktion beendet wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]

##  <a name="editfilter"></a>CHeaderCtrl:: EditFilter

Beginnt, den angegebenen Filter eines Header Steuer Elements zu bearbeiten.

```
BOOL EditFilter(
    int nColumn,
    BOOL bDiscardChanges);
```

### <a name="parameters"></a>Parameter

*ncolumn*<br/>
Die zu bearbeitende Spalte.

*bDiscardChanges*<br/>
Ein Wert, der angibt, wie die Bearbeitungs Änderungen des Benutzers behandelt werden, wenn der Benutzer gerade den Filter bearbeitet, wenn die [HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter) -Nachricht gesendet wird.

Geben Sie true an, um die vom Benutzer vorgenommenen Änderungen zu verwerfen, oder false, um die vom Benutzer vorgenommenen Änderungen zu übernehmen.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode implementiert das Verhalten der Win32-Nachricht [HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]

##  <a name="getbitmapmargin"></a>CHeaderCtrl:: getbitmapmargin

Ruft die Breite des Rands einer Bitmap in einem Header Steuerelement ab.

```
int GetBitmapMargin() const;
```

### <a name="return-value"></a>Rückgabewert

Die Breite des bitmaprandes in Pixel.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [HDM_GETBITMAPMARGIN](/windows/win32/Controls/hdm-getbitmapmargin), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]

##  <a name="getfocuseditem"></a>CHeaderCtrl:: getfocuseditem

Ruft den Index des Elements ab, das im aktuellen Header-Steuerelement den Fokus besitzt.

```
int GetFocusedItem() const;
```

### <a name="return-value"></a>Rückgabewert

Der null basierte Index des Header Elements, das den Fokus besitzt.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [HDM_GETFOCUSEDITEM](/windows/win32/Controls/hdm-getfocuseditem) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die-Variable `m_headerCtrl`definiert, die für den Zugriff auf das aktuelle Header Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden die `SetFocusedItem` - `GetFocusedItem` Methode und die-Methode veranschaulicht. In einem früheren Abschnitt des Codes haben wir ein Header Steuerelement mit fünf Spalten erstellt. Sie können jedoch ein Spalten Trennzeichen ziehen, um die Spalte nicht sichtbar zu machen. Im folgenden Beispiel wird der letzte Spaltenheader mit dem Fokus Element festgelegt und bestätigt.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

##  <a name="getimagelist"></a>CHeaderCtrl:: GetImageList

Ruft das Handle einer Bildliste ab, die zum Zeichnen von Header Elementen in einem Header-Steuerelement verwendet wird.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [HDM_GETIMAGELIST](/windows/win32/Controls/hdm-getimagelist), wie im Windows SDK beschrieben. Das `CImageList` Objekt, auf das der zurückgegebene Zeiger zeigt, ist ein temporäres Objekt und wird in der nächsten Leerlaufzeit Verarbeitung gelöscht.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]

##  <a name="getitem"></a>CHeaderCtrl:: GetItem

Ruft Informationen zu einem Header-Steuerelement ab.

```
BOOL GetItem(
    int nPos,
    HDITEM* pHeaderItem) const;
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Gibt den NULL basierten Index des abzurufenden Elements an.

*pHeaderItem*<br/>
Zeiger auf eine [HDITEM](/windows/win32/api/commctrl/ns-commctrl-_hd_itemw) -Struktur, die das neue Element empfängt. Diese Struktur wird mit den `InsertItem` -und-Member- `SetItem` Funktionen verwendet. Alle Flags, die `mask` im-Element festgelegt sind, stellen sicher, dass Werte in den entsprechenden Elementen bei der Rückgabe ordnungsgemäß ausgefüllt werden. Wenn das `mask` -Element auf 0 (null) festgelegt ist, sind die Werte in den anderen Strukturelementen bedeutungslos.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]

##  <a name="getitemcount"></a>CHeaderCtrl:: GetItemCount

Ruft die Anzahl der Elemente in einem Header Steuerelement ab.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Rückgabewert

Anzahl der Header Kontrollelemente, wenn erfolgreich; andernfalls-1.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CHeaderCtrl::D eleteitem](#deleteitem).

##  <a name="getitemdropdownrect"></a>CHeaderCtrl:: getitemdropdownrect

Ruft das umgebende Rechteck der Dropdown Schaltfläche für ein Header Element im aktuellen Header Steuerelement ab.

```
BOOL GetItemDropDownRect(
    int iItem,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iItem*|in NULL basierter Index eines Header Elements, dessen Stil HDF_SPLITBUTTON ist. Weitere Informationen finden Sie unter dem `fmt` -Member der [HDITEM](/windows/win32/api/commctrl/ns-commctrl-_hd_itemw) -Struktur.|
|*lpRect*|vorgenommen Ein Zeiger auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, um die umschließenden Rechteck Informationen zu erhalten.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Funktion erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [HDM_GETITEMDROPDOWNRECT](/windows/win32/Controls/hdm-getitemdropdownrect) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die-Variable `m_headerCtrl`definiert, die für den Zugriff auf das aktuelle Header Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die `GetItemDropDownRect` -Methode veranschaulicht. In einem früheren Abschnitt des Codes haben wir ein Header Steuerelement mit fünf Spalten erstellt. Im folgenden Codebeispiel wird ein 3D-Rechteck um die Position in der ersten Spalte gezeichnet, die für die Header-Dropdown Schaltfläche reserviert ist.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]

##  <a name="getitemrect"></a>CHeaderCtrl:: GetItemRect

Ruft das umgebende Rechteck für ein angegebenes Element in einem Header Steuerelement ab.

```
BOOL GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der null basierte Index des Header Steuerelement Elements.

*lpRect*<br/>
Ein Zeiger auf die Adresse einer [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die umschließenden Rechteck Informationen empfängt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Methode implementiert das Verhalten der Win32-Nachricht [HDM_GETITEMRECT](/windows/win32/Controls/hdm-getitemrect), wie im Windows SDK beschrieben.

##  <a name="getorderarray"></a>CHeaderCtrl:: getor-Array

Ruft die Reihenfolge der Elemente in einem Header Steuerelement von links nach rechts ab.

```
BOOL GetOrderArray(
    LPINT piArray,
    int iCount);
```

### <a name="parameters"></a>Parameter

*piArray*<br/>
Ein Zeiger auf die Adresse eines Puffers, der die Indexwerte der Elemente im Header Steuerelement in der Reihenfolge empfängt, in der Sie von links nach rechts angezeigt werden.

*iCount*<br/>
Die Anzahl der Header Steuerungselemente. Darf nicht negativ sein.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [HDM_GETORDERARRAY](/windows/win32/Controls/hdm-getorderarray), wie im Windows SDK beschrieben. Sie wird zur Unterstützung der Header Element-Reihenfolge bereitgestellt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]

##  <a name="getoverflowrect"></a>CHeaderCtrl:: GetOverflowRect

Ruft das umgebende Rechteck der Überlauf Schaltfläche des aktuellen Header-Steuer Elements ab.

```
BOOL GetOverflowRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*lpRect*|vorgenommen Ein Zeiger auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die umschließenden Rechteck Informationen empfängt.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Funktion erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Wenn das Header Steuerelement mehr Elemente enthält, als gleichzeitig angezeigt werden können, kann das Steuerelement eine Überlauf Schaltfläche anzeigen, die zu nicht sichtbaren Elementen führt. Das Header Steuerelement muss die Stile HDS_OVERFLOW und HDF_SPLITBUTTON aufweisen, um die Überlauf Schaltfläche anzuzeigen. Das umschließende Rechteck schließt die Überlauf Schaltfläche ein und ist nur vorhanden, wenn die Überlauf Schaltfläche angezeigt wird. Weitere Informationen finden Sie unter [Header-Steuerelement Stile](/windows/win32/Controls/header-control-styles).

Diese Methode sendet die [HDM_GETOVERFLOWRECT](/windows/win32/Controls/hdm-getoverflowrect) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die-Variable `m_headerCtrl`definiert, die für den Zugriff auf das aktuelle Header Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die `GetOverflowRect` -Methode veranschaulicht. In einem früheren Abschnitt des Codes haben wir ein Header Steuerelement mit fünf Spalten erstellt. Sie können jedoch ein Spalten Trennzeichen ziehen, um die Spalte nicht sichtbar zu machen. Wenn einige Spalten nicht sichtbar sind, zeichnet das Header Steuerelement eine Überlauf Schaltfläche. Im folgenden Codebeispiel wird ein 3D-Rechteck um die Position der Überlauf Schaltfläche gezeichnet.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]

##  <a name="hittest"></a>CHeaderCtrl:: HitTest

Bestimmt, welches Header Element, sofern vorhanden, sich an einem angegebenen Punkt befindet.

```
int HitTest(LPHDHITTESTINFO* phdhti);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*phdhti*|[in, out] Ein Zeiger auf eine [hdhittestinfo](/windows/win32/api/commctrl/ns-commctrl-_hd_hittestinfo) -Struktur, die den zu testenden Punkt angibt und die Ergebnisse des Tests empfängt.|

### <a name="return-value"></a>Rückgabewert

Der null basierte Index des Header Elements, sofern vorhanden, an der angegebenen Position. andernfalls-1.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [HDM_HITTEST](/windows/win32/Controls/hdm-hittest) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die-Variable `m_headerCtrl`definiert, die für den Zugriff auf das aktuelle Header Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die `HitTest` -Methode veranschaulicht. In einem früheren Abschnitt dieses Code Beispiels haben wir ein Header Steuerelement mit fünf Spalten erstellt. Sie können jedoch ein Spalten Trennzeichen ziehen, um die Spalte nicht sichtbar zu machen. In diesem Beispiel wird der Index der Spalte angezeigt, wenn Sie sichtbar ist, und-1, wenn die Spalte nicht sichtbar ist.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]

##  <a name="insertitem"></a>CHeaderCtrl:: InsertItem

Fügt ein neues Element am angegebenen Index in ein Header Steuerelement ein.

```
int InsertItem(
    int nPos,
    HDITEM* phdi);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Der nullbasierte Index des einzufügenden Elements. Wenn der Wert 0 (null) ist, wird das Element am Anfang des Header Steuer Elements eingefügt. Wenn der Wert größer als der maximale Wert ist, wird das Element am Ende des Header Steuer Elements eingefügt.

*phdi*<br/>
Zeiger auf eine [HDITEM](/windows/win32/api/commctrl/ns-commctrl-_hd_itemw) -Struktur, die Informationen über das einzufügende Element enthält.

### <a name="return-value"></a>Rückgabewert

Der Index des neuen Elements, wenn es erfolgreich war. andernfalls-1.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]

##  <a name="layout"></a>CHeaderCtrl:: Layout

Ruft die Größe und Position eines Header Steuer Elements innerhalb eines angegebenen Rechtecks ab.

```
BOOL Layout(HDLAYOUT* pHeaderLayout);
```

### <a name="parameters"></a>Parameter

*pHeaderLayout*<br/>
Ein Zeiger auf eine [hdlayout](/windows/win32/api/commctrl/ns-commctrl-_hd_layout) -Struktur, die Informationen enthält, die zum Festlegen der Größe und Position eines Header Steuer Elements verwendet werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Funktion wird verwendet, um die entsprechenden Dimensionen für ein neues Header Steuerelement zu bestimmen, das das angegebene Rechteck belegen soll.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]

##  <a name="ordertoindex"></a>CHeaderCtrl:: orderto Index

Ruft den Indexwert für ein Element auf Grundlage seiner Reihenfolge im Header Steuerelement ab.

```
int OrderToIndex(int nOrder) const;
```

### <a name="parameters"></a>Parameter

*nOrder*<br/>
Die null basierte Reihenfolge, in der das Element im Header Steuerelement angezeigt wird, von links nach rechts.

### <a name="return-value"></a>Rückgabewert

Der Index des Elements auf der Grundlage seiner Reihenfolge im Header Steuerelement. Der Index zählt von links nach rechts, beginnend mit 0.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten des Win32-Makros [HDM_ORDERTOINDEX](/windows/win32/controls/hdm-ordertoindex), wie im Windows SDK beschrieben. Sie wird zur Unterstützung der Header Element-Reihenfolge bereitgestellt.

##  <a name="setbitmapmargin"></a>CHeaderCtrl:: setbitmapmargin

Legt die Breite des Rands einer Bitmap in einem Header Steuerelement fest.

```
int SetBitmapMargin(int nWidth);
```

### <a name="parameters"></a>Parameter

*nWidth*<br/>
Die in Pixel angegebene Breite des Randes, das eine Bitmap in einem vorhandenen Header Steuerelement umgibt.

### <a name="return-value"></a>Rückgabewert

Die Breite des bitmaprandes in Pixel.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [HDM_SETBITMAPMARGIN](/windows/win32/Controls/hdm-setbitmapmargin), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]

##  <a name="setfilterchangetimeout"></a>CHeaderCtrl:: setfilterchangetimeout

Legt das Timeout Intervall zwischen dem Zeitpunkt fest, zu dem eine Änderung in den Filter Attributen stattfindet, und dem Veröffentlichen einer [HDN_FILTERCHANGE](/windows/win32/Controls/hdn-filterchange) -Benachrichtigung.

```
int SetFilterChangeTimeout(DWORD dwTimeOut);
```

### <a name="parameters"></a>Parameter

*dwTimeOut*<br/>
Timeout Wert in Millisekunden.

### <a name="return-value"></a>Rückgabewert

Der Index des Filter Steuer Elements, das geändert wird.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [HDM_SETFILTERCHANGETIMEOUT](/windows/win32/Controls/hdm-setfilterchangetimeout), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]

##  <a name="setfocuseditem"></a>CHeaderCtrl:: setfocuseditem

Legt den Fokus auf ein angegebenes Header Element im aktuellen Header Steuerelement fest.

```
BOOL SetFocusedItem(int iItem);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iItem*|in NULL basierter Index eines Header Elements.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [HDM_SETFOCUSEDITEM](/windows/win32/Controls/hdm-setfocuseditem) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die-Variable `m_headerCtrl`definiert, die für den Zugriff auf das aktuelle Header Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden die `SetFocusedItem` - `GetFocusedItem` Methode und die-Methode veranschaulicht. In einem früheren Abschnitt des Codes haben wir ein Header Steuerelement mit fünf Spalten erstellt. Sie können jedoch ein Spalten Trennzeichen ziehen, um die Spalte nicht sichtbar zu machen. Im folgenden Beispiel wird der letzte Spaltenheader mit dem Fokus Element festgelegt und bestätigt.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

##  <a name="sethotdivider"></a>CHeaderCtrl:: * Host Host

Ändert den unter Teiler zwischen Header Elementen, um einen manuellen Drag & Drop eines Header Elements anzugeben.

```
int SetHotDivider(CPoint pt);
int SetHotDivider(int nIndex);
```

### <a name="parameters"></a>Parameter

*pt*<br/>
Die Position des Zeigers. Das Header Steuerelement markiert den entsprechenden unter Teiler basierend auf der Position des Zeigers.

*nIndex*<br/>
Der Index des hervorgehobenen unter Teilers.

### <a name="return-value"></a>Rückgabewert

Der Index des hervorgehobenen unter Teilers.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [HDM_SETHOTDIVIDER](/windows/win32/Controls/hdm-sethotdivider), wie im Windows SDK beschrieben. Er wird bereitgestellt, um das ziehen und Ablegen von Header Elementen zu unterstützen

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]

##  <a name="setimagelist"></a>CHeaderCtrl:: SetImageList

Weist einem Header Steuerelement eine Bildliste zu.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parameter

*pImageList*<br/>
Ein Zeiger auf ein `CImageList` -Objekt, das die Bildliste enthält, die dem Header Steuerelement zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, das zuvor dem Header Steuerelement zugewiesen wurde.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [HDM_SETIMAGELIST](/windows/win32/Controls/hdm-setimagelist), wie im Windows SDK beschrieben. Das `CImageList` Objekt, auf das der zurückgegebene Zeiger zeigt, ist ein temporäres Objekt und wird in der nächsten Leerlaufzeit Verarbeitung gelöscht.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CHeaderCtrl:: GetImageList](#getimagelist).

##  <a name="setitem"></a>CHeaderCtrl::/TItem

Legt die Attribute des angegebenen Elements in einem Header Steuerelement fest.

```
BOOL SetItem(
    int nPos,
    HDITEM* pHeaderItem);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Der null basierte Index des Elements, das bearbeitet werden soll.

*pHeaderItem*<br/>
Zeiger auf eine [HDITEM](/windows/win32/api/commctrl/ns-commctrl-_hd_itemw) -Struktur, die Informationen über das neue Element enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CHeaderCtrl:: GetItem](#getitem).

##  <a name="setorderarray"></a>CHeaderCtrl:: tarderarray

Legt die Reihenfolge der Elemente in einem Header Steuerelement von links nach rechts fest.

```
BOOL SetOrderArray(
    int iCount,
    LPINT piArray);
```

### <a name="parameters"></a>Parameter

*iCount*<br/>
Die Anzahl der Header Steuerungselemente.

*piArray*<br/>
Ein Zeiger auf die Adresse eines Puffers, der die Indexwerte der Elemente im Header Steuerelement in der Reihenfolge empfängt, in der Sie von links nach rechts angezeigt werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten des Win32-Makros [HDM_SETORDERARRAY](/windows/win32/Controls/hdm-setorderarray), wie im Windows SDK beschrieben. Sie wird zur Unterstützung der Header Element-Reihenfolge bereitgestellt.

### <a name="example"></a>Beispiel

  Sehen Sie sich das Beispiel für [CHeaderCtrl:: getor Array](#getorderarray)an.

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CTabCtrl-Klasse](../../mfc/reference/ctabctrl-class.md)<br/>
[CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md)<br/>
[CImageList-Klasse](../../mfc/reference/cimagelist-class.md)
