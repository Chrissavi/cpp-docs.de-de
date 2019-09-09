---
title: CComControlBase-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComControlBase
- ATLCTL/ATL::CComControlBase
- ATLCTL/ATL::CComControlBase::AppearanceType
- ATLCTL/ATL::CComControlBase::CComControlBase
- ATLCTL/ATL::CComControlBase::ControlQueryInterface
- ATLCTL/ATL::CComControlBase::DoesVerbActivate
- ATLCTL/ATL::CComControlBase::DoesVerbUIActivate
- ATLCTL/ATL::CComControlBase::DoVerbProperties
- ATLCTL/ATL::CComControlBase::FireViewChange
- ATLCTL/ATL::CComControlBase::GetAmbientAppearance
- ATLCTL/ATL::CComControlBase::GetAmbientAutoClip
- ATLCTL/ATL::CComControlBase::GetAmbientBackColor
- ATLCTL/ATL::CComControlBase::GetAmbientCharSet
- ATLCTL/ATL::CComControlBase::GetAmbientCodePage
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayAsDefault
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayName
- ATLCTL/ATL::CComControlBase::GetAmbientFont
- ATLCTL/ATL::CComControlBase::GetAmbientFontDisp
- ATLCTL/ATL::CComControlBase::GetAmbientForeColor
- ATLCTL/ATL::CComControlBase::GetAmbientLocaleID
- ATLCTL/ATL::CComControlBase::GetAmbientMessageReflect
- ATLCTL/ATL::CComControlBase::GetAmbientPalette
- ATLCTL/ATL::CComControlBase::GetAmbientProperty
- ATLCTL/ATL::CComControlBase::GetAmbientRightToLeft
- ATLCTL/ATL::CComControlBase::GetAmbientScaleUnits
- ATLCTL/ATL::CComControlBase::GetAmbientShowGrabHandles
- ATLCTL/ATL::CComControlBase::GetAmbientShowHatching
- ATLCTL/ATL::CComControlBase::GetAmbientSupportsMnemonics
- ATLCTL/ATL::CComControlBase::GetAmbientTextAlign
- ATLCTL/ATL::CComControlBase::GetAmbientTopToBottom
- ATLCTL/ATL::CComControlBase::GetAmbientUIDead
- ATLCTL/ATL::CComControlBase::GetAmbientUserMode
- ATLCTL/ATL::CComControlBase::GetDirty
- ATLCTL/ATL::CComControlBase::GetZoomInfo
- ATLCTL/ATL::CComControlBase::InPlaceActivate
- ATLCTL/ATL::CComControlBase::InternalGetSite
- ATLCTL/ATL::CComControlBase::OnDraw
- ATLCTL/ATL::CComControlBase::OnDrawAdvanced
- ATLCTL/ATL::CComControlBase::OnKillFocus
- ATLCTL/ATL::CComControlBase::OnMouseActivate
- ATLCTL/ATL::CComControlBase::OnPaint
- ATLCTL/ATL::CComControlBase::OnSetFocus
- ATLCTL/ATL::CComControlBase::PreTranslateAccelerator
- ATLCTL/ATL::CComControlBase::SendOnClose
- ATLCTL/ATL::CComControlBase::SendOnDataChange
- ATLCTL/ATL::CComControlBase::SendOnRename
- ATLCTL/ATL::CComControlBase::SendOnSave
- ATLCTL/ATL::CComControlBase::SendOnViewChange
- ATLCTL/ATL::CComControlBase::SetControlFocus
- ATLCTL/ATL::CComControlBase::SetDirty
- ATLCTL/ATL::CComControlBase::m_bAutoSize
- ATLCTL/ATL::CComControlBase::m_bDrawFromNatural
- ATLCTL/ATL::CComControlBase::m_bDrawGetDataInHimetric
- ATLCTL/ATL::CComControlBase::m_bInPlaceActive
- ATLCTL/ATL::CComControlBase::m_bInPlaceSiteEx
- ATLCTL/ATL::CComControlBase::m_bNegotiatedWnd
- ATLCTL/ATL::CComControlBase::m_bRecomposeOnResize
- ATLCTL/ATL::CComControlBase::m_bRequiresSave
- ATLCTL/ATL::CComControlBase::m_bResizeNatural
- ATLCTL/ATL::CComControlBase::m_bUIActive
- ATLCTL/ATL::CComControlBase::m_bUsingWindowRgn
- ATLCTL/ATL::CComControlBase::m_bWasOnceWindowless
- ATLCTL/ATL::CComControlBase::m_bWindowOnly
- ATLCTL/ATL::CComControlBase::m_bWndLess
- ATLCTL/ATL::CComControlBase::m_hWndCD
- ATLCTL/ATL::CComControlBase::m_nFreezeEvents
- ATLCTL/ATL::CComControlBase::m_rcPos
- ATLCTL/ATL::CComControlBase::m_sizeExtent
- ATLCTL/ATL::CComControlBase::m_sizeNatural
- ATLCTL/ATL::CComControlBase::m_spAdviseSink
- ATLCTL/ATL::CComControlBase::m_spAmbientDispatch
- ATLCTL/ATL::CComControlBase::m_spClientSite
- ATLCTL/ATL::CComControlBase::m_spDataAdviseHolder
- ATLCTL/ATL::CComControlBase::m_spInPlaceSite
- ATLCTL/ATL::CComControlBase::m_spOleAdviseHolder
helpviewer_keywords:
- CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
ms.openlocfilehash: 36afd716009848ccd2e2f0ab966f66f573acdfd8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497392"
---
# <a name="ccomcontrolbase-class"></a>CComControlBase-Klasse

Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class ATL_NO_VTABLE CComControlBase
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CComControlBase::AppearanceType](#appearancetype)|Überschreiben Sie `m_nAppearance` , wenn ihre Aktien Eigenschaft nicht vom Typ **Short**ist.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComControlBase::CComControlBase](#ccomcontrolbase)|Der Konstruktor.|
|[CComControlBase::~CComControlBase](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComControlBase::ControlQueryInterface](#controlqueryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|Überprüft, ob der von verwendete *iVerb* -Parameter entweder die Benutzeroberfläche des Steuer Elements aktiviert ( `IOleObjectImpl::DoVerb` *iVerb* ist Gleichheits OLEIVERB_UIACTIVATE) und definiert die Aktion, die ausgeführt wird, wenn der Benutzer auf das Steuerelement doppelklickt (*iVerb* ist Gleichheits OLEIVERB_ Primary), zeigt das Steuerelement an (*iVerb* ist Gleichheits OLEIVERB_SHOW) oder aktiviert das Steuerelement (*iVerb* ist OLEIVERB_INPLACEACTIVATE).|
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|Überprüft, ob der von `IOleObjectImpl::DoVerb` verwendete *iVerb* -Parameter bewirkt, dass die Benutzeroberfläche des Steuer Elements aktiviert wird, und gibt true zurück.|
|[CComControlBase::DoVerbProperties](#doverbproperties)|Zeigt die Eigenschaften Seiten des Steuer Elements an.|
|[CComControlBase::FireViewChange](#fireviewchange)|Aufrufen Sie diese Methode, um dem Container mitzuteilen, dass das Steuerelement neu gezeichnet werden soll, oder die registrierten Ansichts senken, die die Ansicht des Steuer Elements geändert hat.|
|[CComControlBase::GetAmbientAppearance](#getambientappearance)|Ruft DISPID_AMBIENT_APPEARANCE ab, die aktuelle Darstellungs Einstellung für das-Steuerelement: 0 für Flat und 1 für 3D.|
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|Ruft DISPID_AMBIENT_AUTOCLIP ab, ein Flag, das angibt, ob der Container das automatische Abschneiden des Anzeige Bereichs des Steuer Elements unterstützt.|
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|Ruft DISPID_AMBIENT_BACKCOLOR, die Umgebungs Hintergrundfarbe für alle Steuerelemente ab, die durch den Container definiert werden.|
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|Ruft DISPID_AMBIENT_CHARSET, den AMBIENT-Zeichensatz für alle Steuerelemente ab, die durch den Container definiert werden.|
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|Ruft DISPID_AMBIENT_CODEPAGE, den AMBIENT-Zeichensatz für alle Steuerelemente ab, die durch den Container definiert werden.|
|[CComControlBase::GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|Ruft DISPID_AMBIENT_DISPLAYASDEFAULT ab, ein Flag, das true ist, wenn der Container das Steuerelement an dieser Site als Standard Schaltfläche markiert hat und sich ein Schaltflächen-Steuerelement mit einem dickeren Rahmen zeichnen soll.|
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|Ruft DISPID_AMBIENT_DISPLAYNAME ab, den Namen, den der Container für das Steuerelement bereitgestellt hat.|
|[CComControlBase::GetAmbientFont](#getambientfont)|Ruft einen Zeiger auf die Ambient `IFont` -Schnittstelle des Containers ab.|
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|Ruft einen Zeiger auf die Ambient `IFontDisp` Dispatch-Schnittstelle des Containers ab.|
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|Ruft DISPID_AMBIENT_FORECOLOR, die AMBIENT-Vordergrundfarbe für alle Steuerelemente ab, die durch den Container definiert werden.|
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|Ruft DISPID_AMBIENT_LOCALEID, den Bezeichner der Sprache ab, die vom Container verwendet wird.|
|[CComControlBase::GetAmbientMessageReflect](#getambientmessagereflect)|Ruft DISPID_AMBIENT_MESSAGEREFLECT ab, ein Flag, das angibt, ob der Containerfenster Nachrichten (z. b. WM_DRAWITEM) als Ereignisse empfangen möchte.|
|[CComControlBase::GetAmbientPalette](#getambientpalette)|Ruft DISPID_AMBIENT_PALETTE ab, die für den Zugriff auf die hpalette des Containers verwendet werden.|
|[CComControlBase::GetAmbientProperty](#getambientproperty)|Ruft die durch die *ID*angegebene Container Eigenschaft ab.|
|[CComControlBase::GetAmbientRightToLeft](#getambientrighttoleft)|Ruft DISPID_AMBIENT_RIGHTTOLEFT ab, die Richtung, in der Inhalt vom Container angezeigt wird.|
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|Ruft DISPID_AMBIENT_SCALEUNITS, die Umgebungs Einheiten des Containers (z. b. Zoll oder Zentimeter) für Beschriftungs Anzeige ab.|
|[CComControlBase::GetAmbientShowGrabHandles](#getambientshowgrabhandles)|Ruft DISPID_AMBIENT_SHOWGRABHANDLES ab, ein Flag, das angibt, ob der Container dem Steuerelement ermöglicht, Zieh Punkte für sich selbst anzuzeigen, wenn es aktiv ist.|
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|Ruft DISPID_AMBIENT_SHOWHATCHING ab, ein Flag, das angibt, ob der Container dem Steuerelement ermöglicht, sich selbst mit einem Schraffurmuster anzuzeigen, wenn die Benutzeroberfläche aktiv ist.|
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|Ruft DISPID_AMBIENT_SUPPORTSMNEMONICS ab, ein Flag, das angibt, ob der Container mnetmonics-Tastatur unterstützt.|
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|Ruft DISPID_AMBIENT_TEXTALIGN ab, die für den Container bevorzugte Textausrichtung: 0 für allgemeine Ausrichtung (Zahlen rechts, Text Links), 1 für linke Ausrichtung, 2 für die Mittelpunkt Ausrichtung und 3 für Rechte Ausrichtung.|
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|Ruft DISPID_AMBIENT_TOPTOBOTTOM ab, die Richtung, in der Inhalt vom Container angezeigt wird.|
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|Ruft DISPID_AMBIENT_UIDEAD ab, ein Flag, das angibt, ob der Container das Steuerelement auf Aktionen der Benutzeroberfläche reagieren soll.|
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|Ruft DISPID_AMBIENT_USERMODE ab, ein Flag, das angibt, ob sich der Container im Lauf Modus (true) oder im Entwurfs Modus (false) befindet.|
|[CComControlBase::GetDirty](#getdirty)|Gibt den Wert des Datenmembers `m_bRequiresSave`zurück.|
|[CComControlBase::GetZoomInfo](#getzoominfo)|Ruft die x-und y-Werte des zähators und des Nenners des Zoom Faktors für ein Steuerelement ab, das für die direkte Bearbeitung aktiviert ist.|
|[CComControlBase::InPlaceActivate](#inplaceactivate)|Bewirkt, dass das Steuerelement vom inaktiven Zustand in den Zustand übergeht, den das Verb in *iVerb* anzeigt.|
|[CComControlBase::InternalGetSite](#internalgetsite)|Mit dieser Methode können Sie die Steuerungs Website nach einem Zeiger auf die identifizierte Schnittstelle Abfragen.|
|[CComControlBase::OnDraw](#ondraw)|Überschreiben Sie diese Methode zum Zeichnen des Steuer Elements.|
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|Der Standard `OnDrawAdvanced` bereitet einen normalisierten Gerätekontext für das Zeichnen vor und ruft dann die- `OnDraw` Methode der Steuerelement Klasse auf.|
|[CComControlBase::OnKillFocus](#onkillfocus)|Überprüft, ob das Steuerelement direkt aktiv ist und über eine gültige Steuerungs Site verfügt, und informiert den Container darüber, dass das Steuerelement den Fokus verloren hat.|
|[CComControlBase::OnMouseActivate](#onmouseactivate)|Überprüft, ob sich die Benutzeroberfläche im Benutzermodus befindet, und aktiviert dann das Steuerelement.|
|[CComControlBase::OnPaint](#onpaint)|Bereitet den Container für das Zeichnen vor, Ruft den Client Bereich des Steuer Elements ab und ruft dann `OnDraw` die-Methode der Steuerelement Klasse auf.|
|[CComControlBase::OnSetFocus](#onsetfocus)|Überprüft, ob das Steuerelement direkt aktiv ist und über eine gültige Steuerungs Site verfügt, und informiert den Container dann, dass das Steuerelement den Fokus erhalten hat.|
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|Überschreiben Sie diese Methode, um Ihre eigenen Tastaturtasten Kombinationen bereitzustellen.|
|[CComControlBase::SendOnClose](#sendonclose)|Benachrichtigt alle mit dem Anmelde Inhaber registrierten Beratungs senken, dass das Steuerelement geschlossen wurde.|
|[CComControlBase::SendOnDataChange](#sendondatachange)|Benachrichtigt alle mit dem Anmelde Inhaber registrierten Beratungs senken, dass sich die Steuerungsdaten geändert haben.|
|[CComControlBase::SendOnRename](#sendonrename)|Benachrichtigt alle mit dem Anmelde Inhaber registrierten Beratungs senken, dass das Steuerelement über einen neuen Moniker verfügt.|
|[CComControlBase::SendOnSave](#sendonsave)|Benachrichtigt alle mit dem Anmelde Inhaber registrierten Beratungs senken, dass das Steuerelement gespeichert wurde.|
|[CComControlBase::SendOnViewChange](#sendonviewchange)|Benachrichtigt alle registrierten Beratungs senken, dass die Ansicht des Steuer Elements geändert wurde.|
|[CComControlBase::SetControlFocus](#setcontrolfocus)|Legt den Tastaturfokus auf das bzw. aus dem-Steuerelement fest oder entfernt diesen.|
|[CComControlBase::SetDirty](#setdirty)|Legt den Datenmember `m_bRequiresSave` auf den Wert in *bdirty*fest.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComControlBase::m_bAutoSize](#m_bautosize)|Flag, das angibt, dass das Steuerelement keine andere Größe aufweisen kann.|
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|Flag, das `IDataObjectImpl::GetData` angibt `CComControlBase::GetZoomInfo` , dass und die Steuerelement `m_sizeNatural` Größe von und `m_sizeExtent`nicht von festlegen soll.|
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|Flag, das `IDataObjectImpl::GetData` angibt, dass beim Zeichnen himetrische Einheiten und nicht Pixel verwenden soll.|
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|Flag, das angibt, dass das Steuerelement direkt aktiv ist.|
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|Flag, das angibt, dass `IOleInPlaceSiteEx` der Container die Schnittstellen-und OCX96-Steuerelement Funktionen unterstützt, z. b. fensterlose und flimmerfreie Steuerelemente.|
|[CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)|Flag, das angibt, ob das Steuerelement mit dem Container für die Unterstützung von OCX96-Steuerelement Funktionen (z. b. flimmerfreie und fensterlose Steuerelemente) verhandelt hat und ob es sich um ein Fenster oder ein fensterloses Steuerelement handelt.|
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|Flag, das angibt, dass das Steuerelement seine Präsentation neu verfassen möchte, wenn der Container die Anzeige Größe des Steuer Elements ändert.|
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|Flag, das angibt, dass das Steuerelement seit dem letzten Speichern geändert wurde.|
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|Flag, das angibt, dass das Steuerelement die Größe des natürlichen Wertebereichs (dessen Größe nicht skaliert) ändern möchte, wenn der Container die Anzeige Größe des Steuer Elements ändert.|
|[CComControlBase::m_bUIActive](#m_buiactive)|Flag, das angibt, dass die Benutzeroberfläche des Steuer Elements, z. b. Menüs und Symbolleisten, aktiv ist.|
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|Flag, das angibt, dass das Steuerelement den vom Container bereitgestellten Fensterbereich verwendet.|
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|Flag, das anzeigt, dass es sich um ein fensterloses Steuerelement handelt, aber möglicherweise nicht fensterloser ist.|
|[CComControlBase::m_bWindowOnly](#m_bwindowonly)|Flag, das angibt, dass das Steuerelement in einem Fenster angezeigt werden soll, auch wenn der Containerfenster lose Steuerelemente unterstützt.|
|[CComControlBase::m_bWndLess](#m_bwndless)|Flag, das anzeigt, dass das Steuerelement fensterloser ist.|
|[CComControlBase::m_hWndCD](#m_hwndcd)|Enthält einen Verweis auf das Fenster Handle, das dem Steuerelement zugeordnet ist.|
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|Gibt an, wie oft der Container fixierte Ereignisse (abgelehnte Ereignisse) ohne zwischengeschaltete Ereignisse (akzeptieren von Ereignissen) aufweist.|
|[CComControlBase::m_rcPos](#m_rcpos)|Die Position des-Steuer Elements in Pixel, ausgedrückt in den Koordinaten des Containers.|
|[CComControlBase::m_sizeExtent](#m_sizeextent)|Der Umfang des Steuer Elements in HIMETRIC-Einheiten (jede Einheit beträgt 0,01 Millimeter) für eine bestimmte Anzeige.|
|[CComControlBase::m_sizeNatural](#m_sizenatural)|Die physische Größe des Steuer Elements in HIMETRIC-Einheiten (jede Einheit ist 0,01 Millimeter).|
|[CComControlBase::m_spAdviseSink](#m_spadvisesink)|Ein direkter Zeiger auf die Beratungs Verbindung im Container ( [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink)des Containers).|
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|Ein `CComDispatchDriver` -Objekt, mit dem Sie die Eigenschaften des Containers über einen `IDispatch` Zeiger abrufen und festlegen können.|
|[CComControlBase::m_spClientSite](#m_spclientsite)|Ein Zeiger auf die Client Site des-Steuer Elements innerhalb des Containers.|
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|Bietet eine Standard Möglichkeit zum Speichern von Beratungs Verbindungen zwischen Datenobjekten und Raten senken.|
|[CComControlBase::m_spInPlaceSite](#m_spinplacesite)|Ein Zeiger auf den [ioleingeplacesite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)-, [iolumplacesiteex](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)-oder [iolumplacesitewindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) -Schnittstellen Zeiger des Containers.|
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|Stellt eine Standard Implementierung einer Möglichkeit zum halten von Beratungs Verbindungen bereit.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen bereit. Die [CComControl](../../atl/reference/ccomcontrol-class.md) -Klasse `CComControlBase`wird von abgeleitet. Wenn Sie mithilfe des ATL-Steuerelement-Assistenten ein Standard Steuerelement oder ein DHTML-Steuerelement erstellen, leitet `CComControlBase`der Assistent automatisch die Klasse von ab.

Weitere Informationen zum Erstellen eines Steuer Elements finden Sie im [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md). Weitere Informationen zum ATL-Projekt-Assistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="appearancetype"></a>CComControlBase:: kommancetype

Überschreiben Sie `m_nAppearance` , wenn ihre Aktien Eigenschaft nicht vom Typ **Short**ist.

```
typedef short AppearanceType;
```

### <a name="remarks"></a>Hinweise

Der ATL-Steuerelement `m_nAppearance` -Assistent fügt eine Aktien Eigenschaft vom Typ Short hinzu. Über `AppearanceType` schreiben Sie, wenn Sie einen anderen Datentyp verwenden.

##  <a name="ccomcontrolbase"></a>CComControlBase:: CComControlBase

Der Konstruktor.

```
CComControlBase(HWND& h);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Das Handle für das Fenster, das dem Steuerelement zugeordnet ist.

### <a name="remarks"></a>Hinweise

Initialisiert die Größe des Steuer Elements auf 5080x5080 HIMETRIC-Einheiten (2 "x2") und `CComControlBase` initialisiert die Datenmember-Werte in NULL oder false.

##  <a name="dtor"></a>CComControlBase:: ~ CComControlBase

Der Destruktor.

```
~CComControlBase();
```

### <a name="remarks"></a>Hinweise

Wenn das Steuerelement ein Fenster ist `~CComControlBase` , wird es durch Aufrufen von [DestroyWindow](/windows/win32/api/winuser/nf-winuser-destroywindow)zerstört.

##  <a name="controlqueryinterface"></a>CComControlBase:: controlqueryinterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
Der GUID der angeforderten Schnittstelle.

*ppv*<br/>
Ein Zeiger auf den Schnittstellen Zeiger, der durch *IID*identifiziert wird, oder NULL, wenn die Schnittstelle nicht gefunden wurde.

### <a name="remarks"></a>Hinweise

Behandelt nur Schnittstellen in der com-Zuordnungs Tabelle.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]

##  <a name="doesverbactivate"></a>CComControlBase::D oesverbaktivierungs

Überprüft, ob der von verwendete *iVerb* -Parameter entweder die Benutzeroberfläche des Steuer Elements aktiviert ( `IOleObjectImpl::DoVerb` *iVerb* ist Gleichheits OLEIVERB_UIACTIVATE) und definiert die Aktion, die ausgeführt wird, wenn der Benutzer auf das Steuerelement doppelklickt (*iVerb* ist Gleichheits OLEIVERB_ Primary), zeigt das Steuerelement an (*iVerb* ist Gleichheits OLEIVERB_SHOW) oder aktiviert das Steuerelement (*iVerb* ist OLEIVERB_INPLACEACTIVATE).

```
BOOL DoesVerbActivate(LONG iVerb);
```

### <a name="parameters"></a>Parameter

*iVerb*<br/>
Der Wert, der die Aktion angibt, `DoVerb`die von ausgeführt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn *iVerb* OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW oder OLEIVERB_INPLACEACTIVATE ist. Andernfalls wird false zurückgegeben.

### <a name="remarks"></a>Hinweise

Sie können diese Methode überschreiben, um ein eigenes Aktivierungs Verb zu definieren.

##  <a name="doesverbuiactivate"></a>CComControlBase::D oesverbuiaktivierungs

Überprüft, ob der von `IOleObjectImpl::DoVerb` verwendete *iVerb* -Parameter bewirkt, dass die Benutzeroberfläche des Steuer Elements aktiviert wird, und gibt true zurück.

```
BOOL DoesVerbUIActivate(LONG iVerb);
```

### <a name="parameters"></a>Parameter

*iVerb*<br/>
Der Wert, der die Aktion angibt, `DoVerb`die von ausgeführt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn *iVerb* mit OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW oder OLEIVERB_INPLACEACTIVATE Gleichheits Wert ist. Andernfalls gibt die Methode false zurück.

##  <a name="doverbproperties"></a>CComControlBase::D overbproperties

Zeigt die Eigenschaften Seiten des Steuer Elements an.

```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
Reserviert.

*hwndParent*<br/>
Handle des Fensters, das das Steuerelement enthält.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]

[!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]

##  <a name="fireviewchange"></a>CComControlBase:: FireViewChange

Aufrufen Sie diese Methode, um dem Container mitzuteilen, dass das Steuerelement neu gezeichnet werden soll, oder die registrierten Ansichts senken, die die Ansicht des Steuer Elements geändert hat.

```
HRESULT FireViewChange();
```

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

Wenn das Steuerelement aktiv ist (der Steuerelement-Klassendatenmember [CComControlBase:: m_bInPlaceActive](#m_binplaceactive) ist true), benachrichtigt den Container, dass Sie das gesamte Steuerelement neu zeichnen möchten. Wenn das-Steuerelement inaktiv ist, benachrichtigt die registrierten Ansichts senken des-Steuer Elements (über das Steuerelement-Klassendatenmember [CComControlBase:: m_spAdviseSink](#m_spadvisesink)), das die Ansicht des-Steuer Elements geändert hat.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]

##  <a name="getambientappearance"></a>CComControlBase:: getambientappearance

Ruft DISPID_AMBIENT_APPEARANCE ab, die aktuelle Darstellungs Einstellung für das-Steuerelement: 0 für Flat und 1 für 3D.

```
HRESULT GetAmbientAppearance(short& nAppearance);
```

### <a name="parameters"></a>Parameter

*nappearance*<br/>
Die Eigenschaft DISPID_AMBIENT_APPEARANCE.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]

##  <a name="getambientautoclip"></a>CComControlBase:: getambientautoclip

Ruft DISPID_AMBIENT_AUTOCLIP ab, ein Flag, das angibt, ob der Container das automatische Abschneiden des Anzeige Bereichs des Steuer Elements unterstützt.

```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```

### <a name="parameters"></a>Parameter

*bAutoClip*<br/>
Die Eigenschaft DISPID_AMBIENT_AUTOCLIP.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="getambientbackcolor"></a>CComControlBase:: getambientbackcolor

Ruft DISPID_AMBIENT_BACKCOLOR, die Umgebungs Hintergrundfarbe für alle Steuerelemente ab, die durch den Container definiert werden.

```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```

### <a name="parameters"></a>Parameter

*BackColor*<br/>
Die Eigenschaft DISPID_AMBIENT_BACKCOLOR.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="getambientcharset"></a>CComControlBase:: getambientcharset

Ruft DISPID_AMBIENT_CHARSET, den AMBIENT-Zeichensatz für alle Steuerelemente ab, die durch den Container definiert werden.

```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```

### <a name="parameters"></a>Parameter

*bstrCharSet*<br/>
Die Eigenschaft DISPID_AMBIENT_CHARSET.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="getambientcodepage"></a>CComControlBase:: getambientcodepage

Ruft DISPID_AMBIENT_CODEPAGE, die AMBIENT-Codepage für alle Steuerelemente ab, die durch den Container definiert werden.

```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```

### <a name="parameters"></a>Parameter

*ulCodePage*<br/>
Die Eigenschaft DISPID_AMBIENT_CODEPAGE.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="getambientdisplayasdefault"></a>CComControlBase:: GetAmbientDisplayAsDefault

Ruft DISPID_AMBIENT_DISPLAYASDEFAULT ab, ein Flag, das true ist, wenn der Container das Steuerelement an dieser Site als Standard Schaltfläche markiert hat und sich ein Schaltflächen-Steuerelement mit einem dickeren Rahmen zeichnen soll.

```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```

### <a name="parameters"></a>Parameter

*bDisplayAsDefault*<br/>
Die Eigenschaft DISPID_AMBIENT_DISPLAYASDEFAULT.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="getambientdisplayname"></a>CComControlBase:: getambientdisplayname

Ruft DISPID_AMBIENT_DISPLAYNAME ab, den Namen, den der Container für das Steuerelement bereitgestellt hat.

```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```

### <a name="parameters"></a>Parameter

*bstrDisplayName*<br/>
Die Eigenschaft DISPID_AMBIENT_DISPLAYNAME.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="getambientfont"></a>CComControlBase:: getambientfont

Ruft einen Zeiger auf die Ambient `IFont` -Schnittstelle des Containers ab.

```
HRESULT GetAmbientFont(IFont** ppFont);
```

### <a name="parameters"></a>Parameter

*ppFont*<br/>
Ein Zeiger auf die Ambient [IFont](/windows/win32/api/ocidl/nn-ocidl-ifont) -Schnittstelle des Containers.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

Wenn die Eigenschaft NULL ist, ist der Zeiger NULL. Wenn der Zeiger nicht NULL ist, muss der Aufrufer den Zeiger freigeben.

##  <a name="getambientfontdisp"></a>CComControlBase:: GetAmbientFontDisp

Ruft einen Zeiger auf die Ambient `IFontDisp` Dispatch-Schnittstelle des Containers ab.

```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```

### <a name="parameters"></a>Parameter

*ppFont*<br/>
Ein Zeiger auf die Ambient [IFontDisp](/windows/win32/api/ocidl/nn-ocidl-ifontdisp) Dispatch-Schnittstelle des Containers.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Wenn die Eigenschaft NULL ist, ist der Zeiger NULL. Wenn der Zeiger nicht NULL ist, muss der Aufrufer den Zeiger freigeben.

##  <a name="getambientforecolor"></a>CComControlBase:: getambientforecolor

Ruft DISPID_AMBIENT_FORECOLOR, die AMBIENT-Vordergrundfarbe für alle Steuerelemente ab, die durch den Container definiert werden.

```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```

### <a name="parameters"></a>Parameter

*ForeColor*<br/>
Die Eigenschaft DISPID_AMBIENT_FORECOLOR.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="getambientlocaleid"></a>CComControlBase:: getambientlocaleid

Ruft DISPID_AMBIENT_LOCALEID, den Bezeichner der Sprache ab, die vom Container verwendet wird.

```
HRESULT GetAmbientLocaleID(LCID& lcid);
```

### <a name="parameters"></a>Parameter

*lcid*<br/>
Die Eigenschaft DISPID_AMBIENT_LOCALEID.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

Das-Steuerelement kann diesen Bezeichner verwenden, um die Benutzeroberfläche an verschiedene Sprachen anzupassen.

##  <a name="getambientmessagereflect"></a>CComControlBase:: getambientmessagereflect

Ruft DISPID_AMBIENT_MESSAGEREFLECT ab, ein Flag, das angibt, ob der Containerfenster Nachrichten (z `WM_DRAWITEM`. b.) als Ereignisse empfangen möchte.

```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```

### <a name="parameters"></a>Parameter

*bMessageReflect*<br/>
Die Eigenschaft DISPID_AMBIENT_MESSAGEREFLECT.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="getambientpalette"></a>CComControlBase:: getambientpalette

Ruft DISPID_AMBIENT_PALETTE ab, die für den Zugriff auf die hpalette des Containers verwendet werden.

```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```

### <a name="parameters"></a>Parameter

*hPalette*<br/>
Die Eigenschaft DISPID_AMBIENT_PALETTE.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="getambientproperty"></a>CComControlBase:: getAmbientProperty

Ruft die von *DISPID*angegebene Container Eigenschaft ab.

```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```

### <a name="parameters"></a>Parameter

*dispid*<br/>
Der Bezeichner der Container Eigenschaft, die abgerufen werden soll.

*var*<br/>
Variable zum Empfangen der Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

ATL hat eine Reihe von Hilfsfunktionen bereitgestellt, um bestimmte Eigenschaften abzurufen, z. b. [CComControlBase:: getambientbackcolor](#getambientbackcolor). Wenn keine geeignete Methode verfügbar ist, verwenden `GetAmbientProperty`Sie.

##  <a name="getambientrighttoleft"></a>CComControlBase:: getambientrighttoleft

Ruft DISPID_AMBIENT_RIGHTTOLEFT ab, die Richtung, in der Inhalt vom Container angezeigt wird.

```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```

### <a name="parameters"></a>Parameter

*bRightToLeft*<br/>
Die Eigenschaft DISPID_AMBIENT_RIGHTTOLEFT. Auf true festgelegt, wenn der Inhalt von rechts nach links angezeigt wird, false, wenn er von links nach rechts angezeigt wird.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="getambientscaleunits"></a>CComControlBase:: getambientscaleunits

Ruft DISPID_AMBIENT_SCALEUNITS, die Umgebungs Einheiten des Containers (z. b. Zoll oder Zentimeter) für Beschriftungs Anzeige ab.

```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```

### <a name="parameters"></a>Parameter

*bstrScaleUnits*<br/>
Die Eigenschaft DISPID_AMBIENT_SCALEUNITS.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="getambientshowgrabhandles"></a>CComControlBase:: getambientshowgrabhandles

Ruft DISPID_AMBIENT_SHOWGRABHANDLES ab, ein Flag, das angibt, ob der Container dem Steuerelement ermöglicht, Zieh Punkte für sich selbst anzuzeigen, wenn es aktiv ist.

```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```

### <a name="parameters"></a>Parameter

*bShowGrabHandles*<br/>
Die Eigenschaft DISPID_AMBIENT_SHOWGRABHANDLES.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="getambientshowhatching"></a>CComControlBase:: getambientshowhatching

Ruft DISPID_AMBIENT_SHOWHATCHING ab, ein Flag, das angibt, ob der Container es dem Steuerelement ermöglicht, sich selbst mit einem Schraffurmuster anzuzeigen, wenn die Benutzeroberfläche des Steuer Elements aktiv ist.

```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```

### <a name="parameters"></a>Parameter

*bShowHatching*<br/>
Die Eigenschaft DISPID_AMBIENT_SHOWHATCHING.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="getambientsupportsmnemonics"></a>CComControlBase:: getambientsupportsmnetmonics

Ruft DISPID_AMBIENT_SUPPORTSMNEMONICS ab, ein Flag, das angibt, ob der Container mnetmonics-Tastatur unterstützt.

```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```

### <a name="parameters"></a>Parameter

*bSupportsMnemonics*<br/>
Die Eigenschaft DISPID_AMBIENT_SUPPORTSMNEMONICS.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="getambienttextalign"></a>CComControlBase:: getambienttextalign

Ruft DISPID_AMBIENT_TEXTALIGN ab, die für den Container bevorzugte Textausrichtung: 0 für allgemeine Ausrichtung (Zahlen rechts, Text Links), 1 für linke Ausrichtung, 2 für die Mittelpunkt Ausrichtung und 3 für Rechte Ausrichtung.

```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```

### <a name="parameters"></a>Parameter

*nTextAlign*<br/>
Die Eigenschaft DISPID_AMBIENT_TEXTALIGN.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="getambienttoptobottom"></a>CComControlBase:: getambienttopto Bottom

Ruft DISPID_AMBIENT_TOPTOBOTTOM ab, die Richtung, in der Inhalt vom Container angezeigt wird.

```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```

### <a name="parameters"></a>Parameter

*bTopToBottom*<br/>
Die Eigenschaft DISPID_AMBIENT_TOPTOBOTTOM. Auf true festgelegt, wenn der Text von oben nach unten angezeigt wird, false, wenn er von unten nach oben angezeigt wird.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="getambientuidead"></a>CComControlBase:: getambientuidead

Ruft DISPID_AMBIENT_UIDEAD ab, ein Flag, das angibt, ob der Container das Steuerelement auf Aktionen der Benutzeroberfläche reagieren soll.

```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```

### <a name="parameters"></a>Parameter

*bUIDead*<br/>
Die Eigenschaft DISPID_AMBIENT_UIDEAD.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

Wenn true, sollte das Steuerelement nicht Antworten. Dieses Flag gilt unabhängig vom DISPID_AMBIENT_USERMODE-Flag. Weitere Informationen finden Sie unter [CComControlBase:: getambientusermode](#getambientusermode).

##  <a name="getambientusermode"></a>CComControlBase:: getambientusermode

Ruft DISPID_AMBIENT_USERMODE ab, ein Flag, das angibt, ob sich der Container im Lauf Modus (true) oder im Entwurfs Modus (false) befindet.

```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```

### <a name="parameters"></a>Parameter

*bUserMode*<br/>
Die Eigenschaft DISPID_AMBIENT_USERMODE.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="getdirty"></a>CComControlBase:: getdirty

Gibt den Wert des Datenmembers `m_bRequiresSave`zurück.

```
BOOL GetDirty();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wert des Datenmember [m_bRequiresSave](#m_brequiressave)zurück.

### <a name="remarks"></a>Hinweise

Dieser Wert wird mit [CComControlBase:: SetDirty](#setdirty)festgelegt.

##  <a name="getzoominfo"></a>CComControlBase:: getzoominfo

Ruft die x-und y-Werte des zähators und des Nenners des Zoom Faktors für ein Steuerelement ab, das für die direkte Bearbeitung aktiviert ist.

```
void GetZoomInfo(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parameter

*di*<br/>
Die Struktur, in der der Zähler und der Nenner des Zoom Faktors enthalten sein werden. Weitere Informationen finden Sie unter [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md).

### <a name="remarks"></a>Hinweise

Der Zoomfaktor ist der Anteil der natürlichen Größe des Steuer Elements bis zum aktuellen Wert.

##  <a name="inplaceactivate"></a>CComControlBase:: inplaceaktivierungs

Bewirkt, dass das Steuerelement vom inaktiven Zustand in den Zustand übergeht, den das Verb in *iVerb* anzeigt.

```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```

### <a name="parameters"></a>Parameter

*iVerb*<br/>
Der Wert, der die Aktion angibt, die von [ioleobjectimpl ausgeführt werden soll::D overb](../../atl/reference/ioleobjectimpl-class.md#doverb).

*prcPosRect*<br/>
Ein Zeiger auf die Position des direkten Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

Vor der Aktivierung überprüft diese Methode, ob das Steuerelement über einen Client Standort verfügt, überprüft, welcher Teil des Steuer Elements sichtbar ist, und ruft die Position des Steuer Elements im übergeordneten Fenster ab. Nachdem das Steuerelement aktiviert wurde, aktiviert diese Methode die Benutzeroberfläche des Steuer Elements und weist den Container an, das Steuerelement sichtbar zu machen.

Diese Methode `IOleInPlaceSite`ruft auch einen-, `IOleInPlaceSiteEx`-oder `IOleInPlaceSiteWindowless` -Schnittstellen Zeiger für das-Steuerelement ab und speichert ihn im Datenmember der Steuerelement Klasse [CComControlBase:: m_spInPlaceSite](#m_spinplacesite). Die Steuerelement-Klassendatenmember [CComControlBase:: m_bInPlaceSiteEx](#m_binplacesiteex), [CComControlBase:: m_bWndLess](#m_bwndless), [CComControlBase:: m_bWasOnceWindowless](#m_bwasoncewindowless)und [CComControlBase:: m_bNegotiatedWnd](#m_bnegotiatedwnd) werden entsprechend auf true festgelegt.

##  <a name="internalgetsite"></a>CComControlBase:: internalgetsite

Mit dieser Methode können Sie die Steuerungs Website nach einem Zeiger auf die identifizierte Schnittstelle Abfragen.

```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Die IID des Schnittstellen Zeigers, der in *ppunksite*zurückgegeben werden soll.

*ppUnkSite*<br/>
Adresse der Zeiger Variablen, die den in *riid*angeforderten Schnittstellen Zeiger empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Wenn die Site die in *riid*angeforderte Schnittstelle unterstützt, wird der Zeiger mithilfe von *ppunksite*zurückgegeben. Andernfalls wird *ppunksite* auf NULL festgelegt.

##  <a name="m_bautosize"></a>CComControlBase:: m_bAutoSize

Flag, das angibt, dass das Steuerelement keine andere Größe aufweisen kann.

```
unsigned m_bAutoSize:1;
```

### <a name="remarks"></a>Hinweise

Dieses Flag wird von `IOleObjectImpl::SetExtent` überprüft und bewirkt, dass die Funktion, wenn true, E_FAIL zurückgibt.

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

Wenn Sie im ATL-Steuerelement-Assistenten auf der Registerkarte " [Stock Properties](../../atl/reference/stock-properties-atl-control-wizard.md) " die Option **Auto size** hinzufügen, erstellt der Assistent dieses Datenmember automatisch in der Steuerelement Klasse, erstellt Put-und Get-Methoden für die Eigenschaft und unterstützt [IPropertyNotifySink. ](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink), wenn der Container automatisch benachrichtigt werden soll, wenn sich die Eigenschaft ändert.

##  <a name="m_bdrawfromnatural"></a>CComControlBase:: m_bDrawFromNatural

Flag, das `IDataObjectImpl::GetData` angibt `CComControlBase::GetZoomInfo` , dass und die Steuerelement `m_sizeNatural` Größe von und `m_sizeExtent`nicht von festlegen soll.

```
unsigned m_bDrawFromNatural:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_bdrawgetdatainhimetric"></a>CComControlBase:: m_bDrawGetDataInHimetric

Flag, das `IDataObjectImpl::GetData` angibt, dass beim Zeichnen himetrische Einheiten und nicht Pixel verwenden soll.

```
unsigned m_bDrawGetDataInHimetric:1;
```

### <a name="remarks"></a>Hinweise

Jede logische himetrische Einheit ist 0,01 Millimeter.

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_binplaceactive"></a>CComControlBase:: m_bInPlaceActive

Flag, das angibt, dass das Steuerelement direkt aktiv ist.

```
unsigned m_bInPlaceActive:1;
```

### <a name="remarks"></a>Hinweise

Dies bedeutet, dass das Steuerelement sichtbar ist und sein Fenster, sofern vorhanden, sichtbar ist, die Menüs und Symbolleisten jedoch möglicherweise nicht aktiv sind. Das `m_bUIActive` Flag gibt an, dass die Benutzeroberfläche des Steuer Elements, z. b. Menüs, ebenfalls aktiv ist.

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_binplacesiteex"></a>CComControlBase:: m_bInPlaceSiteEx

Flag, das angibt, dass `IOleInPlaceSiteEx` der Container die Schnittstellen-und OCX96-Steuerelement Funktionen unterstützt, z. b. fensterlose und flimmerfreie Steuerelemente.

```
unsigned m_bInPlaceSiteEx:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

`m_spInPlaceSite` Der `m_bWndLess` -Datenmember zeigt abhängig vom Wert der-und-Flags auf eine [iolinplacesite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)-, [iolinplacesiteex](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)-oder [iolinplacesitewindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) - `m_bInPlaceSiteEx` Schnittstelle. (Der Datenmember `m_bNegotiatedWnd` muss "true" sein `m_spInPlaceSite` , damit der Zeiger gültig ist.)

Wenn `m_bWndLess` false ist und `m_bInPlaceSiteEx` true ist, `m_spInPlaceSite` ist ein `IOleInPlaceSiteEx` Schnittstellen Zeiger. Eine Tabelle mit der Beziehung zwischen diesen drei Datenmembern finden Sie unter [m_spInPlaceSite](#m_spinplacesite) .

##  <a name="m_bnegotiatedwnd"></a>CComControlBase:: m_bNegotiatedWnd

Flag, das angibt, ob das Steuerelement mit dem Container für die Unterstützung von OCX96-Steuerelement Funktionen (z. b. flimmerfreie und fensterlose Steuerelemente) verhandelt hat und ob es sich um ein Fenster oder ein fensterloses Steuerelement handelt.

```
unsigned m_bNegotiatedWnd:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

Das `m_bNegotiatedWnd` Flag muss "true" sein `m_spInPlaceSite` , damit der Zeiger gültig ist.

##  <a name="m_brecomposeonresize"></a>CComControlBase:: m_bRecomposeOnResize

Flag, das angibt, dass das Steuerelement seine Präsentation neu verfassen möchte, wenn der Container die Anzeige Größe des Steuer Elements ändert.

```
unsigned m_bRecomposeOnResize:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

Dieses Flag wird von [ioleobjectimpl:: SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent) geprüft, und wenn true, `SetExtent` benachrichtigt den Container über Ansichts Änderungen. Wenn dieses Flag festgelegt ist, sollte das OLEMISC_RECOMPOSEONRESIZE-Bit in der [OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc) -Enumeration ebenfalls festgelegt werden.

##  <a name="m_brequiressave"></a>CComControlBase:: m_bRequiresSave

Flag, das angibt, dass das Steuerelement seit dem letzten Speichern geändert wurde.

```
unsigned m_bRequiresSave:1;
```

### <a name="remarks"></a>Hinweise

Der Wert von `m_bRequiresSave` kann mit [CComControlBase:: SetDirty](#setdirty) festgelegt und mit [CComControlBase:: getdirty](#getdirty)abgerufen werden.

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_bresizenatural"></a>CComControlBase:: m_bResizeNatural

Flag, das angibt, dass das Steuerelement die Größe des natürlichen Wertebereichs (dessen Größe nicht skaliert) ändern möchte, wenn der Container die Anzeige Größe des Steuer Elements ändert.

```
unsigned m_bResizeNatural:1;
```

### <a name="remarks"></a>Hinweise

Dieses Flag wird von `IOleObjectImpl::SetExtent` geprüft, und wenn true, `SetExtent` wird die an `m_sizeNatural`übergebene Größe zugewiesen.

Die an `SetExtent` `m_sizeExtent`eingeführte Größe wird unabhängig vom Wert von `m_bResizeNatural`immer zugewiesen.

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_buiactive"></a>CComControlBase:: m_bUIActive

Flag, das angibt, dass die Benutzeroberfläche des Steuer Elements, z. b. Menüs und Symbolleisten, aktiv ist.

```
unsigned m_bUIActive:1;
```

### <a name="remarks"></a>Hinweise

Das `m_bInPlaceActive` Flag gibt an, dass das Steuerelement aktiv ist, aber nicht, dass die Benutzeroberfläche aktiv ist.

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_busingwindowrgn"></a>CComControlBase:: m_bUsingWindowRgn

Flag, das angibt, dass das Steuerelement den vom Container bereitgestellten Fensterbereich verwendet.

```
unsigned m_bUsingWindowRgn:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_bwasoncewindowless"></a>CComControlBase:: m_bWasOnceWindowless

Flag, das anzeigt, dass es sich um ein fensterloses Steuerelement handelt, aber möglicherweise nicht fensterloser ist.

```
unsigned m_bWasOnceWindowless:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_bwindowonly"></a>CComControlBase:: m_bWindowOnly

Flag, das angibt, dass das Steuerelement in einem Fenster angezeigt werden soll, auch wenn der Containerfenster lose Steuerelemente unterstützt.

```
unsigned m_bWindowOnly:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_bwndless"></a>CComControlBase:: m_bWndLess

Flag, das anzeigt, dass das Steuerelement fensterloser ist.

```
unsigned m_bWndLess:1;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

`m_spInPlaceSite` Der `m_bWndLess` -Datenmember zeigt abhängig vom Wert der-und [CComControlBase:: m_bInPlaceSiteEx](#m_binplacesiteex) -Flags auf eine [iolinplacesite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)-, [iolinplacesiteex](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)-oder [iolinplacesitewindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) -Schnittstelle. (Der Datenmember " [CComControlBase:: m_bNegotiatedWnd](#m_bnegotiatedwnd) " muss "true" sein, damit der [CComControlBase:: m_spInPlaceSite](#m_spinplacesite) -Zeiger gültig ist.)

Wenn `m_bWndLess` den Wert true `m_spInPlaceSite` hat, `IOleInPlaceSiteWindowless` ist ein Schnittstellen Zeiger. Unter [CComControlBase:: m_spInPlaceSite](#m_spinplacesite) finden Sie eine Tabelle, in der die gesamte Beziehung zwischen diesen Datenmembern angezeigt wird.

##  <a name="m_hwndcd"></a>CComControlBase:: m_hWndCD

Enthält einen Verweis auf das Fenster Handle, das dem Steuerelement zugeordnet ist.

```
HWND& m_hWndCD;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_nfreezeevents"></a>CComControlBase:: m_nFreezeEvents

Gibt an, wie oft der Container fixierte Ereignisse (abgelehnte Ereignisse) ohne zwischengeschaltete Ereignisse (akzeptieren von Ereignissen) aufweist.

```
short m_nFreezeEvents;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_rcpos"></a>CComControlBase:: m_rcPos

Die Position des-Steuer Elements in Pixel, ausgedrückt in den Koordinaten des Containers.

```
RECT m_rcPos;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_sizeextent"></a>CComControlBase:: m_sizeExtent

Der Umfang des Steuer Elements in HIMETRIC-Einheiten (jede Einheit beträgt 0,01 Millimeter) für eine bestimmte Anzeige.

```
SIZE m_sizeExtent;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

Diese Größe wird von der Anzeige skaliert. Die physische Größe des Steuer Elements wird im `m_sizeNatural` Datenmember angegeben und ist korrigiert.

Sie können die Größe mit der globalen Funktion [atlhimetrictopixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)in Pixel konvertieren.

##  <a name="m_sizenatural"></a>CComControlBase:: m_sizeNatural

Die physische Größe des Steuer Elements in HIMETRIC-Einheiten (jede Einheit ist 0,01 Millimeter).

```
SIZE m_sizeNatural;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

Diese Größe ist korrigiert, während die Größe in `m_sizeExtent` von der Anzeige skaliert wird.

Sie können die Größe mit der globalen Funktion [atlhimetrictopixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)in Pixel konvertieren.

##  <a name="m_spadvisesink"></a>CComControlBase:: m_spAdviseSink

Ein direkter Zeiger auf die Beratungs Verbindung im Container ( [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink)des Containers).

```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_spambientdispatch"></a>CComControlBase:: m_spAmbientDispatch

Ein `CComDispatchDriver` -Objekt, mit dem Sie die Eigenschaften eines Objekts über einen `IDispatch` Zeiger abrufen und festlegen können.

```
CComDispatchDriver m_spAmbientDispatch;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_spclientsite"></a>CComControlBase:: m_spClientSite

Ein Zeiger auf die Client Site des-Steuer Elements innerhalb des Containers.

```
CComPtr<IOleClientSite>
    m_spClientSite;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

##  <a name="m_spdataadviseholder"></a>CComControlBase:: m_spDataAdviseHolder

Bietet eine Standard Möglichkeit zum Speichern von Beratungs Verbindungen zwischen Datenobjekten und Raten senken.

```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

Ein Datenobjekt ist ein Steuerelement, das Daten übertragen kann und [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject)implementiert, dessen Methoden das Format und das Übertragungsmedium der Daten angeben.

Die- `m_spDataAdviseHolder` Schnittstelle implementiert die [IDataObject::D](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) Advisory-und [IDataObject::D unadvisory](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) -Methoden zum Einrichten und Löschen von Beratungs Verbindungen mit dem Container. Der Container des Steuer Elements muss mithilfe der [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) -Schnittstelle eine Hinweis-Senke implementieren.

##  <a name="m_spinplacesite"></a>CComControlBase:: m_spInPlaceSite

Ein Zeiger auf den [ioleingeplacesite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)-, [iolumplacesiteex](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)-oder [iolumplacesitewindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) -Schnittstellen Zeiger des Containers.

```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

Der `m_spInPlaceSite` Zeiger ist nur gültig, wenn das [m_bNegotiatedWnd](#m_bnegotiatedwnd) -Flag "true" ist.

In der folgenden Tabelle wird gezeigt `m_spInPlaceSite` , wie der Zeigertyp von den Datenmember-Flags [m_bWndLess](#m_bwndless) und [m_bInPlaceSiteEx](#m_binplacesiteex) abhängig ist:

|m_spInPlaceSite-Typ|m_bWndLess-Wert|m_bInPlaceSiteEx-Wert|
|---------------------------|-----------------------|-----------------------------|
|`IOleInPlaceSiteWindowless`|true|TRUE oder false|
|`IOleInPlaceSiteEx`|false|true|
|`IOleInPlaceSite`|false|false|

##  <a name="m_spoleadviseholder"></a>CComControlBase:: m_spOleAdviseHolder

Stellt eine Standard Implementierung einer Möglichkeit zum halten von Beratungs Verbindungen bereit.

```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Um dieses Datenmember in der Steuerelement Klasse zu verwenden, müssen Sie es als Datenmember in der Steuerelement Klasse deklarieren. Die Steuerelement Klasse erbt diesen Datenmember nicht von der Basisklasse, da Sie in einer Union in der Basisklasse deklariert wird.

Die- `m_spOleAdviseHolder` Schnittstelle implementiert die [IOleObject::](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise) Advisory-Methode und die [IOleObject:: unadvisory](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise) -Methode zum Einrichten und Löschen von Beratungs Verbindungen mit dem Container. Der Container des Steuer Elements muss mithilfe der [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) -Schnittstelle eine Hinweis-Senke implementieren.

##  <a name="ondraw"></a>CComControlBase:: OnDraw

Überschreiben Sie diese Methode zum Zeichnen des Steuer Elements.

```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parameter

*di*<br/>
Ein Verweis auf die [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) -Struktur, die Zeichnungs Informationen enthält, wie z. b. den Zeichnungs Aspekt, die Steuerelement Begrenzungen und ob die Zeichnung optimiert ist.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Der Standard `OnDraw` Wert löscht oder stellt den Gerätekontext wieder her, oder es wird keine Aktion ausgeführt, abhängig von den in [CComControlBase:: OnDrawAdvanced](#ondrawadvanced)festgelegten Flags.

Wenn `OnDraw` Sie das Steuerelement mit dem ATL-Steuerelement-Assistenten erstellen, wird der Steuerelement Klasse automatisch eine-Methode hinzugefügt. Der Standard `OnDraw` des Assistenten zeichnet ein Rechteck mit der Bezeichnung "ATL 8,0".

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [CComControlBase:: getambientappearance](#getambientappearance).

##  <a name="ondrawadvanced"></a>CComControlBase:: OnDrawAdvanced

Der Standard `OnDrawAdvanced` bereitet einen normalisierten Gerätekontext für das Zeichnen vor und ruft dann die- `OnDraw` Methode der Steuerelement Klasse auf.

```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parameter

*di*<br/>
Ein Verweis auf die [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) -Struktur, die Zeichnungs Informationen enthält, wie z. b. den Zeichnungs Aspekt, die Steuerelement Begrenzungen und ob die Zeichnung optimiert ist.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, wenn Sie den vom Container übergebenen Gerätekontext akzeptieren möchten, ohne ihn zu normalisieren.

Weitere Informationen finden Sie unter [CComControlBase:: OnDraw](#ondraw) .

##  <a name="onkillfocus"></a>CComControlBase:: onkillfocus

Überprüft, ob das Steuerelement direkt aktiv ist und über eine gültige Steuerungs Site verfügt, und informiert den Container darüber, dass das Steuerelement den Fokus verloren hat.

```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parameter

*nMsg*<br/>
Reserviert.

*wParam*<br/>
Reserviert.

*lParam*<br/>
Reserviert.

*bHandled*<br/>
Flag, das angibt, ob die Fenster Meldung erfolgreich verarbeitet wurde. Der Standardwert ist false.

### <a name="return-value"></a>Rückgabewert

Gibt immer 1 zurück.

##  <a name="onmouseactivate"></a>CComControlBase:: onmousaktivierung

Überprüft, ob sich die Benutzeroberfläche im Benutzermodus befindet, und aktiviert dann das Steuerelement.

```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parameter

*nMsg*<br/>
Reserviert.

*wParam*<br/>
Reserviert.

*lParam*<br/>
Reserviert.

*bHandled*<br/>
Flag, das angibt, ob die Fenster Meldung erfolgreich verarbeitet wurde. Der Standardwert ist false.

### <a name="return-value"></a>Rückgabewert

Gibt immer 1 zurück.

##  <a name="onpaint"></a>CComControlBase:: OnPaint

Bereitet den Container für das Zeichnen vor, Ruft den Client Bereich des Steuer Elements ab und ruft dann `OnDrawAdvanced` die-Methode der Steuerelement Klasse auf.

```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```

### <a name="parameters"></a>Parameter

*nMsg*<br/>
Reserviert.

*wParam*<br/>
Ein vorhandener hdc.

*lParam*<br/>
Reserviert.

*lResult*<br/>
Reserviert.

### <a name="return-value"></a>Rückgabewert

Gibt immer NULL zurück.

### <a name="remarks"></a>Hinweise

Wenn *wParam* nicht NULL ist, `OnPaint` wird davon ausgegangen, dass es einen gültigen HDC enthält und anstelle von [CComControlBase:: m_hWndCD](#m_hwndcd)verwendet wird.

##  <a name="onsetfocus"></a>CComControlBase:: OnSetFocus

Überprüft, ob das Steuerelement direkt aktiv ist und über eine gültige Steuerungs Site verfügt, und informiert den Container dann, dass das Steuerelement den Fokus erhalten hat.

```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parameter

*nMsg*<br/>
Reserviert.

*wParam*<br/>
Reserviert.

*lParam*<br/>
Reserviert.

*bHandled*<br/>
Flag, das angibt, ob die Fenster Meldung erfolgreich verarbeitet wurde. Der Standardwert ist false.

### <a name="return-value"></a>Rückgabewert

Gibt immer 1 zurück.

### <a name="remarks"></a>Hinweise

Sendet eine Benachrichtigung an den Container, dem das Steuerelement den Fokus erhält.

##  <a name="pretranslateaccelerator"></a>CComControlBase::P retranslateaccelerator

Überschreiben Sie diese Methode, um Ihre eigenen Tastaturtasten Kombinationen bereitzustellen.

```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```

### <a name="parameters"></a>Parameter

*pMsg*<br/>
Reserviert.

*hRet*<br/>
Reserviert.

### <a name="return-value"></a>Rückgabewert

Standardmäßig wird false zurückgegeben.

##  <a name="sendonclose"></a>CComControlBase:: sendonclose

Benachrichtigt alle mit dem Anmelde Inhaber registrierten Beratungs senken, dass das Steuerelement geschlossen wurde.

```
HRESULT SendOnClose();
```

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Sendet eine Benachrichtigung, dass das Steuerelement seine Beratungs senken geschlossen hat.

##  <a name="sendondatachange"></a>CComControlBase:: sendondatachange

Benachrichtigt alle mit dem Anmelde Inhaber registrierten Beratungs senken, dass sich die Steuerungsdaten geändert haben.

```
HRESULT SendOnDataChange(DWORD advf = 0);
```

### <a name="parameters"></a>Parameter

*advf*<br/>
Rät Flags, die angeben, wie der [IAdviseSink:: OnDataChange](/windows/win32/api/objidl/nf-objidl-iadvisesink-ondatachange) -Rückruf erfolgt. Werte stammen aus der [ADVF](/windows/win32/api/objidl/ne-objidl-advf) -Enumeration.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="sendonrename"></a>CComControlBase:: sendonrename

Benachrichtigt alle mit dem Anmelde Inhaber registrierten Beratungs senken, dass das Steuerelement über einen neuen Moniker verfügt.

```
HRESULT SendOnRename(IMoniker* pmk);
```

### <a name="parameters"></a>Parameter

*pmk*<br/>
Zeiger auf den neuen Moniker des Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Sendet eine Benachrichtigung, dass der Moniker für das Steuerelement geändert wurde.

##  <a name="sendonsave"></a>CComControlBase:: sendonsave

Benachrichtigt alle mit dem Anmelde Inhaber registrierten Beratungs senken, dass das Steuerelement gespeichert wurde.

```
HRESULT SendOnSave();
```

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Sendet eine Benachrichtigung, dass das Steuerelement soeben seine Daten gespeichert hat.

##  <a name="sendonviewchange"></a>CComControlBase:: sendonviewchange

Benachrichtigt alle registrierten Beratungs senken, dass die Ansicht des Steuer Elements geändert wurde.

```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```

### <a name="parameters"></a>Parameter

*dwAspect*<br/>
Der Aspekt oder die Ansicht des-Steuer Elements.

*lindex*<br/>
Der Teil der Ansicht, der geändert wurde. Nur-1 ist gültig.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

`SendOnViewChange`Ruft [IAdviseSink:: OnViewChange](/windows/win32/api/objidl/nf-objidl-iadvisesink-onviewchange)auf. Der einzige derzeit unterstützte *Lindex* -Wert ist-1, was darauf hinweist, dass die gesamte Ansicht von Interesse ist.

##  <a name="setcontrolfocus"></a>CComControlBase:: setcontrolfocus

Legt den Tastaturfokus auf das bzw. aus dem-Steuerelement fest oder entfernt diesen.

```
BOOL SetControlFocus(BOOL bGrab);
```

### <a name="parameters"></a>Parameter

*bGrab*<br/>
Wenn true, wird der Tastaturfokus auf das aufrufenden Steuerelement festgelegt. Wenn der Wert false ist, wird der Tastaturfokus aus dem aufrufenden Steuerelement entfernt, sofern er den Fokus besitzt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das Steuerelement erfolgreich den Fokus erhält. andernfalls false.

### <a name="remarks"></a>Hinweise

Bei einem Fenster Steuerelement wird die Windows-API-Funktion " [SetFocus](/windows/win32/api/winuser/nf-winuser-setfocus) " aufgerufen. Bei einem fensterlosen Steuerelement wird [ioleingeplacesitewindowless:: SetFocus](/windows/win32/api/ocidl/nf-ocidl-ioleinplacesitewindowless-setfocus) aufgerufen. Durch diesen Aufrufs erhält ein fensterloses Steuerelement den Tastaturfokus und kann auf Fenster Meldungen reagieren.

##  <a name="setdirty"></a>CComControlBase:: SetDirty

Legt den Datenmember `m_bRequiresSave` auf den Wert in *bdirty*fest.

```
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Parameter

*bDirty*<br/>
Wert des Datenmembers [CComControlBase:: m_bRequiresSave](#m_brequiressave).

### <a name="remarks"></a>Hinweise

`SetDirty(TRUE)`sollte aufgerufen werden, um zu markieren, dass das Steuerelement seit dem letzten Speichern geändert wurde. Der Wert von `m_bRequiresSave` wird mit [CComControlBase:: getdirty](#getdirty)abgerufen.

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
