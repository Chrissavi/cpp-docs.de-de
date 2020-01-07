---
title: CComPtrBase-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase::Advise
- ATLCOMCLI/ATL::CComPtrBase::Attach
- ATLCOMCLI/ATL::CComPtrBase::CoCreateInstance
- ATLCOMCLI/ATL::CComPtrBase::CopyTo
- ATLCOMCLI/ATL::CComPtrBase::Detach
- ATLCOMCLI/ATL::CComPtrBase::IsEqualObject
- ATLCOMCLI/ATL::CComPtrBase::QueryInterface
- ATLCOMCLI/ATL::CComPtrBase::Release
- ATLCOMCLI/ATL::CComPtrBase::SetSite
- ATLCOMCLI/ATL::CComPtrBase::p
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
ms.openlocfilehash: 740920225fc513a869b4a92344f87004831e4768
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298610"
---
# <a name="ccomptrbase-class"></a>CComPtrBase-Klasse

Diese Klasse stellt eine Basis für intelligente Zeiger Klassen mithilfe von COM-basierten Speicher Routinen bereit.

## <a name="syntax"></a>Syntax

```
template <class T>
class CComPtrBase
```

#### <a name="parameters"></a>Parameters

*T*<br/>
Der Objekttyp, auf den vom intelligenten Zeiger verwiesen werden soll.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|-Name|Beschreibung|
|----------|-----------------|
|[CComPtrBase::~CComPtrBase](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|-Name|Beschreibung|
|----------|-----------------|
|[CComPtrBase::Advise](#advise)|Rufen Sie diese Methode auf, um eine Verbindung zwischen dem Verbindungspunkt des `CComPtrBase`und der Senke eines Clients herzustellen.|
|[CComPtrBase::Attach](#attach)|Ruft diese Methode auf, um den Besitz eines vorhandenen Zeigers zu übernehmen.|
|[CComPtrBase::CoCreateInstance](#cocreateinstance)|Rufen Sie diese Methode auf, um ein Objekt der Klasse zu erstellen, die einer angegebenen Klassen-ID oder Programm-ID zugeordnet ist.|
|[CComPtrBase::CopyTo](#copyto)|Mit dieser Methode können Sie den `CComPtrBase` Zeiger auf eine andere Zeiger Variable kopieren.|
|[CComPtrBase::Detach](#detach)|Ruft diese Methode auf, um den Besitz eines Zeigers freizugeben.|
|[CComPtrBase::IsEqualObject](#isequalobject)|Ruft diese Methode auf, um zu überprüfen, ob die angegebene `IUnknown` auf dasselbe Objekt verweist, das dem `CComPtrBase` Objekt zugeordnet ist.|
|[CComPtrBase::QueryInterface](#queryinterface)|Ruft diese Methode auf, um einen Zeiger auf eine angegebene Schnittstelle zurückzugeben.|
|[CComPtrBase::Release](#release)|Mit dieser Methode wird die-Schnittstelle freigegeben.|
|[CComPtrBase::SetSite](#setsite)|Mit dieser Methode wird die Site des `CComPtrBase` Objekts auf die `IUnknown` des übergeordneten Objekts festgelegt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|-Name|Beschreibung|
|----------|-----------------|
|[CComPtrBase:: Operator T *](#operator_t_star)|Der Umwandlungs Operator.|
|[CComPtrBase::-Operator!](#operator_not)|Der Not-Operator.|
|[CComPtrBase:: Operator-&](#operator_amp)|Der Operator &.|
|[CComPtrBase:: Operator *](#operator_star)|Der Operator \*.|
|[CComPtrBase:: Operator-<](#ccomptrbase__operator lt)|Der less-than-Operator.|
|[CComPtrBase::operator ==](#operator_eq_eq)|Der Gleichheits Operator.|
|[CComPtrBase:: Operator->](#operator_ptr)|Der Pointer-to-Member-Operator.|

### <a name="public-data-members"></a>Öffentliche Datenelemente

|-Name|Beschreibung|
|----------|-----------------|
|[CComPtrBase::p](#p)|Die Zeiger Datenelement Variable.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt die Grundlage für andere intelligente Zeiger bereit, die Verwaltungsroutinen für com-Speicher verwenden, z. b. [CComQIPtr](../../atl/reference/ccomqiptr-class.md) und [CComPtr](../../atl/reference/ccomptr-class.md). Die abgeleiteten Klassen fügen Ihre eigenen Konstruktoren und Operatoren hinzu, basieren jedoch auf den von `CComPtrBase`bereitgestellten Methoden.

## <a name="requirements"></a>-Anforderungen

**Header:** atlcomcli. h

##  <a name="advise"></a>CComPtrBase:: Rat

Rufen Sie diese Methode auf, um eine Verbindung zwischen dem Verbindungspunkt des `CComPtrBase`und der Senke eines Clients herzustellen.

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>Parameters

*pUnk*<br/>
Ein Zeiger auf den `IUnknown`des Clients.

*iid*<br/>
Die GUID des Verbindungs Punkts. In der Regel ist dies identisch mit der ausgehenden Schnittstelle, die vom Verbindungspunkt verwaltet wird.

*pdw*<br/>
Ein Zeiger auf das Cookie, das die Verbindung eindeutig identifiziert.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder bei einem Fehler HRESULT zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [AtlAdvise](connection-point-global-functions.md#atladvise) .

##  <a name="attach"></a>CComPtrBase:: Attach

Ruft diese Methode auf, um den Besitz eines vorhandenen Zeigers zu übernehmen.

```
void Attach(T* p2) throw();
```

### <a name="parameters"></a>Parameters

*p2*<br/>
Das `CComPtrBase` Objekt übernimmt den Besitz dieses Zeigers.

### <a name="remarks"></a>Hinweise

`Attach` ruft [CComPtrBase:: Release](#release) für die vorhandene [CComPtrBase::p](#p) Member-Variable auf und weist dann *P2* `CComPtrBase::p`zu. Wenn ein `CComPtrBase` Objekt den Besitz eines Zeigers übernimmt, wird automatisch `Release` auf dem Zeiger aufgerufen, der den Zeiger und alle zugeordneten Daten löscht, wenn der Verweis Zähler für das Objekt auf 0 (null) wechselt.

##  <a name="dtor"></a>CComPtrBase:: ~ CComPtrBase

Der Destruktor.

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>Hinweise

Gibt die Schnittstelle frei, auf die `CComPtrBase`zeigt.

##  <a name="cocreateinstance"></a>CComPtrBase:: cokreateingestance

Rufen Sie diese Methode auf, um ein Objekt der Klasse zu erstellen, die einer angegebenen Klassen-ID oder Programm-ID zugeordnet ist.

```
HRESULT CoCreateInstance(
    LPCOLESTR szProgID,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();

HRESULT CoCreateInstance(
    REFCLSID rclsid,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();
```

### <a name="parameters"></a>Parameters

*szProgID*<br/>
Zeiger auf eine ProgID, die verwendet wird, um die CLSID wiederherzustellen.

*pUnkOuter*<br/>
Wenn der Wert NULL ist, wird angegeben, dass das Objekt nicht als Teil eines Aggregats erstellt wird. Wenn ungleich NULL ist, ist ein Zeiger auf die `IUnknown`-Schnittstelle des aggregierten Objekts (das steuernde `IUnknown`).

*dwClsContext*<br/>
Der Kontext, in dem der Code, mit dem das neu erstellte Objekt verwaltet wird, ausgeführt wird.

*rclsid*<br/>
Die CLSID, die den Daten und dem Code zugeordnet ist, die zum Erstellen des Objekts verwendet werden.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING oder E_NOINTERFACE bei einem Fehler zurück. Eine Beschreibung dieser Fehler finden Sie unter [cokreateclassinstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) und [CLSIDFromProgID](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) .

### <a name="remarks"></a>Hinweise

Wenn die erste Form der Methode aufgerufen wird, wird [CLSIDFromProgID](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) verwendet, um die CLSID wiederherzustellen. Beide Formulare aufrufen dann [cokreateclassinstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).

In Debugbuilds tritt ein Fehler auf, wenn [CComPtrBase::p](#p) ungleich NULL ist.

##  <a name="copyto"></a>CComPtrBase:: CopyTo

Mit dieser Methode können Sie den `CComPtrBase` Zeiger auf eine andere Zeiger Variable kopieren.

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>Parameters

*ppT*<br/>
Adresse der Variablen, die den `CComPtrBase` Zeiger empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei erfolgreicher Ausführung E_POINTER bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Kopiert den `CComPtrBase` Zeiger auf *ppT*. Der Verweis Zähler für die [CComPtrBase::p](#p) Member-Variable wird inkrementiert.

Ein HRESULT-Fehler wird zurückgegeben, wenn *ppT* gleich NULL ist. In Debugbuilds tritt ein Fehler auf, wenn *ppT* gleich NULL ist.

##  <a name="detach"></a>CComPtrBase::D Etach

Ruft diese Methode auf, um den Besitz eines Zeigers freizugeben.

```
T* Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine Kopie des Zeigers zurück.

### <a name="remarks"></a>Hinweise

Gibt den Besitz eines Zeigers frei, legt die [CComPtrBase::p](#p) -Datenmember-Variable auf NULL fest und gibt eine Kopie des Zeigers zurück.

##  <a name="isequalobject"></a>CComPtrBase:: isequalobject

Ruft diese Methode auf, um zu überprüfen, ob die angegebene `IUnknown` auf dasselbe Objekt verweist, das dem `CComPtrBase` Objekt zugeordnet ist.

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>Parameters

*nach oben*<br/>
Der zu vergleichende `IUnknown *`.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Objekte identisch sind, andernfalls false.

##  <a name="operator_not"></a>CComPtrBase::-Operator!

Der Not-Operator.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn der `CComHeapPtr` Zeiger gleich NULL ist, andernfalls false.

##  <a name="operator_amp"></a>CComPtrBase:: Operator-&amp;

Der Operator &.

```
T** operator&() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Adresse des Objekts zurück, auf das durch das `CComPtrBase` Objekt verwiesen wird.

##  <a name="operator_star"></a>CComPtrBase:: Operator-\*

Der Operator \*.

```
T& operator*() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wert von [CComPtrBase zurück::p](#p); Das heißt, ein Zeiger auf das Objekt, auf das vom `CComPtrBase` Objekt verwiesen wird.

Wenn Debugbuilds erstellt werden, tritt ein Fehler auf, wenn [CComPtrBase::p](#p) ungleich NULL ist.

##  <a name="operator_eq_eq"></a>CComPtrBase:: Operator = =

Der Gleichheits Operator.

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>Parameters

*pT*<br/>
Ein Zeiger auf ein-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn `CComPtrBase` und *PT* auf dasselbe Objekt zeigen, andernfalls false.

##  <a name="operator_ptr"></a>CComPtrBase:: Operator-&gt;

Der Pointer-to-Member-Operator.

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wert der [CComPtrBase::p](#p) -Datenmember-Variable zurück.

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Operator, um eine Methode in einer Klasse aufzurufen, auf die vom `CComPtrBase` Objekt verwiesen wird. In Debugbuilds tritt ein Assertionsfehler auf, wenn das `CComPtrBase`-Datenmember auf NULL zeigt.

##  <a name="operator_lt"></a>CComPtrBase:: Operator-&lt;

Der less-than-Operator.

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>Parameters

*pT*<br/>
Ein Zeiger auf ein-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn der durch das aktuelle-Objekt verwaltete Zeiger kleiner als der Zeiger ist, mit dem er verglichen wird.

##  <a name="operator_t_star"></a>CComPtrBase:: Operator T-\*

Der Umwandlungs Operator.

```
operator T*() const throw();
```

### <a name="remarks"></a>Hinweise

Gibt einen Zeiger auf den in der Klassen Vorlage definierten Objekt Datentyp zurück.

##  <a name="p"></a>CComPtrBase::p

Die Zeiger Datenelement Variable.

```
T* p;
```

### <a name="remarks"></a>Hinweise

Diese Member-Variable enthält die Zeiger Informationen.

##  <a name="queryinterface"></a>CComPtrBase:: QueryInterface

Ruft diese Methode auf, um einen Zeiger auf eine angegebene Schnittstelle zurückzugeben.

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>Parameters

*Q*<br/>
Der Objekttyp, dessen Schnittstellen Zeiger erforderlich ist.

*pp*<br/>
Adresse der Ausgabevariablen, die den angeforderten Schnittstellen Zeiger empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder E_NOINTERFACE bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))auf.

In Debugbuilds tritt ein Fehler auf, wenn *PP* nicht gleich NULL ist.

##  <a name="release"></a>CComPtrBase:: Release

Mit dieser Methode wird die-Schnittstelle freigegeben.

```
void Release() throw();
```

### <a name="remarks"></a>Hinweise

Die-Schnittstelle wird freigegeben, und [CComPtrBase::p](#p) ist auf NULL festgelegt.

##  <a name="setsite"></a>CComPtrBase:: SetSite

Mit dieser Methode wird die Site des `CComPtrBase` Objekts auf die `IUnknown` des übergeordneten Objekts festgelegt.

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>Parameters

*punkParent*<br/>
Ein Zeiger auf die `IUnknown`-Schnittstelle des übergeordneten Elements.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder bei einem Fehler HRESULT zurück.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [atlsetchildsite](composite-control-global-functions.md#atlsetchildsite)auf.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
