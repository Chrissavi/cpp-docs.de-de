---
title: Delegatmakros und Schnittstellen Zuordnungs Makros (MFC)
ms.date: 03/30/2017
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
ms.openlocfilehash: 01f5cbfb1f751823d218761410bc9091b73cb0a3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837449"
---
# <a name="delegate-and-interface-map-macros"></a>Zuordnungsmakros von Delegaten und Schnittstellen

MFC unterstützt diese Makros für Delegat-und Schnittstellen Zuordnungen:

|Name|Beschreibung|
|-|-|
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|Beginnt eine Delegatzuordnung.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|Beginnt die Definition der Schnitt Zuordnung.|
|[CommandHandler-Delegat](#commandhandler)|Registriert Rückruf Methoden mit einer Befehls Quelle.  |
|[END_DELEGATE_MAP](#end_delegate_map)|Beendet eine Delegatzuordnung.|
|[END_INTERFACE_MAP](#end_interface_map)|Beendet die Schnittstellen Zuordnung in der Implementierungs Datei. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|Erstellt einen Eintrag in der Delegatzuordnung.|
|[INTERFACE_PART](#interface_part)|Wird zwischen dem BEGIN_INTERFACE_MAP-Makro und dem END_INTERFACE_MAP-Makro für jede Schnittstelle verwendet, die das Objekt unterstützt.|
|[MAKE_DELEGATE](#make_delegate)|Fügt einen Ereignishandler an ein verwaltetes Steuerelement an.|

## <a name="begin_delegate_map"></a><a name="begin_delegate_map"></a> BEGIN_DELEGATE_MAP

Beginnt eine Delegatzuordnung.

### <a name="syntax"></a>Syntax

```
BEGIN_DELEGATE_MAP(  CLASS );
```

### <a name="parameters"></a>Parameter

*Klassi*<br/>
Die Klasse, in der das verwaltete Steuerelement gehostet wird.

### <a name="remarks"></a>Bemerkungen

Dieses Makro markiert den Anfang einer Liste von delegateinträgen, die eine Delegatzuordnung bilden. Ein Beispiel für die Verwendung dieses Makros finden Sie unter [EVENT_DELEGATE_ENTRY](#event_delegate_entry).

### <a name="requirements"></a>Requirements (Anforderungen)

**Header:** msclr\event.h

## <a name="begin_interface_map"></a><a name="begin_interface_map"></a> BEGIN_INTERFACE_MAP

Beginnt die Definition der Schnitt Zuordnung, wenn Sie in der Implementierungs Datei verwendet wird.

### <a name="syntax"></a>Syntax

```
BEGIN_INTERFACE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>Parameter

*spiegeln*<br/>
Die Klasse, in der die Schnittstellenzuordnung definiert werden soll

*BaseClass*<br/>
Die Klasse, von der *TheClass* abgeleitet ist.

### <a name="remarks"></a>Bemerkungen

Für jede Schnittstelle, die implementiert wird, gibt es mindestens einen INTERFACE_PART Makro Aufruf. Für jedes Aggregat, das von der-Klasse verwendet wird, gibt es einen INTERFACE_AGGREGATE Makro Aufruf.

Weitere Informationen zu Schnittstellenkarten finden Sie im [technischen Hinweis 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Requirements (Anforderungen)

**Header:** afxwin.h

## <a name="commandhandler-delegate"></a><a name="commandhandler"></a> CommandHandler-Delegat

Registriert Rückruf Methoden mit einer Befehls Quelle.

### <a name="syntax"></a>Syntax

```
delegate void CommandHandler(  UINT^ cmdID  );
```

### <a name="parameters"></a>Parameter

*CMDID*<br/>
Die Befehls-ID.

### <a name="remarks"></a>Bemerkungen

Dieser Delegat registriert Rückruf Methoden mit einer Befehls Quelle. Wenn Sie dem Befehls Quell Objekt einen Delegaten hinzufügen, wird die Rückruf Methode zu einem Handler für Befehle, die aus der angegebenen Quelle stammen.

Weitere Informationen finden Sie unter Gewusst [wie: Hinzufügen von Befehls Routing zum Windows Forms-Steuer](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)Element.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzer Steuer Elements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Requirements (Anforderungen)

**Header:** afxwinforms. h (in Assemblyatlmfc\lib\mfcmifc80.dll definiert)

## <a name="commanduihandler"></a><a name="commanduihandler"></a> CommandUIHandler

Registriert Rückruf Methoden mit einer Benutzeroberflächen-Aktualisierungs Befehlsnachricht.

### <a name="syntax"></a>Syntax

```
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);
```

### <a name="parameters"></a>Parameter

*CMDID*<br/>
Die Befehls-ID.

*cmdUI*<br/>
Die befehlsnachrichten-ID.

### <a name="remarks"></a>Bemerkungen

Dieser Delegat registriert Rückruf Methoden mit einer Benutzeroberflächen-Aktualisierungs Befehls Meldung. `CommandUIHandler` ähnelt [CommandHandler](#commandhandler) , außer dass dieser Delegat mit Befehlen für die Aktualisierung von Benutzeroberflächen Objekten verwendet wird. Die Aktualisierungs Befehle der Benutzeroberfläche sollten mit nachrichtenhandlermethoden eins-zu-eins zugeordnet werden.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzer Steuer Elements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Requirements (Anforderungen)

**Header:** afxwinforms. h (in Assemblyatlmfc\lib\mfcmifc80.dll definiert)

## <a name="end_delegate_map"></a><a name="end_delegate_map"></a> END_DELEGATE_MAP

Beendet eine Delegatzuordnung.

### <a name="syntax"></a>Syntax

```
END_DELEGATE_MAP();
```

### <a name="remarks"></a>Bemerkungen

Dieses Makro markiert das Ende einer Liste von delegateinträgen, die eine Delegatzuordnung bilden. Ein Beispiel für die Verwendung dieses Makros finden Sie unter [EVENT_DELEGATE_ENTRY](#event_delegate_entry).

### <a name="requirements"></a>Requirements (Anforderungen)

**Header:** msclr\event.h

## <a name="end_interface_map"></a><a name="end_interface_map"></a> END_INTERFACE_MAP

Beendet die Schnittstellen Zuordnung in der Implementierungs Datei.

### <a name="syntax"></a>Syntax

```
END_INTERFACE_MAP( )
```

### <a name="remarks"></a>Bemerkungen

Weitere Informationen zu Schnittstellenkarten finden Sie im [technischen Hinweis 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Requirements (Anforderungen)

**Header:** afxwin.h

## <a name="event_delegate_entry"></a><a name="event_delegate_entry"></a> EVENT_DELEGATE_ENTRY

Erstellt einen Eintrag in der Delegatzuordnung.

### <a name="syntax"></a>Syntax

```
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);
```

### <a name="parameters"></a>Parameter

*Kollege*<br/>
Die Ereignishandlermethode, die dem Steuerelement angefügt werden soll.

*ARG0*<br/>
Das erste Argument der verwalteten Ereignishandlermethode, z `Object^` . b..

*Arg1*<br/>
Das zweite Argument der verwalteten Ereignishandlermethode, z `EventArgs^` . b..

### <a name="remarks"></a>Bemerkungen

Jeder Eintrag in der Delegatzuordnung entspricht einem verwalteten Ereignishandlerdelegaten, der von [MAKE_DELEGATE](#make_delegate)erstellt wurde.

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird gezeigt, wie EVENT_DELEGATE_ENTRY verwendet wird, um einen Eintrag in der Delegatzuordnung für den `OnClick` Ereignishandler zu erstellen. Siehe auch das Codebeispiel in MAKE_DELEGATE. Weitere Informationen finden Sie unter Vorgehens [Weise: Senke von Windows Forms Ereignissen von nativen C++-Klassen](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).

```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()
```

### <a name="requirements"></a>Requirements (Anforderungen)

**Header:** msclr\event.h

## <a name="interface_part"></a><a name="interface_part"></a> INTERFACE_PART

Wird zwischen dem BEGIN_INTERFACE_MAP-Makro und dem END_INTERFACE_MAP-Makro für jede Schnittstelle verwendet, die das Objekt unterstützt.

### <a name="syntax"></a>Syntax

```
INTERFACE_PART( theClass, iid, localClass)
```

### <a name="parameters"></a>Parameter

*spiegeln*<br/>
Der Name der Klasse, die die Schnittstellenzuordnung enthält.
*IID*<br/>
Die IID, die der eingebetteten Klasse zugeordnet werden soll.
*localclass*<br/>
Der Name der lokalen Klasse.

### <a name="remarks"></a>Bemerkungen

Sie ermöglicht es Ihnen, eine IID einem Member der Klasse zuzuordnen, die von *TheClass* und *localclass*angegeben wird.

Weitere Informationen zu Schnittstellenkarten finden Sie im [technischen Hinweis 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Requirements (Anforderungen)

**Header:** afxwin.h

## <a name="make_delegate"></a><a name="make_delegate"></a> MAKE_DELEGATE

Fügt einen Ereignishandler an ein verwaltetes Steuerelement an.

### <a name="syntax"></a>Syntax

```
MAKE_DELEGATE( DELEGATE,  MEMBER) ;
```

### <a name="parameters"></a>Parameter

*Führers*<br/>
Der Typ des verwalteten Ereignishandlerdelegaten, z. b. [EventHandler](/dotnet/api/system.eventhandler).

*Kollege*<br/>
Der Name der Ereignishandlermethode, die an das Steuerelement angefügt werden soll.

### <a name="remarks"></a>Bemerkungen

Dieses Makro erstellt einen verwalteten Ereignishandlerdelegaten *vom Typ* Delegat und *des Namens Members*. Der verwaltete Ereignishandlerdelegat ermöglicht es einer systemeigenen Klasse, verwaltete Ereignisse zu behandeln.

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird gezeigt, wie aufgerufen wird `MAKE_DELEGATE` , um einen `OnClick` Ereignishandler an ein MFC-Steuerelement anzufügen `MyControl` . Eine umfassendere Erläuterung der Funktionsweise dieses Makros in einer MFC-Anwendung finden Sie unter Vorgehens [Weise: Senke von Windows Forms Ereignissen von nativen C++-Klassen](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).

```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```

### <a name="requirements"></a>Requirements (Anforderungen)

**Header:** msclr\event.h

## <a name="see-also"></a>Weitere Informationen

[Gewusst wie: senken von Windows Forms Ereignissen aus nativen C++-Klassen](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)<br/>
[Gewusst wie: Hinzufügen von Befehls Routing zum Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[MFC-Makros, globale Funktionen und globale Variablen](mfc-macros-and-globals.md)<br/>
