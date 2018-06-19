---
title: CAtlTransactionManager Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::Close
- ATLTRANSACTIONMANAGER/ATL::Commit
- ATLTRANSACTIONMANAGER/ATL::Create
- ATLTRANSACTIONMANAGER/ATL::CreateFile
- ATLTRANSACTIONMANAGER/ATL::DeleteFile
- ATLTRANSACTIONMANAGER/ATL::FindFirstFile
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributesEx
- ATLTRANSACTIONMANAGER/ATL::GetHandle
- ATLTRANSACTIONMANAGER/ATL::IsFallback
- ATLTRANSACTIONMANAGER/ATL::MoveFile
- ATLTRANSACTIONMANAGER/ATL::RegCreateKeyEx
- ATLTRANSACTIONMANAGER/ATL::RegDeleteKey
- ATLTRANSACTIONMANAGER/ATL::RegOpenKeyEx
- ATLTRANSACTIONMANAGER/ATL::Rollback
- ATLTRANSACTIONMANAGER/ATL::SetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::m_bFallback
- ATLTRANSACTIONMANAGER/ATL::m_hTransaction
dev_langs:
- C++
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02ab9cd6f8867f9e6bc9d81ff825e8fe8f7b57d7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365938"
---
# <a name="catltransactionmanager-class"></a>CAtlTransactionManager-Klasse
CAtlTransactionManager-Klasse stellt einen Wrapper für die Funktionen des Kerneltransaktions-Manager (KTM) bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlTransactionManager;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[~ CAtlTransactionManager](#dtor)|CAtlTransactionManager-Destruktor.|  
|[CAtlTransactionManager](#catltransactionmanager)|CAtlTransactionManager-Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Schließen](#close)|Schließt eine Transaktionshandle des.|  
|[Commit](#commit)|Fordert an, dass die Transaktion ein Commit ausgeführt werden.|  
|[Erstellen](#create)|Erstellt das Transaktionshandle.|  
|[CreateFile](#createfile)|Erstellt oder öffnet eine Datei, eine Dateidatenstrom oder ein Verzeichnis als ein Transaktiver Vorgang.|  
|[DeleteFile](#deletefile)|Löscht eine vorhandene Datei als ein Transaktiver Vorgang an.|  
|[FindFirstFile](#findfirstfile)|Sucht in einem Verzeichnis für eine Datei oder ein Unterverzeichnis als ein Transaktiver Vorgang.|  
|[GetFileAttributes](#getfileattributes)|Ruft die Attribute des Dateisystems für eine angegebene Datei oder ein Verzeichnis als ein Transaktiver Vorgang ab.|  
|[GetFileAttributesEx](#getfileattributesex)|Ruft die Attribute des Dateisystems für eine angegebene Datei oder ein Verzeichnis als ein Transaktiver Vorgang ab.|  
|[GetHandle](#gethandle)|Gibt das Transaktionshandle zurück.|  
|[IsFallback](#isfallback)|Bestimmt, ob das fallback-Aufrufe aktiviert sind.|  
|[MoveFile](#movefile)|Verschiebt eine vorhandene Datei oder ein Verzeichnis ist, einschließlich seiner untergeordneten Elemente als ein Transaktiver Vorgang.|  
|[RegCreateKeyEx](#regcreatekeyex)|Erstellt den angegebenen Registrierungsschlüssel, und ordnet sie einer Transaktion. Wenn der Schlüssel bereits vorhanden ist, wird Sie von die Funktion geöffnet.|  
|[RegDeleteKey](#regdeletekey)|Löscht einen Unterschlüssel und ihre Werte aus der angegebenen Clientplattform-spezifische Ansicht der Registrierung als ein Transaktiver Vorgang.|  
|[Fehler bei RegOpenKeyEx](#regopenkeyex)|Öffnet den angegebenen Registrierungsschlüssel, und ordnet sie einer Transaktion.|  
|[Rollback](#rollback)|Anforderungen, die die Transaktion ein Rollback ausgeführt werden.|  
|[SetFileAttributes](#setfileattributes)|Legt die Attribute für eine Datei oder ein Verzeichnis als ein Transaktiver Vorgang fest.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[m_bFallback](#m_bfallback)|`TRUE` Wenn das Fallback unterstützt wird. `FALSE` andernfalls.|  
|[m_hTransaction](#m_htransaction)|Das Transaktionshandle.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltransactionmanager.h  
  
##  <a name="dtor"></a>  ~ CAtlTransactionManager  
 CAtlTransactionManager-Destruktor.  
  
```
virtual ~CAtlTransactionManager();
```  
  
### <a name="remarks"></a>Hinweise  
 Bei der normalen Verarbeitung wird die Transaktion automatisch ein Commit und geschlossen. Wenn bei einer Ausnahme Entladung der Destruktor aufgerufen wird, wird die Transaktion zurückgesetzt und geschlossen.  
  
##  <a name="catltransactionmanager"></a>  CAtlTransactionManager  
 CAtlTransactionManager-Konstruktor.  
  
```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bFallback`  
 `TRUE` Gibt Unterstützung Fallback an. Wenn transaktive Funktion fehlerhaft ist, ruft die Klasse automatisch die Funktion "nicht transaktiven". `FALSE` gibt keine "fallback" Aufrufe an.  
  
 `bAutoCreateTransaction`  
 `TRUE` Gibt an, dass der Handler für die Transaktion automatisch im Konstruktor erstellt wird. `FALSE` Gibt an, dass es nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="close"></a>  Schließen Sie  
 Schließt das Transaktionshandle.  
  
```
inline BOOL Close();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `CloseHandle` Funktion. Die Methode wird in der Destruktor automatisch aufgerufen.  
  
##  <a name="commit"></a>  Commit  
 Fordert an, dass die Transaktion ein Commit ausgeführt werden.  
  
```
inline BOOL Commit();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `CommitTransaction` Funktion. Die Methode wird in der Destruktor automatisch aufgerufen.  
  
##  <a name="create"></a>  Erstellen  
 Erstellt das Transaktionshandle.  
  
```
inline BOOL Create();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `CreateTransaction` Funktion. Überprüfen Sie diesen  
  
##  <a name="createfile"></a>  CreateFile  
 Erstellt oder öffnet eine Datei, eine Dateidatenstrom oder ein Verzeichnis als ein Transaktiver Vorgang.  
  
```
inline HANDLE CreateFile(
  LPCTSTR lpFileName,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes,
    HANDLE hTemplateFile);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFileName`  
 Der Name eines Objekts erstellt oder geöffnet werden.  
  
 `dwDesiredAccess`  
 Der Zugriff auf das Objekt, das als lesen, schreiben, beide oder keines von beiden (null) zusammengefasst werden kann. Die am häufigsten verwendeten Werte werden GENERIC_READ und/oder GENERIC_WRITE: GENERIC_READ &#124; GENERIC_WRITE.  
  
 `dwShareMode`  
 Der Freigabemodus der ein Objekt, das Lesen, schreiben, die beide, können alle oder keine löschen: 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE.  
  
 `lpSecurityAttributes`  
 Ein Zeiger auf eine SECURITY_ATTRIBUTES-Struktur, die eine optionale Sicherheitsbeschreibung enthält und legt fest, und zwar unabhängig davon, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden kann. Der Parameter sein `NULL`.  
  
 `dwCreationDisposition`  
 Aktion für Dateien ausgeführt werden soll, die vorhanden sein und sind nicht vorhanden. Dieser Parameter muss einer der folgenden Werte können nicht kombiniert werden: CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING oder TRUNCATE_EXISTING.  
  
 `dwFlagsAndAttributes`  
 Die Dateiattribute und Flags. Dieser Parameter kann eine beliebige Kombination der verfügbaren Dateiattribute (FILE_ATTRIBUTE_ *) umfassen. Alle anderen Dateiattribute überschreiben FILE_ATTRIBUTE_NORMAL. Dieser Parameter kann auch Kombinationen der Flags enthalten (FILE_FLAG_\*) Zugriff auf die Steuerung des Verhaltens Pufferung, Modi und andere spezielle Flags. Von diesen Einstellungen wird mit jeder FILE_ATTRIBUTE_\* Werte.  
  
 `hTemplateFile`  
 Ein gültiges Handle auf eine Vorlagendatei mit dem richtigen GENERIC_READ-Zugriff. Die Vorlagendatei bereitstellt, Dateiattribute und der erweiterten Attribute für die Datei, die erstellt wird. Dieser Parameter kann `NULL` sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Handle, das Zugriff auf das Objekt verwendet werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `CreateFileTransacted` Funktion.  
  
##  <a name="deletefile"></a>  DeleteFile  
 Löscht eine vorhandene Datei als ein Transaktiver Vorgang an.  
  
```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFileName`  
 Der Name der zu löschenden Datei.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `DeleteFileTransacted` Funktion.  
  
##  <a name="findfirstfile"></a>  FindFirstFile  
 Sucht in einem Verzeichnis für eine Datei oder ein Unterverzeichnis als ein Transaktiver Vorgang.  
  
```
inline HANDLE FindFirstFile(
  LPCTSTR lpFileName,
  WIN32_FIND_DATA* pNextInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFileName`  
 Das Verzeichnis oder Pfad und den Dateinamen zu suchen. Dieser Parameter kann Platzhalterzeichen, wie z. B. ein Sternchen (*) oder ein Fragezeichen () umfassen.  
  
 `pNextInfo`  
 Ein Zeiger auf die WIN32_FIND_DATA-Struktur, die Informationen über eine gefundene Datei oder ein Unterverzeichnis empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert eine Suchhandle in einem nachfolgenden Aufruf verwendet `FindNextFile` oder `FindClose`. Wenn die Funktion ein Fehler auftritt oder keine Dateien aus der Suchzeichenfolge in findet die `lpFileName` Parameter, der Rückgabewert ist INVALID_HANDLE_VALUE.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `FindFirstFileTransacted` Funktion.  
  
##  <a name="getfileattributes"></a>  GetFileAttributes  
 Ruft die Attribute des Dateisystems für eine angegebene Datei oder ein Verzeichnis als ein Transaktiver Vorgang ab.  
  
```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFileName`  
 Der Name der Datei oder des Verzeichnisses.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `GetFileAttributesTransacted` Funktion.  
  
##  <a name="getfileattributesex"></a>  GetFileAttributesEx  
 Ruft die Attribute des Dateisystems für eine angegebene Datei oder ein Verzeichnis als ein Transaktiver Vorgang ab.  
  
```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFileName`  
 Der Name der Datei oder des Verzeichnisses.  
  
 `fInfoLevelId`  
 Die Ebene der Informationen über Bildattribute abgerufen.  
  
 `lpFileInformation`  
 Ein Zeiger auf einen Puffer, der die Attributinformationen empfängt. Der Typ des in diesem Puffer gespeicherten Attributinformationen wird bestimmt durch den Wert des `fInfoLevelId`. Wenn die `fInfoLevelId` Parameter GetFileExInfoStandard dann dieser Parameter verweist auf eine WIN32_FILE_ATTRIBUTE_DATA-Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `GetFileAttributesTransacted` Funktion.  
  
##  <a name="gethandle"></a>  GetHandle  
 Gibt das Transaktionshandle zurück.  
  
```
HANDLE GetHandle() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Transaktionshandle für eine Klasse zurück. Gibt `NULL` Wenn die `CAtlTransactionManager` nicht an ein Handle angefügt ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isfallback"></a>  IsFallback  
 Bestimmt, ob das fallback-Aufrufe aktiviert sind.  
  
```
BOOL IsFallback() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` ist die Klasse unterstützt das fallback-Aufrufe. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_bfallback"></a>  m_bFallback  
 `TRUE` Wenn das Fallback unterstützt wird. `FALSE` andernfalls.  
  
```
BOOL m_bFallback;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_htransaction"></a>  m_hTransaction  
 Das Transaktionshandle.  
  
```
HANDLE m_hTransaction;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="movefile"></a>  MoveFile  
 Verschiebt eine vorhandene Datei oder ein Verzeichnis ist, einschließlich seiner untergeordneten Elemente als ein Transaktiver Vorgang.  
  
```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpOldFileName`  
 Der aktuelle Name der vorhandenen Datei oder des Verzeichnisses auf dem lokalen Computer.  
  
 `lpNewFileName`  
 Der neue Name für die Datei oder das Verzeichnis. Dieser Name darf nicht bereits vorhanden sein. Eine neue Datei ist möglicherweise auf einem anderen Dateisystem oder dem Laufwerk. Ein neues Verzeichnis muss auf dem gleichen Laufwerk sein.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `MoveFileTransacted` Funktion.  
  
##  <a name="regcreatekeyex"></a>  RegCreateKeyEx  
 Erstellt den angegebenen Registrierungsschlüssel, und ordnet sie einer Transaktion. Wenn der Schlüssel bereits vorhanden ist, wird Sie von die Funktion geöffnet.  
  
```
inline LSTATUS RegCreateKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD dwReserved,
    LPTSTR lpClass,
    DWORD dwOptions,
    REGSAM samDesired,
    CONST LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    PHKEY phkResult,
    LPDWORD lpdwDisposition);
```  
  
### <a name="parameters"></a>Parameter  
 `hKey`  
 Ein Handle für ein Öffnen des Registrierungsschlüssels.  
  
 `lpSubKey`  
 Der Name, der einen Unterschlüssel, den diese Funktion wird geöffnet oder erstellt werden soll.  
  
 `dwReserved`  
 Dieser Parameter ist reserviert und muss 0 (null) sein.  
  
 `lpClass`  
 Die benutzerdefinierte Klasse dieses Schlüssels. Dieser Parameter kann ignoriert werden. Dieser Parameter kann NULL sein.  
  
 `dwOptions`  
 Dieser Parameter kann einen der folgenden Werte sein: REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE oder REG_OPTION_VOLATILE.  
  
 `samDesired`  
 Eine Maske, die Zugriffsrechte für den Schlüssel angibt.  
  
 `lpSecurityAttributes`  
 Ein Zeiger auf eine SECURITY_ATTRIBUTES-Struktur, die bestimmt, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden kann. Wenn `lpSecurityAttributes` ist `NULL`, das Handle kann nicht vererbt werden.  
  
 `phkResult`  
 Ein Zeiger auf eine Variable, die ein Handle für den Schlüssel geöffnet oder erstellt empfängt, werden soll. Wenn der Schlüssel nicht eine der vordefinierten Registrierungsschlüssel ist, rufen Sie die `RegCloseKey` funktionieren, wenn Sie mit dem Handle abgeschlossen haben.  
  
 `lpdwDisposition`  
 Ein Zeiger auf eine Variable, einen der folgenden Dispositionswerte empfängt: REG_CREATED_NEW_KEY oder REG_OPENED_EXISTING_KEY.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `RegCreateKeyTransacted` Funktion.  
  
##  <a name="regdeletekey"></a>  RegDeleteKey  
 Löscht einen Unterschlüssel und ihre Werte aus der angegebenen Clientplattform-spezifische Ansicht der Registrierung als ein Transaktiver Vorgang.  
  
```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`hKey`|Ein Handle für ein Öffnen des Registrierungsschlüssels.|  
|`lpSubKey`|Der Name des Schlüssels, der gelöscht werden.|  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `RegDeleteKeyTransacted` Funktion.  
  
##  <a name="regopenkeyex"></a>  Fehler bei RegOpenKeyEx  
 Öffnet den angegebenen Registrierungsschlüssel, und ordnet sie einer Transaktion.  
  
```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```  
  
### <a name="parameters"></a>Parameter  
 `hKey`  
 Ein Handle für ein Öffnen des Registrierungsschlüssels.  
  
 `lpSubKey`  
 Der Name des Registrierungsunterschlüssels geöffnet werden.  
  
 `ulOptions`  
 Dieser Parameter ist reserviert und muss 0 (null) sein.  
  
 `samDesired`  
 Eine Maske, die Zugriffsrechte für den Schlüssel angibt.  
  
 `phkResult`  
 Ein Zeiger auf eine Variable, die ein Handle für den Schlüssel geöffnet oder erstellt empfängt, werden soll. Wenn der Schlüssel nicht eine der vordefinierten Registrierungsschlüssel ist, rufen Sie die `RegCloseKey` funktionieren, wenn Sie mit dem Handle abgeschlossen haben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert wird  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `RegOpenKeyTransacted` Funktion.  
  
##  <a name="rollback"></a>  Rollback  
 Anforderungen, die die Transaktion ein Rollback ausgeführt werden.  
  
```
inline BOOL Rollback();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `RollbackTransaction` Funktion.  
  
##  <a name="setfileattributes"></a>  SetFileAttributes  
 Legt die Attribute für eine Datei oder ein Verzeichnis als ein Transaktiver Vorgang fest.  
  
```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFileName`  
 Der Name der Datei oder des Verzeichnisses.  
  
 `dwAttributes`  
 Die Dateiattribute, die für die Datei festgelegt. Weitere Informationen finden Sie unter [SetFileAttributesTransacted](http://go.microsoft.com/fwlink/p/?linkid=158699).  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Ruft die `SetFileAttributesTransacted` Funktion.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)
