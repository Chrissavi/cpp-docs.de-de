---
title: CSimpleStringT-Klasse
ms.date: 10/18/2018
f1_keywords:
- CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::PCXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::PXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::Append
- ATLSIMPSTR/ATL::CSimpleStringT::AppendChar
- ATLSIMPSTR/ATL::CSimpleStringT::CopyChars
- ATLSIMPSTR/ATL::CSimpleStringT::CopyCharsOverlapped
- ATLSIMPSTR/ATL::CSimpleStringT::Empty
- ATLSIMPSTR/ATL::CSimpleStringT::FreeExtra
- ATLSIMPSTR/ATL::CSimpleStringT::GetAllocLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetAt
- ATLSIMPSTR/ATL::CSimpleStringT::GetBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::GetBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetManager
- ATLSIMPSTR/ATL::CSimpleStringT::GetString
- ATLSIMPSTR/ATL::CSimpleStringT::IsEmpty
- ATLSIMPSTR/ATL::CSimpleStringT::LockBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::Preallocate
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::SetAt
- ATLSIMPSTR/ATL::CSimpleStringT::SetManager
- ATLSIMPSTR/ATL::CSimpleStringT::SetString
- ATLSIMPSTR/ATL::CSimpleStringT::StringLength
- ATLSIMPSTR/ATL::CSimpleStringT::Truncate
- ATLSIMPSTR/ATL::CSimpleStringT::UnlockBuffer
helpviewer_keywords:
- shared classes, CSimpleStringT
- strings [C++], ATL class
- CSimpleStringT class
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
ms.openlocfilehash: bbbab04ff311d874fc209d2c46fadda57e79a222
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219091"
---
# <a name="csimplestringt-class"></a>CSimpleStringT-Klasse

Diese Klasse stellt ein- `CSimpleStringT` Objekt dar.

## <a name="syntax"></a>Syntax

```
template <typename BaseType>
class CSimpleStringT
```

### <a name="parameters"></a>Parameter

*BaseType*<br/>
Der Zeichentyp der Zeichen folgen Klasse. Dabei kann es sich um eine der folgenden Methoden handeln:

- **`char`**(für ANSI-Zeichen folgen).

- **`wchar_t`**(für Unicode-Zeichen folgen).

- Tchar (für ANSI-und Unicode-Zeichen folgen).

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|[CSimpleStringT::P cxstr](#pcxstr)|Ein Zeiger auf eine Konstantenzeichenfolge.|
|[CSimpleStringT::P xstr](#pxstr)|Ein Zeiger auf eine Zeichenfolge.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[CSimpleStringT::CSimpleStringT](#ctor)|Erstellt- `CSimpleStringT` Objekte auf verschiedene Weise.|
|[CSimpleStringT:: ~ CSimpleStringT](#dtor)|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|name|BESCHREIBUNG|
|----------|-----------------|
|[CSimpleStringT:: Append](#append)|Fügt ein- `CSimpleStringT` Objekt an ein vorhandenes- `CSimpleStringT` Objekt an.|
|[CSimpleStringT:: AppendChar](#appendchar)|Fügt ein Zeichen an ein vorhandenes- `CSimpleStringT` Objekt an.|
|[CSimpleStringT:: copychars](#copychars)|Kopiert ein Zeichen oder Zeichen in eine andere Zeichenfolge.|
|[CSimpleStringT:: copycharsoverlgetauscht](#copycharsoverlapped)|Kopiert ein Zeichen oder Zeichen in eine andere Zeichenfolge, in der sich die Puffer überlappen.|
|[CSimpleStringT:: Empty](#empty)|Erzwingt eine Zeichenfolge mit einer Länge von 0 (null).|
|[CSimpleStringT:: freextra](#freeextra)|Gibt zusätzlichen Arbeitsspeicher frei, der zuvor durch das Zeichen folgen Objekt belegt wurde.|
|[CSimpleStringT:: getalloclength](#getalloclength)|Ruft die zugeordnete Länge eines- `CSimpleStringT` Objekts ab.|
|[CSimpleStringT:: GetAt](#getat)|Gibt das Zeichen an der angegebenen Position zurück.|
|[CSimpleStringT:: GetBuffer](#getbuffer)|Gibt einen Zeiger auf die Zeichen in einer zurück `CSimpleStringT` .|
|[CSimpleStringT:: getbuffersetlength](#getbuffersetlength)|Gibt einen Zeiger auf die Zeichen in einem-Wert zurück `CSimpleStringT` , der auf die angegebene Länge abgeschnitten wird.|
|[CSimpleStringT:: GetLength](#getlength)|Gibt die Anzahl von Zeichen in einem- `CSimpleStringT` Objekt zurück.|
|[CSimpleStringT:: GetManager](#getmanager)|Ruft den Speicher-Manager des- `CSimpleStringT` Objekts ab.|
|[CSimpleStringT:: GetString](#getstring)|Ruft die Zeichenfolge ab.|
|[CSimpleStringT:: IsEmpty](#isempty)|Testet, ob ein- `CSimpleStringT` Objekt keine Zeichen enthält.|
|[CSimpleStringT:: LockBuffer](#lockbuffer)|Deaktiviert die Verweis Zählung und schützt die Zeichenfolge im Puffer.|
|[CSimpleStringT::P neu zuordnen](#preallocate)|Ordnet eine bestimmte Arbeitsspeicher Menge für den Zeichen Puffer zu.|
|[CSimpleStringT:: ReleaseBuffer](#releasebuffer)|Gibt die Steuerung des von zurückgegebenen Puffers frei `GetBuffer` .|
|[CSimpleStringT:: ReleaseBufferSetLength](#releasebuffersetlength)|Gibt die Steuerung des von zurückgegebenen Puffers frei `GetBuffer` .|
|[CSimpleStringT:: *](#setat)|Legt ein Zeichen an der angegebenen Position fest.|
|[CSimpleStringT:: setmanager](#setmanager)|Legt den Speicher-Manager eines- `CSimpleStringT` Objekts fest.|
|[CSimpleStringT:: SetString](#setstring)|Legt die Zeichenfolge eines- `CSimpleStringT` Objekts fest.|
|[CSimpleStringT:: StringLength](#stringlength)|Gibt die Anzahl der Zeichen in der angegebenen Zeichenfolge zurück.|
|[CSimpleStringT:: TRUNCATE](#truncate)|Verkürzt die Zeichenfolge auf eine angegebene Länge.|
|[CSimpleStringT:: UnlockBuffer](#unlockbuffer)|Aktiviert die Verweis Zählung und gibt die Zeichenfolge im Puffer frei.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[CSimpleStringT:: Operator PCXSTR](#operator_pcxstr)|Greift direkt auf in einem- `CSimpleStringT` Objekt gespeicherte Zeichen als Zeichenfolge im C-Format zu.|
|[CSimpleStringT::operator\[\]](#operator_at)|Gibt das Zeichen an der angegebenen Position – Operator Ersetzung für zurück `GetAt` .|
|[CSimpleStringT:: Operator + =](#operator_add_eq)|Verkettet eine neue Zeichenfolge am Ende einer vorhandenen Zeichenfolge.|
|[CSimpleStringT:: Operator =](#operator_eq)|Weist einem-Objekt einen neuen Wert zu `CSimpleStringT` .|

### <a name="remarks"></a>Bemerkungen

`CSimpleStringT`ist die Basisklasse für die verschiedenen Zeichen folgen Klassen, die von Visual C++ unterstützt werden. Sie bietet minimale Unterstützung für die Speicherverwaltung des Zeichen folgen Objekts und der grundlegenden Puffer Bearbeitung. Erweiterte Zeichen folgen Objekte finden Sie unter [CStringT-Klasse](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="requirements"></a>Requirements (Anforderungen)

**Header:** atlsimpstr. h

## <a name="csimplestringtappend"></a><a name="append"></a>CSimpleStringT:: Append

Fügt ein- `CSimpleStringT` Objekt an ein vorhandenes- `CSimpleStringT` Objekt an.

### <a name="syntax"></a>Syntax

```cpp
void Append(const CSimpleStringT& strSrc);
void Append(PCXSTR pszSrc, int nLength);
void Append(PCXSTR pszSrc);
```

#### <a name="parameters"></a>Parameter

*"Straume"*<br/>
Das `CSimpleStringT` anzufügende Objekt.

*pszSrc*<br/>
Ein Zeiger auf eine Zeichenfolge, die die anzufügenden Zeichen enthält.

*nlength*<br/>
Die Anzahl der anzufügenden Zeichen.

### <a name="remarks"></a>Bemerkungen

Rufen Sie diese Methode auf, um ein vorhandenes `CSimpleStringT` Objekt an ein anderes Objekt anzufügen `CSimpleStringT` .

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::Append`.

```cpp
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```

## <a name="csimplestringtappendchar"></a><a name="appendchar"></a>CSimpleStringT:: AppendChar

Fügt ein Zeichen an ein vorhandenes- `CSimpleStringT` Objekt an.

### <a name="syntax"></a>Syntax

```cpp
void AppendChar(XCHAR ch);
```

#### <a name="parameters"></a>Parameter

*ch*<br/>
Das anzufügende Zeichen.

### <a name="remarks"></a>Bemerkungen

Rufen Sie diese Funktion auf, um das angegebene Zeichen an das Ende eines vorhandenen `CSimpleStringT` Objekts anzufügen.

## <a name="csimplestringtcopychars"></a><a name="copychars"></a>CSimpleStringT:: copychars

Kopiert ein Zeichen oder Zeichen in ein- `CSimpleStringT` Objekt.

### <a name="syntax"></a>Syntax

```
static void CopyChars(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>Parameter

*pchdest*<br/>
Ein Zeiger auf eine Zeichenfolge.

*pchsrc*<br/>
Ein Zeiger auf eine Zeichenfolge, die die zu kopierenden Zeichen enthält.

*nchars*<br/>
Die Anzahl der zu kopierenden *pchsrc* -Zeichen.

### <a name="remarks"></a>Bemerkungen

Diese Methode wird aufgerufen, um Zeichen aus *pchsrc* in die *pchdest* -Zeichenfolge zu kopieren.

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::CopyChars`.

```cpp
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```

## <a name="csimplestringtcopycharsoverlapped"></a><a name="copycharsoverlapped"></a>CSimpleStringT:: copycharsoverlgetauscht

Kopiert ein Zeichen oder Zeichen in ein- `CSimpleStringT` Objekt.

### <a name="syntax"></a>Syntax

```
static void CopyCharsOverlapped(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>Parameter

*pchdest*<br/>
Ein Zeiger auf eine Zeichenfolge.

*pchsrc*<br/>
Ein Zeiger auf eine Zeichenfolge, die die zu kopierenden Zeichen enthält.

*nchars*<br/>
Die Anzahl der zu kopierenden *pchsrc* -Zeichen.

### <a name="remarks"></a>Bemerkungen

Diese Methode wird aufgerufen, um Zeichen aus *pchsrc* in die *pchdest* -Zeichenfolge zu kopieren. Im Gegensatz zu `CopyChars` `CopyCharsOverlapped` stellt eine sichere Methode zum Kopieren aus Zeichen Puffern bereit, die möglicherweise überlappen.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [CSimpleStringT:: copychars](#copychars)oder den Quellcode für `CSimpleStringT::SetString` (in atlsimpstr. h).

## <a name="csimplestringtcsimplestringt"></a><a name="ctor"></a>CSimpleStringT::CSimpleStringT

Erstellt ein `CSimpleStringT`-Objekt.

### <a name="syntax"></a>Syntax

```
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr);
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr);
CSimpleStringT(const CSimpleStringT& strSrc);
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw();
```

#### <a name="parameters"></a>Parameter

*"Straume"*<br/>
Ein vorhandenes- `CSimpleStringT` Objekt, das in dieses-Objekt kopiert werden soll `CSimpleStringT` .

*pchsrc*<br/>
Ein Zeiger auf ein Array von Zeichen der Länge *nlength*, nicht Null beendet.

*pszSrc*<br/>
Eine mit NULL endende Zeichenfolge, die in dieses-Objekt kopiert werden soll `CSimpleStringT` .

*nlength*<br/>
Die Anzahl der Zeichen in `pch` .

*pstringmgr*<br/>
Ein Zeiger auf den Speicher-Manager des- `CSimpleStringT` Objekts. Weitere Informationen zu `IAtlStringMgr` und zur Speicherverwaltung für `CSimpleStringT` finden Sie unter [Speicherverwaltung und CStringT](../memory-management-with-cstringt.md).

### <a name="remarks"></a>Bemerkungen

Erstellt ein neues `CSimpleStringT`-Objekt. Da die Konstruktoren die Eingabedaten in neuen zugeordneten Speicher kopieren, können Arbeitsspeicher Ausnahmen entstehen.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Verwendung von `CSimpleStringT::CSimpleStringT` mithilfe von ATL veranschaulicht **`typedef`** `CSimpleString` . `CSimpleString`ist eine häufig verwendete Spezialisierung der Klassen Vorlage `CSimpleStringT` .

```cpp
CSimpleString s1(pMgr);
// Empty string
CSimpleString s2(_T("cat"), pMgr);
// From a C string literal

CSimpleString s3(s2);
// Copy constructor
CSimpleString s4(s2 + _T(" ") + s3);

// From a string expression
CSimpleString s5(_T("xxxxxx"), 6, pMgr);
// s5 = "xxxxxx"
```

## <a name="csimplestringtempty"></a><a name="empty"></a>CSimpleStringT:: Empty

Macht dieses `CSimpleStringT` Objekt zu einer leeren Zeichenfolge und gibt Arbeitsspeicher entsprechend frei.

### <a name="syntax"></a>Syntax

```cpp
void Empty() throw();
```

### <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [String: CString Exception Cleanup](../cstring-exception-cleanup.md).

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::Empty`.

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtfreeextra"></a><a name="freeextra"></a>CSimpleStringT:: freextra

Gibt zusätzlichen Arbeitsspeicher frei, der zuvor von der Zeichenfolge zugeordnet, aber nicht mehr benötigt wird.

### <a name="syntax"></a>Syntax

```cpp
void FreeExtra();
```

### <a name="remarks"></a>Bemerkungen

Dadurch sollte der Arbeitsspeicher Aufwand reduziert werden, der vom Zeichen folgen Objekt beansprucht wird. Die-Methode ordnet den Puffer wieder der exakten Länge zu, die von [GetLength](#getlength)zurückgegeben wird.

### <a name="example"></a>Beispiel

```cpp
CAtlString basestr;
IAtlStringMgr* pMgr;

pMgr= basestr.GetManager();
ASSERT(pMgr != NULL);

// Create a CSimpleString with 28 characters
CSimpleString str(_T("Many sports are fun to play."), 28, pMgr);
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// Assigning a smaller string won't cause CSimpleString to free its
// memory, because it assumes the string will grow again anyway.
str = _T("Soccer is best!");
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// This call forces CSimpleString to release the extra
// memory it doesn't need.
str.FreeExtra();
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());
```

### <a name="remarks"></a>Bemerkungen

Die Ausgabe dieses Beispiels lautet wie folgt:

```Output
Alloc length is 1031, String length is 1024
Alloc length is 1031, String length is 15
Alloc length is 15, String length is 15
```

## <a name="csimplestringtgetalloclength"></a><a name="getalloclength"></a>CSimpleStringT:: getalloclength

Ruft die zugeordnete Länge eines- `CSimpleStringT` Objekts ab.

### <a name="syntax"></a>Syntax

```
int GetAllocLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Zeichen, die diesem-Objekt zugeordnet sind.

### <a name="remarks"></a>Bemerkungen

Mit dieser Methode können Sie die Anzahl der Zeichen bestimmen, die diesem Objekt zugeordnet sind `CSimpleStringT` . Ein Beispiel für den Aufruf dieser Funktion finden Sie unter " [freextra](#freeextra) ".

## <a name="csimplestringtgetat"></a><a name="getat"></a>CSimpleStringT:: GetAt

Gibt ein Zeichen aus einem- `CSimpleStringT` Objekt zurück.

### <a name="syntax"></a>Syntax

```
XCHAR GetAt(int iChar) const;
```

#### <a name="parameters"></a>Parameter

*IChar*<br/>
NULL basierter Index des Zeichens im- `CSimpleStringT` Objekt. Der- *IChar* -Parameter muss größer oder gleich 0 und kleiner als der von [GetLength](#getlength)zurückgegebene Wert sein. Andernfalls `GetAt` wird von eine Ausnahme generiert.

### <a name="return-value"></a>Rückgabewert

Ein `XCHAR` , das das Zeichen an der angegebenen Position in der Zeichenfolge enthält.

### <a name="remarks"></a>Bemerkungen

Mit dieser Methode wird das von *IChar*angegebene Zeichen zurückgegeben. Der überladene Index Operator (**[]**) ist ein bequemer Alias für `GetAt` . Das NULL-Terminator ist adressierbar, ohne dass eine Ausnahme mithilfe von erzeugt wird `GetAt` . Sie wird jedoch nicht von gezählt `GetLength` , und der zurückgegebene Wert ist 0.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Verwendung von veranschaulicht `CSimpleStringT::GetAt` .

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```

## <a name="csimplestringtgetbuffer"></a><a name="getbuffer"></a>CSimpleStringT:: GetBuffer

Gibt einen Zeiger auf den internen Zeichen Puffer für das- `CSimpleStringT` Objekt zurück.

### <a name="syntax"></a>Syntax

```
PXSTR GetBuffer(int nMinBufferLength);
PXSTR GetBuffer();
```

#### <a name="parameters"></a>Parameter

*nminbufferlength*<br/>
Die Mindestanzahl von Zeichen, die der Zeichen Puffer enthalten kann. Dieser Wert enthält keinen Platz für ein NULL-Terminator.

Wenn *nminbufferlength* größer ist als die Länge des aktuellen Puffers, `GetBuffer` zerstört den aktuellen Puffer, ersetzt ihn durch einen Puffer der angeforderten Größe und setzt den Objekt Verweis Zähler auf 0 (null) zurück. Wenn Sie zuvor [Lock Buffer](#lockbuffer) für diesen Puffer aufgerufen haben, verlieren Sie die Puffer Sperre.

### <a name="return-value"></a>Rückgabewert

Ein `PXSTR` Zeiger auf den (null-terminierten) Zeichen Puffer des Objekts.

### <a name="remarks"></a>Bemerkungen

Ruft diese Methode auf, um den Pufferinhalt des-Objekts zurückzugeben `CSimpleStringT` . Der zurückgegebene `PXSTR` ist keine Konstante und ermöglicht daher die direkte `CSimpleStringT` Inhalts Änderung.

Wenn Sie den Zeiger verwenden, der von zurückgegeben `GetBuffer` wird, um den Inhalt der Zeichenfolge zu ändern, müssen Sie [ReleaseBuffer](#releasebuffer) vor der Verwendung anderer Element Methoden aufzurufen `CSimpleStringT` .

Die von zurückgegebene Adresse `GetBuffer` ist nach dem-Rückruf möglicherweise nicht gültig, `ReleaseBuffer` da zusätzliche `CSimpleStringT` Vorgänge dazu führen können, dass der `CSimpleStringT` Puffer neu zugewiesen wird. Wenn Sie die Länge von nicht ändern, wird der Puffer nicht neu zugeordnet `CSimpleStringT` .

Der Puffer Arbeitsspeicher wird automatisch freigegeben, wenn das `CSimpleStringT` Objekt zerstört wird.

Wenn Sie die Zeichen folgen Länge selbst nachverfolgen, sollten Sie das abschließende Null-Zeichen nicht anfügen. Sie müssen jedoch die endgültige Zeichen folgen Länge angeben, wenn Sie den Puffer mit freigeben `ReleaseBuffer` . Wenn Sie ein abschließendes NULL-Zeichen anfügen, sollten Sie-1 (Standard) für die Länge übergeben. `ReleaseBuffer`bestimmt dann die Pufferlänge.

Wenn nicht genügend Arbeitsspeicher vorhanden ist, um die Anforderung zu erfüllen `GetBuffer` , löst diese Methode eine cmemoryexception * aus.

### <a name="example"></a>Beispiel

```cpp
CSimpleString s(_T("abcd"), pMgr);
LPTSTR pBuffer = s.GetBuffer(10);
int sizeOfBuffer = s.GetAllocLength();

// Directly access CSimpleString buffer
_tcscpy_s(pBuffer, sizeOfBuffer, _T("Hello"));
ASSERT(_tcscmp(s, _T("Hello")) == 0);
s.ReleaseBuffer();
```

## <a name="csimplestringtgetbuffersetlength"></a><a name="getbuffersetlength"></a>CSimpleStringT:: getbuffersetlength

Gibt einen Zeiger auf den internen Zeichen Puffer für das- `CSimpleStringT` Objekt zurück, wobei seine Länge bei Bedarf abgeschnitten oder vergrößert wird, um genau mit der in *nlength*angegebenen Länge übereinzustimmen.

### <a name="syntax"></a>Syntax

```
PXSTR GetBufferSetLength(int nLength);
```

#### <a name="parameters"></a>Parameter

*nlength*<br/>
Die genaue Größe des `CSimpleStringT` Zeichen Puffers in Zeichen.

### <a name="return-value"></a>Rückgabewert

Ein `PXSTR` Zeiger auf den (null-terminierten) Zeichen Puffer des Objekts.

### <a name="remarks"></a>Bemerkungen

Rufen Sie diese Methode auf, um eine angegebene Länge des internen Puffers des- `CSimpleStringT` Objekts abzurufen. Der zurückgegebene `PXSTR` Zeiger ist nicht **`const`** und ermöglicht somit eine direkte `CSimpleStringT` Inhalts Änderung.

Wenn Sie den von [getbuffersetlength](#getbuffersetlength) zurückgegebenen Zeiger verwenden, um den Inhalt der Zeichenfolge zu ändern, müssen Sie aufrufen, `ReleaseBuffer` um den internen Zustand von zu aktualisieren, `CsimpleStringT` bevor Sie eine andere `CSimpleStringT` Methode verwenden.

Die von zurückgegebene Adresse `GetBufferSetLength` ist nach dem-Rückruf möglicherweise nicht gültig, `ReleaseBuffer` da zusätzliche `CSimpleStringT` Vorgänge dazu führen können, dass der `CSimpleStringT` Puffer neu zugewiesen wird. Der Puffer wird nicht neu zugewiesen, wenn Sie die Länge von nicht ändern `CSimpleStringT` .

Der Puffer Arbeitsspeicher wird automatisch freigegeben, wenn das `CSimpleStringT` Objekt zerstört wird.

Wenn Sie die Zeichen folgen Länge selbst nachverfolgen, fügen Sie das abschließende Null-Zeichen nicht an. Sie müssen die endgültige Zeichen folgen Länge angeben, wenn Sie den Puffer mit freigeben `ReleaseBuffer` . Wenn Sie beim-Befehl ein abschließendes NULL-Zeichen anfügen, `ReleaseBuffer` übergeben Sie-1 (Standard) für die Länge an `ReleaseBuffer` und `ReleaseBuffer` führt einen für `strlen` den Puffer aus, um seine Länge zu bestimmen.

Weitere Informationen zur Verweis Zählung finden Sie in den folgenden Artikeln:

- [Verwalten von Objekt Lebensdauern durch Verweis Zählung](/windows/win32/com/managing-object-lifetimes-through-reference-counting) in der Windows SDK.

- [Implementieren der Verweis Zählung](/windows/win32/com/implementing-reference-counting) in der Windows SDK.

- [Regeln zum Verwalten der Verweis Anzahl](/windows/win32/com/rules-for-managing-reference-counts) in der Windows SDK.

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::GetBufferSetLength`.

```cpp
CSimpleString str(pMgr);
LPTSTR pstr = str.GetBufferSetLength(3);
pstr[0] = _T('C');
pstr[1] = _T('u');
pstr[2] = _T('p');

// No need for trailing zero or call to ReleaseBuffer()
// because GetBufferSetLength() set it for us.

str += _T(" soccer is best!");
ASSERT(_tcscmp(str, _T("Cup soccer is best!")) == 0);
```

## <a name="csimplestringtgetlength"></a><a name="getlength"></a>CSimpleStringT:: GetLength

Gibt die Anzahl der Zeichen im- `CSimpleStringT` Objekt zurück.

### <a name="syntax"></a>Syntax

```
int GetLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Zeichen in der Zeichenfolge.

### <a name="remarks"></a>Bemerkungen

Mit dieser Methode wird die Anzahl der Zeichen im-Objekt zurückgegeben. Die Anzahl enthält keinen null-Terminator.

Bei Multibytezeichen-Zeichensätzen (MBCS) `GetLength` zählt jedes 8-Bit-Zeichen, d. h., ein Lead-und ein nachfolgendes Byte in einem Multibytezeichen werden als zwei Bytes gezählt. Ein Beispiel für den Aufruf dieser Funktion finden Sie unter " [freextra](#freeextra) ".

## <a name="csimplestringtgetmanager"></a><a name="getmanager"></a>CSimpleStringT:: GetManager

Ruft den Speicher-Manager des- `CSimpleStringT` Objekts ab.

### <a name="syntax"></a>Syntax

```
IAtlStringMgr* GetManager() const throw();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Speicher-Manager für das- `CSimpleStringT` Objekt.

### <a name="remarks"></a>Bemerkungen

Rufen Sie diese Methode auf, um den vom-Objekt verwendeten Speicher-Manager abzurufen `CSimpleStringT` . Weitere Informationen zu Speicher-Managern und Zeichen folgen Objekten finden Sie unter [Speicherverwaltung und CStringT](../memory-management-with-cstringt.md).

## <a name="csimplestringtgetstring"></a><a name="getstring"></a>CSimpleStringT:: GetString

Ruft die Zeichenfolge ab.

### <a name="syntax"></a>Syntax

```
PCXSTR GetString() const throw();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine NULL-terminierte Zeichenfolge.

### <a name="remarks"></a>Bemerkungen

Rufen Sie diese Methode auf, um die dem-Objekt zugeordnete Zeichenfolge abzurufen `CSimpleStringT` .

> [!NOTE]
> Der zurückgegebene `PCXSTR` Zeiger ist, **`const`** und lässt keine direkte Inhalts Änderung zu `CSimpleStringT` .

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::GetString`.

```cpp
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```

## <a name="csimplestringtisempty"></a><a name="isempty"></a>CSimpleStringT:: IsEmpty

Testet ein- `CSimpleStringT` Objekt auf die leere Bedingung.

### <a name="syntax"></a>Syntax

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das `CSimpleStringT` Objekt eine Länge von 0 hat; andernfalls false.

### <a name="remarks"></a>Bemerkungen

Ruft diese Methode auf, um zu bestimmen, ob das Objekt eine leere Zeichenfolge enthält.

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::IsEmpty`.

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtlockbuffer"></a><a name="lockbuffer"></a>CSimpleStringT:: LockBuffer

Deaktiviert die Verweis Zählung und schützt die Zeichenfolge im Puffer.

### <a name="syntax"></a>Syntax

```
PXSTR LockBuffer();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein- `CSimpleStringT` Objekt oder eine NULL terminierte Zeichenfolge.

### <a name="remarks"></a>Bemerkungen

Ruft diese Methode auf, um den Puffer des-Objekts zu sperren `CSimpleStringT` . Wenn `LockBuffer` Sie aufrufen, erstellen Sie eine Kopie der Zeichenfolge mit dem-1 für den Verweis Zähler. Wenn der Verweis Zählerwert-1 ist, wird die Zeichenfolge im Puffer als "gesperrt" eingestuft. Die Zeichenfolge ist im gesperrten Zustand auf zweierlei Weise geschützt:

- Keine andere Zeichenfolge kann einen Verweis auf die Daten in der gesperrten Zeichenfolge erhalten, auch wenn diese Zeichenfolge der gesperrten Zeichenfolge zugewiesen ist.

- Die gesperrte Zeichenfolge verweist nie auf eine andere Zeichenfolge, auch wenn diese andere Zeichenfolge in die gesperrte Zeichenfolge kopiert wird.

Wenn Sie die Zeichenfolge im Puffer sperren, stellen Sie sicher, dass die exklusive Aufbewahrung der Zeichenfolge im Puffer intakt bleibt.

Nachdem Sie mit fertig sind `LockBuffer` , müssen Sie [UnlockBuffer](#unlockbuffer) aufzurufen, um den Verweis Zähler auf 1 zurückzusetzen.

> [!NOTE]
> Wenn Sie [GetBuffer](#getbuffer) für einen gesperrten Puffer aufrufen und der- `GetBuffer` Parameter auf einen Wert `nMinBufferLength` größer als die Länge des aktuellen Puffers festgelegt wird, verlieren Sie die Puffer Sperre. Ein solcher Rückruf `GetBuffer` von zerstört den aktuellen Puffer, ersetzt ihn durch einen Puffer der angeforderten Größe und setzt den Verweis Zähler auf 0 (null) zurück.

Weitere Informationen zur Verweis Zählung finden Sie in den folgenden Artikeln:

- [Verwalten von Objekt Lebensdauern durch Verweis Zählung](/windows/win32/com/managing-object-lifetimes-through-reference-counting) in der Windows SDK

- [Implementieren der Verweis Zählung](/windows/win32/com/implementing-reference-counting) in der Windows SDK

- [Regeln zum Verwalten der Verweis Anzahl](/windows/win32/com/rules-for-managing-reference-counts) in der Windows SDK

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::LockBuffer`.

```cpp
CSimpleString str(_T("Hello"), pMgr);
TCHAR ch;

str.LockBuffer();
ch = str.GetAt(2);
_tprintf_s(_T("%c"), ch);
str.UnlockBuffer();
```

## <a name="csimplestringtoperator"></a><a name="operator_at"></a>CSimpleStringT:: Operator\[\]

Mit dieser Funktion können Sie auf ein einzelnes Zeichen des Zeichen Arrays zugreifen.

### <a name="syntax"></a>Syntax

```
XCHAR operator[](int iChar) const;
```

#### <a name="parameters"></a>Parameter

*IChar*<br/>
NULL basierter Index eines Zeichens in der Zeichenfolge.

### <a name="remarks"></a>Bemerkungen

Der überladene Index Operator (**[]**) gibt ein einzelnes Zeichen zurück, das durch den NULL basierten Index in *IChar*angegeben wird. Dieser Operator ist ein bequemer Ersatz für die [GetAt](#getat) -Member-Funktion.

> [!NOTE]
> Sie können den Index Operator (**[]**) verwenden, um den Wert eines Zeichens in einer zu erhalten `CSimpleStringT` . Sie können ihn jedoch nicht zum Ändern des Werts eines Zeichens in einem verwenden `CSimpleStringT` .

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::operator []`.

```cpp
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```

## <a name="csimplestringtoperator-"></a><a name="operator_at"></a>CSimpleStringT:: Operator\[\]

Mit dieser Funktion können Sie auf ein einzelnes Zeichen des Zeichen Arrays zugreifen.

### <a name="syntax"></a>Syntax

```
XCHAR operator[](int iChar) const;
```

### <a name="parameters"></a>Parameter

*IChar*<br/>
NULL basierter Index eines Zeichens in der Zeichenfolge.

### <a name="remarks"></a>Bemerkungen

Der überladene Index Operator (**[]**) gibt ein einzelnes Zeichen zurück, das durch den NULL basierten Index in *IChar*angegeben wird. Dieser Operator ist ein bequemer Ersatz für die [GetAt](#getat) -Member-Funktion.

> [!NOTE]
> Sie können den Index Operator (**[]**) verwenden, um den Wert eines Zeichens in einer zu erhalten `CSimpleStringT` . Sie können ihn jedoch nicht zum Ändern des Werts eines Zeichens in einem verwenden `CSimpleStringT` .

## <a name="csimplestringtoperator-"></a><a name="operator_add_eq"></a>CSimpleStringT:: Operator + =

Fügt eine neue Zeichenfolge oder ein Zeichen am Ende einer vorhandenen Zeichenfolge an.

### <a name="syntax"></a>Syntax

```
CSimpleStringT& operator +=(PCXSTR pszSrc);
CSimpleStringT& operator +=(const CSimpleStringT& strSrc);
template<int t_nSize>
CSimpleStringT& operator+=(const CStaticString< XCHAR, t_nSize >& strSrc);
CSimpleStringT& operator +=(char ch);
CSimpleStringT& operator +=(unsigned char ch);
CSimpleStringT& operator +=(wchar_t ch);
```

#### <a name="parameters"></a>Parameter

*pszSrc*<br/>
Ein Zeiger auf eine NULL-terminierte Zeichenfolge.

*"Straume"*<br/>
Ein Zeiger auf ein vorhandenes- `CSimpleStringT` Objekt.

*ch*<br/>
Das Zeichen, das angefügt werden soll.

### <a name="remarks"></a>Bemerkungen

Der-Operator akzeptiert ein anderes- `CSimpleStringT` Objekt oder ein-Zeichen. Beachten Sie, dass Arbeitsspeicher Ausnahmen auftreten können, wenn Sie diesen Verkettungs Operator verwenden, da neuer Speicher für Zeichen zugeordnet werden kann, die diesem-Objekt hinzugefügt werden `CSimpleStringT` .

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::operator +=`.

```cpp
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```

## <a name="csimplestringtoperator-"></a><a name="operator_eq"></a>CSimpleStringT:: Operator =

Weist einem-Objekt einen neuen Wert zu `CSimpleStringT` .

### <a name="syntax"></a>Syntax

```
CSimpleStringT& operator =(PCXSTR pszSrc);
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```

#### <a name="parameters"></a>Parameter

*pszSrc*<br/>
Ein Zeiger auf eine NULL-terminierte Zeichenfolge.

*"Straume"*<br/>
Ein Zeiger auf ein vorhandenes- `CSimpleStringT` Objekt.

### <a name="remarks"></a>Bemerkungen

Wenn die Ziel Zeichenfolge (die linke Seite) bereits groß genug ist, um die neuen Daten zu speichern, wird keine neue Speicher Belegung ausgeführt. Beachten Sie, dass Arbeitsspeicher Ausnahmen auftreten können, wenn Sie den Zuweisungs Operator verwenden, da der neue Speicher häufig zum Speichern des resultierenden Objekts zugeordnet wird `CSimpleStringT` .

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::operator =`.

```cpp
CSimpleString s1(pMgr), s2(pMgr);
// Empty CSimpleStringT objects

s1 = _T("cat");
// s1 = "cat"
ASSERT(_tcscmp(s1, _T("cat")) == 0);

s2 = s1;               // s1 and s2 each = "cat"
ASSERT(_tcscmp(s2, _T("cat")) == 0);

s1 = _T("the ") + s1;
// Or expressions
ASSERT(_tcscmp(s1, _T("the cat")) == 0);

s1 = _T("x");
// Or just individual characters
ASSERT(_tcscmp(s1, _T("x")) == 0);
```

## <a name="csimplestringtoperator-pcxstr"></a><a name="operator_pcxstr"></a>CSimpleStringT:: Operator PCXSTR

Greift direkt auf in einem- `CSimpleStringT` Objekt gespeicherte Zeichen als Zeichenfolge im C-Format zu.

### <a name="syntax"></a>Syntax

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeichen Zeiger auf die Daten der Zeichenfolge.

### <a name="remarks"></a>Bemerkungen

Es werden keine Zeichen kopiert. Es wird nur ein-Zeiger zurückgegeben. Seien Sie vorsichtig mit diesem Operator. Wenn Sie ein- `CString` Objekt ändern, nachdem Sie den Zeichen Zeiger abgerufen haben, können Sie eine erneute Zuweisung des Arbeitsspeichers bewirken, der den Zeiger für ungültig erklärt.

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::operator PCXSTR`.

```cpp
// If the prototype of a function is known to the compiler,
// the PCXSTR cast operator may be invoked implicitly.

CSimpleString strSports(L"Soccer is Best!", pMgr);
WCHAR sz[1024];

wcscpy_s(sz, strSports);

// If the prototype isn't known or is a va_arg prototype,
// you must invoke the cast operator explicitly. For example,
// the va_arg part of a call to swprintf_s() needs the cast:

swprintf_s(sz, 1024, L"I think that %s!\n", (PCWSTR)strSports);

// While the format parameter is known to be an PCXSTR and
// therefore doesn't need the cast:

swprintf_s(sz, 1024, strSports);

// Note that some situations are ambiguous. This line will
// put the address of the strSports object to stdout:

wcout << strSports;

// while this line will put the content of the string out:

wcout << (PCWSTR)strSports;
```

## <a name="csimplestringtpcxstr"></a><a name="pcxstr"></a>CSimpleStringT::P cxstr

Ein Zeiger auf eine Konstantenzeichenfolge.

### <a name="syntax"></a>Syntax

```
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;
```

## <a name="csimplestringtpreallocate"></a><a name="preallocate"></a>CSimpleStringT::P neu zuordnen

Ordnet eine bestimmte Byte Menge für das- `CSimpleStringT` Objekt zu.

### <a name="syntax"></a>Syntax

```cpp
void Preallocate( int nLength);
```

#### <a name="parameters"></a>Parameter

*nlength*<br/>
Die genaue Größe des `CSimpleStringT` Zeichen Puffers in Zeichen.

### <a name="remarks"></a>Bemerkungen

Verwenden Sie diese Methode, um eine bestimmte Puffergröße für das- `CSimpleStringT` Objekt zuzuordnen.

`CSimpleStringT`generiert eine STATUS_NO_MEMORY Ausnahme, wenn kein Speicherplatz für den Zeichen Puffer belegt werden kann. Die Speicher Belegung wird standardmäßig von den Win32-API-Funktionen oder durchgeführt `HeapAlloc` `HeapReAlloc` .

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::Preallocate`.

```cpp
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```

## <a name="csimplestringtpxstr"></a><a name="pxstr"></a>CSimpleStringT::P xstr

Ein Zeiger auf eine Zeichenfolge.

### <a name="syntax"></a>Syntax

```
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;
```

## <a name="csimplestringtreleasebuffer"></a><a name="releasebuffer"></a>CSimpleStringT:: ReleaseBuffer

Gibt die Steuerung des Puffers frei, der von [GetBuffer](#getbuffer)zugeordnet wird.

### <a name="syntax"></a>Syntax

```cpp
void ReleaseBuffer(int nNewLength = -1);
```

#### <a name="parameters"></a>Parameter

*nnewlength*<br/>
Die neue Länge der Zeichenfolge in Zeichen, wobei kein NULL-Terminator gezählt wird. Wenn die Zeichenfolge NULL-terminiert ist, legt der Standardwert-1 die `CSimpleStringT` Größe auf die aktuelle Länge der Zeichenfolge fest.

### <a name="remarks"></a>Bemerkungen

Verwenden Sie diese Methode, um den Puffer des Zeichen folgen Objekts neu zuzuordnen oder freizugeben. Wenn Sie wissen, dass die Zeichenfolge im Puffer NULL ist, können Sie das *nnewlength* -Argument weglassen. Wenn die Zeichenfolge nicht NULL endet, verwenden Sie *nnewlength* , um die Länge anzugeben. Die von [GetBuffer](#getbuffer) zurückgegebene Adresse ist nach dem Aufrufen von `ReleaseBuffer` oder einem anderen `CSimpleStringT` Vorgang ungültig.

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::ReleaseBuffer`.

```cpp
const int bufferSize = 1024;
CSimpleString s(_T("abc"), pMgr);
LPTSTR p = s.GetBuffer(bufferSize);
_tcscpy_s(p, bufferSize, _T("abc"));

// use the buffer directly
ASSERT(s.GetLength() == 3);

// String length = 3
s.ReleaseBuffer();

// Surplus memory released, p is now invalid.
ASSERT(s.GetLength() == 3);

// Length still 3
```

## <a name="csimplestringtreleasebuffersetlength"></a><a name="releasebuffersetlength"></a>CSimpleStringT:: ReleaseBufferSetLength

Gibt die Steuerung des Puffers frei, der von [GetBuffer](#getbuffer)zugeordnet wird.

### <a name="syntax"></a>Syntax

```cpp
void ReleaseBufferSetLength(int nNewLength);
```

#### <a name="parameters"></a>Parameter

*nnewlength*<br/>
Die Länge der Zeichenfolge, die freigegeben wird.

### <a name="remarks"></a>Bemerkungen

Diese Funktion ähnelt dem [ReleaseBuffer](#releasebuffer) , mit dem Unterschied, dass eine gültige Länge für das Zeichen folgen Objekt bestehen muss.

## <a name="csimplestringtsetat"></a><a name="setat"></a>CSimpleStringT:: *

Legt ein einzelnes Zeichen aus einem- `CSimpleStringT` Objekt fest.

### <a name="syntax"></a>Syntax

```cpp
void SetAt(int iChar, XCHAR ch);
```

#### <a name="parameters"></a>Parameter

*IChar*<br/>
NULL basierter Index des Zeichens im- `CSimpleStringT` Objekt. Der- *IChar* -Parameter muss größer oder gleich 0 und kleiner als der von [GetLength](#getlength)zurückgegebene Wert sein.

*ch*<br/>
Das neue Zeichen.

### <a name="remarks"></a>Bemerkungen

Mit dieser Methode wird das Zeichen, das sich bei *IChar*befindet, überschrieben. Diese Methode vergrößert die Zeichenfolge nicht, wenn *IChar* die Begrenzungen der vorhandenen Zeichenfolge überschreitet.

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::SetAt`.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
```

## <a name="csimplestringtsetmanager"></a><a name="setmanager"></a>CSimpleStringT:: setmanager

Gibt den Speicher-Manager des- `CSimpleStringT` Objekts an.

### <a name="syntax"></a>Syntax

```cpp
void SetManager(IAtlStringMgr* pStringMgr);
```

#### <a name="parameters"></a>Parameter

*pstringmgr*<br/>
Ein Zeiger auf den neuen Speicher-Manager.

### <a name="remarks"></a>Bemerkungen

Mit dieser Methode können Sie einen neuen Speicher-Manager angeben, der vom-Objekt verwendet wird `CSimpleStringT` . Weitere Informationen zu Speicher-Managern und Zeichen folgen Objekten finden Sie unter [Speicherverwaltung und CStringT](../memory-management-with-cstringt.md).

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::SetManager`.

```cpp
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```

## <a name="csimplestringtsetstring"></a><a name="setstring"></a>CSimpleStringT:: SetString

Legt die Zeichenfolge eines- `CSimpleStringT` Objekts fest.

### <a name="syntax"></a>Syntax

```cpp
void SetString(PCXSTR pszSrc, int nLength);
void SetString(PCXSTR pszSrc);
```

#### <a name="parameters"></a>Parameter

*pszSrc*<br/>
Ein Zeiger auf eine NULL-terminierte Zeichenfolge.

*nlength*<br/>
Die Anzahl der Zeichen in *pszSrc*.

### <a name="remarks"></a>Bemerkungen

Kopieren Sie eine Zeichenfolge in das- `CSimpleStringT` Objekt. `SetString`überschreibt die älteren Zeichen folgen Daten im Puffer.

Beide Versionen von `SetString` überprüfen, ob *pszSrc* ein NULL-Zeiger ist, und wenn dies der Fall ist, lösen Sie einen E_INVALIDARG Fehler aus.

Die 1-Parameter-Version von erwartet, dass `SetString` *pszSrc* auf eine mit NULL endenden Zeichenfolge verweist.

Die zwei-Parameter-Version von `SetString` erwartet auch, dass *pszSrc* eine NULL-terminierte Zeichenfolge ist. Es wird *nlength* als Zeichen folgen Länge verwendet, es sei denn, es findet zuerst ein NULL-Terminator.

Die zwei-Parameter-Version von `SetString` prüft auch, ob *pszSrc* auf eine Position im aktuellen Puffer in verweist `CSimpleStringT` . In diesem speziellen Fall wird `SetString` von eine Speicher Kopierfunktion verwendet, die die Zeichen folgen Daten nicht überschreibt, da die Zeichen folgen Daten zurück in ihren Puffer kopiert werden.

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::SetString`.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```

## <a name="csimplestringtstringlength"></a><a name="stringlength"></a>CSimpleStringT:: StringLength

Gibt die Anzahl der Zeichen in der angegebenen Zeichenfolge zurück.

### <a name="syntax"></a>Syntax

```
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```

#### <a name="parameters"></a>Parameter

*PSZ*<br/>
Ein Zeiger auf eine NULL-terminierte Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Zeichen in *PSZ*; ein NULL-Terminator wird nicht gezählt.

### <a name="remarks"></a>Bemerkungen

Rufen Sie diese Methode auf, um die Anzahl der Zeichen in der Zeichenfolge abzurufen, auf die von *PSZ*verwiesen wird.

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::StringLength`.

```cpp
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
```

## <a name="csimplestringttruncate"></a><a name="truncate"></a>CSimpleStringT:: TRUNCATE

Verkürzt die Zeichenfolge auf die neue Länge.

### <a name="syntax"></a>Syntax

```cpp
void Truncate(int nNewLength);
```

#### <a name="parameters"></a>Parameter

*nnewlength*<br/>
Die neue Länge der Zeichenfolge.

### <a name="remarks"></a>Bemerkungen

Ruft diese Methode auf, um den Inhalt der Zeichenfolge auf die neue Länge zu kürzen.

> [!NOTE]
> Dies wirkt sich nicht auf die zugeordnete Länge des Puffers aus. Informationen zum Verkleinern oder Vergrößern des aktuellen Puffers finden Sie unter " [freextra](#freeextra) " und " [prezuordnen](#preallocate)".

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::Truncate`.

```cpp
CSimpleString str(_T("abcdefghi"), pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
str.Truncate(4);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
```

## <a name="csimplestringtunlockbuffer"></a><a name="unlockbuffer"></a>CSimpleStringT:: UnlockBuffer

Entsperrt den Puffer des- `CSimpleStringT` Objekts.

### <a name="syntax"></a>Syntax

```cpp
void UnlockBuffer() throw();
```

### <a name="remarks"></a>Bemerkungen

Mit dieser Methode wird der Verweis Zähler der Zeichenfolge auf 1 zurückgesetzt.

Der `CSimpleStringT` Dekonstruktor ruft automatisch `UnlockBuffer` auf, um sicherzustellen, dass der Puffer nicht gesperrt ist, wenn der Dekonstruktor aufgerufen wird. Ein Beispiel für diese Methode finden Sie unter [LockBuffer](#lockbuffer).

## <a name="csimplestringtcsimplestringt"></a><a name="dtor"></a>CSimpleStringT:: ~ CSimpleStringT

Zerstört ein `CSimpleStringT` -Objekt.

### <a name="syntax"></a>Syntax

```
~CSimpleStringT() throw();
```

### <a name="remarks"></a>Bemerkungen

Mit dieser Methode wird das `CSimpleStringT` Objekt zerstört.

## <a name="see-also"></a>Weitere Informationen

[Hierarchie Diagramm](../../mfc/hierarchy-chart.md)<br/>
[Gemeinsam genutzte ATL/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)
