---
title: CTime-Klasse
ms.date: 10/18/2018
f1_keywords:
- CTime
- ATLTIME/ATL::CTime
- ATLTIME/ATL::CTime::CTime
- ATLTIME/ATL::CTime::Format
- ATLTIME/ATL::CTime::FormatGmt
- ATLTIME/ATL::CTime::GetAsDBTIMESTAMP
- ATLTIME/ATL::CTime::GetAsSystemTime
- ATLTIME/ATL::CTime::GetCurrentTime
- ATLTIME/ATL::CTime::GetDay
- ATLTIME/ATL::CTime::GetDayOfWeek
- ATLTIME/ATL::CTime::GetGmtTm
- ATLTIME/ATL::CTime::GetHour
- ATLTIME/ATL::CTime::GetLocalTm
- ATLTIME/ATL::CTime::GetMinute
- ATLTIME/ATL::CTime::GetMonth
- ATLTIME/ATL::CTime::GetSecond
- ATLTIME/ATL::CTime::GetTime
- ATLTIME/ATL::CTime::GetYear
- ATLTIME/ATL::CTime::Serialize64
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
ms.openlocfilehash: daf2a0d884a6b7a74b5edde2ed7db3b6aeea368d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491574"
---
# <a name="ctime-class"></a>CTime-Klasse

Stellt eine absolute Uhrzeit und ein Datum dar.

## <a name="syntax"></a>Syntax

```
class CTime
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CTime:: ctime](#ctime)|Erstellt `CTime` -Objekte auf verschiedene Weise.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CTime::Format](#format)|Konvertiert ein `CTime` -Objekt in eine formatierte Zeichenfolge – basierend auf der lokalen Zeitzone.|
|[CTime::FormatGmt](#formatgmt)|Konvertiert ein `CTime` -Objekt in eine formatierte Zeichenfolge – basierend auf UTC.|
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Konvertiert die Zeit Informationen, die im `CTime` -Objekt gespeichert sind, in eine Win32-kompatible DBTIMESTAMP-Struktur.|
|[CTime::GetAsSystemTime](#getassystemtime)|Konvertiert die Zeit Informationen, die im `CTime` -Objekt gespeichert sind, in eine Win32-kompatible [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -Struktur.|
|[CTime::GetCurrentTime](#getcurrenttime)|Erstellt ein `CTime` -Objekt, das die aktuelle Uhrzeit darstellt (statische Member-Funktion).|
|[CTime::GetDay](#getday)|Gibt den Tag zurück, der `CTime` vom-Objekt dargestellt wird.|
|[CTime::GetDayOfWeek](#getdayofweek)|Gibt den Wochentag zurück, der durch das `CTime` -Objekt dargestellt wird.|
|[CTime::GetGmtTm](#getgmttm)|Unterteilt ein `CTime` -Objekt in Komponenten – basierend auf UTC.|
|[CTime::GetHour](#gethour)|Gibt die durch das `CTime` -Objekt dargestellte Stunde zurück.|
|[CTime::GetLocalTm](#getlocaltm)|Unterteilt ein `CTime` -Objekt in Komponenten – basierend auf der lokalen Zeitzone.|
|[CTime::GetMinute](#getminute)|Gibt die Minute zurück, die `CTime` vom-Objekt dargestellt wird.|
|[CTime::GetMonth](#getmonth)|Gibt den Monat zurück, der `CTime` vom-Objekt dargestellt wird.|
|[CTime::GetSecond](#getsecond)|Gibt die zweite zurück, die `CTime` vom-Objekt dargestellt wird.|
|[CTime::GetTime](#gettime)|Gibt einen **__time64_t** -Wert für das `CTime` angegebene Objekt zurück.|
|[CTime::GetYear](#getyear)|Gibt das durch das `CTime` -Objekt dargestellte Jahr zurück.|
|[CTime::Serialize64](#serialize64)|Serialisiert Daten in ein oder aus einem Archiv.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[Operator +-](#operator_add_-)|Diese Operatoren addieren und `CTimeSpan` subtrahieren und- `CTime` Objekte.|
|[operator +=, -=](#operator_add_eq_-_eq)|Diese Operatoren fügen ein `CTimeSpan` -Objekt zu diesem-Objekt hinzu und subtrahieren es. `CTime`|
|[operator =](#operator_eq)|Der Zuweisungs Operator.|
|[Operator = =, < usw.](#ctime_comparison_operators)|Vergleichs Operatoren.|

## <a name="remarks"></a>Hinweise

`CTime`weist keine Basisklasse auf.

`CTime`Werte basieren auf der koordinierten Weltzeit (UTC), die der koordinierten Weltzeit (Greenwich Mean Time, GMT) entspricht. Informationen zur Bestimmung der Zeitzone finden Sie unter [Zeitverwaltung](../../c-runtime-library/time-management.md) .

Wenn Sie ein `CTime` -Objekt erstellen, legen `nDST` Sie den-Parameter auf 0 fest, um anzugeben, dass die Standardzeit wirksam ist, oder auf einen Wert größer als 0, um anzugeben, dass die Sommerzeit wirksam ist, oder auf einen Wert kleiner als 0 (null), um den C-Lauf Zeit Bibliotheks Code zu erstellen. e, ob Normalzeit oder Sommerzeit wirksam ist. `tm_isdst` ist ein Pflichtfeld. Wenn nicht festgelegt, wird sein Wert nicht definiert und der Rückgabewert von [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) ist unvorhersehbar. Wenn `timeptr` auf eine TM-Struktur verweist, die von einem vorherigen-Befehl an [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)oder [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)zurückgegeben wurde, enthält das `tm_isdst` Feld den richtigen Wert.

Eine Begleit Klasse, [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), stellt ein Zeitintervall dar.

Die `CTime` - `CTimeSpan` Klasse und die-Klasse sind nicht für die Ableitung konzipiert. Da keine virtuellen Funktionen vorhanden sind, beträgt die Größe `CTime` von `CTimeSpan` -und-Objekten genau 8 Bytes. Die meisten Element Funktionen sind Inline.

> [!NOTE]
>  Das obere Datums Limit ist 12/31/3000. Der untere Grenzwert beträgt 1/1/1970 12:00:00 Uhr GMT.

Weitere Informationen zum Verwenden von `CTime`finden Sie in den Artikeln " [Datum und Uhrzeit](../../atl-mfc-shared/date-and-time.md)" und " [Zeitverwaltung](../../c-runtime-library/time-management.md) " in der Lauf Zeit Bibliotheks Referenz.

> [!NOTE]
>  Die `CTime` Struktur wurde von MFC 7,1 in MFC 8,0 geändert. Wenn Sie eine `CTime` Struktur mithilfe des **Operators < <** unter MFC 8,0 oder einer höheren Version serialisieren, kann die resultierende Datei in älteren Versionen von MFC nicht gelesen werden.

## <a name="requirements"></a>Anforderungen

**Header:** atltime. h

##  <a name="ctime_comparison_operators"></a>CTime-Vergleichs Operatoren

Vergleichs Operatoren.

```
bool operator==(CTime time) const throw();
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw();
```

### <a name="parameters"></a>Parameter

*time*<br/>
Das zu vergleichende `CTime`-Objekt.

### <a name="return-value"></a>Rückgabewert

Diese Operatoren vergleichen zwei absolute Zeiten und geben "true" zurück, wenn die Bedingung "true" ist. andernfalls false.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

##  <a name="ctime"></a>CTime:: ctime

Erstellt ein neues `CTime` -Objekt, das mit der angegebenen Zeit initialisiert wird.

```
CTime() throw();
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts, int nDST = -1) throw();
```

### <a name="parameters"></a>Parameter

*timeSrc*<br/>
Gibt ein `CTime` -Objekt an, das bereits vorhanden ist.

*time*<br/>
Ein `__time64_t` Uhrzeitwert, der die Anzahl der Sekunden nach dem 1. Januar 1970 UTC ist. Beachten Sie, dass dies an die Ortszeit angepasst wird. Wenn Sie z. b. in New York arbeiten und ein `CTime` -Objekt erstellen, indem Sie einen Parameter von 0 übergeben, gibt [ctime:: getMonth](#getmonth) den Wert 12 zurück.

*nyear*, *nmonth*, *NDAY*, *nHour*, *nmin*, *nsec*<br/>
Gibt die Datums-und Uhrzeitwerte an, die in `CTime` das neue-Objekt kopiert werden sollen.

*nDST*<br/>
Gibt an, ob die Sommerzeit wirksam ist. Kann einen von drei Werten aufweisen:

- " *ndst* " ist auf "0standard Time" festgelegt.

- *ndst* ist auf einen Wert festgelegt, der größer als 0sommer Zeit ist.

- *ndst* ist auf einen Wert festgelegt, der kleiner als der Standardwert ist. Berechnet automatisch, ob die Standardzeit oder die Sommerzeit wirksam ist.

*wDosDate*, *wDosTime*<br/>
MS-und Time-Werte, die in einen Datums-/Uhrzeitwert konvertiert und in `CTime` das neue-Objekt kopiert werden.

*st*<br/>
Eine [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -Struktur, die in einen Datums-/Uhrzeitwert konvertiert und in `CTime` das neue-Objekt kopiert werden soll.

*ft*<br/>
Eine [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) -Struktur, die in einen Datums-/Uhrzeitwert konvertiert und in `CTime` das neue-Objekt kopiert werden soll.

*DBTS*<br/>
Ein Verweis auf eine DBTIMESTAMP-Struktur, die die aktuelle lokale Uhrzeit enthält.

### <a name="remarks"></a>Hinweise

Jeder Konstruktor wird im folgenden beschrieben:

- `CTime();`Erstellt ein nicht initialisiertes `CTime` Objekt. Mit diesem Konstruktor können Sie Objekt `CTime` Arrays definieren. Sie sollten diese Arrays mit gültigen Zeiten initialisieren, bevor Sie verwenden.

- `CTime( const CTime& );`Erstellt ein `CTime` -Objekt aus `CTime` einem anderen-Wert.

- `CTime( __time64_t );`Erstellt ein `CTime` -Objekt aus einem **__time64_t** -Typ. Dieser Konstruktor erwartet eine UTC-Zeit und konvertiert das Ergebnis in eine lokale Zeit, bevor das Ergebnis gespeichert wird.

- `CTime( int, int, ...);`Erstellt ein `CTime` -Objekt aus lokalen Zeit Komponenten, wobei jede Komponente auf die folgenden Bereiche beschränkt ist:

   |Komponente|Bereich|
   |---------------|-----------|
   |*nYear*|1970-3000|
   |*nMonth*|1-12|
   |*nDay*|1-31|
   |*nHour*|0-23|
   |*nMin*|0-59|
   |*nSec*|0-59|

   Dieser Konstruktor führt die entsprechende Konvertierung in UTC durch. Die Debugversion des Microsoft Foundation Class-Bibliothek bestätigt, wenn eine oder mehrere der Zeit Komponenten außerhalb des gültigen Bereichs liegen. Sie müssen die Argumente validieren, bevor Sie aufrufen. Dieser Konstruktor erwartet eine lokale Zeit.

- `CTime( WORD, WORD );`Erstellt ein `CTime` -Objekt aus den angegebenen Datums-und Uhrzeitwerten für MS-DOS. Dieser Konstruktor erwartet eine lokale Zeit.

- `CTime( const SYSTEMTIME& );`Erstellt ein `CTime` -Objekt aus `SYSTEMTIME` einer-Struktur. Dieser Konstruktor erwartet eine lokale Zeit.

- `CTime( const FILETIME& );`Erstellt ein `CTime` -Objekt aus `FILETIME` einer-Struktur. Wahrscheinlich wird die Initialisierung nicht `CTime FILETIME` direkt verwendet. Wenn Sie ein- `CFile` Objekt verwenden, um eine Datei `CFile::GetStatus` zu bearbeiten, Ruft den Datei Zeitstempel für Sie `CTime` über ein-Objekt ab `FILETIME` , das mit einer-Struktur initialisiert wurde. Dieser Konstruktor nimmt eine auf UTC basierende Zeit an und konvertiert den Wert automatisch in lokale Zeit, bevor das Ergebnis gespeichert wird.

   > [!NOTE]
   > Der Konstruktor, `DBTIMESTAMP` der den Parameter verwendet, ist nur verfügbar, wenn "OleDb. h" enthalten ist.

Weitere Informationen finden Sie in der [System Time](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -und [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) -Struktur in der Windows SDK. Weitere Informationen finden Sie auch [in der Windows SDK](/windows/win32/SysInfo/ms-dos-date-and-time) .

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]

##  <a name="format"></a>CTime:: Format

Rufen Sie diese Member-Funktion auf, um eine formatierte Darstellung des Datums-/Uhrzeitwerts zu erstellen.

```
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Parameter

*pszFormat*<br/>
Eine Formatierungs Zeichenfolge `printf` ähnlich der Formatierungs Zeichenfolge. Formatierungscodes, denen ein Prozentzeichen`%`() vorangestellt ist, werden durch `CTime` die entsprechende Komponente ersetzt. Andere Zeichen in der Formatierungs Zeichenfolge werden unverändert in die zurückgegebene Zeichenfolge kopiert. Eine Liste der Formatierungscodes finden Sie in der "Lauf [Zeitfunktion"](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*nFormatID*<br/>
Die ID der Zeichenfolge, die dieses Format identifiziert.

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Wert, der die formatierte Zeit enthält.

### <a name="remarks"></a>Hinweise

Wenn der Status dieses `CTime` Objekts NULL ist, ist der Rückgabewert eine leere Zeichenfolge.

Diese Methode löst eine Ausnahme aus, wenn der zu formatierende Datums-/Uhrzeitwert nicht zwischen Mitternacht, 1. Januar 1970 und dem 31. Dezember 3000 (UTC) liegt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

##  <a name="formatgmt"></a>CTime:: formatgmt

Generiert eine formatierte Zeichenfolge, die `CTime` diesem-Objekt entspricht.

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>Parameter

*pszFormat*<br/>
Gibt eine Format Zeichenfolge ähnlich `printf` der Formatierungs Zeichenfolge an. Weitere Informationen finden Sie unter Lauf [Zeitfunktion.](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)

*nFormatID*<br/>
Die ID der Zeichenfolge, die dieses Format identifiziert.

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Wert, der die formatierte Zeit enthält.

### <a name="remarks"></a>Hinweise

Der Uhrzeitwert wird nicht konvertiert und spiegelt somit die UTC wider.

Diese Methode löst eine Ausnahme aus, wenn der zu formatierende Datums-/Uhrzeitwert nicht zwischen Mitternacht, 1. Januar 1970 und dem 31. Dezember 3000 (UTC) liegt.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [ctime:: Format](#format).

##  <a name="getasdbtimestamp"></a>CTime:: getasdbtimestamp

Mit dieser Member-Funktion können Sie die im `CTime` -Objekt gespeicherten Zeit Informationen in eine Win32-kompatible DBTIMESTAMP-Struktur konvertieren.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>Parameter

*DBTS*<br/>
Ein Verweis auf eine DBTIMESTAMP-Struktur, die die aktuelle lokale Uhrzeit enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Speichert die resultierende Zeit in der referenzierten *DBTS* -Struktur. Für `DBTIMESTAMP` die Datenstruktur, die von dieser Funktion initialisiert `fraction` wurde, wird der Member auf NULL festgelegt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

##  <a name="getassystemtime"></a>CTime:: getassystemtime

Mit dieser Member-Funktion können Sie die im `CTime` -Objekt gespeicherten Zeit Informationen in eine Win32-kompatible [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -Struktur konvertieren.

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>Parameter

*timeDest*<br/>
Ein Verweis auf eine [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -Struktur, die den konvertierten Datums-/Uhrzeitwert des `CTime` -Objekts enthält.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

`GetAsSystemTime`speichert die resultierende Zeit in der referenzierten *timedest* -Struktur. Für `SYSTEMTIME` die Datenstruktur, die von dieser Funktion initialisiert `wMilliseconds` wurde, wird der Member auf NULL festgelegt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

##  <a name="getcurrenttime"></a>CTime:: GetCurrentTime

Gibt ein `CTime` -Objekt zurück, das die aktuelle Uhrzeit darstellt.

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>Hinweise

Gibt das aktuelle Systemdatum und die aktuelle Systemzeit in koordinierter Weltzeit (UTC) zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

##  <a name="getday"></a>CTime:: getDay

Gibt den Tag zurück, der `CTime` vom-Objekt dargestellt wird.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Tag des Monats zurück, basierend auf der Ortszeit im Bereich von 1 bis 31.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`auf, wobei ein interner, statisch zugewiesener Puffer verwendet wird. Die Daten in diesem Puffer werden aufgrund von Aufrufen anderer `CTime` Element Funktionen überschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

##  <a name="getdayofweek"></a>CTime:: getdayof Week

Gibt den Wochentag zurück, der durch das `CTime` -Objekt dargestellt wird.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wochentag basierend auf der Ortszeit zurück. 1 = Sonntag, 2 = Montag, bis 7 = Samstag.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`auf, wobei ein interner, statisch zugewiesener Puffer verwendet wird. Die Daten in diesem Puffer werden aufgrund von Aufrufen anderer `CTime` Element Funktionen überschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

##  <a name="getgmttm"></a>CTime:: GetGmtTm

Ruft eine **Struktur-TM** ab, die eine Zerlegung der in diesem `CTime` -Objekt enthaltenen Zeit enthält.

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parameter

*ptm*<br/>
Verweist auf einen Puffer, der die Zeit Daten empfängt. Wenn dieser Zeiger NULL ist, wird eine Ausnahme ausgelöst.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine ausgefüllte **Struktur-TM** , wie in der include-Dateizeit definiert. Micha. Informationen zum Struktur Layout finden Sie unter [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) .

### <a name="remarks"></a>Hinweise

`GetGmtTm`Gibt die UTC zurück.

*PTM* darf nicht NULL sein. Wenn Sie das alte Verhalten wiederherstellen möchten, bei dem *PTM* NULL sein könnte, um anzugeben, dass ein interner, statisch zugewiesener Puffer verwendet werden soll, dann definieren Sie _SECURE_ATL.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

##  <a name="gethour"></a>CTime:: GetHour

Gibt die durch das `CTime` -Objekt dargestellte Stunde zurück.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Stunde zurück, basierend auf der Ortszeit im Bereich von 0 bis 23.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`auf, wobei ein interner, statisch zugewiesener Puffer verwendet wird. Die Daten in diesem Puffer werden aufgrund von Aufrufen anderer `CTime` Element Funktionen überschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

##  <a name="getlocaltm"></a>CTime:: GetLocalTm

Ruft eine **struct tm-Struktur** ab, die eine Zerlegung der `CTime` in diesem-Objekt enthaltenen Zeit enthält.

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parameter

*ptm*<br/>
Verweist auf einen Puffer, der die Zeit Daten empfängt. Wenn dieser Zeiger NULL ist, wird eine Ausnahme ausgelöst.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine ausgefüllte **Struktur-TM** , wie in der include-Dateizeit definiert. Micha. Informationen zum Struktur Layout finden Sie unter [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) .

### <a name="remarks"></a>Hinweise

`GetLocalTm`Gibt die Ortszeit zurück.

*PTM* darf nicht NULL sein. Wenn Sie das alte Verhalten wiederherstellen möchten, bei dem *PTM* NULL sein könnte, um anzugeben, dass ein interner, statisch zugewiesener Puffer verwendet werden soll, dann definieren Sie _SECURE_ATL.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

##  <a name="getminute"></a>CTime:: GetMinute

Gibt die Minute zurück, die `CTime` vom-Objekt dargestellt wird.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Minute zurück, basierend auf der Ortszeit im Bereich von 0 bis 59.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`auf, wobei ein interner, statisch zugewiesener Puffer verwendet wird. Die Daten in diesem Puffer werden aufgrund von Aufrufen anderer `CTime` Element Funktionen überschrieben.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [GetHour](#gethour).

##  <a name="getmonth"></a>CTime:: getMonth

Gibt den Monat zurück, der `CTime` vom-Objekt dargestellt wird.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Monat zurück, basierend auf der Ortszeit im Bereich von 1 bis 12 (1 = Januar).

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`auf, wobei ein interner, statisch zugewiesener Puffer verwendet wird. Die Daten in diesem Puffer werden aufgrund von Aufrufen anderer `CTime` Element Funktionen überschrieben.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [getDay](#getday).

##  <a name="getsecond"></a>CTime:: GetSecond

Gibt die zweite zurück, die `CTime` vom-Objekt dargestellt wird.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Sekunde zurück, basierend auf der Ortszeit im Bereich von 0 bis 59.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`auf, wobei ein interner, statisch zugewiesener Puffer verwendet wird. Die Daten in diesem Puffer werden aufgrund von Aufrufen anderer `CTime` Element Funktionen überschrieben.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [GetHour](#gethour).

##  <a name="gettime"></a>CTime:: getTime

Gibt einen **__time64_t** -Wert für das `CTime` angegebene Objekt zurück.

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>Rückgabewert

`GetTime`Gibt die Anzahl der Sekunden zwischen dem aktuellen `CTime` -Objekt und dem 1. Januar 1970 zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

##  <a name="getyear"></a>CTime:: getYear

Gibt das durch das `CTime` -Objekt dargestellte Jahr zurück.

```
int GetYear();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Jahr zurück, basierend auf der Ortszeit im Bereich vom 1. Januar 1970 bis zum 2038 18. Januar 1970 (einschließlich).

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`auf, wobei ein interner, statisch zugewiesener Puffer verwendet wird. Die Daten in diesem Puffer werden aufgrund von Aufrufen anderer `CTime` Element Funktionen überschrieben.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [getDay](#getday).

##  <a name="operator_eq"></a>CTime:: Operator =

Der Zuweisungs Operator.

```
CTime& operator=(__time64_t time) throw();
```

### <a name="parameters"></a>Parameter

*time*<br/>
Der neue Datums-/Uhrzeitwert.

### <a name="return-value"></a>Rückgabewert

Das aktualisierte `CTime` -Objekt.

### <a name="remarks"></a>Hinweise

Dieser überladene Zuweisungs Operator kopiert die Quell `CTime` Zeit in dieses-Objekt. Der interne Zeit Speicher in einem `CTime` -Objekt ist unabhängig von der Zeitzone. Die Zeit Zonen Konvertierung ist während der Zuweisung nicht erforderlich.

##  <a name="operator_add_-"></a>CTime:: Operator +,-

Diese Operatoren addieren und `CTimeSpan` subtrahieren und- `CTime` Objekte.

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>Parameter

*timeSpan*<br/>
Das `CTimeSpan` Objekt, das hinzugefügt oder subtrahiert werden soll.

*time*<br/>
Das `CTime` Objekt, das subtrahiert werden soll.

### <a name="return-value"></a>Rückgabewert

Ein `CTime` - `CTimeSpan` oder-Objekt, das das Ergebnis des Vorgangs darstellt.

### <a name="remarks"></a>Hinweise

`CTime`-Objekte repräsentieren die absolute `CTimeSpan` Zeit,-Objekte stellen die relative Zeit dar. Die ersten beiden Operatoren ermöglichen das Hinzufügen und subtrahieren `CTimeSpan` von Objekten zu und von `CTime` Objekten. Mit dem dritten Operator können Sie ein `CTime` Objekt von einem anderen subtrahieren, um ein `CTimeSpan` -Objekt zu erhalten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

##  <a name="operator_add_eq_-_eq"></a>CTime:: Operator + =,-=

Diese Operatoren fügen ein `CTimeSpan` -Objekt zu diesem-Objekt hinzu und subtrahieren es. `CTime`

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Das `CTimeSpan` Objekt, das hinzugefügt oder subtrahiert werden soll.

### <a name="return-value"></a>Rückgabewert

Das aktualisierte `CTime` -Objekt.

### <a name="remarks"></a>Hinweise

Diese Operatoren ermöglichen es Ihnen, ein `CTimeSpan` -Objekt zu und von diesem `CTime` -Objekt hinzuzufügen und zu entfernen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]

##  <a name="serialize64"></a>CTime:: Serialize64

> [!NOTE]
> Diese Methode ist nur in MFC-Projekten verfügbar.

Serialisiert die Daten, die der Element Variablen zugeordnet sind, in ein oder aus einem Archiv.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Parameter

*ar*<br/>
Das `CArchive` Objekt, das Sie aktualisieren möchten.

### <a name="return-value"></a>Rückgabewert

Das aktualisierte `CArchive` -Objekt.

## <a name="see-also"></a>Siehe auch

[asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)<br/>
[_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[CTimeSpan-Klasse](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Gemeinsam genutzte ATL/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)
