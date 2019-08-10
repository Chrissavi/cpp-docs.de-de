---
title: CPropertyPage-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPropertyPage
- AFXDLGS/CPropertyPage
- AFXDLGS/CPropertyPage::CPropertyPage
- AFXDLGS/CPropertyPage::CancelToClose
- AFXDLGS/CPropertyPage::Construct
- AFXDLGS/CPropertyPage::GetPSP
- AFXDLGS/CPropertyPage::OnApply
- AFXDLGS/CPropertyPage::OnCancel
- AFXDLGS/CPropertyPage::OnKillActive
- AFXDLGS/CPropertyPage::OnOK
- AFXDLGS/CPropertyPage::OnQueryCancel
- AFXDLGS/CPropertyPage::OnReset
- AFXDLGS/CPropertyPage::OnSetActive
- AFXDLGS/CPropertyPage::OnWizardBack
- AFXDLGS/CPropertyPage::OnWizardFinish
- AFXDLGS/CPropertyPage::OnWizardNext
- AFXDLGS/CPropertyPage::QuerySiblings
- AFXDLGS/CPropertyPage::SetModified
- AFXDLGS/CPropertyPage::m_psp
helpviewer_keywords:
- CPropertyPage [MFC], CPropertyPage
- CPropertyPage [MFC], CancelToClose
- CPropertyPage [MFC], Construct
- CPropertyPage [MFC], GetPSP
- CPropertyPage [MFC], OnApply
- CPropertyPage [MFC], OnCancel
- CPropertyPage [MFC], OnKillActive
- CPropertyPage [MFC], OnOK
- CPropertyPage [MFC], OnQueryCancel
- CPropertyPage [MFC], OnReset
- CPropertyPage [MFC], OnSetActive
- CPropertyPage [MFC], OnWizardBack
- CPropertyPage [MFC], OnWizardFinish
- CPropertyPage [MFC], OnWizardNext
- CPropertyPage [MFC], QuerySiblings
- CPropertyPage [MFC], SetModified
- CPropertyPage [MFC], m_psp
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
ms.openlocfilehash: f9116306fd2bd6145096b055025bd4dd2075b0c1
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916880"
---
# <a name="cpropertypage-class"></a>CPropertyPage-Klasse

Stellt die einzelnen Seiten eines Eigenschaftenblatts dar; wird auch als "Dialogfeld im Registerformat" bezeichnet.

## <a name="syntax"></a>Syntax

```
class CPropertyPage : public CDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPropertyPage:: CPropertyPage](#cpropertypage)|Erstellt ein `CPropertyPage`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPropertyPage::CancelToClose](#canceltoclose)|Ändert die Schaltfläche OK, um den Lesevorgang zu schließen, und deaktiviert die Schaltfläche Abbrechen nach einer nicht BEHEB baren Änderung auf der Seite eines modalen Eigenschaften Blatts.|
|[CPropertyPage:: Construct](#construct)|Erstellt ein `CPropertyPage`-Objekt. Verwenden `Construct` Sie, wenn Sie die Parameter zur Laufzeit angeben möchten, oder wenn Sie Arrays verwenden.|
|[CPropertyPage::GetPSP](#getpsp)|Ruft die Windows- [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-propsheetpagea_v2) -Struktur ab, `CPropertyPage` die dem-Objekt zugeordnet ist.|
|[CPropertyPage::OnApply](#onapply)|Wird von Framework aufgerufen, wenn auf die Schaltfläche "jetzt anwenden" geklickt wird.|
|[CPropertyPage::OnCancel](#oncancel)|Wird von Framework aufgerufen, wenn auf die Schaltfläche Abbrechen geklickt wird.|
|[CPropertyPage::OnKillActive](#onkillactive)|Wird von Framework aufgerufen, wenn die aktuelle Seite nicht mehr die aktive Seite ist. Führen Sie hier die Datenüberprüfung aus.|
|[CPropertyPage::OnOK](#onok)|Wird von Framework aufgerufen, wenn auf die Schaltfläche OK, jetzt anwenden oder schließen geklickt wird.|
|[CPropertyPage::OnQueryCancel](#onquerycancel)|Wird von Framework aufgerufen, wenn auf die Schaltfläche Abbrechen geklickt wird, und bevor der Abbruch stattfindet.|
|[CPropertyPage::OnReset](#onreset)|Wird von Framework aufgerufen, wenn auf die Schaltfläche Abbrechen geklickt wird.|
|[CPropertyPage::OnSetActive](#onsetactive)|Wird von Framework aufgerufen, wenn die Seite zur aktiven Seite gemacht wird.|
|[CPropertyPage::OnWizardBack](#onwizardback)|Wird von Framework aufgerufen, wenn auf die Schaltfläche "zurück" während der Verwendung eines Eigenschaften Blatts vom Typ "Wizard" geklickt wird.|
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|Wird von Framework aufgerufen, wenn auf die Schaltfläche Fertigstellen während der Verwendung eines Eigenschaften Blatts vom Typ Wizard geklickt wird.|
|[CPropertyPage::OnWizardNext](#onwizardnext)|Wird von Framework aufgerufen, wenn auf die Schaltfläche Weiter geklickt wird, während ein Eigenschaften Blatt des Assistenten angezeigt wird.|
|[CPropertyPage::QuerySiblings](#querysiblings)|Leitet die Nachricht an jede Seite des Eigenschaften Blatts weiter.|
|[CPropertyPage::SetModified](#setmodified)|Ruft auf, um die Schaltfläche jetzt anwenden zu aktivieren oder zu deaktivieren.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPropertyPage::m_psp](#m_psp)|Die Windows- [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-propsheetpagea_v2) -Struktur. Ermöglicht den Zugriff auf grundlegende Eigenschaften Seiten Parameter.|

## <a name="remarks"></a>Hinweise

Wie bei Standard Dialogfeldern leiten Sie eine Klasse von `CPropertyPage` für jede Seite in Ihrem Eigenschaften Blatt ab. Um von `CPropertyPage`abgeleitete Objekte zu verwenden, erstellen Sie zunächst ein [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) -Objekt, und erstellen Sie dann ein-Objekt für jede Seite, die im Eigenschaften Blatt angezeigt wird. Rufen Sie [CPropertySheet:: addPage](../../mfc/reference/cpropertysheet-class.md#addpage) für jede Seite im Blatt auf, und zeigen Sie dann das Eigenschaften Blatt durch Aufrufen von [CPropertySheet::D omodal](../../mfc/reference/cpropertysheet-class.md#domodal) für ein modales Eigenschaften Blatt oder [CPropertySheet:: Create](../../mfc/reference/cpropertysheet-class.md#create) für ein nicht modales Eigenschaften Blatt an.

Sie können ein Dialogfeld vom Typ "Registerkarte" erstellen, das als Assistent bezeichnet wird, der aus einem Eigenschaften Blatt mit einer Sequenz von Eigenschaften Seiten besteht, die den Benutzer durch die Schritte eines Vorgangs leiten, wie z. b. das Einrichten eines Geräts oder das Erstellen eines Newsletter. Im Dialogfeld der Registerkarte "Wizard-Type" sind auf den Eigenschaften Seiten keine Registerkarten enthalten, und es ist jeweils nur eine Eigenschaften Seite sichtbar. Anstatt die Schaltflächen "OK" und "jetzt anwenden" zu verwenden, verfügt das Dialogfeld "Wizard-Type Registerkarte" über eine Schaltfläche "zurück", eine Schaltfläche "weiter" oder "Fertigstellen"

Weitere Informationen zum Einrichten eines Eigenschaften Blatts als Assistent finden Sie unter [CPropertySheet::](../../mfc/reference/cpropertysheet-class.md#setwizardmode)"". Weitere Informationen zur Verwendung von `CPropertyPage` -Objekten finden Sie im Artikel [Eigenschaften Blätter und Eigenschaften Seiten](../../mfc/property-sheets-and-property-pages-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CPropertyPage`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs. h

##  <a name="canceltoclose"></a>CPropertyPage:: canceldeclose

Diese Funktion wird aufgerufen, nachdem eine nicht BEHEB Bare Änderung an den Daten auf einer Seite eines modalen Eigenschaften Blatts vorgenommen wurde.

```
void CancelToClose();
```

### <a name="remarks"></a>Hinweise

Diese Funktion ändert die Schaltfläche OK, um die Schaltfläche Abbrechen zu schließen und zu deaktivieren. Diese Änderung warnt den Benutzer, dass eine Änderung permanent ist und die Änderungen nicht abgebrochen werden können.

Die `CancelToClose` Member-Funktion führt in einem nicht modalem Eigenschaften Blatt keine Aktion aus, da ein nicht modalem Eigenschaften Blatt standardmäßig nicht über die Schaltfläche Abbrechen verfügt.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPropertyPage:: querysiblings](#querysiblings).

##  <a name="construct"></a>CPropertyPage:: Construct

Diese Member-Funktion zum Erstellen eines `CPropertyPage` -Objekts aufzurufen.

```
void Construct(
    UINT nIDTemplate,
    UINT nIDCaption = 0);

void Construct(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption = 0);

void Construct(
    UINT nIDTemplate,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0);

void Construct(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0);
```

### <a name="parameters"></a>Parameter

*nIDTemplate*<br/>
ID der Vorlage, die für diese Seite verwendet wird.

*nIDCaption*<br/>
ID des Namens, der auf der Registerkarte für diese Seite platziert werden soll. Wenn der Wert 0 ist, wird der Name aus der Dialogfeld Vorlage für diese Seite entnommen.

*lpszTemplateName*<br/>
Enthält eine NULL-terminierte Zeichenfolge, die den Namen einer Vorlagen Ressource ist.

*nIDHeaderTitle*<br/>
ID des Namens, der an der Titel Position des Eigenschaften Seiten Headers platziert werden soll. Standardmäßig ist der Wert 0.

*nIDHeaderSubTitle*<br/>
ID des Namens, der in der Untertitel Position des Header der Eigenschaften Seite platziert werden soll. Standardmäßig ist der Wert 0.

### <a name="remarks"></a>Hinweise

Das-Objekt wird angezeigt, nachdem alle der folgenden Bedingungen erfüllt sind:

- Die Seite wurde mithilfe von [CPropertySheet:: addPage](../../mfc/reference/cpropertysheet-class.md#addpage)zu einem Eigenschaften Blatt hinzugefügt.

- Die [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) -oder [Create](../../mfc/reference/cpropertysheet-class.md#create) -Funktion des Eigenschaften Blatts wurde aufgerufen.

- Der Benutzer hat diese Seite ausgewählt (im Registerkarten Format).

`Construct` Wird aufgerufen, wenn einer der anderen Klassenkonstruktoren nicht aufgerufen wurde. Die `Construct` Member-Funktion ist flexibel, da Sie die Parameter Anweisung leer lassen und dann mehrere Parameter und die Konstruktion an einem beliebigen Punkt im Code angeben können.

Sie müssen verwenden `Construct` , wenn Sie mit Arrays arbeiten, und Sie müssen `Construct` für jedes Element des Arrays aufzurufen, damit den Datenmembern ordnungsgemäße Werte zugewiesen werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]

##  <a name="cpropertypage"></a>CPropertyPage:: CPropertyPage

Erstellt ein `CPropertyPage`-Objekt.

```
CPropertyPage();

explicit CPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

explicit CPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

CPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

CPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));
```

### <a name="parameters"></a>Parameter

*nIDTemplate*<br/>
ID der Vorlage, die für diese Seite verwendet wird.

*nIDCaption*<br/>
ID des Namens, der auf der Registerkarte für diese Seite platziert werden soll. Wenn der Wert 0 ist, wird der Name aus der Dialogfeld Vorlage für diese Seite entnommen.

*dwSize*<br/>
*lpsztemplatename* Verweist auf eine Zeichenfolge, die den Namen der Vorlage für diese Seite enthält. Lässt keine NULL-Werte zu.

*nIDHeaderTitle*<br/>
ID des Namens, der an der Titel Position des Eigenschaften Seiten Headers platziert werden soll.

*nIDHeaderSubTitle*<br/>
ID des Namens, der in der Untertitel Position des Header der Eigenschaften Seite platziert werden soll.

### <a name="remarks"></a>Hinweise

Das-Objekt wird angezeigt, nachdem alle der folgenden Bedingungen erfüllt sind:

- Die Seite wurde mithilfe von [CPropertySheet:: addPage](../../mfc/reference/cpropertysheet-class.md#addpage)zu einem Eigenschaften Blatt hinzugefügt.

- Die [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) -oder [Create](../../mfc/reference/cpropertysheet-class.md#create) -Funktion des Eigenschaften Blatts wurde aufgerufen.

- Der Benutzer hat diese Seite ausgewählt (im Registerkarten Format).

Wenn Sie über mehrere Parameter verfügen (z. b. Wenn Sie ein Array verwenden), verwenden Sie [CPropertySheet:: Construct](../../mfc/reference/cpropertysheet-class.md#construct) anstelle von `CPropertyPage`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]

##  <a name="getpsp"></a>CPropertyPage:: getpsp

Ruft die Windows- [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-propsheetpagea_v2) -Struktur ab, `CPropertyPage` die dem-Objekt zugeordnet ist.

```
const PROPSHEETPAGE& GetPSP() const;

PROPSHEETPAGE& GetPSP();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die `PROPSHEETPAGE` -Struktur.

##  <a name="m_psp"></a>CPropertyPage:: m_psp

`m_psp`ist eine-Struktur, deren Member die Merkmale von [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-propsheetpagea_v2)speichern.

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Struktur, um die Darstellung einer Eigenschaften Seite zu initialisieren, nachdem Sie erstellt wurde.

Weitere Informationen zu dieser Struktur, einschließlich einer Auflistung ihrer Member, finden `PROPSHEETPAGE` Sie unter in der Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]

##  <a name="onapply"></a>CPropertyPage:: OnApply

Diese Member-Funktion wird vom Framework aufgerufen, wenn der Benutzer die Schaltfläche "OK" oder "jetzt anwenden" auswählt.

```
virtual BOOL OnApply();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Änderungen akzeptiert werden. andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn das Framework diese Funktion aufruft, werden Änderungen, die an allen Eigenschaften Seiten im Eigenschaften Blatt vorgenommen werden, akzeptiert, das Eigenschaften Blatt behält `OnApply` den Fokus und gibt true zurück (den Wert 1). Bevor `OnApply` vom Framework aufgerufen werden kann, müssen Sie [SetModified](#setmodified) aufgerufen und den Parameter auf true festgelegt haben. Dadurch wird die Schaltfläche jetzt anwenden aktiviert, sobald der Benutzer eine Änderung auf der Eigenschaften Seite vornimmt.

Überschreiben Sie diese Member-Funktion, um anzugeben, welche Aktion das Programm durchführt, wenn der Benutzer auf die Schaltfläche jetzt anwenden klickt Beim Überschreiben sollte die Funktion true zurückgeben, um Änderungen zu akzeptieren, und false, um zu verhindern, dass Änderungen wirksam werden.

Die Standard Implementierung von `OnApply` - `OnOK`aufrufen.

Weitere Informationen zu Benachrichtigungs Meldungen, die gesendet werden, wenn der Benutzer die Schaltfläche "jetzt anwenden" oder "OK" in einem Eigenschaften Blatt drückt, finden Sie unter [PSN_APPLY](/windows/desktop/Controls/psn-apply) im Windows SDK.

### <a name="example"></a>Beispiel

  Sehen Sie sich das Beispiel für [CPropertyPage:: OnOK](#onok)an.

##  <a name="oncancel"></a>CPropertyPage:: OnCancel

Diese Member-Funktion wird von Framework aufgerufen, wenn die Schaltfläche Abbrechen ausgewählt wird.

```
virtual void OnCancel();
```

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Member-Funktion, um Schaltflächen Aktionen für die Ausführung Der Standardwert negiert alle Änderungen, die vorgenommen wurden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]

##  <a name="onkillactive"></a>CPropertyPage:: OnKillActive

Diese Member-Funktion wird von Framework aufgerufen, wenn die Seite nicht mehr die aktive Seite ist.

```
virtual BOOL OnKillActive();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Daten erfolgreich aktualisiert wurden, andernfalls 0.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Member-Funktion, um spezielle Daten Validierungs Tasks auszuführen.

Die Standard Implementierung dieser Member-Funktion kopiert die Einstellungen aus den Steuerelementen auf der Eigenschaften Seite in die Element Variablen der Eigenschaften Seite. Wenn die Daten aufgrund eines DDV-Fehlers (Dialog Datenüberprüfung) nicht erfolgreich aktualisiert wurden, behält die Seite den Fokus.

Nachdem diese Member-Funktion erfolgreich zurückgegeben wurde, ruft das Framework die [OnOK](#onok) -Funktion der Seite auf.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]

##  <a name="onok"></a>CPropertyPage:: OnOK

Diese Member-Funktion wird vom Framework aufgerufen, wenn der Benutzer entweder die Schaltfläche "OK" oder "jetzt anwenden" auswählt, unmittelbar nachdem das Framework [OnKillActive](#onkillactive)aufgerufen hat.

```
virtual void OnOK();
```

### <a name="remarks"></a>Hinweise

Wenn der Benutzer entweder die Schaltfläche OK oder die Schaltfläche jetzt anwenden auswählt, empfängt das Framework die [PSN_APPLY](/windows/desktop/Controls/psn-apply) -Benachrichtigung von der Eigenschaften Seite. Der-Vorgang `OnOK` wird nicht durchgeführt, wenn Sie [CPropertySheet::P ressbutton](../../mfc/reference/cpropertysheet-class.md#pressbutton) aufrufen, da die-Eigenschaften Seite die Benachrichtigung in diesem Fall nicht sendet.

Überschreiben Sie diese Member-Funktion, um zusätzliches Verhalten zu implementieren, das für die derzeit aktive Seite spezifisch ist, wenn der Benutzer das gesamte Eigenschaften Blatt schließt.

Die Standard Implementierung dieser Member-Funktion markiert die Seite als "Clean", um widerzuspiegeln, dass die Daten `OnKillActive` in der Funktion aktualisiert wurden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]

##  <a name="onquerycancel"></a>CPropertyPage:: OnQueryCancel

Diese Member-Funktion wird vom Framework aufgerufen, wenn der Benutzer auf die Schaltfläche Abbrechen klickt und bevor die Aktion abbrechen stattfindet.

```
virtual BOOL OnQueryCancel();
```

### <a name="return-value"></a>Rückgabewert

Gibt false zurück, um den Abbruch Vorgang zu verhindern, oder true, um dies zuzulassen.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, die das Programm annimmt, wenn der Benutzer auf die Schaltfläche Abbrechen klickt

Die Standard Implementierung von `OnQueryCancel` gibt true zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]

##  <a name="onreset"></a>CPropertyPage:: onreset

Diese Member-Funktion wird vom Framework aufgerufen, wenn der Benutzer die Schaltfläche Abbrechen auswählt.

```
virtual void OnReset();
```

### <a name="remarks"></a>Hinweise

Wenn das Framework diese Funktion aufruft, werden Änderungen an allen Eigenschaften Seiten, die zuvor durch den Benutzer vorgenommen wurden, die zuvor die Schaltfläche jetzt anwenden ausgewählt haben, verworfen, und das Eigenschaften Blatt behält den Fokus.

Überschreiben Sie diese Element Funktion, um anzugeben, welche Aktion das Programm durchführt, wenn der Benutzer auf die Schaltfläche Abbrechen klickt.

Die Standard Implementierung von `OnReset` führt keine Aktion aus.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPropertyPage:: OnCancel](#oncancel).

##  <a name="onsetactive"></a>CPropertyPage:: OnSetActive

Diese Member-Funktion wird vom Framework aufgerufen, wenn die Seite vom Benutzer ausgewählt und zur aktiven Seite wird.

```
virtual BOOL OnSetActive();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Seite erfolgreich festgelegt wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Member-Funktion, um Aufgaben auszuführen, wenn eine Seite aktiviert wird. Durch die Überschreibung dieser Member-Funktion wird in der Regel die Standardversion nach dem Aktualisieren von Datenmembern aufgerufen, damit die Seiten Steuerelemente mit den neuen Daten aktualisiert werden können.

Die Standard Implementierung erstellt das Fenster für die Seite, wenn es nicht bereits erstellt wurde, und macht es zur aktiven Seite.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPropertySheet:: setfinishtext](../../mfc/reference/cpropertysheet-class.md#setfinishtext).

##  <a name="onwizardback"></a>CPropertyPage:: onwizardback

Diese Member-Funktion wird vom Framework aufgerufen, wenn der Benutzer auf die Schaltfläche "zurück" in einem Assistenten klickt.

```
virtual LRESULT OnWizardBack();
```

### <a name="return-value"></a>Rückgabewert

0, um automatisch mit der nächsten Seite fortzufahren. -1, um zu verhindern, dass die Seite geändert wird. Um zu einer anderen Seite als der nächsten zu springen, geben Sie den Bezeichner des Dialog Felds an, das angezeigt werden soll.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, die der Benutzer beim Drücken der Schaltfläche "zurück" ausführen muss.

Weitere Informationen zum Erstellen eines Eigenschaften Blatts für einen Assistenten finden Sie unter [CPropertySheet::](../../mfc/reference/cpropertysheet-class.md#setwizardmode)"".

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]

##  <a name="onwizardfinish"></a>CPropertyPage:: onwizardfinish

Diese Member-Funktion wird von Framework aufgerufen, wenn der Benutzer auf die Schaltfläche Fertigstellen in einem Assistenten klickt.

```
virtual BOOL OnWizardFinish();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Eigenschaften Blatt gelöscht wird, wenn der Assistent abgeschlossen ist. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Wenn ein Benutzer auf die Schaltfläche **Fertig** stellen in einem Assistenten klickt, ruft das Framework diese Funktion auf. Wenn `OnWizardFinish` true (einen Wert ungleich 0 (null)) zurückgibt, kann das Eigenschaften Blatt zerstört (aber nicht zerstört) werden. Ruft `DestroyWindow` auf, um das Eigenschaften Blatt zu zerstören. Rufen `DestroyWindow` Sie nicht aus `OnWizardFinish`auf. Dadurch werden Heap Beschädigungen oder andere Fehler verursacht.

Sie können diese Element Funktion überschreiben, um eine Aktion anzugeben, die der Benutzer beim Drücken der Schaltfläche Fertigstellen ausführen muss. Wenn Sie diese Funktion überschreiben, geben Sie false zurück, um zu verhindern, dass das Eigenschaften Blatt zerstört wird.

Weitere Informationen zu Benachrichtigungs Meldungen, die gesendet werden, wenn der Benutzer die Schaltfläche Fertigstellen auf einem Eigenschaften Blatt eines Assistenten drückt, finden Sie unter [PSN_WIZFINISH](/windows/desktop/Controls/psn-wizfinish) im Windows SDK.

Weitere Informationen zum Erstellen eines Eigenschaften Blatts für einen Assistenten finden Sie unter [CPropertySheet::](../../mfc/reference/cpropertysheet-class.md#setwizardmode)"".

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]

[!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]

[!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]

[!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]

##  <a name="onwizardnext"></a>CPropertyPage:: onwizardnext

Diese Member-Funktion wird von Framework aufgerufen, wenn der Benutzer auf die Schaltfläche weiter in einem Assistenten klickt.

```
virtual LRESULT OnWizardNext();
```

### <a name="return-value"></a>Rückgabewert

0, um automatisch mit der nächsten Seite fortzufahren. -1, um zu verhindern, dass die Seite geändert wird. Um zu einer anderen Seite als der nächsten zu springen, geben Sie den Bezeichner des Dialog Felds an, das angezeigt werden soll.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, die der Benutzer beim Drücken der Schaltfläche weiter ausführen muss.

Weitere Informationen zum Erstellen eines Eigenschaften Blatts für einen Assistenten finden Sie unter [CPropertySheet::](../../mfc/reference/cpropertysheet-class.md#setwizardmode)"".

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]

##  <a name="querysiblings"></a>CPropertyPage:: querysiblings

Diese Member-Funktion wird aufgerufen, um eine Meldung an jede Seite im Eigenschaften Blatt weiterzuleiten.

```
LRESULT QuerySiblings(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*wParam*<br/>
Gibt zusätzliche Nachrichten abhängige Informationen an.

*lParam*<br/>
Gibt zusätzliche Nachrichten abhängige Informationen an.

### <a name="return-value"></a>Rückgabewert

Der Wert ungleich 0 (null) von einer Seite im Eigenschaften Blatt oder 0, wenn alle Seiten den Wert 0 zurückgeben.

### <a name="remarks"></a>Hinweise

Wenn eine Seite einen Wert ungleich 0 (null) zurückgibt, sendet das Eigenschaften Blatt die Nachricht nicht an nachfolgende Seiten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]

[!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]

##  <a name="setmodified"></a>CPropertyPage:: SetModified

Diese Member-Funktion wird aufgerufen, um die Schaltfläche "jetzt anwenden" zu aktivieren oder zu deaktivieren, je nachdem, ob die Einstellungen auf der Eigenschaften Seite auf das entsprechende externe Objekt angewendet werden sollen.

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>Parameter

*bchanged*<br/>
TRUE, um anzugeben, dass die Einstellungen der Eigenschaften Seite seit der letzten Anwendung geändert wurden. FALSE, um anzugeben, dass die Eigenschaften Seiteneinstellungen angewendet wurden, oder sollte ignoriert werden.

### <a name="remarks"></a>Hinweise

Das Framework verfolgt, welche Seiten "geändert" werden, d. h. Eigenschaften Seiten, für die Sie aufgerufen `SetModified( TRUE )`haben. Die Schaltfläche jetzt anwenden wird immer aktiviert, wenn Sie `SetModified( TRUE )` für eine der Seiten aufzurufen. Die Schaltfläche jetzt anwenden wird deaktiviert, wenn Sie `SetModified( FALSE )` für eine der Seiten aufzurufen, aber nur, wenn keine der anderen Seiten "Dirty" ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CDialog-Klasse](../../mfc/reference/cdialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CPropertySheet-Klasse](../../mfc/reference/cpropertysheet-class.md)<br/>
[CDialog-Klasse](../../mfc/reference/cdialog-class.md)
