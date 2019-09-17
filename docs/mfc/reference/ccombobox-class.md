---
title: CComboBox-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComboBox
- AFXWIN/CComboBox
- AFXWIN/CComboBox::CComboBox
- AFXWIN/CComboBox::AddString
- AFXWIN/CComboBox::Clear
- AFXWIN/CComboBox::CompareItem
- AFXWIN/CComboBox::Copy
- AFXWIN/CComboBox::Create
- AFXWIN/CComboBox::Cut
- AFXWIN/CComboBox::DeleteItem
- AFXWIN/CComboBox::DeleteString
- AFXWIN/CComboBox::Dir
- AFXWIN/CComboBox::DrawItem
- AFXWIN/CComboBox::FindString
- AFXWIN/CComboBox::FindStringExact
- AFXWIN/CComboBox::GetComboBoxInfo
- AFXWIN/CComboBox::GetCount
- AFXWIN/CComboBox::GetCueBanner
- AFXWIN/CComboBox::GetCurSel
- AFXWIN/CComboBox::GetDroppedControlRect
- AFXWIN/CComboBox::GetDroppedState
- AFXWIN/CComboBox::GetDroppedWidth
- AFXWIN/CComboBox::GetEditSel
- AFXWIN/CComboBox::GetExtendedUI
- AFXWIN/CComboBox::GetHorizontalExtent
- AFXWIN/CComboBox::GetItemData
- AFXWIN/CComboBox::GetItemDataPtr
- AFXWIN/CComboBox::GetItemHeight
- AFXWIN/CComboBox::GetLBText
- AFXWIN/CComboBox::GetLBTextLen
- AFXWIN/CComboBox::GetLocale
- AFXWIN/CComboBox::GetMinVisible
- AFXWIN/CComboBox::GetTopIndex
- AFXWIN/CComboBox::InitStorage
- AFXWIN/CComboBox::InsertString
- AFXWIN/CComboBox::LimitText
- AFXWIN/CComboBox::MeasureItem
- AFXWIN/CComboBox::Paste
- AFXWIN/CComboBox::ResetContent
- AFXWIN/CComboBox::SelectString
- AFXWIN/CComboBox::SetCueBanner
- AFXWIN/CComboBox::SetCurSel
- AFXWIN/CComboBox::SetDroppedWidth
- AFXWIN/CComboBox::SetEditSel
- AFXWIN/CComboBox::SetExtendedUI
- AFXWIN/CComboBox::SetHorizontalExtent
- AFXWIN/CComboBox::SetItemData
- AFXWIN/CComboBox::SetItemDataPtr
- AFXWIN/CComboBox::SetItemHeight
- AFXWIN/CComboBox::SetLocale
- AFXWIN/CComboBox::SetMinVisibleItems
- AFXWIN/CComboBox::SetTopIndex
- AFXWIN/CComboBox::ShowDropDown
helpviewer_keywords:
- CComboBox [MFC], CComboBox
- CComboBox [MFC], AddString
- CComboBox [MFC], Clear
- CComboBox [MFC], CompareItem
- CComboBox [MFC], Copy
- CComboBox [MFC], Create
- CComboBox [MFC], Cut
- CComboBox [MFC], DeleteItem
- CComboBox [MFC], DeleteString
- CComboBox [MFC], Dir
- CComboBox [MFC], DrawItem
- CComboBox [MFC], FindString
- CComboBox [MFC], FindStringExact
- CComboBox [MFC], GetComboBoxInfo
- CComboBox [MFC], GetCount
- CComboBox [MFC], GetCueBanner
- CComboBox [MFC], GetCurSel
- CComboBox [MFC], GetDroppedControlRect
- CComboBox [MFC], GetDroppedState
- CComboBox [MFC], GetDroppedWidth
- CComboBox [MFC], GetEditSel
- CComboBox [MFC], GetExtendedUI
- CComboBox [MFC], GetHorizontalExtent
- CComboBox [MFC], GetItemData
- CComboBox [MFC], GetItemDataPtr
- CComboBox [MFC], GetItemHeight
- CComboBox [MFC], GetLBText
- CComboBox [MFC], GetLBTextLen
- CComboBox [MFC], GetLocale
- CComboBox [MFC], GetMinVisible
- CComboBox [MFC], GetTopIndex
- CComboBox [MFC], InitStorage
- CComboBox [MFC], InsertString
- CComboBox [MFC], LimitText
- CComboBox [MFC], MeasureItem
- CComboBox [MFC], Paste
- CComboBox [MFC], ResetContent
- CComboBox [MFC], SelectString
- CComboBox [MFC], SetCueBanner
- CComboBox [MFC], SetCurSel
- CComboBox [MFC], SetDroppedWidth
- CComboBox [MFC], SetEditSel
- CComboBox [MFC], SetExtendedUI
- CComboBox [MFC], SetHorizontalExtent
- CComboBox [MFC], SetItemData
- CComboBox [MFC], SetItemDataPtr
- CComboBox [MFC], SetItemHeight
- CComboBox [MFC], SetLocale
- CComboBox [MFC], SetMinVisibleItems
- CComboBox [MFC], SetTopIndex
- CComboBox [MFC], ShowDropDown
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
ms.openlocfilehash: b54a1913073ca0b23aeb17a57b16f589a074637b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507190"
---
# <a name="ccombobox-class"></a>CComboBox-Klasse

Stellt die Funktionalität eines Windows-Kombinationsfelds bereit.

## <a name="syntax"></a>Syntax

```
class CComboBox : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComboBox::CComboBox](#ccombobox)|Erstellt ein `CComboBox`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComboBox:: AddString](#addstring)|Fügt eine Zeichenfolge am Ende der Liste im Listenfeld eines Kombinations Felds oder an der sortierten Position für Listenfelder mit dem CBS_SORT-Stil hinzu.|
|[CComboBox::Clear](#clear)|Löscht (löscht) die aktuelle Auswahl, sofern vorhanden, im Bearbeitungs Steuerelement.|
|[CComboBox::CompareItem](#compareitem)|Wird von Framework aufgerufen, um die relative Position eines neuen Listen Elements in einem sortierten, vom Besitzer gezeichneten Kombinations Feld zu bestimmen.|
|[CComboBox::Copy](#copy)|Kopiert die aktuelle Auswahl, sofern vorhanden, im CF_TEXT-Format in die Zwischenablage.|
|[CComboBox::Create](#create)|Erstellt das Kombinations Feld und fügt es an das `CComboBox` -Objekt an.|
|[CComboBox::Cut](#cut)|Löscht (schneidet) die aktuelle Auswahl im Bearbeitungs Steuerelement, sofern vorhanden, und kopiert den gelöschten Text im CF_TEXT-Format in die Zwischenablage.|
|[CComboBox::DeleteItem](#deleteitem)|Wird von Framework aufgerufen, wenn ein Listenelement aus einem vom Besitzer gezeichneten Kombinations Feld gelöscht wird.|
|[CComboBox::DeleteString](#deletestring)|Löscht eine Zeichenfolge aus dem Listenfeld eines Kombinations Felds.|
|[CComboBox::Dir](#dir)|Fügt dem Listenfeld eines Kombinations Felds eine Liste von Dateinamen hinzu.|
|[CComboBox::DrawItem](#drawitem)|Wird von Framework aufgerufen, wenn sich ein visueller Aspekt eines von einem Besitzer gezeichneten Kombinations Felds ändert.|
|[CComboBox::FindString](#findstring)|Sucht die erste Zeichenfolge, die das angegebene Präfix enthält, im Listenfeld eines Kombinations Felds.|
|[CComboBox::FindStringExact](#findstringexact)|Sucht die erste Listenfeld Zeichenfolge (in einem Kombinations Feld), die der angegebenen Zeichenfolge entspricht.|
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|Ruft Informationen über das `CComboBox` Objekt ab.|
|[CComboBox::GetCount](#getcount)|Ruft die Anzahl der Elemente im Listenfeld eines Kombinations Felds ab.|
|[CComboBox::GetCueBanner](#getcuebanner)|Ruft den Hinweis Text ab, der für ein Kombinations Feld-Steuerelement angezeigt wird.|
|[CComboBox::GetCurSel](#getcursel)|Ruft den Index des derzeit ausgewählten Elements (sofern vorhanden) im Listenfeld eines Kombinations Felds ab.|
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|Ruft die Bildschirm Koordinaten des sichtbaren (Dropdown-) Listen Felds eines Dropdown-Kombinations Felds ab.|
|[CComboBox::GetDroppedState](#getdroppedstate)|Bestimmt, ob das Listenfeld eines Dropdown-Kombinations Felds sichtbar (abgelegt) ist.|
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|Ruft die minimale zulässige Breite für den Dropdown-Listenfeld Teil eines Kombinations Felds ab.|
|[CComboBox::GetEditSel](#geteditsel)|Ruft die Position des Anfangs-und des Endzeichens der aktuellen Auswahl im Bearbeitungs Steuerelement eines Kombinations Felds ab.|
|[CComboBox::GetExtendedUI](#getextendedui)|Bestimmt, ob ein Kombinations Feld über die Standardbenutzer Oberfläche oder die erweiterte Benutzeroberfläche verfügt.|
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|Gibt die Breite in Pixel zurück, in der der Listenfeld Bereich des Kombinations Felds horizontal gescrollt werden kann.|
|[CComboBox::GetItemData](#getitemdata)|Ruft den von der Anwendung bereitgestellten 32-Bit-Wert ab, der dem angegebenen Kombinations Feld Element zugeordnet ist.|
|[CComboBox::GetItemDataPtr](#getitemdataptr)|Ruft den von der Anwendung bereitgestellten 32-Bit-Zeiger ab, der dem angegebenen Kombinations Feld Element zugeordnet ist.|
|[CComboBox::GetItemHeight](#getitemheight)|Ruft die Höhe der Listenelemente in einem Kombinations Feld ab.|
|[CComboBox::GetLBText](#getlbtext)|Ruft eine Zeichenfolge aus dem Listenfeld eines Kombinations Felds ab.|
|[CComboBox::GetLBTextLen](#getlbtextlen)|Ruft die Länge einer Zeichenfolge im Listenfeld eines Kombinations Felds ab.|
|[CComboBox::GetLocale](#getlocale)|Ruft den Gebiets Schema Bezeichner für ein Kombinations Feld ab.|
|[CComboBox::GetMinVisible](#getminvisible)|Ruft die Mindestanzahl sichtbarer Elemente in der Dropdown Liste des aktuellen Kombinations Felds ab.|
|[CComboBox::GetTopIndex](#gettopindex)|Gibt den Index des ersten sichtbaren Elements im Listenfeld Bereich des Kombinations Felds zurück.|
|[CComboBox::InitStorage](#initstorage)|Ordnet Speicherblöcke für Elemente und Zeichen folgen im Listenfeld Bereich des Kombinations Felds vorab zu.|
|[CComboBox::InsertString](#insertstring)|Fügt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds ein.|
|[CComboBox::LimitText](#limittext)|Schränkt die Länge des Texts ein, den der Benutzer in das Bearbeitungs Steuerelement eines Kombinations Felds eingeben kann.|
|[CComboBox::MeasureItem](#measureitem)|Wird von Framework aufgerufen, um Kombinations Feld Dimensionen zu bestimmen, wenn ein vom Besitzer gezeichnetes Kombinations Feld erstellt wird.|
|[CComboBox::Paste](#paste)|Fügt die Daten aus der Zwischenablage an der aktuellen Cursorposition in das Bearbeitungs Steuerelement ein. Daten werden nur eingefügt, wenn die Zwischenablage Daten im CF_TEXT-Format enthält.|
|[CComboBox::ResetContent](#resetcontent)|Entfernt alle Elemente aus dem Listenfeld und bearbeitet das Steuerelement eines Kombinations Felds.|
|[CComboBox::SelectString](#selectstring)|Sucht im Listenfeld eines Kombinations Felds nach einer Zeichenfolge, und wenn die Zeichenfolge gefunden wird, wählt die Zeichenfolge im Listenfeld aus und kopiert die Zeichenfolge in das Bearbeitungs Steuerelement.|
|[CComboBox::SetCueBanner](#setcuebanner)|Legt den Hinweis Text fest, der für ein Kombinations Feld-Steuerelement angezeigt wird.|
|[CComboBox::SetCurSel](#setcursel)|Wählt eine Zeichenfolge im Listenfeld eines Kombinations Felds aus.|
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|Legt die minimale zulässige Breite für den Dropdown-Listenfeld Teil eines Kombinations Felds fest.|
|[CComboBox::SetEditSel](#seteditsel)|Wählt Zeichen im Bearbeitungs Steuerelement eines Kombinations Felds aus.|
|[CComboBox::SetExtendedUI](#setextendedui)|Wählt entweder die Standardbenutzer Oberfläche oder die erweiterte Benutzeroberfläche für ein Kombinations Feld mit dem CBS_DROPDOWN-oder CBS_DROPDOWNLIST-Format aus.|
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|Legt die Breite in Pixel fest, in der der Listenfeld Bereich des Kombinations Felds horizontal gescrollt werden kann.|
|[CComboBox::SetItemData](#setitemdata)|Legt den 32-Bit-Wert fest, der dem angegebenen Element in einem Kombinations Feld zugeordnet ist.|
|[CComboBox::SetItemDataPtr](#setitemdataptr)|Legt den 32-Bit-Zeiger fest, der dem angegebenen Element in einem Kombinations Feld zugeordnet ist.|
|[CComboBox::SetItemHeight](#setitemheight)|Legt die Höhe von Listenelementen in einem Kombinations Feld oder die Höhe des Bearbeitungs Steuer Elements (oder statischer Text) eines Kombinations Felds fest.|
|[CComboBox::SetLocale](#setlocale)|Legt den Gebiets Schema Bezeichner für ein Kombinations Feld fest.|
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|Legt die Mindestanzahl sichtbarer Elemente in der Dropdown Liste des aktuellen Kombinations Felds fest.|
|[CComboBox::SetTopIndex](#settopindex)|Weist den Listenfeld Bereich des Kombinations Felds an, das Element mit dem angegebenen Index im oberen Bereich anzuzeigen.|
|[CComboBox::ShowDropDown](#showdropdown)|Blendet das Listenfeld eines Kombinations Felds mit dem Format CBS_DROPDOWN oder CBS_DROPDOWNLIST ein oder aus.|

## <a name="remarks"></a>Hinweise

Ein Kombinations Feld besteht aus einem Listenfeld, das entweder mit einem statischen Steuerelement oder einem Bearbeitungs Steuerelement kombiniert wird. Der Listenfeld Bereich des Steuer Elements kann jederzeit angezeigt werden, oder er wird nur angezeigt, wenn der Benutzer den Dropdown Pfeil neben dem Steuerelement auswählt.

Das aktuell ausgewählte Element (sofern vorhanden) im Listenfeld wird im Steuerelement "statisch" oder "Bearbeiten" angezeigt. Wenn das Kombinations Feld das Dropdown-Listenformat aufweist, kann der Benutzer außerdem das erste Zeichen eines der Elemente in der Liste eingeben, und im Listenfeld wird das nächste Element mit dem ersten Zeichen hervorgehoben.

In der folgenden Tabelle werden die drei Kombinations Feld [Stile](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)verglichen.

|Stil|Wenn das Listenfeld ist sichtbar ist|Static-oder Edit-Steuerelement|
|-----------|-------------------------------|-----------------------------|
|Einfach|Always|Bearbeiten|
|Drop-down|Beim Ablegen|Bearbeiten|
|Dropdownliste|Beim Ablegen|Statisch|

Sie können ein `CComboBox` -Objekt entweder aus einer Dialogfeld Vorlage oder direkt im Code erstellen. Rufen Sie in beiden Fällen zuerst den Konstruktor `CComboBox` auf, um `CComboBox` das Objekt zu erstellen, und rufen Sie dann die [Create](#create) Member-Funktion auf, um `CComboBox` das Steuerelement zu erstellen und es an das Objekt anzufügen

Wenn Sie die von einem Kombinations Feld gesendeten Windows-Benachrichtigungs Meldungen an das übergeordnete Element (in der `CDialog`Regel eine von abgeleitete Klasse) verarbeiten möchten, fügen Sie der übergeordneten Klasse für jede Nachricht einen Message-Map-Eintrag und eine nachrichtenhandlermember-Funktion hinzu.

Jeder Nachrichten Zuordnungs Eintrag hat die folgende Form:

**Bei\_** _Benachrichtigung_ **(** _ID_, _mitgliedungsfxn_ **)**

Dabei gibt die ID des untergeordneten Fensters des Kombinations Feld-Steuer Elements an, das `memberFxn` die Benachrichtigung sendet, und ist der Name der übergeordneten Element Funktion, die Sie zum Verarbeiten der Benachrichtigung geschrieben haben. `id`

Der Prototyp der übergeordneten Funktion ist wie folgt:

**afx_msg** `void` `memberFxn` **( );**

Die Reihenfolge, in der bestimmte Benachrichtigungen gesendet werden, kann nicht vorhergesagt werden. Insbesondere kann eine CBN_SELCHANGE-Benachrichtigung entweder vor oder nach einer CBN_CLOSEUP-Benachrichtigung auftreten.

Mögliche Nachrichten Zuordnungs Einträge sind folgende:

- ON_CBN_CLOSEUP (Windows 3,1 und höher) Das Listenfeld eines Kombinations Felds wurde geschlossen. Diese Benachrichtigungs Meldung wird nicht für ein Kombinations Feld mit dem [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -Format gesendet.

- ON_CBN_DBLCLK der Benutzer doppelklickt auf eine Zeichenfolge im Listenfeld eines Kombinations Felds. Diese Benachrichtigungs Meldung wird nur für ein Kombinations Feld mit dem CBS_SIMPLE-Format gesendet. Ein Kombinations Feld mit dem [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -Stil kann nicht angezeigt werden, da mit einem einzelnen Klick das Listenfeld ausgeblendet wird.

- ON_CBN_DROPDOWN das Listenfeld eines Kombinations Felds wird in der Dropdown Liste angezeigt (sichtbar gemacht). Diese Benachrichtigungs Meldung kann nur für ein Kombinations Feld mit dem Format CBS_DROPDOWN oder CBS_DROPDOWNLIST auftreten.

- ON_CBN_EDITCHANGE der Benutzer hat eine Aktion durchgeführt, die möglicherweise den Text im Bearbeitungs Steuerelement-Teil eines Kombinations Felds geändert hat. Anders als bei der CBN_EDITUPDATE-Nachricht wird diese Nachricht gesendet, nachdem der Bildschirm von Windows aktualisiert wurde. Er wird nicht gesendet, wenn das Kombinations Feld den CBS_DROPDOWNLIST-Stil hat.

- ON_CBN_EDITUPDATE der Bearbeitungs Steuerungsteil eines Kombinations Felds zeigt den geänderten Text an. Diese Benachrichtigung wird gesendet, nachdem das Steuerelement den Text formatiert hat, aber bevor der Text angezeigt wird. Er wird nicht gesendet, wenn das Kombinations Feld den CBS_DROPDOWNLIST-Stil hat.

- ON_CBN_ERRSPACE das Kombinations Feld kann nicht genügend Arbeitsspeicher zuordnen, um eine bestimmte Anforderung zu erfüllen.

- ON_CBN_SELENDCANCEL (Windows 3,1 und höher) Gibt an, dass die Auswahl des Benutzers abgebrochen werden soll. Der Benutzer klickt auf ein Element und klickt dann auf ein anderes Fenster oder Steuerelement, um das Listenfeld eines Kombinations Felds auszublenden. Diese Benachrichtigungs Meldung wird vor der CBN_CLOSEUP-Benachrichtigungs Meldung gesendet, um anzugeben, dass die Auswahl des Benutzers ignoriert werden soll. Die CBN_SELENDCANCEL-oder CBN_SELENDOK-Benachrichtigungs Meldung wird gesendet, auch wenn die CBN_CLOSEUP-Benachrichtigungs Meldung nicht gesendet wird (wie im Fall eines Kombinations Felds mit dem CBS_SIMPLE-Stil).

- ON_CBN_SELENDOK der Benutzer wählt ein Element aus und drückt dann entweder die EINGABETASTE oder klickt auf die nach-unten-Taste, um das Listenfeld eines Kombinations Felds auszublenden. Diese Benachrichtigungs Meldung wird vor der CBN_CLOSEUP-Nachricht gesendet, um anzugeben, dass die Auswahl des Benutzers als gültig betrachtet werden soll. Die CBN_SELENDCANCEL-oder CBN_SELENDOK-Benachrichtigungs Meldung wird gesendet, auch wenn die CBN_CLOSEUP-Benachrichtigungs Meldung nicht gesendet wird (wie im Fall eines Kombinations Felds mit dem CBS_SIMPLE-Stil).

- ON_CBN_KILLFOCUS das Kombinations Feld verliert den Eingabefokus.

- ON_CBN_SELCHANGE die Auswahl im Listenfeld eines Kombinations Felds soll geändert werden, weil der Benutzer entweder auf das Listenfeld klickt oder die Auswahl mithilfe der Pfeiltasten ändert. Bei der Verarbeitung dieser Nachricht kann der Text im Bearbeitungs Steuerelement des Kombinations Felds nur über `GetLBText` oder eine andere ähnliche Funktion abgerufen werden. `GetWindowText`kann nicht verwendet werden.

- ON_CBN_SETFOCUS das Kombinations Feld empfängt den Eingabefokus.

Wenn Sie ein `CComboBox` -Objekt in einem Dialogfeld (über eine Dialogfeld Ressource) erstellen `CComboBox` , wird das Objekt automatisch zerstört, wenn der Benutzer das Dialogfeld schließt.

Wenn Sie ein `CComboBox` -Objekt in ein anderes Fenster Objekt einbetten, müssen Sie es nicht zerstören. Wenn Sie das `CComboBox` Objekt auf dem Stapel erstellen, wird es automatisch zerstört. Wenn Sie das `CComboBox` Objekt auf dem Heap mithilfe der **neuen** Funktion erstellen, müssen Sie **Delete** für das-Objekt erstellen, um es zu zerstören, wenn das Windows-Kombinations Feld zerstört wird.

**Hinweis** Wenn Sie WM_KEYDOWN-und WM_CHAR-Nachrichten verarbeiten möchten, müssen Sie die Steuerelemente für die Bearbeitung und das Listenfeld des Kombinations Felds unter `CEdit` Teilen `CListBox`, Klassen von und ableiten und den abgeleiteten Klassen Handler für diese Nachrichten hinzufügen. Weitere Informationen finden Sie unter [CWnd:: SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CComboBox`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="addstring"></a>CComboBox:: AddString

Fügt eine Zeichenfolge in das Listenfeld eines Kombinations Felds ein.

```
int AddString(LPCTSTR lpszString);
```

### <a name="parameters"></a>Parameter

*lpszString*<br/>
Verweist auf die mit NULL endende Zeichenfolge, die hinzugefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Wenn der Rückgabewert größer als oder gleich 0 ist, ist dies der null basierte Index der Zeichenfolge im Listenfeld. Der Rückgabewert ist CB_ERR, wenn ein Fehler auftritt. der Rückgabewert ist CB_ERRSPACE, wenn nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolge zur Verfügung steht.

### <a name="remarks"></a>Hinweise

Wenn das Listenfeld nicht mit dem Format [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) erstellt wurde, wird die Zeichenfolge am Ende der Liste hinzugefügt. Andernfalls wird die Zeichenfolge in die Liste eingefügt, und die Liste wird sortiert.

> [!NOTE]
>  Diese Funktion wird vom Windows `ComboBoxEx` -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx](/windows/win32/Controls/comboboxex-controls) -Steuerelemente in der Windows SDK.

Um eine Zeichenfolge in eine bestimmte Position in der Liste einzufügen, verwenden Sie die [InsertString](#insertstring) -Member-Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]

##  <a name="ccombobox"></a>CComboBox:: CComboBox

Erstellt ein `CComboBox`-Objekt.

```
CComboBox();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]

##  <a name="clear"></a>CComboBox:: Clear

Löscht (löscht) die aktuelle Auswahl, sofern vorhanden, im Bearbeitungs Steuerelement des Kombinations Felds.

```
void Clear();
```

### <a name="remarks"></a>Hinweise

Um die aktuelle Auswahl zu löschen und den gelöschten Inhalt in die Zwischenablage einzufügen, verwenden Sie die Funktion zum [Ausschneiden](#cut) von Membern.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]

##  <a name="compareitem"></a>CComboBox:: compareitem

Wird von Framework aufgerufen, um die relative Position eines neuen Elements im Listenfeld Abschnitt eines sortierten Besitzers zu bestimmen.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Parameter

*lpCompareItemStruct*<br/>
Ein langer Zeiger auf eine [compareitemstruct](/windows/win32/api/winuser/ns-winuser-compareitemstruct) -Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt die relative Position der beiden in der `COMPAREITEMSTRUCT` -Struktur beschriebenen Elemente an. Dabei kann es sich um einen der folgenden Werte handeln:

|Wert|Bedeutung|
|-----------|-------------|
|- 1|Element 1 wird vor Element 2 sortiert.|
|0|Element 1 und Element 2 Sortieren dasselbe.|
|1|Element 1 sortiert nach Element 2.|

Eine Beschreibung von finden Sie unter `COMPAREITEMSTRUCT` [CWnd:: oncompareitem](../../mfc/reference/cwnd-class.md#oncompareitem) .

### <a name="remarks"></a>Hinweise

Standardmäßig führt diese Member-Funktion keine Aktion aus. Wenn Sie ein Kombinations Feld zum Erstellen eines Besitzers mit dem LBS_SORT-Stil erstellen, müssen Sie diese Element Funktion überschreiben, um dem Framework beim Sortieren von neuen Elementen zu helfen, die dem Listenfeld hinzugefügt werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]

##  <a name="copy"></a>CComboBox:: Copy

Kopiert die aktuelle Auswahl, sofern vorhanden, in das Bearbeitungs Steuerelement des Kombinations Felds in die Zwischenablage im CF_TEXT-Format.

```
void Copy();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]

##  <a name="create"></a>CComboBox:: Create

Erstellt das Kombinations Feld und fügt es an das `CComboBox` -Objekt an.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt den Stil des Kombinations Felds an. Wenden Sie eine beliebige Kombination von Kombinations [Feld Stilen](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) auf das Feld an.

*Rect*<br/>
Zeigt auf die Position und die Größe des Kombinations Felds. Kann eine [Rect-Struktur](/windows/win32/api/windef/ns-windef-rect) oder ein `CRect` -Objekt sein.

*pParentWnd*<br/>
Gibt das übergeordnete Fenster des Kombinations Felds an ( `CDialog`normalerweise ein). Er darf nicht NULL sein.

*nID*<br/>
Gibt die Steuerelement-ID des Kombinations Felds an.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Sie erstellen ein `CComboBox` -Objekt in zwei Schritten. Zuerst wird der-Konstruktor aufgerufen und dann `Create`aufgerufen, wodurch das Windows-Kombinations Feld erstellt und an das `CComboBox` -Objekt angefügt wird.

Wenn `Create` ausgeführt wird, sendet Windows die [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)-, [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)-, [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)-und [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) -Meldungen an das Kombinations Feld.

Diese Nachrichten werden standardmäßig von den Element Funktionen " [onnccreate](../../mfc/reference/cwnd-class.md#onnccreate)", " [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)", " [onnccalcsize](../../mfc/reference/cwnd-class.md#onnccalcsize)" und " [ongetminmaxinfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) " in der `CWnd` Basisklasse verarbeitet. Um die standardmäßige Meldungs Behandlung zu erweitern, leiten `CComboBox`Sie eine Klasse von ab, fügen Sie der neuen Klasse eine Meldungs Zuordnung hinzu, und überschreiben Sie die zuvor genannten nachrichtenhandlerelementfunktionen. Über `OnCreate`schreiben Sie z. b., um die erforderliche Initialisierung für eine neue Klasse auszuführen.

Wenden Sie die folgenden [Fenster Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) auf ein Kombinations Feld-Steuerelement an. :

- WS_CHILD immer

- WS_VISIBLE normalerweise

- WS_DISABLED selten

- WS_VSCROLL zum Hinzufügen eines vertikalen Bildlaufs für das Listenfeld im Kombinations Feld

- WS_HSCROLL zum horizontalen Scrollen für das Listenfeld im Kombinations Feld hinzufügen

- WS_GROUP zum Gruppieren von Steuerelementen

- WS_TABSTOP, um das Kombinations Feld in der Tabstopps-Reihenfolge einzuschließen

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]

##  <a name="cut"></a>CComboBox:: Cut

Löscht (schneidet) die aktuelle Auswahl, sofern vorhanden, im Kombinations Feld-Bearbeitungs Steuerelement und kopiert den gelöschten Text im CF_TEXT-Format in die Zwischenablage.

```
void Cut();
```

### <a name="remarks"></a>Hinweise

Um die aktuelle Auswahl zu löschen, ohne den gelöschten Text in der Zwischenablage zu platzieren, müssen [Sie die Funktion zum Löschen von](#clear) Membern

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]

##  <a name="deleteitem"></a>CComboBox::D eleteitem

Wird von Framework aufgerufen, wenn der Benutzer ein Element aus einem owner-draw `CComboBox` -Objekt löscht oder das Kombinations Feld zerstört.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDeleteItemStruct*<br/>
Ein langer Zeiger auf eine Windows [deleteitemstruct](/windows/win32/api/winuser/ns-winuser-deleteitemstruct) -Struktur, die Informationen über das gelöschte Element enthält. Eine Beschreibung dieser Struktur finden Sie unter [CWnd:: ondeleteitem](../../mfc/reference/cwnd-class.md#ondeleteitem) .

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um das Kombinations Feld bei Bedarf neu zu zeichnen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]

##  <a name="deletestring"></a>CComboBox::D eletestring

Löscht das Element in der Position *nIndex* aus dem Kombinations Feld.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den Index der zu löschenden Zeichenfolge an.

### <a name="return-value"></a>Rückgabewert

Wenn der Rückgabewert größer als oder gleich 0 ist, ist dies die Anzahl der Zeichen folgen, die in der Liste verbleiben. Der Rückgabewert ist CB_ERR, wenn *nIndex* einen Index angibt, der größer als die Anzahl der Elemente in der Liste ist.

### <a name="remarks"></a>Hinweise

Alle Elemente nach *nIndex* werden nun um eine Position nach unten verschoben. Wenn ein Kombinations Feld z. b. zwei Elemente enthält, führt das Löschen des ersten Elements dazu, dass das restliche Element jetzt an der ersten Position liegt. *nIndex*= 0 für das Element an der ersten Position.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]

##  <a name="dir"></a>CComboBox::D IR

Fügt dem Listenfeld eines Kombinations Felds eine Liste von Dateinamen oder Laufwerken hinzu.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Parameter

*attr*<br/>
Kann eine beliebige Kombi **Nation der in** [CFile:: GetStatus beschriebenen Enumerationswerte](../../mfc/reference/cfile-class.md#getstatus) oder eine beliebige Kombination der folgenden Werte sein:

- Die DDL_READWRITE-Datei kann aus gelesen oder geschrieben werden.

- Die DDL_READONLY-Datei kann aus gelesen, aber nicht in geschrieben werden.

- Die DDL_HIDDEN-Datei ist ausgeblendet und wird nicht in einer Verzeichnis Auflistung angezeigt.

- DDL_SYSTEM File ist eine System Datei.

- DDL_DIRECTORY der von *lpszwildcard* angegebene Name gibt ein Verzeichnis an.

- Die DDL_ARCHIVE-Datei wurde archiviert.

- DDL_DRIVES schließen Sie alle Laufwerke ein, die dem von *lpszwildcard*angegebenen Namen entsprechen.

- DDL_EXCLUSIVE exklusives Flag. Wenn das exklusive Flag festgelegt ist, werden nur Dateien des angegebenen Typs aufgelistet. Andernfalls werden Dateien des angegebenen Typs zusätzlich zu "normalen" Dateien aufgelistet.

*lpszWildCard*<br/>
Verweist auf eine Datei Spezifikations Zeichenfolge. Die Zeichenfolge kann Platzhalter enthalten (z. b.\**.).

### <a name="return-value"></a>Rückgabewert

Wenn der Rückgabewert größer als oder gleich 0 ist, ist dies der null basierte Index des letzten Datei namens, der der Liste hinzugefügt wurde. Der Rückgabewert ist CB_ERR, wenn ein Fehler auftritt. der Rückgabewert ist CB_ERRSPACE, wenn nicht genügend Speicherplatz zum Speichern der neuen Zeichen folgen verfügbar ist.

### <a name="remarks"></a>Hinweise

Diese Funktion wird vom Windows `ComboBoxEx` -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx](/windows/win32/Controls/comboboxex-controls) -Steuerelemente in der Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]

##  <a name="drawitem"></a>CComboBox::D rawitem

Wird von Framework aufgerufen, wenn sich ein visueller Aspekt eines Kombinations Felds für den Besitzer zeichnet.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein Zeiger auf eine [drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) -Struktur, die Informationen über den erforderlichen Zeichentyp enthält.

### <a name="remarks"></a>Hinweise

Der `itemAction` -Member `DRAWITEMSTRUCT` der-Struktur definiert die Zeichnungs Aktion, die ausgeführt werden soll. Eine Beschreibung dieser Struktur finden Sie unter [CWnd:: OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) .

Standardmäßig führt diese Member-Funktion keine Aktion aus. Überschreiben Sie diese Member-Funktion, um das Zeichnen für `CComboBox` ein owner-draw-Objekt zu implementieren Bevor diese Member-Funktion beendet wird, sollte die Anwendung alle GDI-Objekte (Graphics Device Interface) wiederherstellen, die für den in *lpdrawitemstruct*angegebenen Anzeige Kontext ausgewählt wurden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]

##  <a name="findstring"></a>CComboBox:: FindString

Sucht die erste Zeichenfolge, die das angegebene Präfix enthält, und wählt Sie nicht aus dem Listenfeld eines Kombinations Felds aus.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszString) const;
```

### <a name="parameters"></a>Parameter

*nStartAfter*<br/>
Enthält den NULL basierten Index des Elements vor dem ersten zu durchsuchenden Element. Wenn die Suche das Ende des Listen Felds erreicht, wird Sie vom oberen Rand des Listen Felds zurück zu dem durch *nstartafter*angegebenen Element. Wenn-1, wird das gesamte Listenfeld von Anfang an durchsucht.

*lpszString*<br/>
Verweist auf die auf NULL endenden Zeichenfolge, die das Präfix enthält, nach dem gesucht werden soll. Die Suche erfolgt unabhängig von der Groß-/Kleinschreibung, sodass diese Zeichenfolge eine beliebige Kombination von Groß-und Kleinbuchstaben enthalten kann.

### <a name="return-value"></a>Rückgabewert

Wenn der Rückgabewert größer als oder gleich 0 ist, ist dies der null basierte Index des übereinstimmenden Elements. Dies ist CB_ERR, wenn die Suche nicht erfolgreich war.

### <a name="remarks"></a>Hinweise

Diese Funktion wird vom Windows `ComboBoxEx` -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx](/windows/win32/Controls/comboboxex-controls) -Steuerelemente in der Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]

##  <a name="findstringexact"></a>CComboBox:: FindStringExact

Ruft die `FindStringExact` Member-Funktion auf, um die erste Listenfeld Zeichenfolge (in einem Kombinations Feld) zu suchen, die mit der in *lpszfind*angegebenen Zeichenfolge übereinstimmt.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Parameter

*nIndexStart*<br/>
Gibt den NULL basierten Index des Elements vor dem ersten zu durchsuchenden Element an. Wenn die Suche das Ende des Listen Felds erreicht, wird Sie vom oberen Rand des Listen Felds zurück zu dem durch *nindexstart*angegebenen Element. Wenn *nindexstart* den Wert-1 aufweist, wird das gesamte Listenfeld von Anfang an durchsucht.

*lpszFind*<br/>
Zeigt auf die zu suchende NULL-terminierte Zeichenfolge. Diese Zeichenfolge kann einen kompletten Dateinamen enthalten, einschließlich der Erweiterung. Bei der Suche wird die Groß-/Kleinschreibung nicht beachtet, sodass diese Zeichenfolge eine beliebige Kombination von Groß-und Kleinbuchstaben enthalten kann.

### <a name="return-value"></a>Rückgabewert

Der null basierte Index des übereinstimmenden Elements oder CB_ERR, wenn die Suche nicht erfolgreich war.

### <a name="remarks"></a>Hinweise

Wenn das Kombinations Feld mit einem Besitzer Zeichnungs Stil, aber ohne den [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -Stil erstellt wurde `FindStringExact` , versucht, den Double Word-Wert mit dem Wert von *lpszfind*abzugleichen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]

##  <a name="getcomboboxinfo"></a>CComboBox:: getcomboboxinfo

Ruft Informationen für das `CComboBox` -Objekt ab.

```
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;
```

### <a name="parameters"></a>Parameter

*pcbi*<br/>
Ein Zeiger auf die [comboboxinfo](/windows/win32/api/winuser/ns-winuser-comboboxinfo) -Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion emuliert die Funktionalität der [CB_GETCOMBOBOXINFO](/windows/win32/Controls/cb-getcomboboxinfo) -Nachricht, wie im Windows SDK beschrieben.

##  <a name="getcount"></a>CComboBox:: GetCount

Mit dieser Member-Funktion können Sie die Anzahl der Elemente im Listenfeld Teil eines Kombinations Felds abrufen.

```
int GetCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente. Die zurückgegebene Anzahl ist ein Wert größer als der Indexwert des letzten Elements (der Index ist NULL basiert). Dies ist CB_ERR, wenn ein Fehler auftritt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]

##  <a name="getcuebanner"></a>CComboBox:: getcuebanner

Ruft den Hinweis Text ab, der für ein Kombinations Feld-Steuerelement angezeigt wird.

```
CString GetCueBanner() const;

BOOL GetCueBanner(
    LPTSTR lpszText,
    int cchText) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*lpszText*|vorgenommen Zeiger auf einen Puffer, der den Hinweis Banner Text empfängt.|
|*cchText*|in Größe des Puffers, auf den der *lpszText* -Parameter verweist.|

### <a name="return-value"></a>Rückgabewert

In der ersten Überladung ein [CString](../../atl-mfc-shared/using-cstring.md) -Objekt, das den Hinweis Banner Text enthält, wenn es vorhanden ist. andernfalls ein `CString` -Objekt, das die Länge 0 (null) aufweist.

-oder-

In der zweiten Überladung true, wenn diese Methode erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Der Hinweis Text ist eine Eingabeaufforderung, die im Eingabebereich des Kombinations Feld-Steuer Elements angezeigt wird. Der Hinweis Text wird angezeigt, bis der Benutzereingaben eingibt.

Diese Methode sendet die [CB_GETCUEBANNER](/windows/win32/Controls/cb-getcuebanner) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getcursel"></a>CComboBox:: getcurrsel

Diese Member-Funktion wird aufgerufen, um zu bestimmen, welches Element im Kombinations Feld ausgewählt ist.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Rückgabewert

Der null basierte Index des derzeit ausgewählten Elements im Listenfeld eines Kombinations Felds oder CB_ERR, wenn kein Element ausgewählt ist.

### <a name="remarks"></a>Hinweise

`GetCurSel`Gibt einen Index in die Liste zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]

##  <a name="getdroppedcontrolrect"></a>CComboBox:: getdroppedcontrolrect

Rufen Sie `GetDroppedControlRect` die Member-Funktion auf, um die Bildschirm Koordinaten des sichtbaren (Dropdown-) Listen Felds eines Dropdown-Kombinations Felds abzurufen.

```
void GetDroppedControlRect(LPRECT lprect) const;
```

### <a name="parameters"></a>Parameter

*lprect*<br/>
Verweist auf die [Rect-Struktur](/windows/win32/api/windef/ns-windef-rect) , die die Koordinaten empfangen soll.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]

##  <a name="getdroppedstate"></a>CComboBox:: getdroppedstate

Ruft die `GetDroppedState` Member-Funktion auf, um zu bestimmen, ob das Listenfeld eines Dropdown-Kombinations Felds sichtbar (gelöscht) ist.

```
BOOL GetDroppedState() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Listenfeld sichtbar ist. andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]

##  <a name="getdroppedwidth"></a>CComboBox:: getdroppeer-DTH

Rufen Sie diese Funktion auf, um die minimale zulässige Breite des Listen Felds eines Kombinations Felds in Pixel abzurufen.

```
int GetDroppedWidth() const;
```

### <a name="return-value"></a>Rückgabewert

Bei Erfolg die zulässige Mindestbreite in Pixel. Andernfalls CB_ERR.

### <a name="remarks"></a>Hinweise

Diese Funktion gilt nur für Kombinations Felder mit dem [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -Stil.

Standardmäßig ist die zulässige Mindestbreite für das Dropdown-Listenfeld 0. Die zulässige Mindestbreite kann durch Aufrufen von [setdroppeer-DTH](#setdroppedwidth)festgelegt werden. Wenn der Listenfeld Bereich des Kombinations Felds angezeigt wird, ist seine Breite die größere der minimal zulässigen Breite oder der Kombinations Feldbreite.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [setdroppeer-DTH](#setdroppedwidth).

##  <a name="geteditsel"></a>CComboBox:: geteditsel

Ruft die Position des Anfangs-und des Endzeichens der aktuellen Auswahl im Bearbeitungs Steuerelement eines Kombinations Felds ab.

```
DWORD GetEditSel() const;
```

### <a name="return-value"></a>Rückgabewert

Ein 32-Bit-Wert, der die Anfangsposition in dem nieder wertigen Wort und die Position des ersten nicht ausgewählten Zeichens nach dem Ende der Auswahl im höherwertigen Wort enthält. Wenn diese Funktion in einem Kombinations Feld ohne Bearbeitungs Steuerelement verwendet wird, wird CB_ERR zurückgegeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]

##  <a name="getextendedui"></a>CComboBox:: getextendedui

Die `GetExtendedUI` Member-Funktion wird aufgerufen, um zu bestimmen, ob ein Kombinations Feld über die Standardbenutzer Oberfläche oder die erweiterte Benutzeroberfläche verfügt.

```
BOOL GetExtendedUI() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Kombinations Feld über die erweiterte Benutzeroberfläche verfügt. andernfalls 0.

### <a name="remarks"></a>Hinweise

Die erweiterte Benutzeroberfläche kann wie folgt identifiziert werden:

- Wenn Sie auf das statische Steuerelement klicken, wird das Listenfeld nur für Kombinations Felder mit dem [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -Stil angezeigt.

- Wenn Sie die nach-unten-Taste drücken, wird das Listenfeld angezeigt (F4 ist deaktiviert).

Das Scrollen im statischen Steuerelement ist deaktiviert, wenn die Elementliste nicht sichtbar ist (Pfeiltasten sind deaktiviert).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]

##  <a name="gethorizontalextent"></a>CComboBox:: gethorizontalblock

Ruft die Breite in Pixel ab, um die der Listenfeld Bereich des Kombinations Felds horizontal gescrollt werden kann.

```
UINT GetHorizontalExtent() const;
```

### <a name="return-value"></a>Rückgabewert

Die scrollbare Breite des Listenfeld Teils des Kombinations Felds in Pixel.

### <a name="remarks"></a>Hinweise

Dies gilt nur, wenn der Listenfeld Bereich des Kombinations Felds über eine horizontale Schiebe Leiste verfügt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]

##  <a name="getitemdata"></a>CComboBox:: GetItemData

Ruft den von der Anwendung bereitgestellten 32-Bit-Wert ab, der dem angegebenen Kombinations Feld Element zugeordnet ist.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält den NULL basierten Index eines Elements im Listenfeld des Kombinations Felds.

### <a name="return-value"></a>Rückgabewert

Der 32-Bit-Wert, der dem Element zugeordnet ist, oder CB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Der 32-Bit-Wert kann mit dem *dwitemdata* -Parameter eines [SetItemData](#setitemdata) -Member-Funktions Aufrufes festgelegt werden. Verwenden Sie `GetItemDataPtr` die Member-Funktion, wenn der 32-Bit-Wert, der abgerufen werden soll, ein Zeiger (**void** <strong>\*</strong>) ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]

##  <a name="getitemdataptr"></a>CComboBox:: getitemdataptr

Ruft den von der Anwendung bereitgestellten 32-Bit-Wert ab, der dem angegebenen Kombinations Feld Element als Zeiger (**void** <strong>\*</strong>) zugeordnet ist.

```
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält den NULL basierten Index eines Elements im Listenfeld des Kombinations Felds.

### <a name="return-value"></a>Rückgabewert

Ruft einen Zeiger ab, oder-1, wenn ein Fehler auftritt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]

##  <a name="getitemheight"></a>CComboBox:: GetItemHeight

Rufen Sie `GetItemHeight` die Member-Funktion auf, um die Höhe der Listenelemente in einem Kombinations Feld abzurufen.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt die Komponente des Kombinations Felds an, dessen Höhe abgerufen werden soll. Wenn der Parameter *nIndex* den Wert-1 hat, wird die Höhe des Abschnitts Edit-Control (oder Static-Text) des Kombinations Felds abgerufen. Wenn das Kombinations Feld den [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -Stil hat, gibt *nIndex* den NULL basierten Index des Listen Elements an, dessen Höhe abgerufen werden soll. Andernfalls sollte *nIndex* auf 0 festgelegt werden.

### <a name="return-value"></a>Rückgabewert

Die Höhe des angegebenen Elements in einem Kombinations Feld in Pixel. Der Rückgabewert ist CB_ERR, wenn ein Fehler auftritt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]

##  <a name="getlbtext"></a>CComboBox:: getlbtext

Ruft eine Zeichenfolge aus dem Listenfeld eines Kombinations Felds ab.

```
int GetLBText(
    int nIndex,
    LPTSTR lpszText) const;

void GetLBText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält den NULL basierten Index der zu kopierenden Listenfeld Zeichenfolge.

*lpszText*<br/>
Verweist auf einen Puffer, der die Zeichenfolge empfangen soll. Der Puffer muss über ausreichend Speicherplatz für die Zeichenfolge und ein abschließendes NULL-Zeichen verfügen.

*rString*<br/>
Ein Verweis auf eine `CString`.

### <a name="return-value"></a>Rückgabewert

Die Länge (in Byte) der Zeichenfolge ohne das abschließende Null Zeichen. Wenn *nIndex* keinen gültigen Index angibt, ist der Rückgabewert CB_ERR.

### <a name="remarks"></a>Hinweise

Die zweite Form dieser Member-Funktion füllt ein `CString` -Objekt mit dem Text des Elements.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]

##  <a name="getlbtextlen"></a>CComboBox:: getlbtextlen

Ruft die Länge einer Zeichenfolge im Listenfeld eines Kombinations Felds ab.

```
int GetLBTextLen(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält den NULL basierten Index der Listenfeld Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Die Länge der Zeichenfolge in Bytes, ohne das abschließende Null Zeichen. Wenn *nIndex* keinen gültigen Index angibt, ist der Rückgabewert CB_ERR.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CComboBox:: getlbtext](#getlbtext).

##  <a name="getlocale"></a>CComboBox:: getLocale

Ruft das vom Kombinations Feld verwendete Gebiets Schema ab.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Rückgabewert

Der LCID-Wert (Locale Identifier) für die Zeichen folgen im Kombinations Feld.

### <a name="remarks"></a>Hinweise

Das Gebiets Schema wird z. b. verwendet, um die Sortierreihenfolge der Zeichen folgen in einem sortierten Kombinations Feld zu bestimmen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CComboBox:: setlocale](#setlocale).

##  <a name="getminvisible"></a>CComboBox:: getminvisible

Ruft die Mindestanzahl sichtbarer Elemente in der Dropdown Liste des aktuellen Kombinations Feld-Steuer Elements ab.

```
int GetMinVisible() const;
```

### <a name="return-value"></a>Rückgabewert

Die Mindestanzahl sichtbarer Elemente in der aktuellen Dropdown Liste.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [CB_GETMINVISIBLE](/windows/win32/Controls/cb-setminvisible) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="gettopindex"></a>CComboBox:: gettopindex

Ruft den NULL basierten Index des ersten sichtbaren Elements im Listenfeld Bereich des Kombinations Felds ab.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Rückgabewert

Der null basierte Index des ersten sichtbaren Elements im Listenfeld Bereich des Kombinations Felds, wenn erfolgreich, CB_ERR andernfalls.

### <a name="remarks"></a>Hinweise

Zuerst befindet sich Element 0 am oberen Rand des Listen Felds, aber wenn im Listenfeld ein Bildlauf durchgeführt wird, befindet sich möglicherweise ein anderes Element im oberen Bereich.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]

##  <a name="initstorage"></a>CComboBox:: InitStorage

Weist Arbeitsspeicher zum Speichern von Listenfeld Elementen im Listenfeld Bereich des Kombinations Felds zu.

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>Parameter

*nItems*<br/>
Gibt die Anzahl der hinzu zufügenden Elemente an.

*nBytes*<br/>
Gibt die Größe des Arbeitsspeichers in Bytes an, der für Element Zeichenfolgen belegt werden soll.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird die maximale Anzahl von Elementen, die im Listenfeld Bereich des Kombinations Felds gespeichert werden können, bevor eine Speicher Belegung erforderlich ist, andernfalls CB_ERRSPACE, was bedeutet, dass nicht genügend Arbeitsspeicher verfügbar ist.

### <a name="remarks"></a>Hinweise

Diese Funktion wird aufgerufen, bevor dem Listenfeld Teil des `CComboBox`eine große Anzahl von Elementen hinzugefügt wird.

Nur Windows 95/98: Der *wParam* -Parameter ist auf 16-Bit-Werte beschränkt. Dies bedeutet, dass Listenfelder nicht mehr als 32.767 Elemente enthalten dürfen. Obwohl die Anzahl der Elemente eingeschränkt ist, wird die Gesamtgröße der Elemente in einem Listenfeld nur durch den verfügbaren Arbeitsspeicher beschränkt.

Diese Funktion beschleunigt die Initialisierung von Listenfeldern, die über eine große Anzahl von Elementen verfügen (mehr als 100). Dadurch wird die angegebene Arbeitsspeicher Menge vorab zugeordnet, sodass nachfolgende [AddString](#addstring)-, [InsertString](#insertstring)-und [dir](#dir) -Funktionen die kürzeste mögliche Zeit beanspruchen. Sie können Schätzwerte für die Parameter verwenden. Wenn Sie den Wert überschätzen, wird ein zusätzlicher Arbeitsspeicher zugewiesen. Wenn Sie unterschätzen, wird die normale Zuordnung für Elemente verwendet, die den vorab zugeordneten Betrag überschreiten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]

##  <a name="insertstring"></a>CComboBox:: InsertString

Fügt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds ein.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält den nullbasierten Index der Position im Listenfeld, die die Zeichenfolge aufnehmen soll. Wenn dieser Parameter-1 ist, wird die Zeichenfolge am Ende der Liste hinzugefügt.

*lpszString*<br/>
Zeigt auf die einzufügende nullterminierte Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index der Position, an der die Zeichenfolge eingefügt wurde. Der Rückgabewert ist CB_ERR, wenn ein Fehler auftritt. Der Rückgabewert ist CB_ERRSPACE, wenn nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolge zur Verfügung steht.

### <a name="remarks"></a>Hinweise

Im Gegensatz zur Memberfunktion [AddString](#addstring) bewirkt die `InsertString` -Memberfunktion nicht die Sortierung einer Liste mit der Formatvorlage [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) .

> [!NOTE]
>  Diese Funktion wird vom Windows `ComboBoxEx` -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx](/windows/win32/Controls/comboboxex-controls) -Steuerelemente in der Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]

##  <a name="limittext"></a>CComboBox:: limittext

Schränkt die Länge des Texts in Bytes ein, der vom Benutzer in das Bearbeitungs Steuerelement eines Kombinations Felds eingegeben werden kann.

```
BOOL LimitText(int nMaxChars);
```

### <a name="parameters"></a>Parameter

*nmaxchars*<br/>
Gibt die Länge (in Byte) des Texts an, den der Benutzer eingeben kann. Wenn dieser Parameter 0 ist, wird die Textlänge auf 65.535 Bytes festgelegt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich. Wenn ein Kombinations Feld mit dem Format [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder einem Kombinations Feld ohne Bearbeitungs Steuerelement aufgerufen wird, ist der Rückgabewert CB_ERR.

### <a name="remarks"></a>Hinweise

Wenn das Kombinations Feld nicht den Stil [CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)hat, wirkt sich das Festlegen des Text Limits auf einen höheren Wert als die Größe des Bearbeitungs Steuer Elements aus.

`LimitText`beschränkt nur den Text, den der Benutzer eingeben kann. Sie hat keine Auswirkung auf einen Text, der sich bereits im Bearbeitungs Steuerelement befindet, wenn die Nachricht gesendet wird, und wirkt sich auch nicht auf die Länge des Texts aus, der in das Bearbeitungs Steuerelement kopiert wird, wenn eine Zeichenfolge im Listenfeld ausgewählt ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]

##  <a name="measureitem"></a>CComboBox:: MeasureItem

Wird von Framework aufgerufen, wenn ein Kombinations Feld mit einer Art von Besitzer zeichnen erstellt wird.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parameter

*lpMeasureItemStruct*<br/>
Ein langer Zeiger auf eine [measureitemstruct](/windows/win32/api/winuser/ns-winuser-measureitemstruct) -Struktur.

### <a name="remarks"></a>Hinweise

Standardmäßig führt diese Member-Funktion keine Aktion aus. Überschreiben Sie diese Member-Funktion, `MEASUREITEMSTRUCT` und füllen Sie die Struktur aus, um Fenster über die Abmessungen des Listen Felds im Kombinations Feld zu informieren. Wenn das Kombinations Feld mit dem [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -Stil erstellt wird, ruft das Framework diese Member-Funktion für jedes Element im Listenfeld auf. Andernfalls wird dieser Member nur einmal aufgerufen.

Die Verwendung des CBS_OWNERDRAWFIXED-Stils in einem mit der [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) -Member-Funktion von erstellten Kombinations `CWnd` Feld "Besitzer zeichnen" umfasst weitere Überlegungen zur Programmierung. Weitere Informationen finden Sie in der [technischen Notiz 14](../../mfc/tn014-custom-controls.md).

Eine Beschreibung der Struktur finden Sie unter `MEASUREITEMSTRUCT` [CWnd:: OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) .

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]

##  <a name="paste"></a>CComboBox::P Aste

Fügt die Daten aus der Zwischenablage in das Bearbeitungs Steuerelement des Kombinations Felds an der aktuellen Cursorposition ein.

```
void Paste();
```

### <a name="remarks"></a>Hinweise

Daten werden nur eingefügt, wenn die Zwischenablage Daten im CF_TEXT-Format enthält.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]

##  <a name="resetcontent"></a>CComboBox:: resetcontent

Entfernt alle Elemente aus dem Listenfeld und bearbeitet das Steuerelement eines Kombinations Felds.

```
void ResetContent();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]

##  <a name="selectstring"></a>CComboBox:: SelectString

Sucht im Listenfeld eines Kombinations Felds nach einer Zeichenfolge, und wenn die Zeichenfolge gefunden wird, wählt die Zeichenfolge im Listenfeld aus und kopiert sie in das Bearbeitungs Steuerelement.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parameter

*nStartAfter*<br/>
Enthält den NULL basierten Index des Elements vor dem ersten zu durchsuchenden Element. Wenn die Suche das Ende des Listen Felds erreicht, wird Sie vom oberen Rand des Listen Felds zurück zu dem durch *nstartafter*angegebenen Element. Wenn-1, wird das gesamte Listenfeld von Anfang an durchsucht.

*lpszString*<br/>
Verweist auf die auf NULL endenden Zeichenfolge, die das Präfix enthält, nach dem gesucht werden soll. Die Suche erfolgt unabhängig von der Groß-/Kleinschreibung, sodass diese Zeichenfolge eine beliebige Kombination von Groß-und Kleinbuchstaben enthalten kann.

### <a name="return-value"></a>Rückgabewert

Der null basierte Index des ausgewählten Elements, wenn die Zeichenfolge gefunden wurde. Wenn die Suche nicht erfolgreich war, ist der Rückgabewert CB_ERR, und die aktuelle Auswahl wird nicht geändert.

### <a name="remarks"></a>Hinweise

Eine Zeichenfolge wird nur ausgewählt, wenn die Anfangs Zeichen (vom Startpunkt) mit den Zeichen in der Präfix Zeichenfolge verglichen werden.

Beachten Sie, `SelectString` dass `FindString` die-und-Element Funktionen beide eine Zeichen `SelectString` Folge suchen, aber die Member-Funktion wählt auch die Zeichenfolge aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]

##  <a name="setcuebanner"></a>CComboBox:: setcuebanner

Legt den Hinweis Text fest, der für ein Kombinations Feld-Steuerelement angezeigt wird.

```
BOOL SetCueBanner(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*lpszText*|in Ein Zeiger auf einen null-terminierten Puffer, der den Hinweis Text enthält.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Methode erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Der Hinweis Text ist eine Eingabeaufforderung, die im Eingabebereich des Kombinations Feld-Steuer Elements angezeigt wird. Der Hinweis Text wird angezeigt, bis der Benutzereingaben eingibt.

Diese Methode sendet die [CB_SETCUEBANNER](/windows/win32/Controls/cb-setcuebanner) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die Variable *m_combobox*definiert, die für den programmgesteuerten Zugriff auf das Kombinations Feld-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird das Hinweis Banner für das Kombinations Feld-Steuerelement festgelegt.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

##  <a name="setcursel"></a>CComboBox:: setcurrsel

Wählt eine Zeichenfolge im Listenfeld eines Kombinations Felds aus.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Parameter

*nWählen*<br/>
Gibt den NULL basierten Index der auszuwählen Zeichenfolge an. Wenn-1, wird die aktuelle Auswahl im Listenfeld entfernt, und das Bearbeitungs Steuerelement wird gelöscht.

### <a name="return-value"></a>Rückgabewert

Der null basierte Index des Elements, das ausgewählt wird, wenn die Nachricht erfolgreich ist. Der Rückgabewert ist CB_ERR, wenn *nselect* größer als die Anzahl der Elemente in der Liste ist oder wenn *nselect* auf-1 festgelegt ist, wodurch die Auswahl gelöscht wird.

### <a name="remarks"></a>Hinweise

Bei Bedarf führt das Listenfeld einen Bildlauf in der Zeichenfolge durch (wenn das Listenfeld sichtbar ist). Der Text im Bearbeitungs Steuerelement des Kombinations Felds wird so geändert, dass die neue Auswahl angezeigt wird. Jede vorherige Auswahl im Listenfeld wird entfernt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]

##  <a name="setdroppedwidth"></a>CComboBox:: setdroppeer-DTH

Mit dieser Funktion können Sie die minimale zulässige Breite des Listen Felds eines Kombinations Felds in Pixel festlegen.

```
int SetDroppedWidth(UINT nWidth);
```

### <a name="parameters"></a>Parameter

*nWidth*<br/>
Die minimale zulässige Breite des Listenfeld Teils des Kombinations Felds in Pixel.

### <a name="return-value"></a>Rückgabewert

Bei Erfolg die neue Breite des Listen Felds, andernfalls CB_ERR.

### <a name="remarks"></a>Hinweise

Diese Funktion gilt nur für Kombinations Felder mit dem [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -Stil.

Standardmäßig ist die zulässige Mindestbreite für das Dropdown-Listenfeld 0. Wenn der Listenfeld Bereich des Kombinations Felds angezeigt wird, ist seine Breite die größere der minimal zulässigen Breite oder der Kombinations Feldbreite.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]

##  <a name="seteditsel"></a>CComboBox:: fest.

Wählt Zeichen im Bearbeitungs Steuerelement eines Kombinations Felds aus.

```
BOOL SetEditSel(
    int nStartChar,
    int nEndChar);
```

### <a name="parameters"></a>Parameter

*nStartChar*<br/>
Gibt die Anfangsposition an. Wenn die Anfangsposition auf-1 festgelegt ist, wird eine vorhandene Auswahl entfernt.

*nEndChar*<br/>
Gibt die Endposition an. Wenn die Endposition auf-1 festgelegt ist, wird der gesamte Text von der Anfangsposition bis zum letzten Zeichen im Bearbeitungs Steuerelement ausgewählt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Member-Funktion erfolgreich ist. andernfalls 0. Der Wert ist CB_ERR `CComboBox` , wenn den [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -Stil hat oder kein Listenfeld aufweist.

### <a name="remarks"></a>Hinweise

Die Positionen sind NULL basiert. Um das erste Zeichen des Bearbeitungs Steuer Elements auszuwählen, geben Sie die Anfangsposition 0 an. Die Endposition ist für das Zeichen direkt nach dem letzten Zeichen, das ausgewählt werden soll. Wenn Sie z. b. die ersten vier Zeichen des Bearbeitungs Steuer Elements auswählen möchten, verwenden Sie die Startposition 0 und die Endposition 4.

> [!NOTE]
>  Diese Funktion wird vom Windows `ComboBoxEx` -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx](/windows/win32/Controls/comboboxex-controls) -Steuerelemente in der Windows SDK.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CComboBox:: geteditsel](#geteditsel).

##  <a name="setextendedui"></a>CComboBox:: abtextendedui

Rufen Sie die `SetExtendedUI`-Memberfunktion auf, um die Standardbenutzeroberfläche oder die erweiterte Benutzeroberfläche für ein Kombinationsfeld auszuwählen, das auf den Stil [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) festgelegt ist.

```
int SetExtendedUI(BOOL bExtended = TRUE);
```

### <a name="parameters"></a>Parameter

*bExtended*<br/>
Gibt an, ob das Kombinations Feld die erweiterte Benutzeroberfläche oder die Standardbenutzer Oberfläche verwenden soll. Der Wert true wählt die erweiterte Benutzeroberfläche aus. mit dem Wert false wird die Standardbenutzer Oberfläche ausgewählt.

### <a name="return-value"></a>Rückgabewert

CB_OKAY, wenn der Vorgang erfolgreich ist, oder CB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Die erweiterte Benutzeroberfläche kann wie folgt identifiziert werden:

- Wenn Sie auf das statische Steuerelement klicken, wird das Listenfeld nur für Kombinations Felder mit dem CBS_DROPDOWNLIST-Stil angezeigt.

- Wenn Sie die nach-unten-Taste drücken, wird das Listenfeld angezeigt (F4 ist deaktiviert).

Das Scrollen im statischen Steuerelement ist deaktiviert, wenn die Elementliste nicht sichtbar ist (die Pfeiltasten sind deaktiviert).

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CComboBox:: getextendedui](#getextendedui).

##  <a name="sethorizontalextent"></a>CComboBox:: CComboBox::

Legt die Breite (in Pixel) fest, um die der Listenfeld Bereich des Kombinations Felds horizontal gescrollt werden kann.

```
void SetHorizontalExtent(UINT nExtent);
```

### <a name="parameters"></a>Parameter

*nextent*<br/>
Gibt die Anzahl der Pixel an, um die der Listenfeld Bereich des Kombinations Felds horizontal gescrollt werden kann.

### <a name="remarks"></a>Hinweise

Wenn die Breite des Listen Felds kleiner als dieser Wert ist, führt die horizontale Schiebe Leiste im Listenfeld einen horizontalen Bildlauf durch. Wenn die Breite des Listen Felds größer oder gleich diesem Wert ist, wird die horizontale Schiebe Leiste ausgeblendet oder, wenn das Kombinations Feld den [CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -Stil hat, deaktiviert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]

##  <a name="setitemdata"></a>CComboBox:: "abtitemdata"

Legt den 32-Bit-Wert fest, der dem angegebenen Element in einem Kombinations Feld zugeordnet ist.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält einen NULL basierten Index für das festzulegende Element.

*dwItemData*<br/>
Enthält den neuen Wert, der dem Element zugeordnet werden soll.

### <a name="return-value"></a>Rückgabewert

CB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Verwenden Sie `SetItemDataPtr` die Member-Funktion, wenn das 32-Bit-Element ein Zeiger sein soll.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]

##  <a name="setitemdataptr"></a>CComboBox:: "abtitemdataptr"

Legt den 32-Bit-Wert, der dem angegebenen Element in einem Kombinations Feld zugeordnet ist, als den angegebenen Zeiger (**void** <strong>\*</strong>) fest.

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält einen NULL basierten Index für das Element.

*pData*<br/>
Enthält den Zeiger, der dem Element zugeordnet werden soll.

### <a name="return-value"></a>Rückgabewert

CB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Dieser Zeiger bleibt für die Lebensdauer des Kombinations Felds gültig, auch wenn die relative Position des Elements im Kombinations Feld geändert werden kann, wenn Elemente hinzugefügt oder entfernt werden. Daher kann der Index des Elements innerhalb des Felds geändert werden, aber der Zeiger bleibt zuverlässig.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]

##  <a name="setitemheight"></a>CComboBox::-Elementhöhe

Ruft die `SetItemHeight` Member-Funktion auf, um die Höhe von Listenelementen in einem Kombinations Feld oder die Höhe des Bearbeitungs Steuer Elements (oder statischer Text) eines Kombinations Felds festzulegen.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt an, ob die Höhe von Listenelementen oder die Höhe des Bearbeitungs Steuer Elements (oder statischer Text) des Kombinations Felds festgelegt wird.

Wenn das Kombinations Feld den [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -Stil hat, gibt *nIndex* den NULL basierten Index des Listen Elements an, dessen Höhe festgelegt werden soll. Andernfalls muss *nIndex* den Wert 0 aufweisen, und die Höhe aller Listenelemente wird festgelegt.

Wenn *nIndex* den Wert-1 hat, muss die Höhe des Abschnitts Edit-Control oder Static-Text im Kombinations Feld festgelegt werden.

*cyItemHeight*<br/>
Gibt die Höhe der durch *nIndex*identifizierten Kombinations Feld Komponente in Pixel an.

### <a name="return-value"></a>Rückgabewert

CB_ERR, wenn der Index oder die Höhe ungültig ist. andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Höhe des Bearbeitungs Steuerelement-Teils (oder statischer Text) des Kombinations Felds wird unabhängig von der Höhe der Listenelemente festgelegt. Eine Anwendung muss sicherstellen, dass die Höhe des Bearbeitungs Steuer Elements (oder statischer Text) nicht kleiner ist als die Höhe eines bestimmten Listenfeld Elements.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]

##  <a name="setlocale"></a>CComboBox:: setlocale

Legt den Gebiets Schema Bezeichner für dieses Kombinations Feld fest.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Parameter

*nNewLocale*<br/>
Der neue LCID-Wert (Locale Identifier), der für das Kombinations Feld festgelegt werden soll.

### <a name="return-value"></a>Rückgabewert

Der vorherige LCID-Wert (Locale Identifier) für dieses Kombinations Feld.

### <a name="remarks"></a>Hinweise

Wenn `SetLocale` nicht aufgerufen wird, wird das Standard Gebiets Schema vom System abgerufen. Dieses Standard Gebiets Schema für das System kann mithilfe der regionalen (oder internationalen) Anwendung der Systemsteuerung geändert werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]

##  <a name="setminvisibleitems"></a>CComboBox:: setminvisibleitems

Legt die Mindestanzahl sichtbarer Elemente in der Dropdown Liste des aktuellen Kombinations Feld-Steuer Elements fest.

```
BOOL SetMinVisibleItems(int iMinVisible);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iMinVisible*|in Gibt die Mindestanzahl von sichtbaren Elementen an.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [CB_SETMINVISIBLE](/windows/win32/Controls/cb-setminvisible) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die Variable *m_combobox*definiert, die für den programmgesteuerten Zugriff auf das Kombinations Feld-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden 20 Elemente in die Dropdown Liste eines Kombinations Feld-Steuer Elements eingefügt. Anschließend wird festgelegt, dass mindestens 10 Elemente angezeigt werden, wenn ein Benutzer auf den Dropdown Pfeil drückt.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

##  <a name="settopindex"></a>CComboBox:: settopindex

Stellt sicher, dass ein bestimmtes Element im Listenfeld Bereich des Kombinations Felds angezeigt wird.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den NULL basierten Index des Listenfeld Elements an.

### <a name="return-value"></a>Rückgabewert

0 (null), wenn erfolgreich, oder CB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Das System führt einen Bildlauf durch das Listenfeld durch, bis entweder das von *nIndex* angegebene Element oben im Listenfeld angezeigt wird oder der maximale scrollbereich erreicht wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]

##  <a name="showdropdown"></a>CComboBox:: ShowDropDown

Blendet das Listenfeld eines Kombinations Felds mit dem Format [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) ein oder aus.

```
void ShowDropDown(BOOL bShowIt = TRUE);
```

### <a name="parameters"></a>Parameter

*bShowIt*<br/>
Gibt an, ob das Dropdown-Listenfeld angezeigt oder ausgeblendet werden soll. Der Wert true zeigt das Listenfeld an. Der Wert false blendet das Listenfeld aus.

### <a name="remarks"></a>Hinweise

Standardmäßig wird in einem Kombinations Feld dieses Stils das Listenfeld angezeigt.

Diese Member-Funktion hat keine Auswirkung auf ein Kombinations Feld, das mit dem [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -Stil erstellt wurde.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CComboBox:: getdroppedstate](#getdroppedstate).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[CButton-Klasse](../../mfc/reference/cbutton-class.md)<br/>
[CEdit-Klasse](../../mfc/reference/cedit-class.md)<br/>
[CListBox-Klasse](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar-Klasse](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic-Klasse](../../mfc/reference/cstatic-class.md)<br/>
[CDialog-Klasse](../../mfc/reference/cdialog-class.md)
