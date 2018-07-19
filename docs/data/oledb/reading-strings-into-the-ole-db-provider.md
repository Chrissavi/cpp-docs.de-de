---
title: Einlesen von Zeichenfolgen in den OLE DB-Anbieter | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 073ddbea18e728ffb6777ff16c86bfa4695e05cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110167"
---
# <a name="reading-strings-into-the-ole-db-provider"></a>Einlesen von Zeichenfolgen in den OLE DB-Anbieter
Die `RMyProviderRowset::Execute` -Funktion öffnet eine Datei und liest Zeichenfolgen. Der Consumer übergibt den Dateinamen an dem Anbieter durch Aufrufen von [ICommandText:: SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx). Der Anbieter empfängt den Dateinamen und speichert ihn in die Membervariable `m_szCommandText`. `Execute` liest den Dateinamen aus `m_szCommandText`. Wenn der Dateiname ungültig ist oder die Datei nicht verfügbar ist, `Execute` gibt einen Fehler zurück. Andernfalls die Datei und ruft Eröffnung `fgets` Zeichenfolgen abgerufen. Für jede von Zeichenfolgen er liest, legen Sie `Execute` erstellt eine Instanz des Benutzerdatensatzes (`CAgentMan`) und platziert es in ein Array.  
  
 Wenn die Datei kann nicht geöffnet werden, `Execute` muss zurückgeben **DB_E_NOTABLE**. Wenn zurückgegeben **E_FAIL** stattdessen der Anbieter funktioniert nicht mit zahlreichen Consumern und OLE DB wird nicht erfolgreich [Konformitätstests](../../data/oledb/testing-your-provider.md).  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Die bearbeitete `Execute` Funktion sieht wie folgt aus:  
  
### <a name="code"></a>Code  
  
```cpp
/////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
class RMyProviderRowset : public CRowsetImpl< RMyProviderRowset, CAgentMan, CRMyProviderCommand>  
{  
public:  
    HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)  
    {  
        enum {  
            sizeOfBuffer = 256,  
            sizeOfFile = MAX_PATH  
        };  
        USES_CONVERSION;  
        FILE* pFile = NULL;  
        TCHAR szString[sizeOfBuffer];  
        TCHAR szFile[sizeOfFile];  
        size_t nLength;        errcodeerr;  
  
        ObjectLock lock(this);  
  
        // From a filename, passed in as a command text, scan the file  
        // placing data in the data array.  
        if (!m_szCommandText)  
        {  
            ATLTRACE("No filename specified");  
            return E_FAIL;  
        }  
  
        // Open the file  
        _tcscpy_s(szFile, sizeOfFile, m_szCommandText);  
        if (szFile[0] == _T('\0') ||   
            ((err = fopen_s(&pFile, &szFile[0], "r")) == 0))  
        {  
            ATLTRACE("Could not open file");  
            return DB_E_NOTABLE;  
        }  
  
        // Scan and parse the file.  
        // The file should contain two strings per record  
        LONG cFiles = 0;  
        while (fgets(szString, sizeOfBuffer, pFile) != NULL)  
        {  
            nLength = strnlen(szString, sizeOfBuffer);  
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF  
            CAgentMan am;  
            _tcscpy_s(am.szCommand, am.sizeOfCommand, szString);  
            _tcscpy_s(am.szCommand2, am.sizeOfCommand2, szString);  
  
            if (fgets(szString, sizeOfBuffer, pFile) != NULL)  
            {  
                nLength = strnlen(szString, sizeOfBuffer);  
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF  
                _tcscpy_s(am.szText, am.sizeOfText, szString);  
                _tcscpy_s(am.szText2, am.sizeOfText2, szString);  
            }  
  
            am.dwBookmark = ++cFiles;  
            if (!m_rgRowData.Add(am))  
            {  
                ATLTRACE("Couldn't add data to array");  
                fclose(pFile);  
                return E_FAIL;  
            }  
        }  
  
        if (pcRowsAffected != NULL)  
            *pcRowsAffected = cFiles;  
        return S_OK;  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren des einfachen schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md)