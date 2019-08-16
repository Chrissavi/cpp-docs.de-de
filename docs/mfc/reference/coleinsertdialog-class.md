---
title: Coleingesertdialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
helpviewer_keywords:
- COleInsertDialog [MFC], COleInsertDialog
- COleInsertDialog [MFC], CreateItem
- COleInsertDialog [MFC], DoModal
- COleInsertDialog [MFC], GetClassID
- COleInsertDialog [MFC], GetDrawAspect
- COleInsertDialog [MFC], GetIconicMetafile
- COleInsertDialog [MFC], GetPathName
- COleInsertDialog [MFC], GetSelectionType
- COleInsertDialog [MFC], m_io
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
ms.openlocfilehash: a884f946b60be0567f39477f434db8efe041e393
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503931"
---
# <a name="coleinsertdialog-class"></a>Coleingesertdialog-Klasse

Wird für das OLE-Dialogfeld "Objekt einfügen" verwendet.

## <a name="syntax"></a>Syntax

```
class COleInsertDialog : public COleDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|Erstellt ein `COleInsertDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleInsertDialog::CreateItem](#createitem)|Erstellt das Element, das im Dialogfeld ausgewählt ist.|
|[COleInsertDialog::DoModal](#domodal)|Zeigt das OLE-Dialogfeld "Objekt einfügen" an.|
|[COleInsertDialog::GetClassID](#getclassid)|Ruft die CLSID ab, die dem ausgewählten Element zugeordnet ist.|
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|Gibt an, ob das Element als Symbol gezeichnet werden soll.|
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle für die Metadatei ab, die der ikonischen Form dieses Elements zugeordnet ist.|
|[COleInsertDialog::GetPathName](#getpathname)|Ruft den vollständigen Pfad zur Datei ab, die im Dialogfeld ausgewählt wird.|
|[COleInsertDialog::GetSelectionType](#getselectiontype)|Ruft den ausgewählten Objekttyp ab.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleInsertDialog::m_io](#m_io)|Eine Struktur vom Typ oleuiinsertobject zum Steuern des Verhaltens des Dialog Felds.|

## <a name="remarks"></a>Hinweise

Erstellen Sie ein Objekt der `COleInsertDialog` -Klasse, wenn Sie dieses Dialogfeld aufzurufen. Nachdem ein `COleInsertDialog` -Objekt erstellt wurde, können Sie die [m_io](#m_io) -Struktur verwenden, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die `m_io` Struktur ist vom Typ oleuiinsertobject. Weitere Informationen zum Verwenden dieser Dialogfeld Klasse finden Sie unter der [DoModal](#domodal) -Member-Funktion.

> [!NOTE]
>  Vom Anwendungs-Assistenten generierter Container Code verwendet diese Klasse.

Weitere Informationen finden Sie in der [oleuiinsertobject](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw) -Struktur in der Windows SDK.

Weitere Informationen zu OLE-spezifischen Dialogfeldern finden Sie in den Artikel [Dialogfeldern in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleInsertDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs. h

##  <a name="coleinsertdialog"></a>Coleingesertdialog:: colansertdialog

Diese Funktion erstellt nur ein `COleInsertDialog` -Objekt.

```
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Erstellungs Kennzeichen, das eine beliebige Anzahl der folgenden Werte enthält, die mit dem bitweisen OR-Operator kombiniert werden sollen:

- IOF_SHOWHELP gibt an, dass die Schaltfläche Hilfe angezeigt wird, wenn das Dialogfeld aufgerufen wird.

- IOF_SELECTCREATENEW gibt an, dass das Optionsfeld neu erstellen zunächst ausgewählt wird, wenn das Dialogfeld aufgerufen wird. Dies ist die Standardeinstellung und kann nicht mit IOF_SELECTCREATEFROMFILE verwendet werden.

- IOF_SELECTCREATEFROMFILE gibt an, dass das Optionsfeld aus Datei erstellen zuerst ausgewählt wird, wenn das Dialogfeld aufgerufen wird. Kann nicht mit IOF_SELECTCREATENEW verwendet werden.

- IOF_CHECKLINK gibt an, dass das Kontrollkästchen Link zunächst überprüft wird, wenn das Dialogfeld aufgerufen wird.

- IOF_DISABLELINK gibt an, dass das Kontrollkästchen Link deaktiviert wird, wenn das Dialogfeld aufgerufen wird.

- IOF_CHECKDISPLAYASICON gibt an, dass das Kontrollkästchen als Symbol anzeigen anfänglich überprüft wird, das aktuelle Symbol angezeigt wird und die Schaltfläche zum Ändern des Symbols aktiviert wird, wenn das Dialogfeld aufgerufen wird.

- IOF_VERIFYSERVERSEXIST gibt an, dass das Dialogfeld die dem Listenfeld hinzu zufügenden Klassen überprüfen soll, indem sichergestellt wird, dass die in der Registrierungsdatenbank angegebenen Server vorhanden sind, bevor das Dialogfeld angezeigt wird. Durch Festlegen dieses Flags kann die Leistung erheblich beeinträchtigt werden.

*pParentWnd*<br/>
Zeigt auf das übergeordnete oder Besitzer Fenster Objekt (vom `CWnd`Typ), zu dem das Dialog Objekt gehört. Wenn er NULL ist, wird das übergeordnete Fenster des Dialog Objekts auf das Hauptanwendungsfenster festgelegt.

### <a name="remarks"></a>Hinweise

Um das Dialogfeld anzuzeigen, müssen Sie die Funktion [DoModal](#domodal) aufrufen.

##  <a name="createitem"></a>Coleingesertdialog:: anateitem

Rufen Sie diese Funktion auf, um ein Objekt vom Typ [COleClientItem](../../mfc/reference/coleclientitem-class.md) nur dann zu erstellen, wenn [DoModal](#domodal) IDOK zurückgibt.

```
BOOL CreateItem(COleClientItem* pItem);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Verweist auf das Element, das erstellt werden soll.

### <a name="return-value"></a>Rückgabewert

Nicht NULL, wenn Element erstellt wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Sie müssen das `COleClientItem` -Objekt zuordnen, bevor Sie diese Funktion abrufen können.

##  <a name="domodal"></a>Colansertdialog::D omodal

Mit dieser Funktion wird das OLE-Dialogfeld "Objekt einfügen" angezeigt.

```
virtual INT_PTR
    DoModal();

INT_PTR
    DoModal(DWORD  dwFlags);
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Einer der folgenden Werte:

`COleInsertDialog::DocObjectsOnly`Fügt nur docobjects ein.

`COleInsertDialog::ControlsOnly`Fügt nur ActiveX-Steuerelemente ein.

NULL fügt weder ein DocObject-noch ein ActiveX-Steuerelement ein. Dieser Wert ergibt dieselbe Implementierung wie der erste oben aufgeführte Prototyp.

### <a name="return-value"></a>Rückgabewert

Abschluss Status für das Dialogfeld. Einer der folgenden Werte:

- IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.

- IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.

- Idabort, wenn ein Fehler aufgetreten ist. Wenn idabort zurückgegeben wird, können Sie die Member-Funktion [COleDialog:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) aufrufen, um weitere Informationen zum aufgetretenen Fehlertyp abzurufen. Eine Auflistung möglicher Fehler finden Sie unter der [oleuiinsertobject](/windows/win32/api/oledlg/nf-oledlg-oleuiinsertobjectw) -Funktion in der Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Dialogfeld-Steuerelemente durch Festlegen der Member der [m_io](#m_io) -Struktur initialisieren möchten, sollten Sie dies vor `DoModal`dem Aufrufen von tun, nachdem das Dialogfeld Objekt erstellt wurde.

Wenn `DoModal` IDOK zurückgibt, können Sie andere Element Funktionen aufrufen, um die Einstellungen oder Informationen einzugeben, die vom Benutzer in das Dialogfeld eingegeben werden.

##  <a name="getclassid"></a>COleInsertDialog:: GetClassID

Mit dieser Funktion wird die CLSID, die dem ausgewählten Element zugeordnet ist, nur dann aufgerufen, wenn [DoModal](#domodal) IDOK zurück `COleInsertDialog::createNewItem`gibt und der Auswahltyp ist.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die CLSID zurück, die dem ausgewählten Element zugeordnet ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [CLSID-Schlüssel](/windows/win32/com/clsid-key-hklm) in der Windows SDK.

##  <a name="getdrawaspect"></a>Coleingesertdialog:: getdrawaspect

Diese Funktion aufrufen, um zu bestimmen, ob der Benutzer das ausgewählte Element als Symbol anzeigt.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Rückgabewert

Die Methode, die zum Rendering des-Objekts erforderlich ist.

- DVASPECT_CONTENT wird zurückgegeben, wenn das Kontrollkästchen als Symbol anzeigen nicht aktiviert wurde.

- DVASPECT_ICON wird zurückgegeben, wenn das Kontrollkästchen als Symbol anzeigen aktiviert wurde.

### <a name="remarks"></a>Hinweise

Diese Funktion wird nur aufgerufen, wenn die [Domäne](#domodal) IDOK zurückgibt.

Weitere Informationen zum Zeichnen-Aspekt finden Sie unter [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) Data Structure in the Windows SDK.

##  <a name="geticonicmetafile"></a>COleInsertDialog:: getikonicmetafile

Mit dieser Funktion können Sie ein Handle für die Metadatei abrufen, die den ikonischen Aspekt des ausgewählten Elements enthält.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Rückgabewert

Das Handle für die Metadatei, das den ikonischen Aspekt des ausgewählten Elements enthält, wenn das Kontrollkästchen als Symbol anzeigen beim Verwerfen des Dialog Felds aktiviert wurde, indem Sie auf **OK**klicken. andernfalls NULL.

##  <a name="getpathname"></a>COleInsertDialog:: getPathname

Mit dieser Funktion können Sie den vollständigen Pfad der ausgewählten Datei nur abrufen, wenn die [Domäne](#domodal) IDOK und der Auswahltyp nicht `COleInsertDialog::createNewItem`zurückgibt.

```
CString GetPathName() const;
```

### <a name="return-value"></a>Rückgabewert

Der vollständige Pfad zu der Datei, die im Dialogfeld ausgewählt ist. Wenn der Auswahltyp `createNewItem`ist, gibt diese Funktion ein `CString` bedeutungsloses im Releasemodus zurück oder verursacht eine-Assertion im Debugmodus.

##  <a name="getselectiontype"></a>COleInsertDialog:: GetSelectionType

Mit dieser Funktion können Sie den ausgewählten wählungstyp abrufen, wenn das Dialogfeld Objekt einfügen geschlossen wurde, indem Sie auf **OK klicken**.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Rückgabewert

Der Typ der Auswahl.

### <a name="remarks"></a>Hinweise

Die Rückgabetyp Werte werden durch `Selection` den Enumerationstyp angegeben `COleInsertDialog` , der in der-Klasse deklariert ist.

```
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };
```

Im folgenden finden Sie eine kurze Beschreibung dieser Werte:

- `COleInsertDialog::createNewItem`Das Optionsfeld Create New wurde ausgewählt.

- `COleInsertDialog::insertFromFile`Das Optionsfeld aus Datei erstellen wurde ausgewählt, und das Kontrollkästchen Link wurde nicht aktiviert.

- `COleInsertDialog::linkToFile`Das Optionsfeld aus Datei erstellen wurde ausgewählt, und das Kontrollkästchen Link wurde aktiviert.

##  <a name="m_io"></a>Colansertdialog:: m_io

Struktur vom Typ "oleuiinsertobject", die zum Steuern des Verhaltens des Dialog Felds "Objekt einfügen" verwendet wird.

```
OLEUIINSERTOBJECT m_io;
```

### <a name="remarks"></a>Hinweise

Member dieser Struktur können entweder direkt oder über Element Funktionen geändert werden.

Weitere Informationen finden Sie in der [oleuiinsertobject](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw) -Struktur in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
