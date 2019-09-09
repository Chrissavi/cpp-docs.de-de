---
title: CToolBar-Klasse
ms.date: 11/04/2016
f1_keywords:
- CToolBar
- AFXEXT/CToolBar
- AFXEXT/CToolBar::CToolBar
- AFXEXT/CToolBar::CommandToIndex
- AFXEXT/CToolBar::Create
- AFXEXT/CToolBar::CreateEx
- AFXEXT/CToolBar::GetButtonInfo
- AFXEXT/CToolBar::GetButtonStyle
- AFXEXT/CToolBar::GetButtonText
- AFXEXT/CToolBar::GetItemID
- AFXEXT/CToolBar::GetItemRect
- AFXEXT/CToolBar::GetToolBarCtrl
- AFXEXT/CToolBar::LoadBitmap
- AFXEXT/CToolBar::LoadToolBar
- AFXEXT/CToolBar::SetBitmap
- AFXEXT/CToolBar::SetButtonInfo
- AFXEXT/CToolBar::SetButtons
- AFXEXT/CToolBar::SetButtonStyle
- AFXEXT/CToolBar::SetButtonText
- AFXEXT/CToolBar::SetHeight
- AFXEXT/CToolBar::SetSizes
helpviewer_keywords:
- CToolBar [MFC], CToolBar
- CToolBar [MFC], CommandToIndex
- CToolBar [MFC], Create
- CToolBar [MFC], CreateEx
- CToolBar [MFC], GetButtonInfo
- CToolBar [MFC], GetButtonStyle
- CToolBar [MFC], GetButtonText
- CToolBar [MFC], GetItemID
- CToolBar [MFC], GetItemRect
- CToolBar [MFC], GetToolBarCtrl
- CToolBar [MFC], LoadBitmap
- CToolBar [MFC], LoadToolBar
- CToolBar [MFC], SetBitmap
- CToolBar [MFC], SetButtonInfo
- CToolBar [MFC], SetButtons
- CToolBar [MFC], SetButtonStyle
- CToolBar [MFC], SetButtonText
- CToolBar [MFC], SetHeight
- CToolBar [MFC], SetSizes
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
ms.openlocfilehash: 4977cbe0b749724f999d6d7089d46f12d1e2963e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502390"
---
# <a name="ctoolbar-class"></a>CToolBar-Klasse

Steuerleisten, die eine Zeile mit Bitmapschaltflächen und optionalen Trennzeichen enthalten.

## <a name="syntax"></a>Syntax

```
class CToolBar : public CControlBar
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CToolBar::CToolBar](#ctoolbar)|Erstellt ein `CToolBar`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CToolBar::CommandToIndex](#commandtoindex)|Gibt den Index einer Schaltfläche mit der angegebenen Befehls-ID zurück.|
|[CToolBar::Create](#create)|Erstellt die Windows-Symbolleiste und fügt Sie `CToolBar` an das-Objekt an.|
|[CToolBar::CreateEx](#createex)|Erstellt ein `CToolBar` -Objekt mit zusätzlichen Stilen für das `CToolBarCtrl` eingebettete Objekt.|
|[CToolBar::GetButtonInfo](#getbuttoninfo)|Ruft die ID, den Stil und die Bildnummer einer Schaltfläche ab.|
|[CToolBar::GetButtonStyle](#getbuttonstyle)|Ruft den Stil für eine Schaltfläche ab.|
|[CToolBar::GetButtonText](#getbuttontext)|Ruft den Text ab, der auf einer Schaltfläche angezeigt wird.|
|[CToolBar::GetItemID](#getitemid)|Gibt die Befehls-ID einer Schaltfläche oder eines Trenn Zeichens am angegebenen Index zurück.|
|[CToolBar::GetItemRect](#getitemrect)|Ruft das Anzeige Rechteck für das Element am angegebenen Index ab.|
|[CToolBar::GetToolBarCtrl](#gettoolbarctrl)|Ermöglicht den direkten Zugriff auf das zugrunde liegende allgemeine Steuerelement.|
|[CToolBar::LoadBitmap](#loadbitmap)|Lädt die Bitmap, die Bitmap-Button-Bilder enthält.|
|[CToolBar::LoadToolBar](#loadtoolbar)|Lädt eine Symbolleisten Ressource, die mit dem Ressourcen-Editor erstellt wurde.|
|[CToolBar::SetBitmap](#setbitmap)|Legt ein Bitmap-Bild fest.|
|[CToolBar::SetButtonInfo](#setbuttoninfo)|Legt die ID, den Stil und die Bildnummer einer Schaltfläche fest.|
|[CToolBar::SetButtons](#setbuttons)|Legt Schaltflächen Stile und einen Index von Schaltflächen Bildern innerhalb der Bitmap fest.|
|[CToolBar::SetButtonStyle](#setbuttonstyle)|Legt den Stil für eine Schaltfläche fest.|
|[CToolBar::SetButtonText](#setbuttontext)|Legt den Text fest, der auf einer Schaltfläche angezeigt wird.|
|[CToolBar::SetHeight](#setheight)|Legt die Höhe der Symbolleiste fest.|
|[CToolBar::SetSizes](#setsizes)|Legt die Größe von Schaltflächen und deren Bitmaps fest.|

## <a name="remarks"></a>Hinweise

Die Schaltflächen können wie Pushbuttons, Kontrollkästchen oder Options Felder fungieren. `CToolBar`-Objekte sind in der Regel eingebettete Member von Frame-Window-Objekten, die von der-Klasse [CFrameWnd](../../mfc/reference/cframewnd-class.md) oder [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)abgeleitet werden.

[CToolBar:: GetToolBarCtrl](#gettoolbarctrl), eine Member-Funktion, die neu in MFC 4,0 ist, ermöglicht es Ihnen, die Unterstützung von Symbolleisten Anpassung und zusätzlichen Funktionen von der allgemeinen Windows-Steuerelement Funktion zu nutzen. `CToolBar`Member-Funktionen verfügen über die meisten Funktionen der allgemeinen Windows-Steuerelemente. Wenn Sie jedoch aufzurufen `GetToolBarCtrl`, können Sie die Symbolleisten noch mehr über die Merkmale von Windows 95/98-Symbolleisten verfügen. Wenn Sie aufzurufen `GetToolBarCtrl`, wird ein Verweis auf ein `CToolBarCtrl` -Objekt zurückgegeben. Weitere Informationen zum Entwerfen von Symbolleisten mit allgemeinen Windows-Steuerelementen finden Sie unter [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) . Allgemeinere Informationen zu allgemeinen Steuerelementen finden Sie unter Allgemeine Steuer [Elemente](/windows/win32/Controls/common-controls-intro) in der Windows SDK.

Visual C++ bietet zwei Methoden zum Erstellen einer Symbolleiste. Führen Sie die folgenden Schritte aus, um mit dem Ressourcen-Editor eine Symbolleisten Ressource zu erstellen:

1. Erstellen Sie eine Symbolleisten Ressource.

1. Erstellen Sie `CToolBar` das-Objekt.

1. Rufen Sie die [Create](#create) ( [oder die](#createex)Funktion "up)" auf, um die Windows-Symbolleiste `CToolBar` zu erstellen und an das-Objekt anzufügen.

1. Laden Sie [LoadToolBar](#loadtoolbar) zum Laden der Symbolleisten Ressource.

Führen Sie andernfalls die folgenden Schritte aus:

1. Erstellen Sie `CToolBar` das-Objekt.

1. Rufen Sie die [Create](#create) ( [oder die](#createex)Funktion "up)" auf, um die Windows-Symbolleiste `CToolBar` zu erstellen und an das-Objekt anzufügen.

1. Ruft [LoadBitmap](#loadbitmap) auf, um die Bitmap zu laden, die die Symbolleisten-Schaltflächen Bilder enthält.

1. Aufrufen von [setButtons](#setbuttons) zum Festlegen des Schaltflächen Stils und Zuordnen der einzelnen Schaltflächen zu einem Bild in der Bitmap.

Alle Schaltflächen Bilder auf der Symbolleiste werden aus einer Bitmap entnommen, die für jede Schaltfläche ein Bild enthalten muss. Alle Bilder müssen dieselbe Größe aufweisen. der Standardwert ist 16 Pixel breit und 15 Pixel hoch. Bilder müssen nebeneinander in der Bitmap angezeigt werden.

Die `SetButtons` -Funktion nimmt einen Zeiger auf ein Array von Steuerelement-IDs und eine ganze Zahl an, die die Anzahl der Elemente im Array angibt. Die-Funktion legt die ID der einzelnen Schaltflächen auf den Wert des entsprechenden Elements des Arrays fest und weist jeder Schaltfläche einen Bildindex zu, der die Position des Bild der Schaltfläche in der Bitmap angibt. Wenn ein Array Element den Wert ID_SEPARATOR aufweist, wird kein Bildindex zugewiesen.

Die Reihenfolge der Bilder in der Bitmap ist in der Regel die Reihenfolge, in der Sie auf dem Bildschirm gezeichnet werden, aber Sie können die [SetButtonInfo](#setbuttoninfo) -Funktion verwenden, um die Beziehung zwischen Bild Reihenfolge und Zeichnungsreihenfolge zu ändern.

Alle Schaltflächen in einer Symbolleiste haben dieselbe Größe. Der Standardwert beträgt 24 x 22 Pixel, gemäß den *Richtlinien für die Windows-Benutzeroberfläche für den Software Entwurf*. Alle zusätzlichen Leerzeichen zwischen der Bild-und der Schaltflächen Dimension werden verwendet, um einen Rahmen um das Bild zu bilden.

Jede Schaltfläche verfügt über ein Bild. Die verschiedenen Schaltflächen Zustände und-Stile (gedrückt, hoch, nach unten, deaktiviert, deaktiviert und unbestimmt) werden aus diesem ein Bild generiert. Obwohl Bitmaps eine beliebige Farbe sein können, können Sie die besten Ergebnisse mit Bildern in schwarz und Graustufen erzielen.

> [!WARNING]
> `CToolBar`unterstützt Bitmaps mit maximal 16 Farben. Wenn Sie ein Bild in einen Symbolleisten-Editor laden, konvertiert Visual Studio das Bild bei Bedarf automatisch in eine 16-farbige Bitmap und zeigt eine Warnmeldung an, wenn das Image konvertiert wurde. Wenn Sie ein Bild mit mehr als 16 Farben (mit einem externen Editor zum Bearbeiten des Bilds) verwenden, verhält sich die Anwendung möglicherweise unerwartet.

Symbolleisten Schaltflächen imitieren standardmäßig Pushbuttons. Mit Symbolleisten Schaltflächen können jedoch auch Kontrollkästchen oder Options Felder imitiert werden. Kontrollkästchen-Schaltflächen haben drei Zustände: aktiviert, deaktiviert und unbestimmt. Options Felder haben nur zwei Zustände: aktiviert und deaktiviert.

Wenn Sie eine einzelne Schaltfläche oder einen Trennzeichen Stil ohne Verweis auf ein Array festlegen möchten, rufen Sie [GetButtonStyle](#getbuttonstyle) auf, um den Stil abzurufen, und `SetButtons`rufen Sie dann [setbuttonstyle](#setbuttonstyle) anstelle von auf. `SetButtonStyle`ist besonders nützlich, wenn Sie den Stil einer Schaltfläche zur Laufzeit ändern möchten.

Um Text zuzuweisen, der auf einer Schaltfläche angezeigt wird, rufen Sie [getbuttontext](#getbuttontext) auf, um den Text abzurufen, der auf der Schaltfläche angezeigt werden soll, und rufen Sie dann [SetButtonText](#setbuttontext) auf, um den Text

Um eine Kontrollkästchen-Schaltfläche zu erstellen, weisen Sie Ihr den Stil TBBS_CHECKBOX `CCmdUI` zu, `SetCheck` oder verwenden Sie die Member-Funktion eines Objekts in einem ON_UPDATE_COMMAND_UI-Handler. Durch `SetCheck` Aufrufen von wird ein PUSHBUTTON in eine Kontrollkästchen-Schaltfläche umgewandelt. Übergeben `SetCheck` Sie ein Argument von 0 für deaktiviert, 1 für aktiviert oder 2 für unbestimmt.

Um ein Optionsfeld zu erstellen, rufen Sie die [setradio](../../mfc/reference/ccmdui-class.md#setradio) -Member-Funktion eines [CCmdUI](../../mfc/reference/ccmdui-class.md) -Objekts aus einem ON_UPDATE_COMMAND_UI-Handler auf. Übergeben `SetRadio` Sie ein Argument von 0 für deaktiviert oder nicht NULL für aktiviert. Um das gegenseitig ausschließende Verhalten einer Radiogruppe bereitzustellen, müssen Sie über ON_UPDATE_COMMAND_UI Handler für alle Schaltflächen in der Gruppe verfügen.

Weitere Informationen zur Verwendung von `CToolBar`finden Sie im Artikel [MFC-Symbol](../../mfc/mfc-toolbar-implementation.md) leisten [Implementierung und Technical Note 31: Steuer leisten](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CToolBar`

## <a name="requirements"></a>Anforderungen

**Header:** Afxext. h

##  <a name="commandtoindex"></a>CToolBar:: commanddeindex

Diese Member-Funktion gibt den Index der ersten Symbolleisten Schaltfläche zurück, beginnend an Position 0, `nIDFind`deren Befehls-ID übereinstimmt.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parameter

*nIDFind*<br/>
Befehls-ID einer Symbolleisten-Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Der Index der Schaltfläche oder-1, wenn keine Schaltfläche über die angegebene Befehls-ID verfügt.

##  <a name="create"></a>CToolBar:: Create

Diese Member-Funktion erstellt eine Windows-Symbolleiste (ein untergeordnetes Fenster) und `CToolBar` ordnet Sie dem-Objekt zu.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Zeiger auf das Fenster, das das übergeordnete Symbol der Symbolleiste ist.

*dwStyle*<br/>
Der Symbolleisten Stil. Zusätzliche Symbolleisten Stile werden unterstützt:

- Die CBRS_TOP-Steuerleiste befindet sich am oberen Rand des Rahmen Fensters.

- Die CBRS_BOTTOM-Steuerleiste befindet sich am unteren Rand des Rahmen Fensters.

- Die CBRS_NOALIGN-Steuerleiste wird nicht neu positioniert, wenn die Größe des übergeordneten Elements geändert wird.

- In der CBRS_TOOLTIPS-Steuerleiste werden Quick Infos angezeigt.

- Die CBRS_SIZE_DYNAMIC-Steuerleiste ist dynamisch.

- Die CBRS_SIZE_FIXED-Steuerleiste ist korrigiert.

- Die CBRS_FLOATING-Steuerleiste ist unverankert.

- CBRS_FLYBY Status Leiste zeigt Informationen über die Schaltfläche an.

- Die CBRS_HIDE_INPLACE-Steuerleiste wird dem Benutzer nicht angezeigt.

*nID*<br/>
Die ID des untergeordneten Fensters der Symbolleiste.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Außerdem wird die Höhe der Symbolleiste auf einen Standardwert festgelegt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]

##  <a name="createex"></a>CToolBar:: kreateex

Rufen Sie diese Funktion auf, um eine Windows-Symbolleiste (ein untergeordnetes Fenster) `CToolBar` zu erstellen und Sie dem-Objekt zuzuordnen.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = TBSTYLE_FLAT,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_ALIGN_TOP,
    CRect rcBorders = CRect(
    0,
    0,
    0,
    0),
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Zeiger auf das Fenster, das das übergeordnete Symbol der Symbolleiste ist.

*dwCtrlStyle*<br/>
Zusätzliche Stile für die Erstellung des eingebetteten [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) -Objekts. Standardmäßig ist dieser Wert auf TBSTYLE_FLAT festgelegt. Eine umfassende Liste der Symbolleisten Stile finden Sie unter *dwstyle*.

*dwStyle*<br/>
Der Symbolleisten Stil. Eine Liste geeigneter Stile finden Sie unter [Symbolleisten-Steuerelement-und Schaltflächen Stile](/windows/win32/Controls/toolbar-control-and-button-styles) im Windows SDK.

*rcborders*<br/>
Ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Breite des Symbolleisten Fensterrahmens definiert. Diese Rahmen werden standardmäßig auf 0, 0, 0 und 0 festgelegt. dadurch entsteht ein Symbolleisten Fenster ohne Rahmen.

*nID*<br/>
Die ID des untergeordneten Fensters der Symbolleiste.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Außerdem wird die Höhe der Symbolleiste auf einen Standardwert festgelegt.

Verwenden `CreateEx`Sie anstelle von [Create](#create), wenn bestimmte Stile während der Erstellung des eingebetteten Toolbar-Steuer Elements vorhanden sein müssen. Legen Sie beispielsweise *dwctrlstyle* auf TBSTYLE_FLAT &#124; TBSTYLE_TRANSPARENT fest, um eine Symbolleiste zu erstellen, die den Internet Explorer 4-Symbolleisten ähnelt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]

##  <a name="ctoolbar"></a>CToolBar:: CToolBar

Diese Member-Funktion erstellt `CToolBar` ein-Objekt und legt die Standardgrößen fest.

```
CToolBar();
```

### <a name="remarks"></a>Hinweise

Rufen Sie die Funktion [Create](#create) Member auf, um das Symbolleisten Fenster zu erstellen.

##  <a name="getbuttoninfo"></a>CToolBar:: getbuttoninfo

Diese Member-Funktion Ruft die Steuerelement-ID, den Stil und den Bild Index der Symbolleisten-Schaltfläche oder des Trenn Zeichens an der durch *nIndex* angegebenen Position ab.

```
void GetButtonInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& iImage) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index der Symbolleisten-Schaltfläche oder des Trenn Zeichens, dessen Informationen abgerufen werden sollen.

*nID*<br/>
Verweis auf eine uint, die auf die Befehls-ID der Schaltfläche festgelegt ist.

*nStyle*<br/>
Verweis auf einen uint-Wert, der auf den Stil der Schaltfläche festgelegt ist.

*iImage*<br/>
Verweis auf eine Ganzzahl, die auf den Index des Bilds der Schaltfläche innerhalb der Bitmap festgelegt ist.

### <a name="remarks"></a>Hinweise

Diese Werte werden den Variablen zugewiesen, auf die von *NID*, *nstyle*und *iImage*verwiesen wird. Der Bildindex ist die Position des Bilds innerhalb der Bitmap, das Bilder für alle Symbolleisten Schaltflächen enthält. Das erste Bild befindet sich an Position 0.

Wenn *nIndex* ein Trennzeichen angibt, wird *iImage* auf die Trennlinie in Pixel festgelegt.

##  <a name="getbuttonstyle"></a>CToolBar:: GetButtonStyle

Rufen Sie diese Member-Funktion auf, um den Stil einer Schaltfläche oder eines Trenn Zeichens auf der Symbolleiste abzurufen.

```
UINT GetButtonStyle(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index der Symbolleisten Schaltfläche oder des Trenn Zeichens, das abgerufen werden soll.

### <a name="return-value"></a>Rückgabewert

Der Stil der Schaltfläche oder des Trenn Zeichens, das von *nIndex*angegeben wird.

### <a name="remarks"></a>Hinweise

Der Stil einer Schaltfläche bestimmt, wie die Schaltfläche angezeigt wird und wie Sie auf Benutzereingaben reagiert. Beispiele für Schaltflächen Stile finden Sie unter [setbuttonstyle](#setbuttonstyle) .

##  <a name="getbuttontext"></a>CToolBar:: getbuttontext

Rufen Sie diese Element Funktion auf, um den Text abzurufen, der auf einer Schaltfläche angezeigt wird.

```
CString GetButtonText(int nIndex) const;

void GetButtonText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des abzurufenden Texts.

*rString*<br/>
Ein Verweis auf ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den Text enthält, der abgerufen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein `CString` -Objekt, das den Schaltflächen Text enthält.

### <a name="remarks"></a>Hinweise

Die zweite Form dieser Member-Funktion füllt ein `CString` -Objekt mit dem Zeichen folgen Text.

##  <a name="getitemid"></a>CToolBar:: getItemID

Diese Member-Funktion gibt die Befehls-ID der durch *nIndex*angegebenen Schaltfläche oder des Trenn Zeichens zurück.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index des Elements, dessen ID abgerufen werden soll.

### <a name="return-value"></a>Rückgabewert

Die Befehls-ID der durch *nIndex*angegebenen Schaltfläche oder des Trenn Zeichens.

### <a name="remarks"></a>Hinweise

Trennzeichen geben ID_SEPARATOR zurück.

##  <a name="getitemrect"></a>CToolBar:: GetItemRect

Diese Member-Funktion füllt `RECT` die-Struktur, deren Adresse in *lprect* enthalten ist, mit den Koordinaten der Schaltfläche oder des Trenn Zeichens, das von *nIndex*angegeben wird.

```
virtual void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index des Elements (Schaltfläche oder Trennzeichen), dessen Rechteck Koordinaten abgerufen werden sollen.

*lpRect*<br/>
Adresse der [Rect](/windows/win32/api/windef/ns-windef-rect) -Struktur, die die Koordinaten des Elements enthält.

### <a name="remarks"></a>Hinweise

Die Koordinaten befinden sich in Pixel relativ zur linken oberen Ecke der Symbolleiste.

Verwenden `GetItemRect` Sie, um die Koordinaten eines Trenn Zeichens zu erhalten, das Sie durch ein Kombinations Feld oder ein anderes Steuerelement ersetzen möchten.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CToolBar:: setSizes](#setsizes).

##  <a name="gettoolbarctrl"></a>CToolBar:: GetToolBarCtrl

Diese Member-Funktion ermöglicht den direkten Zugriff auf das zugrunde liegende allgemeine Steuerelement.

```
CToolBarCtrl& GetToolBarCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf ein `CToolBarCtrl`-Objekt.

### <a name="remarks"></a>Hinweise

Verwenden `GetToolBarCtrl` Sie, um die Funktionalität des allgemeinen Windows-Symbolleisten-Steuer Elements zu nutzen und die Unterstützung von [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) für die Anpassung der Symbolleiste zu nutzen.

Weitere Informationen zum Verwenden von allgemeinen Steuerelementen finden Sie im Artikel Steuer [Elemente](../../mfc/controls-mfc.md) und [Allgemeine Steuerelemente](/windows/win32/Controls/common-controls-intro) in der Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]

##  <a name="loadbitmap"></a>CToolBar:: LoadBitmap

Mit dieser Member-Funktion können Sie die durch `lpszResourceName` or `nIDResource`angegebene Bitmap laden.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>Parameter

*lpszResourceName*<br/>
Zeiger auf den Ressourcennamen der zu ladenden Bitmap.

*nIDResource*<br/>
Die Ressourcen-ID der Bitmap, die geladen werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Die Bitmap sollte für jede Symbolleisten Schaltfläche ein Bild enthalten. Wenn die Bilder nicht die Standardgröße haben (16 Pixel breit und 15 Pixel hoch), können Sie [setSizes](#setsizes) aufrufen, um die Schaltflächen Größen und Ihre Bilder festzulegen.

> [!WARNING]
> `CToolBar`unterstützt Bitmaps mit maximal 16 Farben. Wenn Sie ein Bild in einen Symbolleisten-Editor laden, konvertiert Visual Studio das Bild bei Bedarf automatisch in eine 16-farbige Bitmap und zeigt eine Warnmeldung an, wenn das Image konvertiert wurde. Wenn Sie ein Bild mit mehr als 16 Farben (mit einem externen Editor zum Bearbeiten des Bilds) verwenden, verhält sich die Anwendung möglicherweise unerwartet.

##  <a name="loadtoolbar"></a>CToolBar:: LoadToolBar

Mit dieser Member-Funktion können Sie die von *lpszresourcename* oder *nidresource*angegebene Symbolleiste laden.

```
BOOL LoadToolBar(LPCTSTR lpszResourceName);
BOOL LoadToolBar(UINT nIDResource);
```

### <a name="parameters"></a>Parameter

*lpszResourceName*<br/>
Zeiger auf den Ressourcennamen der Symbolleiste, die geladen werden soll.

*nIDResource*<br/>
Die Ressourcen-ID der zu ladenden Symbolleiste.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Weitere Informationen zum Erstellen einer Symbolleisten Ressource finden Sie unter Symbolleisten- [Editor](../../windows/toolbar-editor.md) in.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CToolBar::](#createex)up-Ex.

##  <a name="setbitmap"></a>CToolBar:: SetBitmap

Mit dieser Member-Funktion wird das Bitmap-Bild für die Symbolleiste festgelegt.

```
BOOL SetBitmap(HBITMAP hbmImageWell);
```

### <a name="parameters"></a>Parameter

*hbmImageWell*<br/>
Handle eines Bitmap-Bilds, das einer Symbolleiste zugeordnet ist.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Beispielsweise wird aufgerufen `SetBitmap` , um das Bitmap-Bild zu ändern, nachdem der Benutzer eine Aktion für ein Dokument durchführt, das die Aktion einer Schaltfläche ändert.

##  <a name="setbuttoninfo"></a>CToolBar:: SetButtonInfo

Mit dieser Member-Funktion können Sie die Befehls-ID, den Stil und die Bildnummer der Schaltfläche festlegen.

```
void SetButtonInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int iImage);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
NULL basierter Index der Schaltfläche oder des Trenn Zeichens, für das Informationen festgelegt werden sollen.

*nID*<br/>
Der Wert, auf den die Befehls-ID der Schaltfläche festgelegt wird.

*nStyle*<br/>
Der neue Schaltflächen Stil. Die folgenden Schaltflächen Stile werden unterstützt:

- TBBS_BUTTON Standard-PUSHBUTTON (Standard)

- TBBS_SEPARATOR-Trennzeichen

- TBBS_CHECKBOX Schaltfläche "automatisch aktivieren"

- TBBS_GROUP markiert den Anfang einer Gruppe von Schaltflächen.

- TBBS_CHECKGROUP markiert den Anfang einer Gruppe von Kontrollkästchen-Schaltflächen.

- TBBS_DROPDOWN erstellt eine Dropdown Listen Schaltfläche.

- TBBS_AUTOSIZE die Breite der Schaltfläche wird basierend auf dem Text der Schaltfläche berechnet, nicht mit der Größe des Bilds.

- TBBS_NOPREFIX dem Schaltflächen Text wird kein Zugriffstasten Präfix zugeordnet.

*iImage*<br/>
Neuer Index für das Bild der Schaltfläche innerhalb der Bitmap.

### <a name="remarks"></a>Hinweise

Für Trennzeichen, die den Stil TBBS_SEPARATOR haben, legt diese Funktion die Breite des Trenn Zeichens in Pixel auf den in *iImage*gespeicherten Wert fest.

> [!NOTE]
>  Sie können auch die Schaltflächen Zustände mithilfe des *nstyle* -Parameters festlegen. Da Schaltflächen Status jedoch vom [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) -Handler gesteuert werden, gehen alle Zustände, die `SetButtonInfo` Sie mithilfe von festlegen, während der nächsten Leerlauf Verarbeitung verloren. Weitere Informationen finden [Sie unter Aktualisieren von Benutzeroberflächen Objekten](../../mfc/how-to-update-user-interface-objects.md) und [TN031: Steuer leisten](../../mfc/tn031-control-bars.md) , um weitere Informationen zu finden.

Informationen zu Bitmap-Bildern und-Schaltflächen finden Sie unter Übersicht über [CToolBar](../../mfc/reference/ctoolbar-class.md) und [CToolBar:: LoadBitmap](#loadbitmap).

##  <a name="setbuttons"></a>CToolBar:: SetButtons

Diese Member-Funktion legt die Befehls-ID jeder Symbolleisten-Schaltfläche auf den Wert fest, der durch das entsprechende Element des Arrays *lpidarray*angegeben wird.

```
BOOL SetButtons(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parameter

*lpIDArray*<br/>
Zeiger auf ein Array von Befehls-IDs. Der Wert kann NULL sein, um leere Schaltflächen zuzuordnen.

*nIDCount*<br/>
Anzahl der Elemente im Array, auf die von *lpidarray*verwiesen wird.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Wenn ein Element des Arrays den Wert ID_SEPARATOR aufweist, wird ein Trennzeichen an der entsprechenden Position der Symbolleiste erstellt. Mit dieser Funktion wird auch der Stil der einzelnen Schaltflächen auf TBBS_BUTTON und der Stil jedes Trenn Zeichens auf TBBS_SEPARATOR festgelegt, und jeder Schaltfläche wird ein Bild Index zugewiesen. Der Bildindex gibt die Position des Bild der Schaltfläche innerhalb der Bitmap an.

Es ist nicht erforderlich, Trennzeichen in der Bitmap zu berücksichtigen, da diese Funktion keine Bild Indizes für Trennzeichen zuweist. Wenn die Symbolleiste über Schaltflächen an den Positionen 0, 1 und 3 und ein Trennzeichen an Position 2 verfügt, werden die Bilder an den Positionen 0, 1 und 2 in der Bitmap den Schaltflächen an den Positionen 0, 1 bzw. 3 zugewiesen.

Wenn *lpidarray* den Wert NULL hat, ordnet diese Funktion Platz für die Anzahl von Elementen zu, die von *nidcount*angegeben werden. Verwenden Sie [SetButtonInfo](#setbuttoninfo) , um die Attribute jedes Elements festzulegen.

##  <a name="setbuttonstyle"></a>CToolBar:: setbuttonstyle

Mit dieser Member-Funktion können Sie den Stil einer Schaltfläche oder eines Trenn Zeichens festlegen oder Schaltflächen gruppieren.

```
void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index der Schaltfläche oder des Trenn Zeichens, dessen Informationen festgelegt werden sollen.

*nStyle*<br/>
Der Stil der Schaltfläche. Die folgenden Schaltflächen Stile werden unterstützt:

- TBBS_BUTTON Standard-PUSHBUTTON (Standard)

- TBBS_SEPARATOR-Trennzeichen

- TBBS_CHECKBOX Schaltfläche "automatisch aktivieren"

- TBBS_GROUP markiert den Anfang einer Gruppe von Schaltflächen.

- TBBS_CHECKGROUP markiert den Anfang einer Gruppe von Kontrollkästchen-Schaltflächen.

- TBBS_DROPDOWN erstellt eine Dropdown Listen Schaltfläche.

- TBBS_AUTOSIZE die Breite der Schaltfläche wird basierend auf dem Text der Schaltfläche berechnet, nicht auf der Größe des Bilds.

- TBBS_NOPREFIX dem Schaltflächen Text wird kein Zugriffstasten Präfix zugeordnet.

### <a name="remarks"></a>Hinweise

Der Stil einer Schaltfläche bestimmt, wie die Schaltfläche angezeigt wird und wie Sie auf Benutzereingaben reagiert.

Rufen Sie `SetButtonStyle`vor dem Aufrufen der [GetButtonStyle](#getbuttonstyle) -Element Funktion auf, um die Schaltfläche oder den Trenn Zeichenstil abzurufen.

> [!NOTE]
>  Sie können auch die Schaltflächen Zustände mithilfe des *nstyle* -Parameters festlegen. Da Schaltflächen Status jedoch vom [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) -Handler gesteuert werden, gehen alle Zustände, die `SetButtonStyle` Sie mithilfe von festlegen, während der nächsten Leerlauf Verarbeitung verloren. Weitere Informationen finden [Sie unter Aktualisieren von Benutzeroberflächen Objekten](../../mfc/how-to-update-user-interface-objects.md) und [TN031: Steuer leisten](../../mfc/tn031-control-bars.md) , um weitere Informationen zu finden.

##  <a name="setbuttontext"></a>CToolBar:: SetButtonText

Mit dieser Funktion können Sie den Text auf einer Schaltfläche festlegen.

```
BOOL SetButtonText(
    int nIndex,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index der Schaltfläche, deren Text festgelegt werden soll.

*lpszText*<br/>
Zeigt auf den Text, der auf einer Schaltfläche festgelegt werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CToolBar:: GetToolBarCtrl](#gettoolbarctrl).

##  <a name="setheight"></a>CToolBar:: Ort

Diese Member-Funktion legt die Höhe der Symbolleiste auf den in *cyheight*angegebenen Wert in Pixel fest.

```
void SetHeight(int cyHeight);
```

### <a name="parameters"></a>Parameter

*cyheight*<br/>
Die Höhe der Symbolleiste in Pixel.

### <a name="remarks"></a>Hinweise

Verwenden Sie nach dem Aufrufen von [setSizes](#setsizes)diese Member-Funktion, um die Standard Symbolleisten Höhe zu überschreiben. Wenn die Höhe zu klein ist, werden die Schaltflächen unten abgeschnitten.

Wenn diese Funktion nicht aufgerufen wird, verwendet das Framework die Größe der Schaltfläche, um die Höhe der Symbolleiste zu bestimmen.

##  <a name="setsizes"></a>CToolBar:: setSizes

Diese Member-Funktion wird aufgerufen, um die Schaltflächen der Symbolleiste auf die in *sizeButton*angegebene Größe in Pixel festzulegen.

```
void SetSizes(
    SIZE sizeButton,
    SIZE sizeImage);
```

### <a name="parameters"></a>Parameter

*sizeButton*<br/>
Die Größe der einzelnen Schaltflächen in Pixel.

*sizeImage*<br/>
Die Größe jedes Bilds in Pixel.

### <a name="remarks"></a>Hinweise

Der *sizeimage* -Parameter muss die Größe der Bilder in der Bitmap der Symbolleiste in Pixel enthalten. Die Dimensionen in *sizeButton* müssen ausreichend sein, um das Bild plus 7 Pixel zusätzlich in der Breite und 6 Pixel zusätzliche Höhe zu halten. Diese Funktion legt auch die Höhe der Symbolleiste auf die Schaltflächen fest.

Diese Member-Funktion wird nur für Symbolleisten aufgerufen, die nicht den *Richtlinien der Windows-Benutzeroberfläche für Software Entwurfs* Empfehlungen für Schaltflächen-und Bildgrößen folgen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel DOCKTOOL](../../overview/visual-cpp-samples.md)<br/>
[CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl-Klasse](../../mfc/reference/ctoolbarctrl-class.md)<br/>
[CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)
