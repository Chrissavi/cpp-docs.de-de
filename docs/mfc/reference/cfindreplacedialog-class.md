---
title: CFindReplaceDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
helpviewer_keywords:
- CFindReplaceDialog [MFC], CFindReplaceDialog
- CFindReplaceDialog [MFC], Create
- CFindReplaceDialog [MFC], FindNext
- CFindReplaceDialog [MFC], GetFindString
- CFindReplaceDialog [MFC], GetNotifier
- CFindReplaceDialog [MFC], GetReplaceString
- CFindReplaceDialog [MFC], IsTerminating
- CFindReplaceDialog [MFC], MatchCase
- CFindReplaceDialog [MFC], MatchWholeWord
- CFindReplaceDialog [MFC], ReplaceAll
- CFindReplaceDialog [MFC], ReplaceCurrent
- CFindReplaceDialog [MFC], SearchDown
- CFindReplaceDialog [MFC], m_fr
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
ms.openlocfilehash: 71234adec214bcbf5d42090edb582a7e5dd552b0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506524"
---
# <a name="cfindreplacedialog-class"></a>CFindReplaceDialog-Klasse

Ermöglicht die Implementierung von Dialogfeldern zum Suchen und Ersetzen von Standard Zeichenfolgen in Ihrer Anwendung.

## <a name="syntax"></a>Syntax

```
class CFindReplaceDialog : public CCommonDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|Mit dieser Funktion können Sie ein `CFindReplaceDialog` -Objekt erstellen.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFindReplaceDialog::Create](#create)|Erstellt ein `CFindReplaceDialog` Dialogfeld und zeigt es an.|
|[CFindReplaceDialog::FindNext](#findnext)|Mit dieser Funktion können Sie feststellen, ob der Benutzer das nächste Vorkommen der Such Zeichenfolge finden möchte.|
|[CFindReplaceDialog::GetFindString](#getfindstring)|Rufen Sie diese Funktion auf, um die aktuelle Such Zeichenfolge abzurufen.|
|[CFindReplaceDialog::GetNotifier](#getnotifier)|Rufen Sie diese Funktion auf, `FINDREPLACE` um die Struktur in Ihrem registrierten Nachrichten Handler abzurufen.|
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|Rufen Sie diese Funktion auf, um die aktuelle Replace-Zeichenfolge abzurufen.|
|[CFindReplaceDialog::IsTerminating](#isterminating)|Diese Funktion wird aufgerufen, um zu bestimmen, ob das Dialogfeld beendet wird.|
|[CFindReplaceDialog::MatchCase](#matchcase)|Mit dieser Funktion können Sie ermitteln, ob der Benutzer genau mit der Groß-/Kleinschreibung der Such Zeichenfolge übereinstimmen möchte.|
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|Diese Funktion wird aufgerufen, um zu bestimmen, ob der Benutzer nur ganze Wörter zuordnen möchte.|
|[CFindReplaceDialog::ReplaceAll](#replaceall)|Mit dieser Funktion können Sie feststellen, ob der Benutzer alle Vorkommen der Zeichenfolge ersetzen soll.|
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|Mit dieser Funktion können Sie feststellen, ob der Benutzer das aktuelle Wort ersetzen soll.|
|[CFindReplaceDialog::SearchDown](#searchdown)|Mit dieser Funktion können Sie feststellen, ob die Suche nach unten fortgesetzt werden soll.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CFindReplaceDialog::m_fr](#m_fr)|Eine-Struktur, mit der `CFindReplaceDialog` ein-Objekt angepasst wird.|

## <a name="remarks"></a>Hinweise

Im Gegensatz zu den anderen allgemeinen Windows- `CFindReplaceDialog` Dialogfeldern sind Objekte nicht modesfähig, sodass Benutzer mit anderen Fenstern interagieren können, während Sie auf dem Bildschirm angezeigt werden. Es gibt zwei Arten von `CFindReplaceDialog` Objekten: Dialogfelder Suchen und Dialogfelder Suchen/ersetzen. Obwohl in den Dialogfeldern das Eingeben von Such-und Such-/Ersetzungs Zeichenfolgen möglich ist, führen Sie keine Such-und Ersetzungs Funktionen aus. Sie müssen diese der Anwendung hinzufügen.

Verwenden Sie zum `CFindReplaceDialog` Erstellen eines-Objekts den bereitgestellten Konstruktor (der keine Argumente aufweist). Da es sich hierbei um ein nicht modalem Dialogfeld handelt, weisen Sie das-Objekt dem Heap mithilfe des **New** -Operators anstelle des Stapels zu.

Sobald ein `CFindReplaceDialog` -Objekt erstellt wurde, müssen Sie die [Create](#create) Member-Funktion aufrufen, um das Dialogfeld zu erstellen und anzuzeigen.

Verwenden Sie die [m_fr](#m_fr) -Struktur, um das Dialogfeld zu `Create`initialisieren, bevor Sie aufrufen. Die `m_fr` Struktur ist vom Typ " [FindReplace](/windows/win32/api/commdlg/ns-commdlg-findreplacew)". Weitere Informationen zu dieser Struktur finden Sie in der Windows SDK.

Damit das übergeordnete Fenster über Anforderungen zum Suchen/Ersetzen benachrichtigt werden kann, müssen Sie die Windows [RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew) -Funktion verwenden und das [ON_REGISTERED_MESSAGE](message-map-macros-mfc.md#on_registered_message) Message-Map-Makro in ihrem Rahmen Fenster verwenden, das diese registrierte Nachricht verarbeitet.

Sie können feststellen, ob der Benutzer das Dialogfeld mit der `IsTerminating` Member-Funktion beendet hat.

`CFindReplaceDialog`basiert auf der kommdlg. DLL-Datei, die in der Windows-Version 3,1 und höher enthalten ist.

Zum Anpassen des Dialog Felds leiten Sie eine Klasse von `CFindReplaceDialog`ab, geben eine benutzerdefinierte Dialogfeld Vorlage an und fügen eine Meldungs Zuordnung hinzu, um die Benachrichtigungs Meldungen von den erweiterten Steuerelementen zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten an die Basisklasse übermittelt werden.

Das Anpassen der Hook-Funktion ist nicht erforderlich.

Weitere Informationen zum Verwenden von `CFindReplaceDialog`finden Sie unter [Allgemeine Dialog Klassen](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFindReplaceDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs. h

##  <a name="cfindreplacedialog"></a>CFindReplaceDialog:: CFindReplaceDialog

Erstellt ein `CFindReplaceDialog`-Objekt.

```
CFindReplaceDialog();
```

### <a name="remarks"></a>Hinweise

Da es `CFindReplaceDialog` sich bei dem Objekt um ein nicht modalem Dialogfeld handelt, müssen Sie es mithilfe des **New** -Operators auf dem Heap erstellen.

Während der Zerstörung versucht das Framework, einen **Lösch** Vorgang für den Zeiger auf das Dialogfeld auszuführen. Wenn Sie das Dialogfeld auf dem Stapel erstellt haben, ist **dieser** Zeiger nicht vorhanden, und es kann ein nicht definiertes Verhalten entstehen.

Weitere Informationen zur Erstellung von `CFindReplaceDialog` Objekten finden Sie in der Übersicht über [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) . Verwenden Sie die [CFindReplaceDialog:: Create](#create) Member-Funktion, um das Dialogfeld anzuzeigen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]

##  <a name="create"></a>CFindReplaceDialog:: Create

Erstellt und zeigt ein Dialogfeld Objekt suchen oder Suchen/Ersetzen an, abhängig vom Wert von `bFindDialogOnly`.

```
virtual BOOL Create(
    BOOL bFindDialogOnly,
    LPCTSTR lpszFindWhat,
    LPCTSTR lpszReplaceWith = NULL,
    DWORD dwFlags = FR_DOWN,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*bFindDialogOnly*<br/>
Legen Sie diesen Parameter auf "true" fest, um ein Dialogfeld **Suchen** anzuzeigen. Legen Sie diese Einstellung auf "false" fest, um ein Dialogfeld **Suchen/Ersetzen** anzuzeigen.

*lpszFindWhat*<br/>
Ein Zeiger auf die Standard Such Zeichenfolge, wenn das Dialogfeld angezeigt wird. Wenn der Wert NULL ist, enthält das Dialogfeld keine Standard Such Zeichenfolge.

*lpszReplaceWith*<br/>
Zeiger auf die standardmäßige Ersetzungs Zeichenfolge, wenn das Dialogfeld angezeigt wird. Wenn der Wert NULL ist, enthält das Dialogfeld keine standardmäßige Ersetzungs Zeichenfolge.

*dwFlags*<br/>
Ein oder mehrere Flags, die Sie verwenden können, um die Einstellungen des Dialog Felds mithilfe des bitweisen OR-Operators zu ändern. Der Standardwert ist FR_DOWN. er gibt an, dass die Suche nach unten fortgesetzt werden soll. Weitere Informationen zu diesen Flags finden Sie in der [FindReplace](/windows/win32/api/commdlg/ns-commdlg-findreplacew) -Struktur in der Windows SDK.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete oder Besitzer Fenster des Dialog Felds. Dies ist das Fenster, das die spezielle Nachricht empfängt, die angibt, dass eine Aktion zum Suchen/Ersetzen angefordert wird. Wenn der Wert NULL ist, wird das Hauptfenster der Anwendung verwendet.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Dialogfeld Objekt erfolgreich erstellt wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Damit das übergeordnete Fenster über Anforderungen zum Suchen/Ersetzen benachrichtigt werden kann, müssen Sie die Windows [RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew) -Funktion verwenden, deren Rückgabewert eine Nachrichten-ID ist, die für die Instanz der Anwendung eindeutig ist. Das Rahmen Fenster sollte über einen Meldungs Zuordnungs Eintrag verfügen, der die `OnFindReplace` Rückruffunktion deklariert (im folgenden Beispiel), die diese registrierte Nachricht verarbeitet. Das folgende Code Fragment ist ein Beispiel dafür, wie dies für eine Frame Fenster Klasse mit dem `CMyRichEditView`Namen erfolgt:

[!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]

[!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]

[!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]

In Ihrer `OnFindReplace` Funktion interpretieren Sie die Absichten des Benutzers mithilfe der [CFindReplaceDialog:: FindNext](#findnext) -Methode und der [CFindReplaceDialog:: IsTerminating](#isterminating) -Methode, und Sie erstellen den Code für die Suchen/Ersetzen-Vorgänge.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFindReplaceDialog:: CFindReplaceDialog](#cfindreplacedialog).

##  <a name="findnext"></a>CFindReplaceDialog:: FindNext

Rufen Sie diese Funktion von ihrer Rückruffunktion auf, um zu bestimmen, ob der Benutzer das nächste Vorkommen der Such Zeichenfolge finden möchte.

```
BOOL FindNext() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn der Benutzer das nächste Vorkommen der Such Zeichenfolge finden möchte. andernfalls 0.

##  <a name="getfindstring"></a>CFindReplaceDialog:: getfindstring

Rufen Sie diese Funktion von ihrer Rückruffunktion auf, um die zu suchende Standard Zeichenfolge abzurufen.

```
CString GetFindString() const;
```

### <a name="return-value"></a>Rückgabewert

Die zu suchende Standard Zeichenfolge.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

##  <a name="getnotifier"></a>CFindReplaceDialog:: getnotifier

Rufen Sie diese Funktion auf, um einen Zeiger auf das aktuelle Dialogfeld Suchen Ersetzen abzurufen.

```
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*lParam*<br/>
Der *LPARAM* -Wert, der an die Member `OnFindReplace` -Funktion des Frame Fensters übermittelt wird.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das aktuelle Dialogfeld.

### <a name="remarks"></a>Hinweise

Es sollte innerhalb ihrer Rückruffunktion verwendet werden, um auf das aktuelle Dialogfeld zuzugreifen, seine Member-Funktionen aufzurufen `m_fr` und auf die-Struktur zuzugreifen.

### <a name="example"></a>Beispiel

Unter [CFindReplaceDialog:: Create](#create) finden Sie ein Beispiel für die Registrierung des onfindreplace-Handlers für den Empfang von Benachrichtigungen über das Dialogfeld Ersetzen suchen.

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

##  <a name="getreplacestring"></a>CFindReplaceDialog:: getreplacestring

Rufen Sie diese Funktion auf, um die aktuelle Replace-Zeichenfolge abzurufen.

```
CString GetReplaceString() const;
```

### <a name="return-value"></a>Rückgabewert

Die Standard Zeichenfolge, mit der gefundene Zeichen folgen ersetzt werden sollen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFindReplaceDialog:: getfindstring](#getfindstring).

##  <a name="isterminating"></a>CFindReplaceDialog:: IsTerminating

Rufen Sie diese Funktion innerhalb der Rückruffunktion auf, um zu bestimmen, ob der Benutzer das Dialogfeld beendet hat.

```
BOOL IsTerminating() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Benutzer entschieden hat, das Dialogfeld zu beenden. andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn diese Funktion einen Wert ungleich 0 (null) zurück `DestroyWindow` gibt, sollten Sie die Member-Funktion des aktuellen Dialog Felds aufzurufen und eine beliebige Dialogfeld-Zeiger Variable auf NULL festlegen. Optional können Sie auch den zuletzt eingegebenen Text suchen/ersetzen speichern und ihn verwenden, um das nächste Dialogfeld Suchen/Ersetzen zu initialisieren.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFindReplaceDialog:: getfindstring](#getfindstring).

##  <a name="m_fr"></a>CFindReplaceDialog:: m_fr

Wird verwendet, um `CFindReplaceDialog` ein-Objekt anzupassen.

```
FINDREPLACE m_fr;
```

### <a name="remarks"></a>Hinweise

`m_fr`ist eine Struktur des Typs [FindReplace](/windows/win32/api/commdlg/ns-commdlg-findreplacew). Seine Member speichern die Merkmale des Dialogfeld Objekts. Nach dem Erstellen `CFindReplaceDialog` eines-Objekts können Sie `m_fr` verwenden, um verschiedene Werte im Dialogfeld zu ändern.

Weitere Informationen zu dieser Struktur finden Sie in der `FINDREPLACE` -Struktur im Windows SDK.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFindReplaceDialog:: CFindReplaceDialog](#cfindreplacedialog).

##  <a name="matchcase"></a>CFindReplaceDialog:: MatchCase

Mit dieser Funktion können Sie ermitteln, ob der Benutzer genau mit der Groß-/Kleinschreibung der Such Zeichenfolge übereinstimmen möchte.

```
BOOL MatchCase() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Benutzer Vorkommen der Such Zeichenfolge ermitteln möchte, die exakt mit der Groß-/Kleinschreibung der Such Zeichenfolge andernfalls 0.

##  <a name="matchwholeword"></a>CFindReplaceDialog:: MatchWholeWord

Diese Funktion wird aufgerufen, um zu bestimmen, ob der Benutzer nur ganze Wörter zuordnen möchte.

```
BOOL MatchWholeWord() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn der Benutzer nur die ganzen Wörter der Such Zeichenfolge zuordnen möchte. andernfalls 0.

##  <a name="replaceall"></a>CFindReplaceDialog:: ReplaceAll

Mit dieser Funktion können Sie feststellen, ob der Benutzer alle Vorkommen der Zeichenfolge ersetzen soll.

```
BOOL ReplaceAll() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0, wenn der Benutzer angefordert hat, dass alle Zeichen folgen, die mit der Ersetzungs Zeichenfolge andernfalls 0.

##  <a name="replacecurrent"></a>CFindReplaceDialog:: replacecurrent

Mit dieser Funktion können Sie feststellen, ob der Benutzer das aktuelle Wort ersetzen soll.

```
BOOL ReplaceCurrent() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0, wenn der Benutzer angefordert hat, dass die aktuell ausgewählte Zeichenfolge durch die Zeichenfolge REPLACE ersetzt wird; andernfalls 0.

##  <a name="searchdown"></a>CFindReplaceDialog:: searchdown

Mit dieser Funktion können Sie feststellen, ob die Suche nach unten fortgesetzt werden soll.

```
BOOL SearchDown() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Benutzer möchte, dass die Suche nach unten verläuft. 0, wenn der Benutzer möchte, dass die Suche nach oben verläuft.

## <a name="see-also"></a>Siehe auch

[CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
