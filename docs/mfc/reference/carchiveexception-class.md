---
title: CArchiveException Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CArchiveException
- AFX/CArchiveException
- AFX/CArchiveException::CArchiveException
- AFX/CArchiveException::m_cause
- AFX/CArchiveException::m_strFileName
dev_langs:
- C++
helpviewer_keywords:
- CArchiveException [MFC], CArchiveException
- CArchiveException [MFC], m_cause
- CArchiveException [MFC], m_strFileName
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2763335a9165c1667160864a40200dcfd44b7f34
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953099"
---
# <a name="carchiveexception-class"></a>CArchiveException-Klasse
Stellt eine serialisierungsausnahmebedingung dar  
  
## <a name="syntax"></a>Syntax  
  
```  
class CArchiveException : public CException  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArchiveException::CArchiveException](#carchiveexception)|Erstellt ein `CArchiveException`-Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArchiveException::m_cause](#m_cause)|Gibt die Ursache der Ausnahme.|  
|[CArchiveException::m_strFileName](#m_strfilename)|Gibt den Namen der Datei für diese Ausnahmebedingung.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CArchiveException` Klasse enthält einen öffentlichen Datenmember, der die Ursache der Ausnahme angibt.  
  
 `CArchiveException` Objekte werden erstellt und ausgelöst in [CArchive](../../mfc/reference/carchive-class.md) Memberfunktionen. Sie können diese Objekte innerhalb des Bereichs der zugreifen eine **CATCH** Ausdruck. Der Ursachencode ist unabhängig von dem Betriebssystem. Weitere Informationen zur ausnahmeverarbeitung finden Sie unter [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CArchiveException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="carchiveexception"></a>  CArchiveException::CArchiveException  
 Erstellt eine `CArchiveException` Objekt, das Speichern des Werts *dazu führen, dass* im-Objekt.  
  
```  
CArchiveException(
    int cause = CArchiveException::none,  
    LPCTSTR lpszArchiveName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *Ursache*  
 Ein Aufzählungstyp-Variable, die die Ursache der Ausnahme angibt. Eine Liste von Enumeratoren, finden Sie unter der [M_cause](#m_cause) -Datenmember.  
  
 *lpszArchiveName*  
 Verweist auf eine Zeichenfolge mit dem Namen des dem `CArchive` Objekt, der die Ausnahme verursacht.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CArchiveException` -Objekt, auf dem Heap und wirft den Zettel selbst oder lassen Sie die globale Funktion [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) für Sie zu behandeln.  
  
 Verwenden Sie diesen Konstruktor nicht direkt auf; Rufen Sie stattdessen die globale Funktion `AfxThrowArchiveException`.  
  
##  <a name="m_cause"></a>  CArchiveException::m_cause  
 Gibt die Ursache der Ausnahme an.  
  
```  
int m_cause;  
```  
  
### <a name="remarks"></a>Hinweise  
 Datenmember ist eine öffentliche Variable des Typs **Int**. Die Werte werden definiert, durch eine `CArchiveException` Aufzählungstyp. Die Enumeratoren und ihre Bedeutungen lauten wie folgt:  
  
- **CArchiveException::none** kein Fehler aufgetreten ist.  
  
- **CArchiveException::genericException** nicht angegebener Fehler.  
  
- **CArchiveException::readOnly** hat versucht, die in einem für das Laden von geöffneten Archiv zu schreiben.  
  
- **CArchiveException::endOfFile** Dateiende wurde erreicht, beim Lesen eines Objekts.  
  
- **CArchiveException::writeOnly** hat versucht, das Lesen aus einem Archiv, das zum Speichern von geöffnet.  
  
- **CArchiveException::badIndex** Ungültiges Dateiformat.  
  
- **CArchiveException::badClass** hat versucht, ein Objekt in ein Objekt des falschen Typs zu lesen.  
  
- **CArchiveException::badSchema** versucht, ein Objekt mit einer anderen Version der Klasse zu lesen.  
  
    > [!NOTE]
    >  Diese `CArchiveException`-Ursachenenumeratoren unterscheiden sich von den `CFileException`-Ursachenenumeratoren.  
  
    > [!NOTE]
    > **CArchiveException::generic** ist veraltet. Verwendung **GenericException** stattdessen. Wenn **generische** in einer Anwendung verwendet und erstellt mit "/ CLR", werden Syntaxfehler, die nicht leicht entschlüsselt werden.  
  
##  <a name="m_strfilename"></a>  CArchiveException::m_strFileName  
 Gibt den Namen der Datei für diese Ausnahmebedingung.  
  
```  
CString m_strFileName;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CArchive-Klasse](../../mfc/reference/carchive-class.md)   
 [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)   
 [Ausnahmeverarbeitung](../../mfc/reference/exception-processing.md)

