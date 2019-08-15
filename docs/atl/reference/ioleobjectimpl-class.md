---
title: Ioleobjectimpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl::Advise
- ATLCTL/ATL::IOleObjectImpl::Close
- ATLCTL/ATL::IOleObjectImpl::DoVerb
- ATLCTL/ATL::IOleObjectImpl::DoVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::DoVerbHide
- ATLCTL/ATL::IOleObjectImpl::DoVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::DoVerbOpen
- ATLCTL/ATL::IOleObjectImpl::DoVerbPrimary
- ATLCTL/ATL::IOleObjectImpl::DoVerbShow
- ATLCTL/ATL::IOleObjectImpl::DoVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::EnumAdvise
- ATLCTL/ATL::IOleObjectImpl::EnumVerbs
- ATLCTL/ATL::IOleObjectImpl::GetClientSite
- ATLCTL/ATL::IOleObjectImpl::GetClipboardData
- ATLCTL/ATL::IOleObjectImpl::GetExtent
- ATLCTL/ATL::IOleObjectImpl::GetMiscStatus
- ATLCTL/ATL::IOleObjectImpl::GetMoniker
- ATLCTL/ATL::IOleObjectImpl::GetUserClassID
- ATLCTL/ATL::IOleObjectImpl::GetUserType
- ATLCTL/ATL::IOleObjectImpl::InitFromData
- ATLCTL/ATL::IOleObjectImpl::IsUpToDate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::SetClientSite
- ATLCTL/ATL::IOleObjectImpl::SetColorScheme
- ATLCTL/ATL::IOleObjectImpl::SetExtent
- ATLCTL/ATL::IOleObjectImpl::SetHostNames
- ATLCTL/ATL::IOleObjectImpl::SetMoniker
- ATLCTL/ATL::IOleObjectImpl::Unadvise
- ATLCTL/ATL::IOleObjectImpl::Update
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
ms.openlocfilehash: ded158b0ec862de5b0d0b23dd4b9edb50ad577ef
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495731"
---
# <a name="ioleobjectimpl-class"></a>Ioleobjectimpl-Klasse

Diese Klasse implementiert `IUnknown` und ist die Prinzipal Schnittstelle, über die ein Container mit einem-Steuerelement kommuniziert.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IOleObjectImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IOleObjectImpl::Advise](#advise)|Stellt eine Beratungs Verbindung mit dem-Steuerelement her.|
|[IOleObjectImpl::Close](#close)|Ändert den Zustand des Steuer Elements von wird ausgeführt in geladen.|
|[IOleObjectImpl::DoVerb](#doverb)|Weist das-Steuerelement an, eine seiner Aufzählungs Aktionen auszuführen.|
|[IOleObjectImpl::DoVerbDiscardUndo](#doverbdiscardundo)|Weist das Steuerelement an, alle rückgängigzustände zu verwerfen, die Sie beibehalten.|
|[IOleObjectImpl::DoVerbHide](#doverbhide)|Weist das Steuerelement an, seine Benutzeroberfläche aus der Ansicht zu entfernen.|
|[IOleObjectImpl::DoVerbInPlaceActivate](#doverbinplaceactivate)|Führt das-Steuerelement aus und installiert das zugehörige Fenster, die Benutzeroberfläche des Steuer Elements wird jedoch nicht installiert.|
|[IOleObjectImpl::DoVerbOpen](#doverbopen)|Bewirkt, dass das Steuerelement in einem separaten Fenster geöffnet wird.|
|[IOleObjectImpl::DoVerbPrimary](#doverbprimary)|Führt die angegebene Aktion aus, wenn der Benutzer auf das-Steuerelement doppelklickt. Das-Steuerelement definiert die Aktion, normalerweise, um das Steuerelement direkt zu aktivieren.|
|[IOleObjectImpl::DoVerbShow](#doverbshow)|Zeigt ein neu eingefügtes Steuerelement für den Benutzer an.|
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|Aktiviert das Steuerelement direkt und zeigt die Benutzeroberfläche des Steuer Elements an, z. b. Menüs und Symbolleisten.|
|[IOleObjectImpl::EnumAdvise](#enumadvise)|Listet die Beratungs Verbindungen des-Steuer Elements auf.|
|[IOleObjectImpl::EnumVerbs](#enumverbs)|Listet Aktionen für das-Steuerelement auf.|
|[IOleObjectImpl::GetClientSite](#getclientsite)|Ruft die Client Site des-Steuer Elements ab.|
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|Ruft Daten aus der Zwischenablage ab. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleObjectImpl::GetExtent](#getextent)|Ruft den Umfang des Anzeige Bereichs des Steuer Elements ab.|
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|Ruft den Status des Steuer Elements ab.|
|[IOleObjectImpl::GetMoniker](#getmoniker)|Ruft den Moniker des Steuer Elements ab. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|Ruft den Klassen Bezeichner des Steuer Elements ab.|
|[IOleObjectImpl::GetUserType](#getusertype)|Ruft den Benutzertyp Namen des Steuer Elements ab.|
|[IOleObjectImpl::InitFromData](#initfromdata)|Initialisiert das Steuerelement aus den ausgewählten Daten. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleObjectImpl::IsUpToDate](#isuptodate)|Überprüft, ob das Steuerelement auf dem neuesten Stand ist. Die ATL-Implementierung gibt S_OK zurück.|
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|Wird von [doverbverwerfen Dundo](#doverbdiscardundo) aufgerufen, nachdem der Zustand rückgängig gemacht wurde.|
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|Wird von [doverbhide](#doverbhide) aufgerufen, nachdem das Steuerelement ausgeblendet ist.|
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|Wird von [doverbinplaceaktivierungs](#doverbinplaceactivate) aufgerufen, nachdem das Steuerelement direkt aktiviert wurde.|
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|Wird von [doverbopen](#doverbopen) aufgerufen, nachdem das Steuerelement in einem separaten Fenster zum Bearbeiten geöffnet wurde.|
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|Wird von [doverbshow](#doverbshow) aufgerufen, nachdem das Steuerelement sichtbar gemacht wurde.|
|[IOleObjectImpl::OnPostVerbUIActivate](#onpostverbuiactivate)|Wird von [doverbuiaktivierungs](#doverbuiactivate) aufgerufen, nachdem die Benutzeroberfläche des Steuer Elements aktiviert wurde.|
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|Wird von [doverbverwerfen Dundo](#doverbdiscardundo) aufgerufen, bevor der Zustand rückgängig gemacht wird.|
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|Wird von [doverbhide](#doverbhide) aufgerufen, bevor das-Steuerelement ausgeblendet wird.|
|[IOleObjectImpl::OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|Wird von [doverbinplaceaktivierungs](#doverbinplaceactivate) aufgerufen, bevor das Steuerelement an Ort und Stelle aktiviert wird.|
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|Wird von [doverbopen](#doverbopen) aufgerufen, bevor das Steuerelement in einem separaten Fenster zum Bearbeiten geöffnet wurde.|
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|Wird von [doverbshow](#doverbshow) aufgerufen, bevor das Steuerelement sichtbar gemacht wurde.|
|[IOleObjectImpl::OnPreVerbUIActivate](#onpreverbuiactivate)|Wird von [doverbuiaktivierungs](#doverbuiactivate) aufgerufen, bevor die Benutzeroberfläche des Steuer Elements aktiviert wurde.|
|[IOleObjectImpl::SetClientSite](#setclientsite)|Weist das-Steuerelement an seine Client Site im Container zu.|
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|Empfiehlt ggf. ein Farbschema für die Anwendung des Steuer Elements. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleObjectImpl::SetExtent](#setextent)|Legt den Umfang des Anzeige Bereichs des-Steuer Elements fest.|
|[IOleObjectImpl::SetHostNames](#sethostnames)|Weist das-Steuerelement an, die Namen der Containeranwendung und des Container Dokuments zu steuern.|
|[IOleObjectImpl::SetMoniker](#setmoniker)|Teilt dem Steuerelement mit, was sein Moniker ist. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleObjectImpl::Unadvise](#unadvise)|Löscht eine Beratungs Verbindung mit dem-Steuerelement.|
|[IOleObjectImpl::Update](#update)|Aktualisiert das-Steuerelement. Die ATL-Implementierung gibt S_OK zurück.|

## <a name="remarks"></a>Hinweise

Die [IOleObject](/windows/win32/api/oleidl/nn-oleidl-ioleobject) -Schnittstelle ist die Prinzipal Schnittstelle, über die ein Container mit einem-Steuerelement kommuniziert. Die `IOleObjectImpl` -Klasse stellt eine Standard Implementierung dieser Schnittstelle `IUnknown` bereit und implementiert durch das Senden von Informationen an das dumpgerät in Debugbuilds.

**Verwandte Artikel** [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IOleObject`

`IOleObjectImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="advise"></a>Ioleobjectimpl:: Empfehlung

Stellt eine Beratungs Verbindung mit dem-Steuerelement her.

```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IOleObject:: Rat](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise) in der Windows SDK.

##  <a name="close"></a>Ioleobjectimpl:: Close

Ändert den Zustand des Steuer Elements von wird ausgeführt in geladen.

```
STDMETHOD(Close)(DWORD dwSaveOption);
```

### <a name="remarks"></a>Hinweise

Deaktiviert das Steuerelement und zerstört das Fenster des Steuer Elements, sofern es vorhanden ist. Wenn der Steuerelement-Klassendatenmember [CComControlBase:: m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) true und der *dwsaveoption* -Parameter entweder OLECLOSE_SAVEIFDIRTY oder OLECLOSE_PROMPTSAVE ist, werden die Steuerelement Eigenschaften vor dem Schließen gespeichert.

Die Zeiger in den Steuerelement-klassendatenmembern [CComControlBase:: m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) und [CComControlBase:: m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) werden freigegeben, und die Datenmember [CComControlBase:: m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd), [CComControlBase:: M_ bwnless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless)und [CComControlBase:: m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) sind auf false festgelegt.

Weitere Informationen finden Sie im Windows SDK unter [IOleObject:: Close](/windows/win32/api/oleidl/nf-oleidl-ioleobject-close) .

##  <a name="doverb"></a>Ioleobjectimpl::D overb

Weist das-Steuerelement an, eine seiner Aufzählungs Aktionen auszuführen.

```
STDMETHOD(DoVerb)(
    LONG iVerb,
    LPMSG /* pMsg */,
    IOleClientSite* pActiveSite,
    LONG /* lindex */,
    HWND hwndParent,
    LPCRECT lprcPosRect);
```

### <a name="remarks"></a>Hinweise

Abhängig vom Wert von `iVerb`wird eine der ATL `DoVerb` -Hilfsfunktionen wie folgt aufgerufen:

|*iVerb* Wert|DoVerb Helper-Funktion namens|
|-------------------|-----------------------------------|
|OLEIVERB_DISCARDUNDOSTATE|[DoVerbDiscardUndo](#doverbdiscardundo)|
|OLEIVERB_HIDE|[DoVerbHide](#doverbhide)|
|OLEIVERB_INPLACEACTIVATE|[DoVerbInPlaceActivate](#doverbinplaceactivate)|
|OLEIVERB_OPEN|[DoVerbOpen](#doverbopen)|
|OLEIVERB_PRIMARY|[DoVerbPrimary](#doverbprimary)|
|OLEIVERB_PROPERTIES|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|
|OLEIVERB_SHOW|[DoVerbShow](#doverbshow)|
|OLEIVERB_UIACTIVATE|[DoVerbUIActivate](#doverbuiactivate)|

Weitere Informationen finden Sie unter [IOleObject::D overb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) in der Windows SDK.

##  <a name="doverbdiscardundo"></a>Ioleobjectimpl::D overbverwerdundo

Weist das Steuerelement an, alle rückgängigzustände zu verwerfen, die Sie beibehalten.

```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
in Zeiger auf das Rechteck, in dem das Steuerelement gezeichnet werden soll.

*hwndParent*<br/>
in Handle des Fensters, das das Steuerelement enthält.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="doverbhide"></a>Ioleobjectimpl::D overbhide

Deaktiviert und entfernt die Benutzeroberfläche des Steuer Elements und blendet das Steuerelement aus.

```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
in Zeiger auf das Rechteck, in dem das Steuerelement gezeichnet werden soll.

*hwndParent*<br/>
in Handle des Fensters, das das Steuerelement enthält. Wird in der ATL-Implementierung nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="doverbinplaceactivate"></a>Ioleobjectimpl::D overbinplaceaktivierungs

Führt das-Steuerelement aus und installiert das zugehörige Fenster, die Benutzeroberfläche des Steuer Elements wird jedoch nicht installiert.

```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
in Zeiger auf das Rechteck, in dem das Steuerelement gezeichnet werden soll.

*hwndParent*<br/>
in Handle des Fensters, das das Steuerelement enthält. Wird in der ATL-Implementierung nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

Aktiviert das Steuerelement direkt durch Aufrufen von [CComControlBase:: inplaceaktivierungs](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate). Wenn der Datenmember `m_bWindowOnly` der Steuerelement Klasse nicht true `DoVerbInPlaceActivate` ist, versucht zuerst, das Steuerelement als fensterloses Steuerelement zu aktivieren (nur möglich, wenn der Container [ioleingeplacesitewindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless)unterstützt). Wenn dies fehlschlägt, versucht die Funktion, das Steuerelement mit erweiterten Funktionen zu aktivieren (Dies ist nur möglich, wenn der Container [ioleingeplacesiteex](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)unterstützt). Wenn dies fehlschlägt, versucht die Funktion, das Steuerelement ohne erweiterte Funktionen zu aktivieren (Dies ist nur möglich, wenn der Container [ioleingeplacesite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)unterstützt). Wenn die Aktivierung erfolgreich ist, benachrichtigt die Funktion den Container, dass das Steuerelement aktiviert wurde.

##  <a name="doverbopen"></a>Ioleobjectimpl::D overbopen

Bewirkt, dass das Steuerelement in einem separaten Fenster geöffnet wird.

```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
in Zeiger auf das Rechteck, in dem das Steuerelement gezeichnet werden soll.

*hwndParent*<br/>
in Handle des Fensters, das das Steuerelement enthält.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="doverbprimary"></a>Ioleobjectimpl::D overbprimary

Definiert die Aktion, die ausgeführt wird, wenn der Benutzer auf das-Steuerelement doppelklickt.

```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
in Zeiger auf das Rechteck, in dem das Steuerelement gezeichnet werden soll.

*hwndParent*<br/>
in Handle des Fensters, das das Steuerelement enthält.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

Standardmäßig legen Sie fest, um die Eigenschaften Seiten anzuzeigen. Sie können dies in der Steuerelement Klasse überschreiben, um ein anderes Verhalten beim Doppelklicken aufzurufen. Beispielsweise können Sie ein Video abspielen oder direkt in den aktiven Schritt wechseln.

##  <a name="doverbshow"></a>Ioleobjectimpl::D overbshow

Weist den Container an, das Steuerelement sichtbar zu machen.

```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
in Zeiger auf das Rechteck, in dem das Steuerelement gezeichnet werden soll.

*hwndParent*<br/>
in Handle des Fensters, das das Steuerelement enthält. Wird in der ATL-Implementierung nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="doverbuiactivate"></a>Ioleobjectimpl::D overbuiaktivierungs

Aktiviert die Benutzeroberfläche des Steuer Elements und benachrichtigt den Container, dass die Menüs durch zusammengesetzte Menüs ersetzt werden.

```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
in Zeiger auf das Rechteck, in dem das Steuerelement gezeichnet werden soll.

*hwndParent*<br/>
in Handle des Fensters, das das Steuerelement enthält. Wird in der ATL-Implementierung nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="enumadvise"></a>Ioleobjectimpl:: Endbenutzer

Stellt eine Enumeration registrierter Beratungs Verbindungen für dieses Steuerelement bereit.

```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```

### <a name="remarks"></a>Hinweise

Siehe [IOleObject:: EnumAdvise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumadvise) in der Windows SDK.

##  <a name="enumverbs"></a>Ioleobjectimpl:: EnumVerbs

Stellt eine Enumeration registrierter Aktionen (Verben) für dieses Steuerelement bereit `OleRegEnumVerbs`, indem aufgerufen wird.

```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```

### <a name="remarks"></a>Hinweise

Sie können Verben zur RGS-Datei Ihres Projekts hinzufügen. Informationen hierzu finden Sie beispielsweise unter circctl. RGS im [CIRC](../../overview/visual-cpp-samples.md) -Beispiel.

Siehe [IOleObject:: EnumVerbs](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs) in der Windows SDK.

##  <a name="getclientsite"></a>Ioleobjectimpl:: GetClientSite

Versetzt den Zeiger in den Datenmember der Steuerelement Klasse [CComControlBase:: m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) in *ppclientsite* und erhöht den Verweis Zähler für den Zeiger.

```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IOleObject:: GetClientSite](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclientsite) im Windows SDK.

##  <a name="getclipboarddata"></a>Ioleobjectimpl:: GetClipboardData

Ruft Daten aus der Zwischenablage ab.

```
STDMETHOD(GetClipboardData)(
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Siehe [IOleObject:: GetClipboardData](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclipboarddata) im Windows SDK.

##  <a name="getextent"></a>Ioleobjectimpl:: GetExtent

Ruft die Anzeige Größe eines ausgelaufenden Steuer Elements in HIMETRIC-Einheiten ab (0,01 Millimeter pro Einheit).

```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Hinweise

Die Größe wird im Datenmember der Steuerelement Klasse [CComControlBase:: m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)gespeichert.

Siehe [IOleObject:: GetExtent](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getextent) in der Windows SDK.

##  <a name="getmiscstatus"></a>Ioleobjectimpl:: getfehlstatus

Gibt einen Zeiger auf registrierte Statusinformationen für das-Steuerelement `OleRegGetMiscStatus`zurück, indem aufgerufen wird.

```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```

### <a name="remarks"></a>Hinweise

Die Statusinformationen umfassen Verhalten, die von den Steuerelement-und Präsentationsdaten unterstützt werden. Sie können Statusinformationen zur RGS-Datei Ihres Projekts hinzufügen.

Siehe [IOleObject:: getfehlstatus](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) in der Windows SDK.

##  <a name="getmoniker"></a>Ioleobjectimpl:: getmoniker

Ruft den Moniker des Steuer Elements ab.

```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Siehe [IOleObject:: getmoniker](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmoniker) in der Windows SDK.

##  <a name="getuserclassid"></a>Ioleobjectimpl:: GetUserClassID

Gibt den Klassen Bezeichner des Steuer Elements zurück.

```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```

### <a name="remarks"></a>Hinweise

Siehe [IOleObject:: GetUserClassID](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getuserclassid) in der Windows SDK.

##  <a name="getusertype"></a>Ioleobjectimpl:: GetUserType

Gibt den Benutzertyp Namen des Steuer Elements zurück `OleRegGetUserType`, indem aufgerufen wird.

```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```

### <a name="remarks"></a>Hinweise

Der Benutzertyp Name wird zur Anzeige in Benutzeroberflächen Elementen wie Menüs und Dialogfeldern verwendet. Sie können den Benutzertyp Namen in der RGS-Datei Ihres Projekts ändern.

Siehe [IOleObject:: GetUserType](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getusertype) in der Windows SDK.

##  <a name="initfromdata"></a>Ioleobjectimpl:: initfromdata

Initialisiert das Steuerelement aus den ausgewählten Daten.

```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Siehe [IOleObject:: initfromdata](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata) in der Windows SDK.

##  <a name="isuptodate"></a>Ioleobjectimpl:: isupdedate

Überprüft, ob das Steuerelement auf dem neuesten Stand ist.

```
STDMETHOD(IsUpToDate)(void);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IOleObject:: isuptopdate](/windows/win32/api/oleidl/nf-oleidl-ioleobject-isuptodate) in der Windows SDK.

##  <a name="onpostverbdiscardundo"></a>Ioleobjectimpl:: onpostverbverwerdundo

Wird von [doverbverwerfen Dundo](#doverbdiscardundo) aufgerufen, nachdem der Zustand rückgängig gemacht wurde.

```
HRESULT OnPostVerbDiscardUndo();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode mit Code, der ausgeführt werden soll, nachdem der Rückgängig-Zustand verworfen wurde.

##  <a name="onpostverbhide"></a>Ioleobjectimpl:: onpostverbhide

Wird von [doverbhide](#doverbhide) aufgerufen, nachdem das Steuerelement ausgeblendet ist.

```
HRESULT OnPostVerbHide();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode mit Code, den Sie ausführen möchten, nachdem das Steuerelement ausgeblendet ist.

##  <a name="onpostverbinplaceactivate"></a>Ioleobjectimpl:: onpostverbinplaceaktivierungs

Wird von [doverbinplaceaktivierungs](#doverbinplaceactivate) aufgerufen, nachdem das Steuerelement direkt aktiviert wurde.

```
HRESULT OnPostVerbInPlaceActivate();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode mit Code, den Sie ausführen möchten, nachdem das Steuerelement direkt aktiviert wurde.

##  <a name="onpostverbopen"></a>Ioleobjectimpl:: onpostverbopen

Wird von [doverbopen](#doverbopen) aufgerufen, nachdem das Steuerelement in einem separaten Fenster zum Bearbeiten geöffnet wurde.

```
HRESULT OnPostVerbOpen();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode mit Code, den Sie ausführen möchten, nachdem das Steuerelement in einem separaten Fenster zum Bearbeiten geöffnet wurde.

##  <a name="onpostverbshow"></a>Ioleobjectimpl:: onpostverbshow

Wird von [doverbshow](#doverbshow) aufgerufen, nachdem das Steuerelement sichtbar gemacht wurde.

```
HRESULT OnPostVerbShow();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode mit dem Code, den Sie ausführen möchten, nachdem das Steuerelement sichtbar gemacht wurde.

##  <a name="onpostverbuiactivate"></a>Ioleobjectimpl:: onpostverbuiaktivierungs

Wird von [doverbuiaktivierungs](#doverbuiactivate) aufgerufen, nachdem die Benutzeroberfläche des Steuer Elements aktiviert wurde.

```
HRESULT OnPostVerbUIActivate();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode mit Code, den Sie ausführen möchten, nachdem die Benutzeroberfläche des Steuer Elements aktiviert wurde.

##  <a name="onpreverbdiscardundo"></a>Ioleobjectimpl:: onpreverbverwerdundo

Wird von [doverbverwerfen Dundo](#doverbdiscardundo) aufgerufen, bevor der Zustand rückgängig gemacht wird.

```
HRESULT OnPreVerbDiscardUndo();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Um zu verhindern, dass der Rückgängig-Zustand verworfen wird, überschreiben Sie diese Methode, um einen Fehler HRESULT zurückzugeben.

##  <a name="onpreverbhide"></a>Ioleobjectimpl:: onpreverbhide

Wird von [doverbhide](#doverbhide) aufgerufen, bevor das-Steuerelement ausgeblendet wird.

```
HRESULT OnPreVerbHide();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Um zu verhindern, dass das Steuerelement ausgeblendet wird, überschreiben Sie diese Methode, um einen Fehler HRESULT zurückzugeben.

##  <a name="onpreverbinplaceactivate"></a>Ioleobjectimpl:: onpreverbinplaceaktivierungs

Wird von [doverbinplaceaktivierungs](#doverbinplaceactivate) aufgerufen, bevor das Steuerelement an Ort und Stelle aktiviert wird.

```
HRESULT OnPreVerbInPlaceActivate();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Um zu verhindern, dass das Steuerelement direkt aktiviert wird, überschreiben Sie diese Methode, um einen Fehler HRESULT zurückzugeben.

##  <a name="onpreverbopen"></a>Ioleobjectimpl:: onpreverbopen

Wird von [doverbopen](#doverbopen) aufgerufen, bevor das Steuerelement in einem separaten Fenster zum Bearbeiten geöffnet wurde.

```
HRESULT OnPreVerbOpen();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Um zu verhindern, dass das Steuerelement zur Bearbeitung in einem separaten Fenster geöffnet wird, überschreiben Sie diese Methode, um einen Fehler HRESULT zurückzugeben.

##  <a name="onpreverbshow"></a>Ioleobjectimpl:: onpreverbshow

Wird von [doverbshow](#doverbshow) aufgerufen, bevor das Steuerelement sichtbar gemacht wurde.

```
HRESULT OnPreVerbShow();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Um zu verhindern, dass das Steuerelement sichtbar gemacht wird, überschreiben Sie diese Methode, um einen Fehler HRESULT zurückzugeben.

##  <a name="onpreverbuiactivate"></a>Ioleobjectimpl:: onpreverbuiaktivierungs

Wird von [doverbuiaktivierungs](#doverbuiactivate) aufgerufen, bevor die Benutzeroberfläche des Steuer Elements aktiviert wurde.

```
HRESULT OnPreVerbUIActivate();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Um zu verhindern, dass die Benutzeroberfläche des Steuer Elements aktiviert wird, überschreiben Sie diese Methode, um einen Fehler HRESULT zurückzugeben.

##  <a name="setclientsite"></a>Ioleobjectimpl:: SetClientSite

Weist das-Steuerelement an seine Client Site im Container zu.

```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```

### <a name="remarks"></a>Hinweise

Die-Methode gibt dann S_OK zurück.

Weitere Informationen finden Sie unter [IOleObject:: SetClientSite](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setclientsite) im Windows SDK.

##  <a name="setcolorscheme"></a>Ioleobjectimpl:: SetColorScheme

Empfiehlt ggf. ein Farbschema für die Anwendung des Steuer Elements.

```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Siehe [IOleObject:: SetColorScheme](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) in der Windows SDK.

##  <a name="setextent"></a>Ioleobjectimpl:: abtextent

Legt den Umfang des Anzeige Bereichs des-Steuer Elements fest.

```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Hinweise

Andernfalls speichert den Wert, auf den im Steuerelement-Klassendatenmember " [CComControlBase:: m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)" gezeigt wird `psizel`. `SetExtent` Dieser Wert ist in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit).

Wenn der Steuerelement-Klassendatenmember [CComControlBase:: m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) auf true festgelegt ist, `SetExtent` speichert auch den `psizel` Wert, auf den im Steuerelement-Klassendatenmember [CComControlBase:: m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)gezeigt wird.

Wenn der Steuerelement-Klassendatenmember [CComControlBase:: m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) true `SendOnDataChange` ist `SendOnViewChange` , `SetExtent` ruft und auf, um alle mit dem Anmelde Inhaber registrierten Beratungs senken zu benachrichtigen, dass sich die Steuerelement Größe geändert hat.

Siehe [IOleObject:: SetExtent](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setextent) in der Windows SDK.

##  <a name="sethostnames"></a>Ioleobjectimpl:: lthostnames

Weist das-Steuerelement an, die Namen der Containeranwendung und des Container Dokuments zu steuern.

```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Siehe [IOleObject:: sethostnames](/windows/win32/api/oleidl/nf-oleidl-ioleobject-sethostnames) im Windows SDK.

##  <a name="setmoniker"></a>Ioleobjectimpl:: setmoniker

Teilt dem Steuerelement mit, was sein Moniker ist.

```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Siehe [IOleObject:: setmoniker](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setmoniker) in der Windows SDK.

##  <a name="unadvise"></a>Ioleobjectimpl:: unempfehlung

Löscht die beratungsverbindung, die im Datenmember `m_spOleAdviseHolder` der Steuerelement Klasse gespeichert ist.

```
STDMETHOD(Unadvise)(DWORD dwConnection);
```

### <a name="remarks"></a>Hinweise

Siehe [IOleObject:: Unrat](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise) im Windows SDK.

##  <a name="update"></a>Ioleobjectimpl:: Update

Aktualisiert das-Steuerelement.

```
STDMETHOD(Update)(void);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IOleObject:: Update](/windows/win32/api/oleidl/nf-oleidl-ioleobject-update) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX-Steuerelement Schnittstellen](/windows/win32/com/activex-controls-interfaces)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
