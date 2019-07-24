---
title: CFile-Klasse
ms.date: 06/12/2018
f1_keywords:
- CFile
- AFX/CFile
- AFX/CFile::CFile
- AFX/CFile::Abort
- AFX/CFile::Close
- AFX/CFile::Duplicate
- AFX/CFile::Flush
- AFX/CFile::GetFileName
- AFX/CFile::GetFilePath
- AFX/CFile::GetFileTitle
- AFX/CFile::GetLength
- AFX/CFile::GetPosition
- AFX/CFile::GetStatus
- AFX/CFile::LockRange
- AFX/CFile::Open
- AFX/CFile::Read
- AFX/CFile::Remove
- AFX/CFile::Rename
- AFX/CFile::Seek
- AFX/CFile::SeekToBegin
- AFX/CFile::SeekToEnd
- AFX/CFile::SetFilePath
- AFX/CFile::SetLength
- AFX/CFile::SetStatus
- AFX/CFile::UnlockRange
- AFX/CFile::Write
- AFX/CFile::hFileNull
- AFX/CFile::m_hFile
- AFX/CFile::m_pTM
helpviewer_keywords:
- CFile [MFC], CFile
- CFile [MFC], Abort
- CFile [MFC], Close
- CFile [MFC], Duplicate
- CFile [MFC], Flush
- CFile [MFC], GetFileName
- CFile [MFC], GetFilePath
- CFile [MFC], GetFileTitle
- CFile [MFC], GetLength
- CFile [MFC], GetPosition
- CFile [MFC], GetStatus
- CFile [MFC], LockRange
- CFile [MFC], Open
- CFile [MFC], Read
- CFile [MFC], Remove
- CFile [MFC], Rename
- CFile [MFC], Seek
- CFile [MFC], SeekToBegin
- CFile [MFC], SeekToEnd
- CFile [MFC], SetFilePath
- CFile [MFC], SetLength
- CFile [MFC], SetStatus
- CFile [MFC], UnlockRange
- CFile [MFC], Write
- CFile [MFC], hFileNull
- CFile [MFC], m_hFile
- CFile [MFC], m_pTM
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
ms.openlocfilehash: a258773633f503dc0638d76509953b3410dafbd8
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2019
ms.locfileid: "68375757"
---
# <a name="cfile-class"></a>CFile-Klasse

Die Basisklasse für Microsoft Foundation Class-Dateiklassen.

## <a name="syntax"></a>Syntax

```
class CFile : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CFile::CFile](#cfile)|Erstellt ein `CFile` -Objekt aus einem Pfad-oder Datei handle.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFile::Abort](#abort)|Schließt eine Datei, die alle Warnungen und Fehler ignoriert.|
|[CFile:: Close](#close)|Schließt eine Datei und löscht das-Objekt.|
|[CFile::Duplicate](#duplicate)|Erstellt auf der Grundlage dieser Datei ein doppeltes-Objekt.|
|[CFile:: Flush](#flush)|Leert alle Daten, die geschrieben werden sollen.|
|[CFile::GetFileName](#getfilename)|Ruft den Dateinamen der ausgewählten Datei ab.|
|[CFile::GetFilePath](#getfilepath)|Ruft den vollständigen Dateipfad der ausgewählten Datei ab.|
|[CFile::GetFileTitle](#getfiletitle)|Ruft den Titel der ausgewählten Datei ab.|
|[CFile::GetLength](#getlength)|Ruft die Länge der Datei ab.|
|[CFile::GetPosition](#getposition)|Ruft den aktuellen Dateizeiger ab.|
|[CFile::GetStatus](#getstatus)|Ruft den Status der geöffneten Datei ab, oder ruft in der statischen Version den Status der angegebenen Datei (statisch, virtuelle Funktion) ab.|
|[CFile:: lockrange](#lockrange)|Sperrt einen Bereich von Bytes in einer Datei.|
|[CFile:: Open](#open)|Öffnet eine Datei mit einer Fehler Testoption.|
|[CFile:: Read](#read)|Liest (nicht gepufferte) Daten an der aktuellen Dateiposition aus einer Datei.|
|[CFile:: Remove](#remove)|Löscht die angegebene Datei (statische Funktion).|
|[CFile:: Rename](#rename)|Benennt die angegebene Datei um (statische Funktion).|
|[CFile:: Seek](#seek)|Positioniert den aktuellen Dateizeiger.|
|[CFile::SeekToBegin](#seektobegin)|Positioniert den aktuellen Dateizeiger am Anfang der Datei.|
|[CFile::SeekToEnd](#seektoend)|Positioniert den aktuellen Dateizeiger am Ende der Datei.|
|[CFile::SetFilePath](#setfilepath)|Legt den vollständigen Dateipfad der ausgewählten Datei fest.|
|[CFile:: SetLength](#setlength)|Ändert die Länge der Datei.|
|[CFile::SetStatus](#setstatus)|Legt den Status der angegebenen Datei fest (statische, virtuelle Funktion).|
|[CFile:: unlockrange](#unlockrange)|Entsperrt einen Bereich von Bytes in einer Datei.|
|[CFile:: Write](#write)|Schreibt (nicht gepufferte) Daten in eine Datei an die aktuelle Dateiposition.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CFile:: Operator handle](#operator_handle)|Ein Handle für ein `CFile` -Objekt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CFile::hFileNull](#hfilenull)|Bestimmt, ob `CFile` das-Objekt über ein gültiges Handle verfügt.|
|[CFile::m_hFile](#m_hfile)|Enthält normalerweise das Datei Handle des Betriebssystems.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CFile::m_pTM](#m_ptm)|Zeiger auf `CAtlTransactionManager` das-Objekt.|

## <a name="remarks"></a>Hinweise

Sie stellt direkt nicht gepufferte, binäre Datenträger-Eingabe-/Ausgabedienste bereit und unterstützt indirekt Textdateien und Speicherdateien durch die abgeleiteten Klassen. `CFile`arbeitet in Verbindung mit der `CArchive` -Klasse, um die Serialisierung von Microsoft Foundation Class-Objekten zu unterstützen.

Die hierarchische Beziehung zwischen dieser Klasse und den abgeleiteten Klassen ermöglicht dem Programm das Arbeiten mit allen Datei Objekten über die polymorphe `CFile` Schnittstelle. Eine Speicherdatei verhält sich z. b. wie eine Datenträger Datei.

Verwenden `CFile` Sie und die abgeleiteten Klassen für allgemeine Datenträger-e/a. Verwenden `ofstream` Sie oder andere `iostream` Microsoft-Klassen für formatierten Text, der an eine Datenträger Datei gesendet wird

Normalerweise wird eine Datenträger Datei bei der `CFile` Erstellung automatisch geöffnet und bei der Zerstörung geschlossen. Mit statischen Element Funktionen können Sie den Status einer Datei Abfragen, ohne die Datei zu öffnen.

Weitere Informationen zur Verwendung von `CFile`finden Sie in den Artikeln [Dateien in MFC](../../mfc/files-in-mfc.md) und [Datei Behandlung](../../c-runtime-library/file-handling.md) in der *Lauf Zeit Bibliotheks Referenz*.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CFile`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="abort"></a>CFile:: Abort

Schließt die Datei, die diesem-Objekt zugeordnet ist, und macht die Datei zum Lesen oder schreiben nicht verfügbar.

```
virtual void Abort();
```

### <a name="remarks"></a>Hinweise

Wenn Sie die Datei vor dem Zerstören des Objekts nicht geschlossen haben, wird Sie vom debugtor für Sie geschlossen.

Bei der Behandlung von `CFile::Abort` Ausnahmen unter `CFile::Close` scheidet sich von in zweierlei Hinsicht von. Erstens löst die `Abort` Funktion bei Fehlern keine Ausnahme aus, da Fehler von `Abort`ignoriert werden. Zweitens wird nicht bestätigt, wenn die Datei nicht geöffnet oder zuvor geschlossen wurde.  `Abort`

Wenn Sie **New** verwendet haben, um `CFile` das Objekt auf dem Heap zuzuordnen, müssen Sie es nach dem Schließen der Datei löschen. `Abort`legt `m_hFile` auf`CFile::hFileNull`fest.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]

##  <a name="cfile"></a>CFile:: CFile

Erstellt und initialisiert ein `CFile`-Objekt.

```
CFile();
CFile(CAtlTransactionManager* pTM);
CFile(HANDLE hFile);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags,
CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Parameter

*hFile*<br/>
Handle einer Datei zum Anhängen an das `CFile`-Objekt.

*lpszFileName*<br/>
Relativer oder vollständiger Pfad einer Datei zum Anhängen an das `CFile`-Objekt.

*nOpenFlags*<br/>
Bitweise Kombination (OR) der Dateizugriffsoptionen für die angegebene Datei. Mögliche Optionen finden Sie im Abschnitt "Hinweise".

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="remarks"></a>Hinweise

In den folgenden fünf Tabellen sind die möglichen Optionen für den *nopenflags* -Parameter aufgeführt.

Wählen Sie eine der folgenden Dateizugriffsmodus-Optionen. Der standardmäßige Dateizugriffsmodus ist `CFile::modeRead`, wobei es sich um einen schreibgeschützten Modus handelt.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::modeRead`|Fordert nur Lesezugriff an.|
|`CFile::modeWrite`|Fordert nur Schreibzugriff an.|
|`CFile::modeReadWrite`|Fordert Lese- und Schreibzugriff an.|

Wählen Sie eine der folgenden Zeichenmodus-Optionen.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::typeBinary`|Legt den Binärmodus fest (nur in abgeleiteten Klassen verwendet).|
|`CFile::typeText`|Legt den Textmodus mit spezieller Verarbeitung für Wagen Rücklauf-Zeilenvorschub Paare fest (wird nur in abgeleiteten Klassen verwendet).|
|`CFile::typeUnicode`|Legt den Unicode-Modus fest (nur in abgeleiteten Klassen verwendet). Text wird im Unicode-Format in die Datei geschrieben, wenn die Anwendung in einer Unicode-Konfiguration erstellt wurde. Es wird keine BOM in die Datei geschrieben.|

Wählen Sie eine der folgenden Dateifreigabemodus-Optionen. Der standardmäßige Dateifreigabemodus ist `CFile::shareExclusive`, wobei es sich um einen exklusiven Modus handelt.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::shareDenyNone`|Keine Freigabebeschränkungen.|
|`CFile::shareDenyRead`|Verweigert allen anderen Lesezugriff.|
|`CFile::shareDenyWrite`|Verweigert allen anderen Schreibzugriff.|
|`CFile::shareExclusive`|Verweigert allen anderen Lese- und Schreibzugriff.|

Wählen Sie die erste oder beide Dateierstellungsmodus-Optionen. Der standardmäßige Dateierstellungsmodus ist `CFile::modeNoTruncate`, wobei es sich um "offen vorhanden" handelt.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::modeCreate`|Erstellt eine neue Datei, wenn keine Datei vorhanden ist. Wenn die Datei bereits vorhanden ist, wird sie überschrieben und anfangs auf die Länge 0 (null) festgelegt.|
|`CFile::modeNoTruncate`|Erstellt eine neue Datei, wenn keine Datei vorhanden ist. Andernfalls, wenn die Datei bereits vorhanden ist, wird Sie an das `CFile` -Objekt angefügt.|

Wählen Sie die folgenden Datei-Cache-Optionen wie beschrieben. Standardmäßig verwendet das System ein allgemeines zwischen Speicherungs Schema, das nicht als Option verfügbar ist.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::osNoBuffer`|Das System verwendet keinen zwischen Cache für die Datei. Diese Option bricht die beiden folgenden Optionen ab.|
|`CFile::osRandomAccess`|Der Datei-Cache wird für wahlfreien Zugriff optimiert. Verwenden Sie nicht diese Option und die Option für sequenzielle Scans.|
|`CFile::osSequentialScan`|Der Datei-Cache wird für sequenziellen Zugriff optimiert. Verwenden Sie nicht diese Option und die Option für den zufälligen Zugriff.|
|`CFile::osWriteThrough`|Schreibvorgänge werden ohne Verzögerung ausgeführt.|

Wählen Sie die folgende Sicherheitsoption, um zu verhindern, dass der Dateihandle übergeben wird. Standardmäßig können alle neuen untergeordneten Prozesse den Dateihandle verwenden.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::modeNoInherit`|Verhindert, dass untergeordnete Prozesse den Dateihandle verwenden.|

Der Standardkonstruktor initialisiert Member, aber fügt keine Datei an `CFile` das-Objekt an. Nachdem Sie diesen Konstruktor verwendet haben, verwenden Sie die [CFile:: Open](#open) -Methode, um eine Datei zu `CFile` öffnen und an das-Objekt anzufügen.

Der Konstruktor mit einem Parameter initialisiert Member und hängt eine vorhandene Datei an das `CFile`-Objekt an.

Der Konstruktor mit zwei Parametern initialisiert Member und versucht, die angegebene Datei zu öffnen. Wenn der Konstruktor die angegebene Datei erfolgreich öffnet, wird die Datei an das `CFile`-Objekt angehängt; anderenfalls löst der Konstruktor einen Zeiger auf ein `CInvalidArgException`-Objekt aus. Weitere Informationen zum Behandeln von Ausnahmen finden Sie unter [Ausnahmen](../../mfc/exception-handling-in-mfc.md).

Wenn ein- `CFile` `CFile` Objekt eine angegebene Datei erfolgreich öffnet, wird diese Datei automatisch geschlossen, wenn das Objekt zerstört wird. andernfalls müssen Sie die Datei explizit schließen, nachdem Sie nicht mehr an das-Objekt angefügt wurde. `CFile`

### <a name="example"></a>Beispiel

Der folgende Code veranschaulicht die Verwendung einer `CFile`.

[!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]

##  <a name="close"></a>CFile:: Close

Schließt die Datei, die diesem-Objekt zugeordnet ist, und macht die Datei zum Lesen oder schreiben nicht verfügbar.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Wenn Sie die Datei vor dem Zerstören des Objekts nicht geschlossen haben, wird Sie vom debugtor für Sie geschlossen.

Wenn Sie **New** verwendet haben, um `CFile` das Objekt auf dem Heap zuzuordnen, müssen Sie es nach dem Schließen der Datei löschen. `Close`legt `m_hFile` auf`CFile::hFileNull`fest.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [CFile:: CFile](#cfile).

##  <a name="duplicate"></a>CFile::D uplicate

Erstellt ein doppeltes `CFile` -Objekt für eine angegebene Datei.

```
virtual CFile* Duplicate() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein doppeltes `CFile` Objekt.

### <a name="remarks"></a>Hinweise

Diese Funktion entspricht der C-Lauf Zeitfunktion `_dup`.

##  <a name="flush"></a>CFile:: Flush

Erzwingt, dass alle im Datei Puffer verbleibenden Daten in die Datei geschrieben werden.

```
virtual void Flush();
```

### <a name="remarks"></a>Hinweise

Die Verwendung von `Flush` garantiert `CArchive` nicht, dass Puffer geleert werden. Wenn Sie ein Archiv verwenden, nennen Sie zuerst [CArchive:: Flush](../../mfc/reference/carchive-class.md#flush) .

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [CFile:: setfilepath](#setfilepath).

##  <a name="getfilename"></a>CFile:: GetFilename

Rufen Sie diese Member-Funktion auf, um den Namen einer angegebenen Datei abzurufen.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name der Datei.

### <a name="remarks"></a>Hinweise

Wenn Sie z. b. `GetFileName` aufzurufen, um dem Benutzer eine Meldung über die `c:\windows\write\myfile.wri`Datei zu generieren, `myfile.wri`wird der Dateiname zurückgegeben.

Um den gesamten Pfad der Datei zurückzugeben, einschließlich des Namens, nennen Sie [GetFilePath](#getfilepath). Um den Titel der Datei ( `myfile`) zurückzugeben, nennen Sie [GetFileTitle](#getfiletitle).

### <a name="example"></a>Beispiel

Dieses Code Fragment öffnet das System. INI-Datei in Ihrem Windows-Verzeichnis. Wenn Sie gefunden wird, druckt das Beispiel den Namen und den Pfad und den Titel, wie unterausgabe gezeigt:

[!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]

##  <a name="getfilepath"></a>CFile:: GetFilePath

Rufen Sie diese Member-Funktion auf, um den vollständigen Pfad einer angegebenen Datei abzurufen.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Rückgabewert

Der vollständige Pfad der angegebenen Datei.

### <a name="remarks"></a>Hinweise

Wenn Sie z. b. `GetFilePath` aufzurufen, um dem Benutzer eine Meldung über die `c:\windows\write\myfile.wri`Datei zu generieren `c:\windows\write\myfile.wri`, wird der Dateipfad zurückgegeben.

Um nur den Namen der Datei (`myfile.wri`) zurückzugeben, nennen Sie [GetFileName](#getfilename). Um den Titel der Datei (`myfile`) zurückzugeben, nennen Sie [GetFileTitle](#getfiletitle).

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für " [GetFileName](#getfilename)".

##  <a name="getfiletitle"></a>CFile:: GetFileTitle

Rufen Sie diese Member-Funktion auf, um den Datei Titel (den anzeigen Amen) für die Datei abzurufen.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Rückgabewert

Der Titel der zugrunde liegenden Datei.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [GetFileTitle](/windows/desktop/api/commdlg/nf-commdlg-getfiletitlea) auf, um den Titel der Datei abzurufen. Bei erfolgreicher Ausführung gibt die Methode die Zeichenfolge zurück, die das System verwendet, um dem Benutzer den Dateinamen anzuzeigen. Andernfalls ruft die-Methode [pathfindfilename](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) auf, um den Dateinamen (einschließlich der Dateierweiterung) der zugrunde liegenden Datei abzurufen. Dies bedeutet, dass die Dateierweiterung nicht immer in der zurückgegebenen Datei Titel Zeichenfolge enthalten ist. Weitere Informationen finden Sie unter " [GetFileTitle](/windows/desktop/api/commdlg/nf-commdlg-getfiletitlea) " und " [pathfindfilename](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) " in der Windows SDK.

Um den gesamten Pfad der Datei zurückzugeben, einschließlich des Namens, nennen Sie [GetFilePath](#getfilepath). Um nur den Namen der Datei zurückzugeben, nennen Sie [GetFileName](#getfilename).

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für " [GetFileName](#getfilename)".

##  <a name="getlength"></a>CFile:: GetLength

Ruft die aktuelle logische Länge der Datei in Bytes ab.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Rückgabewert

Die Länge der Datei.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]

##  <a name="getposition"></a>CFile:: GetPosition

Ruft den aktuellen Wert des Dateizeigers ab, der in späteren Aufrufen von `Seek`verwendet werden kann.

```
virtual ULONGLONG GetPosition() const;
```

### <a name="return-value"></a>Rückgabewert

Der Dateizeiger.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]

##  <a name="getstatus"></a>CFile:: GetStatus

Diese Methode ruft Statusinformationen zu einer angegebenen `CFile` Objektinstanz oder einem angegebenen Dateipfad ab.

```
BOOL GetStatus(CFileStatus& rStatus) const;

static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*rStatus*<br/>
Ein Verweis auf eine vom Benutzer bereit `CFileStatus` gestellte-Struktur, die die Statusinformationen empfängt. Die `CFileStatus` Struktur verfügt über die folgenden Felder:

- `CTime m_ctime`Das Datum und die Uhrzeit, zu der die Datei erstellt wurde.

- `CTime m_mtime`Das Datum und die Uhrzeit der letzten Änderung der Datei.

- `CTime m_atime`Das Datum und die Uhrzeit des letzten Zugriffs auf die Datei zum Lesen.

- `ULONGLONG m_size`Die logische Größe der Datei in Bytes, wie vom dir-Befehl gemeldet.

- `BYTE m_attribute`Das Attribut Byte der Datei.

- `char m_szFullName[_MAX_PATH]`Der absolute Dateiname im Windows-Zeichensatz.

*lpszFileName*<br/>
Eine Zeichenfolge im Windows-Zeichensatz, bei der es sich um den Pfad zur gewünschten Datei handelt. Der Pfad kann relativ oder absolut sein, oder er kann einen Netzwerk Pfadnamen enthalten.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Statusinformationen für die angegebene Datei erfolgreich abgerufen wurden. andernfalls false.

### <a name="remarks"></a>Hinweise

Die nicht statische Version von `GetStatus` ruft Statusinformationen der geöffneten Datei ab, die dem angegebenen `CFile` Objekt zugeordnet ist.  Die statische Version von `GetStatus` erhält den Dateistatus aus einem angegebenen Dateipfad, ohne die Datei tatsächlich zu öffnen. Diese Version ist nützlich, um das vorhanden sein und die Zugriffsrechte einer Datei zu testen.

Der `m_attribute` -Member `CFileStatus` der-Struktur verweist auf den Satz von Dateiattributen. Die `CFile` -Klasse stellt den Enumerationstyp des **Attributs** bereit, sodass Dateiattribute symbolisch angegeben werden können:

```
enum Attribute {
    normal =    0x00,
    readOnly =  0x01,
    hidden =    0x02,
    system =    0x04,
    volume =    0x08,
    directory = 0x10,
    archive =   0x20
    };
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#10](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_6.cpp)]

##  <a name="hfilenull"></a>CFile:: hfileull

Bestimmt, ob ein gültiges Datei Handle für das `CFile` -Objekt vorhanden ist.

```
static AFX_DATA const HANDLE hFileNull;
```

### <a name="remarks"></a>Hinweise

Diese Konstante wird verwendet, um zu bestimmen `CFile` , ob das Objekt über ein gültiges Datei Handle verfügt.

Dieser Vorgang wird im folgenden Beispiel veranschaulicht:

[!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]

##  <a name="lockrange"></a>CFile:: lockrange

Sperrt einen Bereich von Bytes in einer geöffneten Datei und löst eine Ausnahme aus, wenn die Datei bereits gesperrt ist.

```
virtual void LockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Parameter

*dwPos*<br/>
Der Byte Offset des Starts des zu Sperr enden Byte Bereichs.

*dwCount*<br/>
Die Anzahl der zu Sperr enden Bytes im Bereich.

### <a name="remarks"></a>Hinweise

Das Sperren von Bytes in einer Datei verhindert den Zugriff auf diese Bytes durch andere Prozesse. Sie können mehr als einen Bereich einer Dateisperren, aber es sind keine überlappenden Bereiche zulässig.

Wenn Sie die Region mithilfe der `UnlockRange` Member-Funktion entsperren, muss der Byte Bereich exakt dem zuvor gesperrten Bereich entsprechen. Mit `LockRange` der-Funktion werden keine angrenzenden Bereiche zusammengeführt. Wenn zwei gesperrte Bereiche nebeneinander liegen, müssen Sie jede Region separat entsperren.

> [!NOTE]
>  Diese Funktion ist für die `CMemFile`von abgeleitete Klasse nicht verfügbar.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

##  <a name="m_hfile"></a>CFile:: m_hFile

Enthält das Datei Handle des Betriebssystems für eine geöffnete Datei.

```
HANDLE m_hFile;
```

### <a name="remarks"></a>Hinweise

`m_hFile`ist eine öffentliche Variable vom Typ uint. Sie enthält `CFile::hFileNull`einen Betriebssystem unabhängigen, leeren Datei Indikator, wenn das Handle nicht zugewiesen wurde.

Die Verwendung `m_hFile` von wird nicht empfohlen, da die Bedeutung des Members von der abgeleiteten Klasse abhängt. `m_hFile`ist ein öffentliches Element für die Unterstützung der nicht polymorphen Verwendung der-Klasse.

##  <a name="m_ptm"></a>CFile:: m_pTM

Zeiger auf ein `CAtlTransactionManager` -Objekt.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Hinweise

##  <a name="open"></a>CFile:: Open

Überladen. `Open`ist für die Verwendung mit dem Standardkonstruktor `CFile` konzipiert.

```
virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*lpszFileName*<br/>
Eine Zeichenfolge, die den Pfad zur gewünschten Datei enthält. Der Pfad kann relativ, absolut oder ein Netzwerkname (UNC) sein.

*nOpenFlags*<br/>
Ein uint, das den Freigabe-und Zugriffsmodus der Datei definiert. Gibt die Aktion an, die beim Öffnen der Datei ausgeführt werden soll. Optionen können mithilfe des bitweisen OR-Operators ( **&#124;** ) kombiniert werden. Eine Zugriffsberechtigung und eine Freigabe Option sind erforderlich. die `modeCreate` Modi `modeNoInherit` und sind optional. Eine Liste der Modusoptionen finden Sie im [CFile](#cfile) -Konstruktor.

*pError*<br/>
Ein Zeiger auf ein vorhandenes Datei Ausnahme Objekt, das den Status einer fehlgeschlagenen Operation empfängt.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Öffnen erfolgreich war. andernfalls 0. Der *perror* -Parameter ist nur dann sinnvoll, wenn 0 zurückgegeben wird.

### <a name="remarks"></a>Hinweise

Die beiden `Open` Funktionen sind "sichere" Methoden zum Öffnen einer Datei, bei der ein Fehler eine normale, erwartete Bedingung ist.

Während der `CFile` Konstruktor eine Ausnahme in einem Fehlerzustand auslöst, `Open` gibt bei Fehlerbedingungen false zurück. `Open`kann dennoch ein [CFileException](../../mfc/reference/cfileexception-class.md) -Objekt initialisieren, um den Fehler zu beschreiben. Wenn Sie den *perror* -Parameter nicht angeben oder NULL für *perror*übergeben, `Open` `CFileException`gibt false zurück und löst keine aus. Wenn Sie einen Zeiger an einen vorhandenen `CFileException`übergeben und `Open` auf einen Fehler stößt, füllt die Funktion ihn mit Informationen aus, die diesen Fehler beschreiben. `Open`löst in beiden Fällen keine Ausnahme aus.

In der folgenden Tabelle werden die möglichen Ergebnisse `Open`von beschrieben.

|`pError`|Fehler aufgetreten|Rückgabewert|CFileException-Inhalt|
|--------------|------------------------|------------------|----------------------------|
|NULL|Nein|true|n/v|
|PTR an`CFileException`|Nein|true|unverändert|
|NULL|Ja|false|n/v|
|PTR an`CFileException`|Ja|false|Initialisiert zum Beschreiben des Fehlers.|

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]

[!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]

##  <a name="operator_handle"></a>CFile:: Operator handle

Verwenden Sie diesen Operator, um ein Handle an `CFile` ein-Objekt an Funktionen wie "read [fileex](/windows/desktop/api/fileapi/nf-fileapi-readfileex) " und " [GetFileTime](/windows/desktop/api/fileapi/nf-fileapi-getfiletime) " zu übergeben, die einen `HANDLE`erwarten.

```
operator HANDLE() const;
```

##  <a name="read"></a>CFile:: Read

Liest Daten aus der Datei, die dem `CFile` -Objekt zugeordnet ist, in einen Puffer.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parameter

*lpBuf*<br/>
Ein Zeiger auf den vom Benutzer bereitgestellten Puffer, der die aus der Datei gelesenen Daten empfangen soll.

*nCount*<br/>
Die maximale Anzahl von Bytes, die aus der Datei gelesen werden sollen. Bei textmodusdateien werden Wagen Rücklauf-und Zeilenvorschub Paare als einzelne Zeichen gezählt.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der in den Puffer übertrageben Bytes. Bei allen `CFile` Klassen kann der Rückgabewert kleiner als *nCount* sein, wenn das Ende der Datei erreicht wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]

Ein weiteres Beispiel finden Sie unter [CFile:: Open](#open).

##  <a name="remove"></a>CFile:: Remove

Diese statische Funktion löscht die durch den Pfad angegebene Datei.

```
static void PASCAL Remove(
    LPCTSTR lpszFileName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*lpszFileName*<br/>
Eine Zeichenfolge, die den Pfad zur gewünschten Datei ist. Der Pfad kann relativ oder absolut sein und kann einen Netzwerknamen enthalten.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="remarks"></a>Hinweise

`Remove`entfernt ein Verzeichnis nicht.

Die `Remove` Member-Funktion löst eine Ausnahme aus, wenn die verbundene Datei geöffnet ist oder wenn die Datei nicht entfernt werden kann. Diese Funktion entspricht dem Befehl del.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]

##  <a name="rename"></a>CFile:: Rename

Diese statische Funktion benennt die angegebene Datei um.

```
static void PASCAL Rename(
    LPCTSTR lpszOldName,
    LPCTSTR lpszNewName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*lpszOldName*<br/>
Der alte Pfad.

*lpszNewName*<br/>
Der neue Pfad.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="remarks"></a>Hinweise

Verzeichnisse können nicht umbenannt werden. Diese Funktion entspricht dem ren-Befehl.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]

##  <a name="seek"></a>CFile:: Seek

Positioniert den Dateizeiger in einer geöffneten Datei.

```
virtual ULONGLONG Seek(
LONGLONG lOff,
UINT nFrom);
```

### <a name="parameters"></a>Parameter

*lOff*<br/>
Anzahl von Bytes zum Verschieben des Dateizeigers. Positive Werte verschieben Sie den Dateizeiger an das Ende der Datei. negative Werte verschieben Sie den Dateizeiger an den Anfang der Datei.

*nFrom*<br/>
Position, von der gesucht werden soll. Mögliche Werte finden Sie im Abschnitt "Hinweise".

### <a name="return-value"></a>Rückgabewert

Die Position des Dateizeigers, wenn die Methode erfolgreich war. Andernfalls ist der Rückgabewert nicht definiert, und ein Zeiger auf `CFileException` eine-Ausnahme wird ausgelöst.

### <a name="remarks"></a>Hinweise

In der folgenden Tabelle sind die möglichen Werte für den *nfrom* -Parameter aufgeführt.

|Wert|Beschreibung|
|-----------|-----------------|
|`CFile::begin`|Suchen Sie am Anfang der Datei.|
|`CFile::current`|Suchen von der aktuellen Position des Dateizeigers.|
|`CFile::end`|Suchen Sie am Ende der Datei.|

Wenn eine Datei geöffnet wird, wird der Dateizeiger am Anfang der Datei auf 0 positioniert.

Sie können den Dateizeiger auf eine Position hinter dem Ende einer Datei festlegen. Wenn Sie dies tun, erhöht sich die Größe der Datei nicht, bis Sie in die Datei schreiben.

Der Ausnahmehandler für diese Methode muss das Ausnahme Objekt löschen, nachdem die Ausnahme verarbeitet wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]

##  <a name="seektobegin"></a>CFile:: seektobegin

Legt den Wert des Dateizeigers auf den Anfang der Datei fest.

```
void SeekToBegin();
```

### <a name="remarks"></a>Hinweise

`SeekToBegin()` entspricht `Seek( 0L, CFile::begin )`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

##  <a name="seektoend"></a>CFile:: seektoend

Legt den Wert des Dateizeigers auf das logische Ende der Datei fest.

```
ULONGLONG SeekToEnd();
```

### <a name="return-value"></a>Rückgabewert

Die Länge der Datei in Byte.

### <a name="remarks"></a>Hinweise

`SeekToEnd()` entspricht `CFile::Seek( 0L, CFile::end )`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

##  <a name="setfilepath"></a>CFile:: setfilepath

Mit dieser Funktion können Sie den Pfad der Datei angeben. Wenn z. b. der Pfad einer Datei nicht verfügbar ist, wenn ein [CFile](../../mfc/reference/cfile-class.md) -Objekt erstellt `SetFilePath` wird, geben Sie an, um Sie bereitzustellen.

```
virtual void SetFilePath(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>Parameter

*lpszNewName*<br/>
Zeiger auf eine Zeichenfolge, die den neuen Pfad angibt.

### <a name="remarks"></a>Hinweise

> [!NOTE]
> `SetFilePath`die Datei wird nicht geöffnet, oder die Datei wird nicht erstellt. Sie ordnet das `CFile` Objekt einfach einem Pfadnamen zu, der dann verwendet werden kann.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]

##  <a name="setlength"></a>CFile:: SetLength

Mit dieser Funktion können Sie die Länge der Datei ändern.

```
virtual void SetLength(ULONGLONG dwNewLen);
```

### <a name="parameters"></a>Parameter

*dwNewLen*<br/>
Gewünschte Länge der Datei in Bytes. Dieser Wert kann größer oder kleiner als die aktuelle Länge der Datei sein. Die Datei wird entsprechend erweitert oder abgeschnitten.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Mit `CMemFile`könnte diese Funktion ein `CMemoryException` -Objekt auslösen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]

##  <a name="setstatus"></a>CFile:: SetStatus

Legt den Status der Datei fest, die diesem Datei Speicherort zugeordnet ist.

```
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,
    const CFileStatus& status,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*lpszFileName*<br/>
Eine Zeichenfolge, die den Pfad zur gewünschten Datei ist. Der Pfad kann relativ oder absolut sein und kann einen Netzwerknamen enthalten.

*Status*<br/>
Der Puffer, der die neuen Statusinformationen enthält. Rufen Sie `GetStatus` die Member-Funktion auf, `CFileStatus` um die Struktur mit aktuellen Werten vorab auszufüllen, und nehmen Sie dann die erforderlichen Änderungen vor. Wenn ein Wert 0 ist, wird das entsprechende Status Element nicht aktualisiert. Eine Beschreibung der `CFileStatus` Struktur finden Sie in der [GetStatus](#getstatus) -Member-Funktion.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="remarks"></a>Hinweise

Um den Zeitpunkt festzulegen, ändern `m_mtime` Sie das Feld des *Status*.

Wenn Sie einen Aufruf `SetStatus` von durchführen, um nur die Attribute der Datei zu ändern, und das `m_mtime` -Element der Dateistatus Struktur ungleich NULL ist, können auch die Attribute beeinträchtigt werden (das Ändern des Zeitstempels kann Nebenwirkungen auf die Attribute haben). Wenn Sie nur die Attribute der Datei ändern möchten, legen Sie zuerst den `m_mtime` Member der Dateistatus Struktur auf NULL fest, und führen Sie dann einen- `SetStatus`Rückruf aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]

##  <a name="unlockrange"></a>CFile:: unlockrange

Entsperrt einen Bereich von Bytes in einer geöffneten Datei.

```
virtual void UnlockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Parameter

*dwPos*<br/>
Der Byte Offset des Starts des zu entsperrenden Byte Bereichs.

*dwCount*<br/>
Die Anzahl der zu entsperrenden Bytes im Bereich.

### <a name="remarks"></a>Hinweise

Ausführliche Informationen finden Sie in der Beschreibung der [lockrange](#lockrange) -Member-Funktion.

> [!NOTE]
>  Diese Funktion ist für die `CMemFile`von abgeleitete Klasse nicht verfügbar.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

##  <a name="write"></a>CFile:: Write

Schreibt Daten aus einem Puffer in die Datei, die dem `CFile` -Objekt zugeordnet ist.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parameter

*lpBuf*<br/>
Ein Zeiger auf den vom Benutzer bereitgestellten Puffer, der die Daten enthält, die in die Datei geschrieben werden sollen.

*nCount*<br/>
Die Anzahl der Bytes, die aus dem Puffer übertragen werden sollen. Bei textmodusdateien werden Wagen Rücklauf-und Zeilenvorschub Paare als einzelne Zeichen gezählt.

### <a name="remarks"></a>Hinweise

`Write`löst eine Ausnahme als Reaktion auf verschiedene Bedingungen aus, einschließlich des Datenträger-vollständigen Zustands.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]

Weitere Informationen finden Sie auch in den Beispielen für [CFile:: CFile](#cfile) und [CFile:: Open](#open).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CStdioFile-Klasse](../../mfc/reference/cstdiofile-class.md)<br/>
[CMemFile-Klasse](../../mfc/reference/cmemfile-class.md)
