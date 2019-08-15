---
title: CFtpConnection-Klasse
ms.date: 11/04/2016
f1_keywords:
- CFtpConnection
- AFXINET/CFtpConnection
- AFXINET/CFtpConnection::CFtpConnection
- AFXINET/CFtpConnection::Command
- AFXINET/CFtpConnection::CreateDirectory
- AFXINET/CFtpConnection::GetCurrentDirectory
- AFXINET/CFtpConnection::GetCurrentDirectoryAsURL
- AFXINET/CFtpConnection::GetFile
- AFXINET/CFtpConnection::OpenFile
- AFXINET/CFtpConnection::PutFile
- AFXINET/CFtpConnection::Remove
- AFXINET/CFtpConnection::RemoveDirectory
- AFXINET/CFtpConnection::Rename
- AFXINET/CFtpConnection::SetCurrentDirectory
helpviewer_keywords:
- CFtpConnection [MFC], CFtpConnection
- CFtpConnection [MFC], Command
- CFtpConnection [MFC], CreateDirectory
- CFtpConnection [MFC], GetCurrentDirectory
- CFtpConnection [MFC], GetCurrentDirectoryAsURL
- CFtpConnection [MFC], GetFile
- CFtpConnection [MFC], OpenFile
- CFtpConnection [MFC], PutFile
- CFtpConnection [MFC], Remove
- CFtpConnection [MFC], RemoveDirectory
- CFtpConnection [MFC], Rename
- CFtpConnection [MFC], SetCurrentDirectory
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
ms.openlocfilehash: 977a8c9fc6dd653a59434d29bb72b0fe28900001
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506374"
---
# <a name="cftpconnection-class"></a>CFtpConnection-Klasse

Verwaltet die FTP-Verbindung mit einem Internet Server und ermöglicht die direkte Bearbeitung von Verzeichnissen und Dateien auf diesem Server.

## <a name="syntax"></a>Syntax

```
class CFtpConnection : public CInternetConnection
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CFtpConnection:: CFtpConnection](#cftpconnection)|Erstellt ein `CFtpConnection`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFtpConnection:: Command](#command)|Sendet einen Befehl direkt an einen FTP-Server.|
|[CFtpConnection::CreateDirectory](#createdirectory)|Erstellt ein Verzeichnis auf dem Server.|
|[CFtpConnection::GetCurrentDirectory](#getcurrentdirectory)|Ruft das aktuelle Verzeichnis für diese Verbindung ab.|
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|Ruft das aktuelle Verzeichnis für diese Verbindung als URL ab.|
|[CFtpConnection::GetFile](#getfile)|Ruft eine Datei vom verbundenen Server ab.|
|[CFtpConnection::OpenFile](#openfile)|Öffnet eine Datei auf dem verbundenen Server.|
|[CFtpConnection::PutFile](#putfile)|Platziert eine Datei auf dem Server.|
|[CFtpConnection::Remove](#remove)|Entfernt eine Datei vom Server.|
|[CFtpConnection::RemoveDirectory](#removedirectory)|Entfernt das angegebene Verzeichnis vom Server.|
|[CFtpConnection:: Rename](#rename)|Benennt eine Datei auf dem Server um.|
|[CFtpConnection::SetCurrentDirectory](#setcurrentdirectory)|Legt das aktuelle FTP-Verzeichnis fest.|

## <a name="remarks"></a>Hinweise

FTP ist einer der drei Internet Dienste, die von den MFC-WinInet-Klassen erkannt werden.

Um mit einem FTP-Internet Server zu kommunizieren, müssen Sie zuerst eine Instanz von [cinternetzession](../../mfc/reference/cinternetsession-class.md)erstellen und dann ein `CFtpConnection` -Objekt erstellen. Sie erstellen ein `CFtpConnection` -Objekt niemals direkt. Rufen Sie stattdessen [cinternetzession:: GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)auf, das `CFtpConnection` das Objekt erstellt und einen Zeiger darauf zurückgibt.

Weitere Informationen `CFtpConnection` zum Arbeiten mit den anderen MFC-Internet Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md). Weitere Informationen zur Kommunikation mit den anderen beiden unterstützten Diensten, http und Gopher, finden Sie unter den Klassen " [CHttpConnection](../../mfc/reference/chttpconnection-class.md) " und " [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)".

## <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel in der Übersicht über die [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) -Klasse.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CFtpConnection`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="cftpconnection"></a>CFtpConnection:: CFtpConnection

Diese Member-Funktion wird aufgerufen, um `CFtpConnection` ein-Objekt zu erstellen.

```
CFtpConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CFtpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 0,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
```

### <a name="parameters"></a>Parameter

*pSession*<br/>
Ein Zeiger auf das zugehörige [cinternetzession](../../mfc/reference/cinternetsession-class.md) -Objekt.

*hConnected*<br/>
Das Windows-Handle der aktuellen Internet Sitzung.

*pstrServer*<br/>
Ein Zeiger auf eine Zeichenfolge, die den FTP-Servernamen enthält.

*dwContext*<br/>
Der Kontext Bezeichner für den Vorgang. *dwcontext* identifiziert die von [cinternetzession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)zurückgegebenen Statusinformationen des Vorgangs. Der Standardwert wird auf 1 festgelegt. Sie können jedoch explizit eine bestimmte Kontext-ID für den Vorgang zuweisen. Das-Objekt und alle Aufgaben, die es durchführt, werden mit dieser Kontext-ID verknüpft.

*pstrUserName*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen des Benutzers angibt, der angemeldet werden soll. Wenn der Wert NULL ist, ist der Standardwert Anonymous.

*pstrPassword*<br/>
Ein Zeiger auf eine mit NULL endende Zeichenfolge, die das Kennwort für die Anmeldung angibt. Wenn sowohl *pstraupassword* als auch *pstrusername* NULL sind, ist das anonyme Standard Kennwort der e-Mail-Name des Benutzers. Wenn *pstraupassword* NULL (oder eine leere Zeichenfolge) ist, aber *pstrusername* nicht NULL ist, wird ein leeres Kennwort verwendet. In der folgenden Tabelle wird das Verhalten der vier möglichen Einstellungen von *pstrusername* und *pstrinpassword*beschrieben:

|*pstrUserName*|*pstrPassword*|An FTP-Server gesendeter Benutzername|Kennwort an FTP-Server gesendet|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL oder ""|NULL oder ""|Anonymous|E-Mail-Name des Benutzers|
|Zeichenfolge ungleich NULL|NULL oder ""|*pstrUserName*|" "|
|NULL-Zeichenfolge ungleich NULL|Fehler|Fehler||
|Zeichenfolge ungleich NULL|Zeichenfolge ungleich NULL|*pstrUserName*|*pstrPassword*|

*nPort*<br/>
Eine Zahl, die den auf dem Server zu verwendenden TCP/IP-Port identifiziert.

*bPassive*<br/>
Gibt den passiven oder aktiven Modus für diese FTP-Sitzung an. Wenn der Wert auf true festgelegt ist, wird das Win32-API- *dwFlag* auf INTERNET_FLAG_PASSIVE festgelegt.

### <a name="remarks"></a>Hinweise

Sie erstellen niemals direkt `CFtpConnection` ein-Objekt. Aufrufen Sie stattdessen [cinternetzession:: GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), die das `CFptConnection` -Objekt erstellt.

##  <a name="command"></a>CFtpConnection:: Command

Sendet einen Befehl direkt an einen FTP-Server.

```
CInternetFile* Command(
    LPCTSTR pszCommand,
    CmdResponseType eResponse = CmdRespNone,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parameter

*pszCommand*<br/>
Ein Zeiger auf eine Zeichenfolge, die den zu sendenden Befehl enthält.

*eresponse*<br/>
Bestimmt, ob eine Antwort vom FTP-Server erwartet wird. Kann einer der folgenden Werte sein:

- `CmdRespNone`Es wird keine Antwort erwartet.

- `CmdRespRead`Es wird eine Antwort erwartet.

*dwFlags*<br/>
Ein Wert mit den Flags, die diese Funktion steuern. Eine komplette Liste finden Sie unter [ftpcommand](/windows/win32/api/wininet/nf-wininet-ftpcommandw).

*dwContext*<br/>
Ein Zeiger auf einen Wert mit einem anwendungsdefinierten Wert, der zur Identifizierung des Anwendungskontexts in Rückrufen verwendet wird.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Member-Funktion emuliert die Funktionalität der [ftpcommand](/windows/win32/api/wininet/nf-wininet-ftpcommandw) -Funktion, wie im Windows SDK beschrieben.

Wenn ein Fehler auftritt, löst MFC eine Ausnahme vom Typ [cinternettexception](../../mfc/reference/cinternetexception-class.md)aus.

##  <a name="createdirectory"></a>CFtpConnection:: kreatedirectory

Rufen Sie diese Member-Funktion auf, um ein Verzeichnis auf dem verbundenen Server zu erstellen.

```
BOOL CreateDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Parameter

*pstrDirName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen des zu erstellenden Verzeichnisses enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Windows-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Verwenden `GetCurrentDirectory` Sie, um das aktuelle Arbeitsverzeichnis für diese Verbindung mit dem Server zu ermitteln. Gehen Sie nicht davon aus, dass das Remote System eine Verbindung mit dem Stammverzeichnis hergestellt hat.

Der `pstrDirName` -Parameter kann entweder ein teilweise oder ein voll qualifizierter Dateiname sein, der relativ zum aktuellen Verzeichnis ist. Ein umgekehrter schräg\\Strich () oder ein Schrägstrich (/) kann als Verzeichnis Trennzeichen für beide Namen verwendet werden. `CreateDirectory`übersetzt die Verzeichnisnamen Trennzeichen in die entsprechenden Zeichen, bevor Sie verwendet werden.

##  <a name="getcurrentdirectory"></a>CFtpConnection:: GetCurrentDirectory

Mit dieser Member-Funktion können Sie den Namen des aktuellen Verzeichnisses abrufen.

```
BOOL GetCurrentDirectory(CString& strDirName) const;

BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>Parameter

*strDirName*<br/>
Ein Verweis auf eine Zeichenfolge, die den Namen des Verzeichnisses empfängt.

*pstrDirName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen des Verzeichnisses empfängt.

*lpdwLen*<br/>
Ein Zeiger auf ein DWORD, das die folgenden Informationen enthält:

|||
|-|-|
|Bei Eintrag|Die Größe des Puffers, auf den von *pstrindirname*verwiesen wird.|
|Bei Rückgabe|Die Anzahl der in " *pstrindirname*" gespeicherten Zeichen. Wenn die Member-Funktion fehlschlägt und ERROR_INSUFFICIENT_BUFFER zurückgegeben wird, enthält *lpdwlen* die Anzahl von Bytes, die die Anwendung zuordnen muss, um die Zeichenfolge zu empfangen.|

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Wenn Sie stattdessen den Verzeichnisnamen als URL abrufen möchten, müssen Sie [GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)aufrufen.

Bei den Parametern " *pstrindirname* " oder " *Strauch Name* " kann es sich entweder um teilweise qualifizierte Dateinamen in Bezug auf das aktuelle Verzeichnis oder um einen voll qualifizierten Ein umgekehrter schräg\\Strich () oder ein Schrägstrich (/) kann als Verzeichnis Trennzeichen für beide Namen verwendet werden. `GetCurrentDirectory`übersetzt die Verzeichnisnamen Trennzeichen in die entsprechenden Zeichen, bevor Sie verwendet werden.

##  <a name="getcurrentdirectoryasurl"></a>CFtpConnection:: getcurrentdirector yasurl

Mit dieser Member-Funktion können Sie den Namen des aktuellen Verzeichnisses als URL abrufen.

```
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;

BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>Parameter

*strDirName*<br/>
Ein Verweis auf eine Zeichenfolge, die den Namen des Verzeichnisses empfängt.

*pstrDirName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen des Verzeichnisses empfängt.

*lpdwLen*<br/>
Ein Zeiger auf ein DWORD, das die folgenden Informationen enthält:

|||
|-|-|
|Bei Eintrag|Die Größe des Puffers, auf den von *pstrindirname*verwiesen wird.|
|Bei Rückgabe|Die Anzahl der in " *pstrindirname*" gespeicherten Zeichen. Wenn die Member-Funktion fehlschlägt und ERROR_INSUFFICIENT_BUFFER zurückgegeben wird, enthält *lpdwlen* die Anzahl von Bytes, die die Anwendung zuordnen muss, um die Zeichenfolge zu empfangen.|

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

`GetCurrentDirectoryAsURL`verhält sich wie [GetCurrentDirectory](#getcurrentdirectory)

Der Parameter "" "" "" "" "" "" "" "" "" "" "" "". Ein umgekehrter schräg\\Strich () oder ein Schrägstrich (/) kann als Verzeichnis Trennzeichen für beide Namen verwendet werden. `GetCurrentDirectoryAsURL`übersetzt die Verzeichnisnamen Trennzeichen in die entsprechenden Zeichen, bevor Sie verwendet werden.

##  <a name="getfile"></a>CFtpConnection:: GetFile

Mit dieser Member-Funktion können Sie eine Datei von einem FTP-Server abrufen und auf dem lokalen Computer speichern.

```
BOOL GetFile(
    LPCTSTR pstrRemoteFile,
    LPCTSTR pstrLocalFile,
    BOOL bFailIfExists = TRUE,
    DWORD dwAttributes = FILE_ATTRIBUTE_NORMAL,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parameter

*pstrRemoteFile*<br/>
Ein Zeiger auf eine NULL-terminierte Zeichenfolge mit dem Namen einer Datei, die vom FTP-Server abgerufen werden soll.

*pstrLocalFile*<br/>
Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Namen der Datei enthält, die auf dem lokalen System erstellt werden soll.

*bFailIfExists*<br/>
Gibt an, ob der Dateiname bereits von einer vorhandenen Datei verwendet werden kann. Wenn der Name der lokalen Datei bereits vorhanden ist und dieser Parameter true ist `GetFile` , schlägt fehl. `GetFile` Andernfalls löscht die vorhandene Kopie der Datei.

*dwAttributes*<br/>
Gibt die Attribute der Datei an. Dabei kann es sich um eine beliebige Kombination der folgenden FILE_ATTRIBUTE_ *-Flags handeln.

- FILE_ATTRIBUTE_ARCHIVE bei der Datei handelt es sich um eine Archivdatei. Anwendungen verwenden dieses Attribut, um Dateien für die Sicherung oder Entfernung zu markieren.

- FILE_ATTRIBUTE_COMPRESSED die Datei oder das Verzeichnis ist komprimiert. Bei einer Datei bedeutet die Komprimierung, dass alle Daten in der Datei komprimiert sind. Für ein Verzeichnis ist die Komprimierung der Standardwert für neu erstellte Dateien und Unterverzeichnisse.

- FILE_ATTRIBUTE_DIRECTORY die Datei ist ein Verzeichnis.

- FILE_ATTRIBUTE_NORMAL für die Datei sind keine anderen Attribute festgelegt. Dieses Attribut ist nur gültig, wenn es allein verwendet wird. Alle anderen Dateiattribute überschreiben FILE_ATTRIBUTE_NORMAL:

- FILE_ATTRIBUTE_HIDDEN die Datei ist ausgeblendet. Er darf nicht in eine gewöhnliche Verzeichnis Auflistung eingeschlossen werden.

- FILE_ATTRIBUTE_READONLY die Datei ist schreibgeschützt. Anwendungen können die Datei lesen, aber nicht schreiben oder löschen.

- FILE_ATTRIBUTE_SYSTEM die Datei ist Teil von oder wird ausschließlich vom Betriebs System verwendet.

- FILE_ATTRIBUTE_TEMPORARY die Datei wird für den temporären Speicher verwendet. Anwendungen sollten nur dann in die Datei schreiben, wenn dies unbedingt erforderlich ist. Die meisten Daten der Datei verbleiben im Arbeitsspeicher, ohne auf die Medien geleert zu werden, da die Datei in Kürze gelöscht wird.

*dwFlags*<br/>
Gibt die Bedingungen an, unter denen die Übertragung erfolgt. Dieser Parameter kann ein beliebiger *dwFlags* -Wert sein, der in der Windows SDK unter [ftpgetfile](/windows/win32/api/wininet/nf-wininet-ftpgetfilew) beschrieben wird.

*dwContext*<br/>
Der Kontext Bezeichner für das Abrufen von Dateien. Weitere Informationen zu *dwcontext*finden Sie unter " **Hinweise** ".

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

`GetFile`ist eine allgemeine Routine, die den gesamten mehr Aufwand für das Lesen einer Datei von einem FTP-Server und die lokale Speicherung behandelt. Anwendungen, die nur Datei Daten abrufen oder die eine schließende Kontrolle über die Dateiübertragung benötigen, `OpenFile` sollten stattdessen und [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read) verwenden.

Wenn *dwFlags* den Wert FILE_TRANSFER_TYPE_ASCII hat, konvertiert die Übersetzung von Datei Daten auch Steuerzeichen und Formatierungszeichen in Windows-Entsprechungen. Die Standard Übertragung ist der binäre Modus, bei dem die Datei im gleichen Format wie auf dem Server heruntergeladen wird.

Sowohl *pstrauremotefile* als auch *pstrinlocalfile* können entweder teilweise qualifizierte Dateinamen in Relation zum aktuellen Verzeichnis oder voll qualifiziert sein. Ein umgekehrter schräg\\Strich () oder ein Schrägstrich (/) kann als Verzeichnis Trennzeichen für beide Namen verwendet werden. `GetFile`übersetzt die Verzeichnisnamen Trennzeichen in die entsprechenden Zeichen, bevor Sie verwendet werden.

Überschreiben Sie den *dwcontext* -Standard, um den Kontext Bezeichner auf einen Wert Ihrer Wahl festzulegen. Der Kontext Bezeichner ist diesem speziellen Vorgang des Objekts zugeordnet `CFtpConnection` , das vom [cinternetzession](../../mfc/reference/cinternetsession-class.md) -Objekt erstellt wurde. Der Wert wird an [cinternetzession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zurückgegeben, um den Status für den Vorgang bereitzustellen, mit dem er identifiziert wird. Weitere Informationen finden [Sie im Artikel Internet First Steps: WinInet](../../mfc/wininet-basics.md) für weitere Informationen zum Kontext Bezeichner.

##  <a name="openfile"></a>CFtpConnection:: OpenFile

Mit dieser Member-Funktion können Sie eine Datei öffnen, die sich auf einem FTP-Server zum Lesen oder schreiben befindet.

```
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,
    DWORD dwAccess = GENERIC_READ,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parameter

*pstrFileName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen der zu öffnenden Datei enthält.

*dwAccess*<br/>
Bestimmt, wie auf die Datei zugegriffen wird. Kann entweder GENERIC_READ oder GENERIC_WRITE sein, aber nicht beides.

*dwFlags*<br/>
Gibt die Bedingungen an, unter denen nachfolgende Übertragungen stattfinden. Dies kann eine der folgenden FTP_TRANSFER_ *-Konstanten sein:

- FTP_TRANSFER_TYPE_ASCII die Dateiübertragung mithilfe der FTP-ASCII-Übertragungsmethode (Typ A). Konvertiert Steuerelement-und Formatierungsinformationen in lokale Entsprechungen.

- FTP_TRANSFER_TYPE_BINARY die Datei überträgt Daten mithilfe der FTP-Abbild Übertragungsmethode (Typ I). Die Datei überträgt Daten genau so, wie Sie vorhanden sind, ohne Änderungen. Dies ist die Standard Übertragungsmethode.

*dwContext*<br/>
Der Kontext Bezeichner zum Öffnen der Datei. Weitere Informationen zu *dwcontext*finden Sie unter " **Hinweise** ".

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CInternetFile](../../mfc/reference/cinternetfile-class.md) -Objekt.

### <a name="remarks"></a>Hinweise

`OpenFile`sollte in den folgenden Situationen verwendet werden:

- Eine Anwendung verfügt über Daten, die als Datei auf dem FTP-Server gesendet und erstellt werden müssen, diese Daten befinden sich jedoch nicht in einer lokalen Datei. Sobald `OpenFile` eine Datei geöffnet wird, verwendet die Anwendung [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write) , um die FTP-Datei Daten an den Server zu senden.

- Eine Anwendung muss eine Datei vom Server abrufen und in Anwendungs gesteuerten Speicher platzieren, anstatt Sie auf den Datenträger zu schreiben. Die Anwendung verwendet [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read) nach der `OpenFile` Verwendung von, um die Datei zu öffnen.

- Eine Anwendung benötigt eine gute Steuerungsebene für eine Dateiübertragung. Die Anwendung kann z. b. ein Status-Steuerelement anzeigen, das den Fortschritt des Datei Übertragungs Status beim Herunterladen einer Datei anzeigt.

Nach dem `OpenFile` Aufrufen von und `CInternetConnection::Close`bis zum Aufrufen von kann die Anwendung nur [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write), `CInternetConnection::Close`oder [CFtpFileFind:: FindFile](../../mfc/reference/cftpfilefind-class.md#findfile)aufrufen. Aufrufe an andere FTP-Funktionen für dieselbe FTP-Sitzung schlagen fehl, und der Fehlercode wird auf FTP_ETRANSFER_IN_PROGRESS festgelegt.

Der *pstrinfilename* -Parameter kann entweder ein teilweise qualifizierter Dateiname relativ zum aktuellen Verzeichnis oder voll qualifiziert sein. Ein umgekehrter schräg\\Strich () oder ein Schrägstrich (/) kann als Verzeichnis Trennzeichen für beide Namen verwendet werden. `OpenFile`übersetzt die Verzeichnisnamen Trennzeichen vor der Verwendung in die entsprechenden Zeichen.

Überschreiben Sie den *dwcontext* -Standard, um den Kontext Bezeichner auf einen Wert Ihrer Wahl festzulegen. Der Kontext Bezeichner ist diesem speziellen Vorgang des Objekts zugeordnet `CFtpConnection` , das vom [cinternetzession](../../mfc/reference/cinternetsession-class.md) -Objekt erstellt wurde. Der Wert wird an [cinternetzession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zurückgegeben, um den Status für den Vorgang bereitzustellen, mit dem er identifiziert wird. Weitere Informationen finden [Sie im Artikel Internet First Steps: WinInet](../../mfc/wininet-basics.md) für weitere Informationen zum Kontext Bezeichner.

##  <a name="putfile"></a>CFtpConnection::P utfile

Mit dieser Member-Funktion können Sie eine Datei auf einem FTP-Server speichern.

```
BOOL PutFile(
    LPCTSTR pstrLocalFile,
    LPCTSTR pstrRemoteFile,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parameter

*pstrLocalFile*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen der Datei enthält, die vom lokalen System gesendet werden soll.

*pstrRemoteFile*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen der Datei enthält, die auf dem FTP-Server erstellt werden soll.

*dwFlags*<br/>
Gibt die Bedingungen an, unter denen die Übertragung der Datei erfolgt. Kann eine der in [OpenFile](#openfile)beschriebenen FTP_TRANSFER_ *-Konstanten sein.

*dwContext*<br/>
Der Kontext Bezeichner zum Platzieren der Datei. Weitere Informationen zu *dwcontext*finden Sie unter " **Hinweise** ".

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

`PutFile`ist eine allgemeine Routine, die alle Vorgänge behandelt, die mit dem Speichern einer Datei auf einem FTP-Server verbunden sind. Anwendungen, die nur Daten senden oder eine genauere Kontrolle über die Dateiübertragung benötigen, sollten [OpenFile](#openfile) und [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write)verwenden.

Überschreiben Sie den `dwContext`-Standard, um den Kontextbezeichner auf einen ausgewählten Wert festzulegen. Der Kontext Bezeichner ist diesem speziellen Vorgang des Objekts zugeordnet `CFtpConnection` , das vom [cinternetzession](../../mfc/reference/cinternetsession-class.md) -Objekt erstellt wurde. Der Wert wird an [cinternetzession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zurückgegeben, um den Status für den Vorgang bereitzustellen, mit dem er identifiziert wird. Weitere Informationen finden [Sie im Artikel Internet First Steps: WinInet](../../mfc/wininet-basics.md) für weitere Informationen zum Kontext Bezeichner.

##  <a name="remove"></a>CFtpConnection:: Remove

Mit dieser Member-Funktion wird die angegebene Datei vom verbundenen Server gelöscht.

```
BOOL Remove(LPCTSTR pstrFileName);
```

### <a name="parameters"></a>Parameter

*pstrFileName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Dateinamen enthält, der entfernt werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Der *pstrinfilename* -Parameter kann entweder ein teilweise qualifizierter Dateiname relativ zum aktuellen Verzeichnis oder voll qualifiziert sein. Ein umgekehrter schräg\\Strich () oder ein Schrägstrich (/) kann als Verzeichnis Trennzeichen für beide Namen verwendet werden. Die `Remove` -Funktion übersetzt die Verzeichnisnamen Trennzeichen in die entsprechenden Zeichen, bevor Sie verwendet werden.

##  <a name="removedirectory"></a>CFtpConnection:: RemoveDirectory

Mit dieser Member-Funktion wird das angegebene Verzeichnis vom verbundenen Server entfernt.

```
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Parameter

*pstrDirName*<br/>
Ein Zeiger auf eine Zeichenfolge, die das zu entfernende Verzeichnis enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Verwenden Sie [GetCurrentDirectory](#getcurrentdirectory) , um das aktuelle Arbeitsverzeichnis des Servers zu bestimmen. Gehen Sie nicht davon aus, dass das Remote System eine Verbindung mit dem Stammverzeichnis hergestellt hat.

Der *pstrindirname* -Parameter kann entweder ein teilweise oder voll qualifizierter Dateiname relativ zum aktuellen Verzeichnis sein. Ein umgekehrter schräg\\Strich () oder ein Schrägstrich (/) kann als Verzeichnis Trennzeichen für beide Namen verwendet werden. `RemoveDirectory`übersetzt die Verzeichnisnamen Trennzeichen in die entsprechenden Zeichen, bevor Sie verwendet werden.

##  <a name="rename"></a>CFtpConnection:: Rename

Mit dieser Member-Funktion können Sie die angegebene Datei auf dem verbundenen Server umbenennen.

```
BOOL Rename(
    LPCTSTR pstrExisting,
    LPCTSTR pstrNew);
```

### <a name="parameters"></a>Parameter

*pstrExisting*<br/>
Ein Zeiger auf eine Zeichenfolge, die den aktuellen Namen der Datei enthält, die umbenannt werden soll.

*pstraunew*<br/>
Ein Zeiger auf eine Zeichenfolge, die den neuen Namen der Datei enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Die Parameter *pstrexisting* und *pstrenew* können entweder ein teilweise qualifizierter Dateiname relativ zum aktuellen Verzeichnis oder voll qualifiziert sein. Ein umgekehrter schräg\\Strich () oder ein Schrägstrich (/) kann als Verzeichnis Trennzeichen für beide Namen verwendet werden. `Rename`übersetzt die Verzeichnisnamen Trennzeichen in die entsprechenden Zeichen, bevor Sie verwendet werden.

##  <a name="setcurrentdirectory"></a>CFtpConnection:: SetCurrentDirectory

Mit dieser Member-Funktion können Sie in ein anderes Verzeichnis auf dem FTP-Server wechseln.

```
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Parameter

*pstrDirName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen des Verzeichnisses enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Der *pstrindirname* -Parameter kann entweder ein teilweise oder voll qualifizierter Dateiname relativ zum aktuellen Verzeichnis sein. Ein umgekehrter schräg\\Strich () oder ein Schrägstrich (/) kann als Verzeichnis Trennzeichen für beide Namen verwendet werden. `SetCurrentDirectory`übersetzt die Verzeichnisnamen Trennzeichen in die entsprechenden Zeichen, bevor Sie verwendet werden.

Verwenden Sie [GetCurrentDirectory](#getcurrentdirectory) , um das aktuelle Arbeitsverzeichnis eines FTP-Servers zu bestimmen. Gehen Sie nicht davon aus, dass das Remote System eine Verbindung mit dem Stammverzeichnis hergestellt hat.

## <a name="see-also"></a>Siehe auch

[CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)<br/>
[CInternetSession-Klasse](../../mfc/reference/cinternetsession-class.md)
