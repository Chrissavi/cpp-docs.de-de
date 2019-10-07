---
title: CaCl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAcl
- ATLSECURITY/ATL::CAcl
- ATLSECURITY/ATL::CAcl::CAccessMaskArray
- ATLSECURITY/ATL::CAcl::CAceFlagArray
- ATLSECURITY/ATL::CAcl::CAceTypeArray
- ATLSECURITY/ATL::CAcl::CAcl
- ATLSECURITY/ATL::CAcl::GetAceCount
- ATLSECURITY/ATL::CAcl::GetAclEntries
- ATLSECURITY/ATL::CAcl::GetAclEntry
- ATLSECURITY/ATL::CAcl::GetLength
- ATLSECURITY/ATL::CAcl::GetPACL
- ATLSECURITY/ATL::CAcl::IsEmpty
- ATLSECURITY/ATL::CAcl::IsNull
- ATLSECURITY/ATL::CAcl::RemoveAce
- ATLSECURITY/ATL::CAcl::RemoveAces
- ATLSECURITY/ATL::CAcl::SetEmpty
- ATLSECURITY/ATL::CAcl::SetNull
helpviewer_keywords:
- CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
ms.openlocfilehash: 5d03154597f800042846e82d0a0cf5e7c46b613f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497890"
---
# <a name="cacl-class"></a>CaCl-Klasse

Diese Klasse ist ein Wrapper für eine `ACL` (Access-Control List)-Struktur.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CAcl
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CAcl::CAccessMaskArray](#caccessmaskarray)|Ein Array von ACCESS_MASKs.|
|[CAcl::CAceFlagArray](#caceflagarray)|Ein Bytearray.|
|[CAcl::CAceTypeArray](#cacetypearray)|Ein Bytearray.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CaCl:: CAcl](#cacl)|Der Konstruktor.|
|[CAcl::~CAcl](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAcl::GetAceCount](#getacecount)|Gibt die Anzahl der ACE (Access Control Entry)-Objekte zurück.|
|[CAcl::GetAclEntries](#getaclentries)|Ruft die Einträge in der Zugriffs Steuerungs Liste (Access Control List, ACL) aus dem `CAcl` -Objekt ab.|
|[CAcl::GetAclEntry](#getaclentry)|Ruft alle Informationen zu einem Eintrag in einem `CAcl` -Objekt ab.|
|[CAcl::GetLength](#getlength)|Gibt die Länge der ACL zurück.|
|[CAcl::GetPACL](#getpacl)|Gibt eine Pacl (Zeiger auf eine ACL) zurück.|
|[CAcl::IsEmpty](#isempty)|Testet das `CAcl` -Objekt auf Einträge.|
|[CAcl::IsNull](#isnull)|Gibt den Status des `CAcl` -Objekts zurück.|
|[CAcl::RemoveAce](#removeace)|Entfernt einen bestimmten ACE (Zugriffs Steuerungs Eintrag) aus dem `CAcl` -Objekt.|
|[CAcl::RemoveAces](#removeaces)|Entfernt alle ACEs (Zugriffs Steuerungs Einträge) aus der `CAcl` , die auf den angegebenen `CSid`angewendet werden.|
|[CAcl::SetEmpty](#setempty)|Markiert das `CAcl` -Objekt als leer.|
|[CAcl::SetNull](#setnull)|Markiert das `CAcl` Objekt als NULL.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CaCl:: Operator Konstanten ACL *](#operator_const_acl__star)|Wandelt ein `CAcl` -Objekt in `ACL` eine-Struktur um.|
|[CaCl:: Operator =](#operator_eq)|Zuweisungsoperator.|

## <a name="remarks"></a>Hinweise

Die `ACL` -Struktur ist der Header einer Zugriffs Steuerungs Liste (Access Control List, ACL). Eine ACL enthält eine sequenzielle Liste von NULL oder mehr [ACEs](/windows/win32/SecAuthZ/access-control-entries) (Access-Control-Einträge). Die einzelnen ACEs in einer ACL sind von 0 bis *n-1*nummeriert, wobei *n* die Anzahl der ACEs in der ACL ist. Wenn eine ACL bearbeitet wird, bezieht sich eine Anwendung auf einen Zugriffs Steuerungs Eintrag (ACE) innerhalb der ACL durch ihren Index.

Es gibt zwei ACL-Typen:

- Räumen

- System

Eine freigegebene Zugriffs Steuerungs Liste wird vom Besitzer eines Objekts gesteuert, oder jeder Person, die WRITE_DAC Zugriff auf das Objekt gewährt hat. Er gibt den Zugriff an, den bestimmte Benutzer und Gruppen auf ein Objekt haben können. Der Besitzer einer Datei kann z. b. eine freigegebene ACL verwenden, um zu steuern, welche Benutzer und Gruppen Zugriff auf die Datei haben können.

Einem Objekt können auch Sicherheitsinformationen auf Systemebene in Form einer System-ACL zugeordnet werden, die von einem Systemadministrator gesteuert wird. Eine System-ACL kann es dem Systemadministrator ermöglichen, alle Versuche, Zugriff auf ein Objekt zu erhalten, zu überwachen.

Weitere Informationen finden Sie in der [ACL](/windows/win32/SecAuthZ/access-control-lists) -Diskussion in der Windows SDK.

Eine Einführung zum Zugriffs Steuerungsmodell in Windows finden Sie unter [Access Control](/windows/win32/SecAuthZ/access-control) in der Windows SDK.

## <a name="requirements"></a>Anforderungen

**Header:** ATLSecurity. h

##  <a name="caccessmaskarray"></a>CaCl:: caccessmaskarray

Ein Array von ACCESS_MASK-Objekten.

```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>Hinweise

Diese Typdefinition gibt den Arraytyp an, der zum Speichern der in Zugriffs Steuerungs Einträgen (ACEs) verwendeten Zugriffsrechte verwendet werden kann.

##  <a name="caceflagarray"></a>CaCl:: caceflagarray

Ein Bytearray.

```
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>Hinweise

Diese Typdefinition gibt den Arraytyp an, der verwendet wird, um die ACE (Access Control Entry)-typspezifische Steuerungsflags zu definieren. Eine komplette Liste möglicher Flags finden Sie in der [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) -Definition.

##  <a name="cacetypearray"></a>CaCl:: cacetypeer Array

Ein Bytearray.

```
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>Hinweise

Diese Typdefinition gibt den Arraytyp an, der zum Definieren der Art der ACE-Objekte (Access Control Entry) verwendet wird, z. b. ACCESS_ALLOWED_ACE_TYPE oder ACCESS_DENIED_ACE_TYPE. Eine umfassende Liste möglicher Typen finden Sie in der [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) -Definition.

##  <a name="cacl"></a>CaCl:: CAcl

Der Konstruktor.

```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Ein vorhandenes `CAcl`-Objekt.

### <a name="remarks"></a>Hinweise

Das `CAcl` -Objekt kann optional mit einem vorhandenen `CAcl` -Objekt erstellt werden.

##  <a name="dtor"></a>CaCl:: ~ CAcl

Der Destruktor.

```
virtual ~CAcl() throw();
```

### <a name="remarks"></a>Hinweise

Der Dekonstruktor gibt alle Ressourcen frei, die vom-Objekt abgerufen wurden.

##  <a name="getacecount"></a>CaCl:: getacecount

Gibt die Anzahl der ACE (Access Control Entry)-Objekte zurück.

```
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der ACE-Einträge im `CAcl` -Objekt zurück.

##  <a name="getaclentries"></a>CaCl:: getaclentries

Ruft die Einträge in der Zugriffs Steuerungs Liste (Access Control List, ACL) aus dem `CAcl` -Objekt ab.

```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSids*<br/>
Ein Zeiger auf ein Array von [CSID](../../atl/reference/csid-class.md) -Objekten.

*pAccessMasks*<br/>
Die Zugriffs Masken.

*pAceTypes*<br/>
Die ACE-Typen (Access Control Entry, Zugriffs Steuerungs Eintrag).

*pAceFlags*<br/>
Die ACE-Flags.

### <a name="remarks"></a>Hinweise

Diese Methode füllt die Array Parameter mit den Details jedes ACE-Objekts, das im `CAcl` -Objekt enthalten ist. Verwenden Sie NULL, wenn die Details für dieses bestimmte Array nicht erforderlich sind.

Der Inhalt jedes Arrays entspricht einander, d. h., das erste Element des `CAccessMaskArray` Arrays entspricht dem ersten Element `CSidArray` im Array usw.

Weitere Informationen zu ACE-Typen und-Flags finden Sie unter [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

##  <a name="getaclentry"></a>CaCl:: getaclentry

Ruft alle Informationen zu einem Eintrag in einer Zugriffs Steuerungs Liste (Access Control List, ACL) ab.

```
void GetAclEntry(
    UINT nIndex,
    CSid* pSid,
    ACCESS_MASK* pMask = NULL,
    BYTE* pType = NULL,
    BYTE* pFlags = NULL,
    GUID* pObjectType = NULL,
    GUID* pInheritedObjectType = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index des abzurufenden ACL-Eintrags.

*pSid*<br/>
Das [CSID](../../atl/reference/csid-class.md) -Objekt, für das der ACL-Eintrag gilt.

*pMask*<br/>
Die Maske, die Berechtigungen angibt, um Zugriff zu gewähren oder zu verweigern.

*pType*<br/>
Der ACE-Typ.

*pFlags*<br/>
Die ACE-Flags.

*pObjectType*<br/>
Der Objekttyp. Diese wird auf GUID_NULL festgelegt, wenn der Objekttyp nicht im ACE angegeben ist, oder wenn der ACE kein Objekt-ACE ist.

*pInheritedObjectType*<br/>
Der geerbte Objekttyp. Diese wird auf GUID_NULL festgelegt, wenn der geerbte Objekttyp nicht im ACE angegeben ist, oder wenn der ACE kein Objekt-ACE ist.

### <a name="remarks"></a>Hinweise

Mit dieser Methode werden alle Informationen zu einem einzelnen ACE abgerufen, und es werden mehr Informationen bereitgestellt, als " [CaCl:: getaclentries](#getaclentries) Alone" verfügbar macht.

Weitere Informationen zu ACE-Typen und-Flags finden Sie unter [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

##  <a name="getlength"></a>CaCl:: GetLength

Gibt die Länge der Zugriffs Steuerungs Liste (Access Control List, ACL) zurück.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die erforderliche Länge in Bytes zurück, die zum `ACL` Speichern der Struktur erforderlich ist.

##  <a name="getpacl"></a>CaCl:: getpacl

Gibt einen Zeiger auf eine Zugriffs Steuerungs Liste (Access Control List, ACL) zurück.

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die `ACL` -Struktur zurück.

##  <a name="isempty"></a>CaCl:: IsEmpty

Testet das `CAcl` -Objekt auf Einträge.

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>Hinweise

Gibt "true" `CAcl` zurück, wenn das Objekt nicht NULL ist und keine Einträge enthält. Gibt false zurück, `CAcl` wenn das Objekt entweder NULL ist oder mindestens einen Eintrag enthält.

##  <a name="isnull"></a>CaCl:: IsNull

Gibt den Status des `CAcl` -Objekts zurück.

```
bool IsNull() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, `CAcl` wenn das Objekt NULL ist, andernfalls false.

##  <a name="operator_const_acl__star"></a>CaCl:: Operator Konstanten ACL *

Wandelt ein `CAcl` -Objekt in `ACL` eine-Struktur (Zugriffs Steuerungs Liste) um.

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>Hinweise

Gibt die Adresse `ACL` der-Struktur zurück.

##  <a name="operator_eq"></a>CaCl:: Operator =

Zuweisungsoperator.

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Der `CAcl` , der dem vorhandenen Objekt zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf das aktualisierte `CAcl` Objekt zurück.

##  <a name="removeace"></a>CaCl:: RemoveAce

Entfernt einen bestimmten ACE (Zugriffs Steuerungs Eintrag) aus dem `CAcl` -Objekt.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index für den zu entfern-ACE-Eintrag.

### <a name="remarks"></a>Hinweise

Diese Methode wird von [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat) abgeleitet.

##  <a name="removeaces"></a>CaCl:: removeaces

Entfernt alle-ACEs (Zugriffs Steuerungs Einträge) aus der `CAcl` , die auf den angegebenen `CSid`angewendet werden.

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Ein Verweis auf ein `CSid`-Objekt.

##  <a name="setempty"></a>CAcl::SetEmpty

Markiert das `CAcl` -Objekt als leer.

```
void SetEmpty() throw();
```

### <a name="remarks"></a>Hinweise

`CAcl` Kann auf leer oder auf NULL festgelegt werden: die beiden Zustände sind unterschiedlich.

##  <a name="setnull"></a>CaCl:: SetNull

Markiert das `CAcl` Objekt als NULL.

```
void SetNull() throw();
```

### <a name="remarks"></a>Hinweise

`CAcl` Kann auf leer oder auf NULL festgelegt werden: die beiden Zustände sind unterschiedlich.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
