---
title: CGopherConnection Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherConnection
- AFXINET/CGopherConnection
- AFXINET/CGopherConnection::CGopherConnection
- AFXINET/CGopherConnection::CreateLocator
- AFXINET/CGopherConnection::GetAttribute
- AFXINET/CGopherConnection::OpenFile
dev_langs:
- C++
helpviewer_keywords:
- CGopherConnection [MFC], CGopherConnection
- CGopherConnection [MFC], CreateLocator
- CGopherConnection [MFC], GetAttribute
- CGopherConnection [MFC], OpenFile
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49fe725c700a46e59625289de7ca5edf4b4d25b2
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955686"
---
# <a name="cgopherconnection-class"></a>CGopherConnection-Klasse
Verwaltet die Verbindung mit einem Gopherinternetserver.  
  
> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und ihre Member sind veraltet, da sie nicht auf Windows XP-Plattform funktionieren, jedoch wird auf älteren Plattformen funktionieren weiterhin.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherConnection::CGopherConnection](#cgopherconnection)|Erstellt ein `CGopherConnection`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherConnection::CreateLocator](#createlocator)|Erstellt eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt, um Dateien auf einem Gopherserver zu suchen.|  
|[CGopherConnection::GetAttribute](#getattribute)|Ruft Informationen über das Gopher-Objekt ab.|  
|[CGopherConnection::OpenFile](#openfile)|Öffnet eine Gopherdatei.|  
  
## <a name="remarks"></a>Hinweise  
 Gopher-Dienst ist einer der drei Internetdienste, die von der MFC-WinInet-Klassen erkannt.  
  
 Die Klasse `CGopherConnection` enthält einen Konstruktor und drei zusätzliche Memberfunktionen, die den Gopher-Dienst zu verwalten: [OpenFile](#openfile), [CreateLocator](#createlocator), und [GetAttribute](#getattribute).  
  
 Die Kommunikation mit einem gopherinternetserver müssen zuerst erstellen Sie eine Instanz des [CInternetSession](../../mfc/reference/cinternetsession-class.md), und rufen dann [CInternetSession:: GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), erstellt die `CGopherConnection` -Objekt und gibt einen Zeiger darauf zurück. Erstellen Sie nie eine `CGopherConnection` -Objekts direkt.  
  
 Erfahren Sie mehr darüber, wie `CGopherConnection` funktioniert mit anderen Internet MFC-Klassen finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md). Weitere Informationen zum Verwenden von der anderen beiden Internetdienste unterstützt, FTP und HTTP-finden Sie unter den Klassen [CHttpConnection](../../mfc/reference/chttpconnection-class.md) und [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CGopherConnection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cgopherconnection"></a>  CGopherConnection::CGopherConnection  
 Diese Memberfunktion wird aufgerufen, um das Erstellen einer `CGopherConnection` Objekt.  
  
```  
CGopherConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CGopherConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 0,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>Parameter  
 *pSession*  
 Ein Zeiger auf den zugehörigen [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt.  
  
 *hConnected*  
 Das Windows-handle von der aktuellen Internet-Sitzung.  
  
 *pstrServer*  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des FTP-Server enthält.  
  
 *dwContext*  
 Der Kontextbezeichner für den Vorgang. *DwContext* identifiziert den Vorgang vom zurückgegebenen Statusinformationen [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Die Standardeinstellung ist auf 1 festgelegt. Allerdings können Sie eine bestimmten Kontext-ID für den Vorgang explizit zuweisen. Das Objekt und jede Arbeit, die es ausführt, werden dieser Kontext-ID zugeordnet werden.  
  
 *pstrUserName*  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen des Benutzers anmelden angibt. Wenn **NULL**, der Standardwert ist anonymous.  
  
 *pstrPassword*  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, das Kennwort zur Anmeldung verwenden. Wenn beide *PstrPassword* und *PstrUserName* sind **NULL**, das anonymen Standard-Kennwort ist die e-Mail-Namen des Benutzers. Wenn *PstrPassword* ist **NULL** (oder eine leere Zeichenfolge), aber *PstrUserName* nicht **NULL**, ein leeres Kennwort verwendet. Die folgende Tabelle beschreibt das Verhalten für die vier möglichen Einstellungen der *PstrUserName* und *PstrPassword*:  
  
|*pstrUserName*|*pstrPassword*|FTP-Server gesendeten Benutzernamen|Kennwort mit FTP-Server gesendet wird.|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL** oder ""|**NULL** oder ""|"Anonym"|Die e-Mail-Namen des Benutzers|  
|Nicht- **NULL** Zeichenfolge|**NULL** oder ""|*pstrUserName*|" "|  
|**NULL** nicht- **NULL** Zeichenfolge|**FEHLER**|**FEHLER**||  
|Nicht- **NULL** Zeichenfolge|Nicht- **NULL** Zeichenfolge|*pstrUserName*|*pstrPassword*|  
  
 *%nPort*  
 Eine Zahl, die TCP/IP-Port für die Verwendung auf dem Server identifiziert.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CGopherConnection` direkt. Rufen Sie stattdessen [CInternetSession:: GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), erstellt ein `CGopherConnection` -Objekt und gibt einen Zeiger darauf zurück.  
  
##  <a name="createlocator"></a>  CGopherConnection:: CreateLocator  
 Rufen Sie diese Memberfunktion zum Erstellen eines Gopher-Locators, um zu suchen oder eine Datei auf einem Gopherserver zu identifizieren.  
  
```  
CGopherLocator CreateLocator(
    LPCTSTR pstrDisplayString,  
    LPCTSTR pstrSelectorString,  
    DWORD dwGopherType);  
  
static CGopherLocator CreateLocator(LPCTSTR pstrLocator);

 
static CGopherLocator CreateLocator(
    LPCTSTR pstrServerName,  
    LPCTSTR pstrDisplayString,  
    LPCTSTR pstrSelectorString,  
    DWORD dwGopherType,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrDisplayString*  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Gopher-Dokuments oder des Verzeichnisses abgerufen werden sollen. Wenn die *PstrDisplayString* Parameter ist **NULL**, das Standardverzeichnis für das Gopher-Server zurückgegeben.  
  
 *pstrSelectorString*  
 Ein Zeiger auf die Auswahlzeiger-Zeichenfolge, die an den Gopherserver gesendet werden, um ein Element abgerufen werden. *PstrSelectorString* kann **NULL**.  
  
 *dwGopherType*  
 Dies gibt an, ob *PstrSelectorString* bezieht sich auf ein Verzeichnis oder das Dokument, und gibt an, ob die Anforderung Gopher oder Gopher erfolgt. Finden Sie die Attribute für die Struktur [GOPHER_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa384215) im Windows SDK.  
  
 *pstrLocator*  
 Ein Zeiger auf eine Zeichenfolge, die zu öffnende Datei identifiziert. Im Allgemeinen wird diese Zeichenfolge zurückgegeben, Aufrufen von [CGopherFileFind:: GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator).  
  
 *pstrServerName*  
 Ein Zeiger auf eine Zeichenfolge, die den Gopher-Servernamen enthält.  
  
 *%nPort*  
 Die Anzahl den Internet-Port für diese Verbindung identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die statische Member-Funktion erfordert Sie einen Server angeben, während die Version nicht statische den Servernamen aus dem Verbindungsobjekt verwendet.  
  
 Zum Abrufen von Informationen aus einem Gopherserver muss eine Anwendung zunächst einen Gopher-Locator abrufen. Die Anwendung muss dann des Locators als nicht transparenter Token behandeln (bedeutet, dass die Anwendung kann des Locators verwenden, aber nicht direkt bearbeiten oder vergleichen Sie sie). In der Regel wird die Anwendung den Locator für Aufrufe verwendet die [CGopherFileFind:: FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) Memberfunktion versucht, eine bestimmte Information abzurufen.  
  
##  <a name="getattribute"></a>  CGopherConnection::GetAttribute  
 Rufen Sie diese Memberfunktion, um spezifische Informationen über ein Element aus dem Gopherserver abzurufen.  
  
```  
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,  
    CString& strResult,);
```  
  
### <a name="parameters"></a>Parameter  
 *refLocator*  
 Ein Verweis auf eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.  
  
 *strRequestedAttributes*  
 Eine durch Leerzeichen getrennte Zeichenfolge die Namen der angeforderten Attribute angeben.  
  
 *"strResult"*  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) , empfängt den URL-Typ.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
##  <a name="openfile"></a>  CGopherConnection:: OpenFile  
 Rufen Sie diese Memberfunktion, um eine Datei auf einem Gopherserver zu öffnen.  
  
```  
CGopherFile* OpenFile(
    CGopherLocator& refLocator,  
    DWORD dwFlags = 0,  
    LPCTSTR pstrView = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 *refLocator*  
 Ein Verweis auf eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.  
  
 *dwFlags*  
 Eine beliebige Kombination von INTERNET_FLAG_ * kennzeichnet. Finden Sie unter [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) für Weitere Informationen zu INTERNET_FLAG_\* Flags.  
  
 *pstrView*  
 Ein Zeiger auf eine Dateiansicht Zeichenfolge. Wenn mehrere Ansichten der Datei auf dem Server vorhanden sind, gibt dieser Parameter die Dateiansicht zu öffnen. Wenn *PstrView* ist **NULL**, die Standardansicht für die Datei wird verwendet.  
  
 *dwContext*  
 Die Kontext-ID für die Datei geöffnet wird. Finden Sie unter **"Hinweise"** Weitere Informationen zu *DwContext*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CGopherFile](../../mfc/reference/cgopherfile-class.md) zu öffnende Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie die *DwContext* Standard, um den Kontextbezeichner auf einen Wert Ihrer Wahl festzulegen. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordneten der `CGopherConnection` Objekt erstellt wird, dessen [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Vorgangs bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen über den Kontextbezeichner.  
  
## <a name="see-also"></a>Siehe auch  
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFtpConnection-Klasse](../../mfc/reference/cftpconnection-class.md)   
 [CHttpConnection-Klasse](../../mfc/reference/chttpconnection-class.md)   
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [CGopherLocator-Klasse](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession-Klasse](../../mfc/reference/cinternetsession-class.md)
