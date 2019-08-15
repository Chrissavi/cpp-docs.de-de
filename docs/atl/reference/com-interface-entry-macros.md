---
title: Einstiegs Makros für COM-Schnittstellen
ms.date: 03/28/2017
f1_keywords:
- atlcom/ATL::COM_INTERFACE_ENTRY
- atlcom/ATL::COM_INTERFACE_ENTRY_IID
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_BREAK
- atlcom/ATL::COM_INTERFACE_ENTRY_CACHED_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_CHAIN
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_NOINTERFACE
helpviewer_keywords:
- COM interfaces, COM interface entry macros
ms.assetid: 19dcb768-2e1f-4b8d-a618-453a01a4bd00
ms.openlocfilehash: 1e1674bad1164e640939d430a860beac7a6e4208
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496724"
---
# <a name="com_interface_entry-macros"></a>COM_INTERFACE_ENTRY-Makros

Diese Makros geben die Schnittstellen eines Objekts in seine com-Zuordnung ein, damit Sie von `QueryInterface`auf Sie zugreifen können. Die Reihenfolge der Einträge in der com-Zuordnung besteht darin, dass die Bestell Schnittstellen auf eine entsprechende IID während `QueryInterface`der Prüfung geprüft werden.

|||
|-|-|
|[COM_INTERFACE_ENTRY](#com_interface_entry)|Gibt Schnittstellen in die COM-Schnittstellen Zuordnung ein.|
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Verwenden Sie dieses Makro, um zwei Verzweigungs Vererbungen eindeutig zu machen.|
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|Verwenden Sie dieses Makro, um die Schnittstelle in die com-Zuordnung einzugeben und ihre IID anzugeben.|
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|Identisch mit [COM_INTERFACE_ENTRY2](#com_interface_entry2), mit dem Unterschied, dass Sie eine andere IID angeben können.|
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|Wenn die durch *IID* identifizierte Schnittstelle abgefragt wird, `COM_INTERFACE_ENTRY_AGGREGATE` wird an weiter `punk`geleitet.|
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), mit dem Unterschied, dass die Abfrage für eine IID dazu führt, dass die Abfrage an *Punk*weitergeleitet wird.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), mit dem Unterschied, dass *Punk* NULL ist, wird das von der *CLSID*beschriebene Aggregat automatisch erstellt.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|Identisch mit [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), mit dem Unterschied, dass die Abfrage für eine IID dazu führt, dass die Abfrage an den *Punk*weitergeleitet wird, und wenn der Wert NULL ist, wird das von der *CLSID*beschriebene Aggregat automatisch erstellt.|
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Bewirkt, dass das Programm "Debug [break](/windows/win32/api/debugapi/nf-debugapi-debugbreak) " aufruft, wenn die angegebene Schnittstelle abgefragt wird.|
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Speichert die schnittstellenspezifischen Daten für jede Instanz.|
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Macht Ihre abtrenn Schnittstellen verfügbar.|
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|Verarbeitet die com-Zuordnung der Basisklasse, wenn die Verarbeitung diesen Eintrag in der com-Zuordnung erreicht.|
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|Ein allgemeiner Mechanismus zum Einbinden der ATL- `QueryInterface` Logik.|
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|Identisch mit [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), mit dem Unterschied, dass die Abfrage für eine IID zu einem *Func*-Aufrufe führt.|
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|Gibt E_NOINTERFACE zurück und beendet die com-Zuordnungs Verarbeitung, wenn die angegebene Schnittstelle abgefragt wird.|

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

## <a name="com_interface_entry"></a>COM_INTERFACE_ENTRY

Gibt Schnittstellen in die COM-Schnittstellen Zuordnung ein.

### <a name="syntax"></a>Syntax

```
COM_INTERFACE_ENTRY( x )
```

### <a name="parameters"></a>Parameter

*w*<br/>
in Der Name einer Schnittstelle, von der das Klassenobjekt direkt abgeleitet ist.

### <a name="remarks"></a>Hinweise

In der Regel ist dies der Eintragstyp, den Sie am häufigsten verwenden.

### <a name="example"></a>Beispiel

```cpp
BEGIN_COM_MAP(CThisExample)
   COM_INTERFACE_ENTRY(IThisExample)
   COM_INTERFACE_ENTRY(IDispatch)
   COM_INTERFACE_ENTRY(ISupportErrorInfo)
END_COM_MAP()
```

### <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="com_interface_entry2"></a>COM_INTERFACE_ENTRY2

Verwenden Sie dieses Makro, um zwei Verzweigungs Vererbungen eindeutig zu machen.

```
COM_INTERFACE_ENTRY2(x, x2)
```

### <a name="parameters"></a>Parameter

*w*<br/>
in Der Name einer Schnittstelle, die Sie aus dem-Objekt verfügbar machen möchten.

*x2*<br/>
in Der Name der Vererbungs Verzweigung, von der *x* verfügbar gemacht wird.

### <a name="remarks"></a>Hinweise

Wenn Sie z. b. das Klassenobjekt von zwei Dual Schnittstellen ableiten, machen `IDispatch` Sie mithilfe von `IDispatch` COM_INTERFACE_ENTRY2 verfügbar, da aus einer der Schnittstellen abgerufen werden kann.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]

##  <a name="com_interface_entry_iid"></a>COM_INTERFACE_ENTRY_IID

Verwenden Sie dieses Makro, um die Schnittstelle in die com-Zuordnung einzugeben und ihre IID anzugeben.

```
COM_INTERFACE_ENTRY_IID(iid, x)
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Die GUID der Schnittstelle, die verfügbar gemacht wird.

*w*<br/>
in Der Name der Klasse, deren vtable als die durch *IID*identifizierte Schnittstelle verfügbar gemacht wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]

##  <a name="com_interface_entry2_iid"></a>COM_INTERFACE_ENTRY2_IID

Identisch mit [COM_INTERFACE_ENTRY2](#com_interface_entry2), mit dem Unterschied, dass Sie eine andere IID angeben können.

```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Die GUID, die Sie für die Schnittstelle angeben.

*w*<br/>
in Der Name einer Schnittstelle, von der das Klassenobjekt direkt abgeleitet ist.

*x2*<br/>
in Der Name einer zweiten Schnittstelle, von der das Klassenobjekt direkt abgeleitet wird.

##  <a name="com_interface_entry_aggregate"></a>COM_INTERFACE_ENTRY_AGGREGATE

Wenn die durch *IID* identifizierte Schnittstelle abgefragt wird, wird COM_INTERFACE_ENTRY_AGGREGATE an *Punk*weitergeleitet.

```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Die GUID der Schnittstelle, die abgefragt wird.

*Kro*<br/>
in Der Name eines `IUnknown` Zeigers.

### <a name="remarks"></a>Hinweise

Der *Punk* -Parameter wird davon ausgegangen, dass er auf den inneren unbekannten eines Aggregats oder auf NULL verweist. in diesem Fall wird der Eintrag ignoriert. In der Regel würden `CoCreate` Sie das Aggregat `FinalConstruct`in.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]

##  <a name="com_interface_entry_aggregate_blind"></a>COM_INTERFACE_ENTRY_AGGREGATE_BLIND

Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), mit dem Unterschied, dass die Abfrage für eine IID dazu führt, dass die Abfrage an *Punk*weitergeleitet wird.

```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```

### <a name="parameters"></a>Parameter

*Kro*<br/>
in Der Name eines `IUnknown` Zeigers.

### <a name="remarks"></a>Hinweise

Wenn die Schnittstellen Abfrage fehlschlägt, wird die Verarbeitung der com-Zuordnung fortgesetzt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]

##  <a name="com_interface_entry_autoaggregate"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE

Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), mit dem Unterschied, dass *Punk* NULL ist, wird das von der *CLSID*beschriebene Aggregat automatisch erstellt.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Die GUID der Schnittstelle, die abgefragt wird.

*Kro*<br/>
in Der Name eines `IUnknown` Zeigers. Muss ein Member der-Klasse sein, die die com-Zuordnung enthält.

*clsid*<br/>
in Der Bezeichner des Aggregats, das erstellt wird , wenn der Wert NULL ist.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]

##  <a name="com_interface_entry_autoaggregate_blind"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND

Identisch mit [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), mit dem Unterschied, dass die Abfrage für eine IID dazu führt, dass die Abfrage an den *Punk*weitergeleitet wird, und wenn der Wert NULL ist, wird das von der *CLSID*beschriebene Aggregat automatisch erstellt.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```

### <a name="parameters"></a>Parameter

*Kro*<br/>
in Der Name eines `IUnknown` Zeigers. Muss ein Member der-Klasse sein, die die com-Zuordnung enthält.

*clsid*<br/>
in Der Bezeichner des Aggregats, das erstellt wird , wenn der Wert NULL ist.

### <a name="remarks"></a>Hinweise

Wenn die Schnittstellen Abfrage fehlschlägt, wird die Verarbeitung der com-Zuordnung fortgesetzt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]

##  <a name="com_interface_entry_break"></a>COM_INTERFACE_ENTRY_BREAK

Bewirkt, dass das Programm "Debug [break](/windows/win32/api/debugapi/nf-debugapi-debugbreak) " aufruft, wenn die angegebene Schnittstelle abgefragt wird.

```
COM_INTERFACE_ENTRY_BREAK(x)
```

### <a name="parameters"></a>Parameter

*w*<br/>
in Text, der zum Erstellen des Schnittstellen Bezeichners verwendet wird.

### <a name="remarks"></a>Hinweise

Die IID der Schnittstelle wird erstellt, indem *x* an `IID_`angehängt wird. Wenn z `IID_IPersistStorage`. b. " `IPersistStorage` *x* " ist, ist die IID.

##  <a name="com_interface_entry_cached_tear_off"></a>COM_INTERFACE_ENTRY_CACHED_TEAR_OFF

Speichert die schnittstellenspezifischen Daten für jede Instanz.

```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Der GUID der deaktivierten Schnittstelle.

*w*<br/>
in Der Name der Klasse, die die-Schnittstelle implementiert.

*Kro*<br/>
in Der Name eines `IUnknown` Zeigers. Muss ein Member der-Klasse sein, die die com-Zuordnung enthält. Sollte im Konstruktor des Klassen Objekts mit NULL initialisiert werden.

### <a name="remarks"></a>Hinweise

Wenn die Schnittstelle nicht verwendet wird, verringert dies die Gesamtgröße des Objekts.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]

##  <a name="com_interface_entry_tear_off"></a>COM_INTERFACE_ENTRY_TEAR_OFF

Macht Ihre abtrenn Schnittstellen verfügbar.

```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Der GUID der deaktivierten Schnittstelle.

*w*<br/>
in Der Name der Klasse, die die-Schnittstelle implementiert.

### <a name="remarks"></a>Hinweise

Eine abtrenn Schnittstelle wird als separates Objekt implementiert, das jedes Mal instanziiert wird, wenn die Schnittstelle, für die Sie steht, abgefragt wird. In der Regel erstellen Sie die Schnittstelle als Abbild, wenn die Schnittstelle selten verwendet wird, da dadurch ein vtable-Zeiger in jeder Instanz des Haupt Objekts gespeichert wird. Die Löschung wird gelöscht, wenn der Verweis Zähler Null wird. Die Klasse, die das Abbild implementiert, sollte von `CComTearOffObjectBase` abgeleitet sein und über eine eigene com-Zuordnung verfügen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

##  <a name="com_interface_entry_chain"></a>COM_INTERFACE_ENTRY_CHAIN

Verarbeitet die com-Zuordnung der Basisklasse, wenn die Verarbeitung diesen Eintrag in der com-Zuordnung erreicht.

```
COM_INTERFACE_ENTRY_CHAIN(classname)
```

### <a name="parameters"></a>Parameter

*classname*<br/>
in Eine Basisklasse des aktuellen-Objekts.

### <a name="remarks"></a>Hinweise

Beispielsweise im folgenden Code:

[!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]

Beachten Sie, dass der erste Eintrag in der com-Zuordnung eine Schnittstelle für das Objekt sein muss, das die com-Zuordnung enthält. Daher können Sie die com-Zuordnungs Einträge nicht mit COM_INTERFACE_ENTRY_CHAIN starten, was bewirkt, dass die com-Zuordnung eines anderen Objekts an dem Punkt durchsucht wird, an dem **COM_INTERFACE_ENTRY_CHAIN (** `COtherObject` **)** in der com-Zuordnung Ihres Objekts angezeigt wird. Wenn Sie zuerst die com-Zuordnung eines anderen Objekts durchsuchen möchten, fügen Sie der com `IUnknown` -Zuordnung einen Schnittstellen Eintrag für hinzu, und verketten Sie dann die com-Zuordnung des anderen Objekts. Beispiel:

[!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]

##  <a name="com_interface_entry_func"></a>COM_INTERFACE_ENTRY_FUNC

Ein allgemeiner Mechanismus zum Einbinden der ATL- `QueryInterface` Logik.

```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Die GUID der Schnittstelle, die verfügbar gemacht wird.

*dw*<br/>
in Ein Parameter, der an die *Funktion*übergeben wird.

*func*<br/>
in Der Funktionszeiger, der *IID*zurückgibt.

### <a name="remarks"></a>Hinweise

Wenn *IID* mit der IID der Schnittstelle übereinstimmt, die nach abgefragt wird, wird die von *Func* angegebene Funktion aufgerufen. Die Deklaration für die Funktion sollte wie folgt lauten:

`HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`

Wenn Ihre Funktion aufgerufen wird, `pv` verweist auf das Klassenobjekt. Der *riid* -Parameter verweist auf die Schnittstelle, die abgefragt `ppv` wird, ist der Zeiger auf den Speicherort, an dem die Funktion den Zeiger auf die Schnittstelle speichern soll, und *DW* ist der Parameter, den Sie im Eintrag angegeben haben. Die-Funktion sollte \* auf NULL festgelegt `ppv` werden und E_NOINTERFACE oder S_FALSE zurückgeben, wenn Sie nicht die Rückgabe einer Schnittstelle auswählt. Mit E_NOINTERFACE wird die com-Zuordnungs Verarbeitung beendet. Mit S_FALSE wird die com-Zuordnungs Verarbeitung fortgesetzt, obwohl kein Schnittstellen Zeiger zurückgegeben wurde. Wenn die Funktion einen Schnittstellen Zeiger zurückgibt, sollte Sie S_OK zurückgeben.

##  <a name="com_interface_entry_func_blind"></a>COM_INTERFACE_ENTRY_FUNC_BLIND

Identisch mit [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), mit dem Unterschied, dass die Abfrage für eine IID zu einem *Func*-Aufrufe führt.

```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```

### <a name="parameters"></a>Parameter

*dw*<br/>
in Ein Parameter, der an die *Funktion*übergeben wird.

*func*<br/>
in Die Funktion, die aufgerufen wird, wenn dieser Eintrag in der com-Zuordnung verarbeitet wird.

### <a name="remarks"></a>Hinweise

Jeder Fehler führt dazu, dass die Verarbeitung auf der com-Karte fortgesetzt wird. Wenn die Funktion einen Schnittstellen Zeiger zurückgibt, sollte Sie S_OK zurückgeben.

##  <a name="com_interface_entry_nointerface"></a>COM_INTERFACE_ENTRY_NOINTERFACE

Gibt E_NOINTERFACE zurück und beendet die com-Zuordnungs Verarbeitung, wenn die angegebene Schnittstelle abgefragt wird.

```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```

### <a name="parameters"></a>Parameter

*w*<br/>
in Text, der zum Erstellen des Schnittstellen Bezeichners verwendet wird.

### <a name="remarks"></a>Hinweise

Sie können dieses Makro verwenden, um zu verhindern, dass eine Schnittstelle in einem bestimmten Fall verwendet wird. Beispielsweise können Sie dieses Makro direkt vor COM_INTERFACE_ENTRY_AGGREGATE_BLIND in die com-Zuordnung einfügen, um zu verhindern, dass eine Abfrage für die Schnittstelle an den inneren unbekannten des Aggregats weitergeleitet wird.

Die IID der Schnittstelle wird erstellt, indem *x* an `IID_`angehängt wird. Wenn z `IID_IPersistStorage`. b. " `IPersistStorage` *x* " ist, ist die IID.
