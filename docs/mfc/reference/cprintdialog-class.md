---
title: CPrintDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPrintDialog
- AFXDLGS/CPrintDialog
- AFXDLGS/CPrintDialog::CPrintDialog
- AFXDLGS/CPrintDialog::CreatePrinterDC
- AFXDLGS/CPrintDialog::DoModal
- AFXDLGS/CPrintDialog::GetCopies
- AFXDLGS/CPrintDialog::GetDefaults
- AFXDLGS/CPrintDialog::GetDeviceName
- AFXDLGS/CPrintDialog::GetDevMode
- AFXDLGS/CPrintDialog::GetDriverName
- AFXDLGS/CPrintDialog::GetFromPage
- AFXDLGS/CPrintDialog::GetPortName
- AFXDLGS/CPrintDialog::GetPrinterDC
- AFXDLGS/CPrintDialog::GetToPage
- AFXDLGS/CPrintDialog::PrintAll
- AFXDLGS/CPrintDialog::PrintCollate
- AFXDLGS/CPrintDialog::PrintRange
- AFXDLGS/CPrintDialog::PrintSelection
- AFXDLGS/CPrintDialog::m_pd
helpviewer_keywords:
- CPrintDialog [MFC], CPrintDialog
- CPrintDialog [MFC], CreatePrinterDC
- CPrintDialog [MFC], DoModal
- CPrintDialog [MFC], GetCopies
- CPrintDialog [MFC], GetDefaults
- CPrintDialog [MFC], GetDeviceName
- CPrintDialog [MFC], GetDevMode
- CPrintDialog [MFC], GetDriverName
- CPrintDialog [MFC], GetFromPage
- CPrintDialog [MFC], GetPortName
- CPrintDialog [MFC], GetPrinterDC
- CPrintDialog [MFC], GetToPage
- CPrintDialog [MFC], PrintAll
- CPrintDialog [MFC], PrintCollate
- CPrintDialog [MFC], PrintRange
- CPrintDialog [MFC], PrintSelection
- CPrintDialog [MFC], m_pd
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
ms.openlocfilehash: 1f4a4dbec9a1c79ac1e0cec925156ae7db4c293e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502901"
---
# <a name="cprintdialog-class"></a>CPrintDialog-Klasse

Kapselt die Dienste, die vom allgemeinen Windows-Dialogfeld für das Drucken bereitgestellt werden.

## <a name="syntax"></a>Syntax

```
class CPrintDialog : public CCommonDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPrintDialog::CPrintDialog](#cprintdialog)|Erstellt ein `CPrintDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|Erstellt einen Drucker Gerätekontext, ohne das Dialogfeld Drucken anzuzeigen.|
|[CPrintDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht es dem Benutzer, eine Auswahl vorzunehmen.|
|[CPrintDialog::GetCopies](#getcopies)|Ruft die Anzahl der angeforderten Kopien ab.|
|[CPrintDialog::GetDefaults](#getdefaults)|Ruft Geräte Standardwerte ab, ohne ein Dialogfeld anzuzeigen.|
|[CPrintDialog::GetDeviceName](#getdevicename)|Ruft den Namen des aktuell ausgewählten Drucker Geräts ab.|
|[CPrintDialog::GetDevMode](#getdevmode)|Ruft die `DEVMODE` -Struktur ab.|
|[CPrintDialog::GetDriverName](#getdrivername)|Ruft den Namen des aktuell ausgewählten Druckertreibers ab.|
|[CPrintDialog::GetFromPage](#getfrompage)|Ruft die Startseite des Druck Bereichs ab.|
|[CPrintDialog::GetPortName](#getportname)|Ruft den Namen des aktuell ausgewählten Drucker Ports ab.|
|[CPrintDialog::GetPrinterDC](#getprinterdc)|Ruft ein Handle für den Drucker Gerätekontext ab.|
|[CPrintDialog::GetToPage](#gettopage)|Ruft die Endseite des Druck Bereichs ab.|
|[CPrintDialog::PrintAll](#printall)|Bestimmt, ob alle Seiten des Dokuments gedruckt werden.|
|[CPrintDialog::PrintCollate](#printcollate)|Bestimmt, ob sortierte Kopien angefordert werden.|
|[CPrintDialog::PrintRange](#printrange)|Bestimmt, ob nur ein angegebener Seitenbereich gedruckt werden soll.|
|[CPrintDialog::PrintSelection](#printselection)|Bestimmt, ob nur die aktuell ausgewählten Elemente gedruckt werden.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPrintDialog::m_pd](#m_pd)|Eine-Struktur, mit der `CPrintDialog` ein-Objekt angepasst wird.|

## <a name="remarks"></a>Hinweise

Allgemeine Druck Dialogfelder bieten eine einfache Möglichkeit, Druck-und Druck Setup Dialogfelder auf eine Weise zu implementieren, die mit Windows-Standards konsistent ist.

> [!NOTE]
>  Die `CPrintDialogEx` -Klasse kapselt die Dienste, die vom Windows-Druckeigenschaften Blatt bereitgestellt werden. Weitere Informationen finden Sie in der Übersicht über [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) .

`CPrintDialog`die Funktionalität wird durch die von [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)ersetzt, die für die Bereitstellung eines gemeinsamen Dialog Felds sowohl für Druck-als auch für das Einrichten der Seite vorgesehen ist.

Sie können sich auf das Framework verlassen, um viele Aspekte des Druckprozesses für Ihre Anwendung zu bewältigen. In diesem Fall zeigt das Framework automatisch das Windows-Dialogfeld "Allgemein" für den Druck an. Sie können auch das Framework-Handle für die Anwendung drucken lassen, aber das Dialogfeld "allgemeiner Druck" mit dem Dialogfeld "Drucken" außer Kraft setzen. Weitere Informationen zum Verwenden des Frameworks zum Verarbeiten von Druckaufgaben finden Sie im Artikel [Drucken](../../mfc/printing.md).

Wenn Sie möchten, dass Ihre Anwendung den Druck ohne die Einbindung des Frameworks behandelt, können `CPrintDialog` Sie die-Klasse mit dem bereitgestellten Konstruktor "unverändert" verwenden, oder Sie können eine eigene `CPrintDialog` Dialogfeld Klasse von ableiten und einen Konstruktor für Ihre Bedürfnisse schreiben. In beiden Fällen verhalten sich diese Dialogfelder wie Standard-MFC-Dialogfelder, da Sie von der `CCommonDialog`-Klasse abgeleitet sind.

Um ein `CPrintDialog` -Objekt zu verwenden, erstellen Sie zunächst das `CPrintDialog` -Objekt mit dem-Konstruktor. Nachdem das Dialogfeld erstellt wurde, können Sie alle Werte in der [m_pd](#m_pd) -Struktur festlegen oder ändern, um die Werte der Steuerelemente des Dialog Felds zu initialisieren. Die `m_pd` Struktur ist vom Typ [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-pdw). Weitere Informationen zu dieser Struktur finden Sie in der Windows SDK.

`m_pd` Wenn Sie für die `hDevMode` Member und keine eigenen Handles in bereitstellen `hDevNames` , müssen Sie die Windows-Funktion `GlobalFree` für diese Handles aufzurufen, wenn Sie das Dialogfeld verwenden. Wenn Sie die Druck Setup Implementierung von Frameworks verwenden `CWinApp::OnFilePrintSetup`, die von bereitgestellt wird, müssen Sie diese Handles nicht freigeben. Die Handles werden von verwaltet `CWinApp` und im `CWinApp`Dekonstruktor von freigegeben. Es ist nur erforderlich, diese Handles freizugeben, `CPrintDialog` Wenn Sie eigenständig verwenden.

Nachdem Sie die Dialogfeld Steuerelemente initialisiert haben `DoModal` , können Sie die Member-Funktion aufrufen, um das Dialogfeld anzuzeigen und dem Benutzer die Auswahl von Druckoptionen zu ermöglichen. `DoModal`Gibt zurück, ob der Benutzer die Schaltfläche OK (IDOK) oder Abbrechen (IDCANCEL) ausgewählt hat.

Wenn `DoModal` IDOK zurückgibt, können Sie eine der `CPrintDialog`-Member-Funktionen verwenden, um die vom Benutzer eingegebenen Informationen abzurufen.

Die `CPrintDialog::GetDefaults` Member-Funktion ist nützlich, um die aktuellen Drucker Standardwerte abzurufen, ohne ein Dialogfeld anzuzeigen. Diese Member-Funktion erfordert keine Benutzerinteraktion.

Mit der Windows `CommDlgExtendedError` -Funktion können Sie feststellen, ob während der Initialisierung des Dialog Felds ein Fehler aufgetreten ist, und weitere Informationen zum Fehler erhalten. Weitere Informationen zu dieser Funktion finden Sie in der Windows SDK.

`CPrintDialog`basiert auf der kommdlg. DLL-Datei, die in der Windows-Version 3,1 und höher enthalten ist.

Zum Anpassen des Dialog Felds leiten Sie eine Klasse von `CPrintDialog`ab, geben eine benutzerdefinierte Dialogfeld Vorlage an und fügen eine Meldungs Zuordnung hinzu, um die Benachrichtigungs Meldungen von den erweiterten Steuerelementen zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten an die Basisklasse weitergegeben werden. Das Anpassen der Hook-Funktion ist nicht erforderlich.

Sie müssen für jedes Dialogfeld eine Klasse ableiten, um die gleiche Nachricht in Abhängigkeit davon zu unterscheiden, ob es sich bei dem Dialogfeld um eine Druck-oder Druck Installation handelt. Sie müssen auch die Windows `AttachOnSetup` -Funktion außer Kraft setzen, die die Erstellung eines neuen Dialog Felds behandelt, wenn die Schaltfläche Druck Einrichtung innerhalb eines Druck Dialogfelds ausgewählt wird.

Weitere Informationen zum Verwenden von `CPrintDialog`finden Sie unter [Allgemeine Dialog Klassen](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs. h

##  <a name="cprintdialog"></a>CPrintDialog:: CPrintDialog

Erstellt entweder ein Windows-Druck-oder Druck Setup Dialogfeld Objekt.

```
CPrintDialog(
    BOOL bPrintSetupOnly,
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*bPrintSetupOnly*<br/>
Gibt an, ob das Dialogfeld Windows-Standarddruck oder Druck Setup angezeigt wird. Legen Sie diesen Parameter auf "true" fest, um das Standard Dialogfeld Windows-Druck Setup anzuzeigen. Legen Sie diese Einstellung auf false fest, um das Dialogfeld Windows-Druck anzuzeigen. Wenn *bprintsetuponly* auf false festgelegt ist, wird im Dialogfeld Drucken weiterhin das Optionsfeld Druck Setup angezeigt.

*dwFlags*<br/>
Ein oder mehrere Flags, die Sie verwenden können, um die Einstellungen des Dialog Felds mithilfe des bitweisen OR-Operators zu ändern. Beispielsweise legt das Flag PD_ALLPAGES den Standarddruck Bereich auf alle Seiten des Dokuments fest. Weitere Informationen zu diesen Flags finden Sie in der [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-pdw) -Struktur im Windows SDK.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete oder Besitzer Fenster des Dialog Felds.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion erstellt nur das-Objekt. Verwenden Sie `DoModal` die Member-Funktion, um das Dialogfeld anzuzeigen.

Beachten Sie Folgendes: Wenn Sie den Konstruktor aufrufen, bei dem *bprintsetuponly* auf false festgelegt ist, wird das PD_RETURNDC-Flag automatisch verwendet. Nach dem `DoModal`aufrufen `GetDefaults`von, `GetPrinterDC`oder wird ein Drucker-DC in `m_pd.hDC`zurückgegeben. Dieser Domänen Controller muss durch einen Aufruf von [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) vom Aufrufer `CPrintDialog`von freigegeben werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]

##  <a name="createprinterdc"></a>CPrintDialog:: kreateprinterdc

Erstellt einen Drucker Gerätekontext (DC) aus den [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) -und [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) -Strukturen.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Rückgabewert

Handle für den neu erstellten Drucker Gerätekontext.

### <a name="remarks"></a>Hinweise

Es wird davon ausgegangen, dass es sich bei diesem DC um den aktuellen Drucker-DC handelt, und alle anderen zuvor erhaltenen Drucker-DCS müssen vom Benutzer gelöscht werden. Diese Funktion kann aufgerufen werden, und der resultierende DC wird verwendet, ohne dass das Dialogfeld "Drucken" angezeigt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]

##  <a name="domodal"></a>CPrintDialog::D omodal

Zeigt das Dialogfeld "allgemeiner Windows-Druck" an und ermöglicht dem Benutzer die Auswahl verschiedener Druckoptionen, wie z. b. die Anzahl von Kopien, den Seitenbereich und ob Kopien sortiert werden sollen.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

IDOK oder IDCANCEL. Wenn IDCANCEL zurückgegeben wird, rufen Sie die Windows-Funktion [commdlgextendederror](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) auf, um zu bestimmen, ob ein Fehler aufgetreten ist.

IDOK und IDCANCEL sind Konstanten, die angeben, ob der Benutzer die Schaltfläche OK oder Abbrechen ausgewählt hat.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Druck Dialogfeld Optionen durch Festlegen der Elemente der `m_pd` Struktur initialisieren möchten, sollten Sie dies vor dem Aufrufen `DoModal`von tun, nachdem das Dialogfeld Objekt erstellt wurde.

Nach dem `DoModal`Aufrufen von können Sie andere Element Funktionen aufrufen, um die Einstellungen oder die Eingabeinformationen vom Benutzer in das Dialogfeld abzurufen.

Beachten Sie Folgendes: Wenn Sie den Konstruktor aufrufen, bei dem *bprintsetuponly* auf false festgelegt ist, wird das PD_RETURNDC-Flag automatisch verwendet. Nach dem `DoModal`aufrufen `GetDefaults`von, `GetPrinterDC`oder wird ein Drucker-DC in `m_pd.hDC`zurückgegeben. Dieser Domänen Controller muss durch einen Aufruf von [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) vom Aufrufer `CPrintDialog`von freigegeben werden.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPrintDialog:: kreateprinterdc](#createprinterdc).

##  <a name="getcopies"></a>CPrintDialog:: getkopien

Ruft die Anzahl der angeforderten Kopien ab.

```
int GetCopies() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der angeforderten Kopien.

### <a name="remarks"></a>Hinweise

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um die Anzahl der angeforderten Kopien abzurufen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPrintDialog::P rintcollate](#printcollate).

##  <a name="getdefaults"></a>CPrintDialog:: getdefaults

Ruft die Geräte Standardwerte des Standard Druckers ab, ohne ein Dialogfeld anzuzeigen.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Die abgerufenen Werte werden in die `m_pd` Struktur eingefügt.

In einigen Fällen ruft ein Aufrufen dieser Funktion den [Konstruktor](#cprintdialog) für `CPrintDialog` auf, wobei *bprintsetuponly* auf false festgelegt ist. In diesen Fällen werden ein Drucker-DC `hDevNames` und `hDevMode` und (zwei Handles, die `m_pd` sich im Datenmember befinden) automatisch zugeordnet.

Wenn der Konstruktor für `CPrintDialog` mit *bprintsetuponly* auf false festgelegt wurde, gibt diese Funktion nicht nur zurück `hDevNames` und `hDevMode` befindet sich `m_pd.hDevNames` in `m_pd.hDevMode`und) an den Aufrufer, sondern gibt auch einen Drucker-DC in `m_pd.hDC`. Es liegt in der Verantwortung des Aufrufers, den Drucker-DC zu löschen und die Windows [Global Free](/windows/win32/api/winbase/nf-winbase-globalfree) -Funktion für die Handles aufzurufen `CPrintDialog` , wenn Sie mit dem-Objekt fertig sind.

### <a name="example"></a>Beispiel

Dieses Code Fragment Ruft den Gerätekontext des Standard Druckers ab und meldet dem Benutzer die Auflösung des Druckers in dpi (Punkte pro Zoll). (Dieses Attribut der Funktionen des Druckers wird häufig als dpi bezeichnet.)

[!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]

##  <a name="getdevicename"></a>CPrintDialog:: GetDeviceName

Ruft den Namen des aktuell ausgewählten Drucker Geräts ab.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des aktuell ausgewählten Druckers.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion nach dem Aufrufen von [DoModal](#domodal) auf, um den Namen des aktuell ausgewählten Druckers abzurufen, oder nachdem Sie [getdefaults](#getdefaults) aufgerufen haben, um die aktuellen Geräte Standardwerte des Standard Druckers abzurufen. Verwenden Sie einen Zeiger auf `CString` das Objekt, `GetDeviceName` das von als Wert `lpszDeviceName` von zurückgegeben wird, in einem Aufrufen von [CDC:: anatedc](../../mfc/reference/cdc-class.md#createdc).

### <a name="example"></a>Beispiel

Dieses Code Fragment zeigt den Standarddrucker Namen des Benutzers und den Port an, mit dem er verbunden ist, zusammen mit dem spoolernamen, den der Drucker verwendet. Der Code zeigt möglicherweise ein Meldungs Feld mit dem Hinweis "Ihr Standarddrucker ist HP LaserJet IIIP on \\\server\share using winspool", z. b.

[!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]

##  <a name="getdevmode"></a>CPrintDialog:: getdevmode

Ruft die `DEVMODE` -Struktur ab.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Rückgabewert

Die [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) -Datenstruktur, die Informationen über die Geräte Initialisierung und die Umgebung eines Druck Treibers enthält. Sie müssen den von dieser Struktur erstellten Arbeitsspeicher mit der Funktion Windows [globalunlock](/windows/win32/api/winbase/nf-winbase-globalunlock) entsperren, die im Windows SDK beschrieben wird.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion nach dem Aufrufen von " [DoModal](#domodal) " oder " [getdefaults](#getdefaults) " auf, um Informationen zum Druck Gerät abzurufen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPrintDialog::P rintcollate](#printcollate).

##  <a name="getdrivername"></a>CPrintDialog:: getDriverName

Ruft den Namen des aktuell ausgewählten Druckertreibers ab.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` , der den Namen des System definierten Treibers angibt.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion nach dem Aufrufen von " [DoModal](#domodal) " oder " [getdefaults](#getdefaults) " auf, um den Namen des System definierten Drucker-Gerätetreibers abzurufen. Verwenden Sie einen Zeiger auf `CString` das Objekt, `GetDriverName` das von als Wert `lpszDriverName` von zurückgegeben wird, in einem Aufrufen von [CDC:: anatedc](../../mfc/reference/cdc-class.md#createdc).

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPrintDialog:: GetDeviceName](#getdevicename).

##  <a name="getfrompage"></a>CPrintDialog:: GetFromPage

Ruft die Startseite des Druck Bereichs ab.

```
int GetFromPage() const;
```

### <a name="return-value"></a>Rückgabewert

Die Nummer der Startseite im Bereich der zu druckenden Seiten.

### <a name="remarks"></a>Hinweise

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um die Anfangs Seitenzahl im Bereich der zu druckenden Seiten abzurufen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPrintDialog:: m_pd](#m_pd).

##  <a name="getportname"></a>CPrintDialog:: getportname

Ruft den Namen des aktuell ausgewählten Drucker Ports ab.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des aktuell ausgewählten Drucker Anschlusses.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion nach dem Aufrufen von " [DoModal](#domodal) " oder " [getdefaults](#getdefaults) " auf, um den Namen des aktuell ausgewählten Drucker Ports abzurufen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPrintDialog:: GetDeviceName](#getdevicename).

##  <a name="getprinterdc"></a>CPrintDialog:: getPrinterDC

Ruft ein Handle für den Drucker Gerätekontext ab.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für den Drucker Gerätekontext, wenn der Vorgang erfolgreich war. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Wenn der *bprintsetuponly* -Parameter des `CPrintDialog` Konstruktors false war (was anzeigt, dass das Dialogfeld Drucken `GetPrinterDC` angezeigt wird), gibt ein Handle für den Drucker Gerätekontext zurück. Sie müssen die Windows [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) -Funktion aufrufen, um den Gerätekontext zu löschen, wenn Sie ihn nicht mehr benötigen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]

##  <a name="gettopage"></a>CPrintDialog:: GetToPage

Ruft die Endseite des Druck Bereichs ab.

```
int GetToPage() const;
```

### <a name="return-value"></a>Rückgabewert

Die Endseiten Zahl im Seitenbereich, der gedruckt werden soll.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion auf `DoModal` , nachdem Sie aufgerufen haben, um die Endseiten Zahl im zu druckenden Seitenbereich abzurufen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPrintDialog:: m_pd](#m_pd).

##  <a name="m_pd"></a>CPrintDialog:: m_pd

Eine-Struktur, deren Elemente die Merkmale des Dialog Objekts speichern.

```
PRINTDLG& m_pd;
```

### <a name="remarks"></a>Hinweise

Nachdem Sie ein `CPrintDialog` -Objekt erstellt haben, `m_pd` können Sie verwenden, um verschiedene Aspekte des Dialog Felds festzulegen, bevor Sie die [DoModal](#domodal) -Member-Funktion aufrufen. Weitere Informationen zur `m_pd` -Struktur finden Sie unter [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-pdw) in der Windows SDK.

Wenn Sie den `m_pd` Datenmember direkt ändern, überschreiben Sie jedes Standardverhalten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]

##  <a name="printall"></a>CPrintDialog::P rintall

Bestimmt, ob alle Seiten des Dokuments gedruckt werden.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn alle Seiten im Dokument gedruckt werden sollen. andernfalls 0.

### <a name="remarks"></a>Hinweise

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um zu bestimmen, ob alle Seiten im Dokument gedruckt werden sollen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPrintDialog:: m_pd](#m_pd).

##  <a name="printcollate"></a>CPrintDialog::P rintcollate

Bestimmt, ob sortierte Kopien angefordert werden.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn der Benutzer im Dialogfeld das Kontrollkästchen COLLATE auswählt. andernfalls 0.

### <a name="remarks"></a>Hinweise

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um zu bestimmen, ob der Drucker alle gedruckten Kopien des Dokuments anordnen soll.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]

##  <a name="printrange"></a>CPrintDialog::P rintrange

Bestimmt, ob nur ein angegebener Seitenbereich gedruckt werden soll.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn nur ein Seitenbereich im Dokument gedruckt werden soll. andernfalls 0.

### <a name="remarks"></a>Hinweise

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um zu bestimmen, ob nur ein Bereich von Seiten im Dokument gedruckt werden soll.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPrintDialog:: m_pd](#m_pd).

##  <a name="printselection"></a>CPrintDialog::P rintselection

Bestimmt, ob nur die aktuell ausgewählten Elemente gedruckt werden.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn nur die ausgewählten Elemente gedruckt werden sollen. andernfalls 0.

### <a name="remarks"></a>Hinweise

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um zu bestimmen, ob nur die aktuell ausgewählten Elemente gedruckt werden sollen

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPrintDialog:: m_pd](#m_pd).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo-Struktur](../../mfc/reference/cprintinfo-structure.md)
