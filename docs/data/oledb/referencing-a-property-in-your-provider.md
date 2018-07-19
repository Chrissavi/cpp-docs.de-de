---
title: Verweisen auf eine Eigenschaft im Anbieter | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 36965ac33fc0a563951c0c0dfdce60d9d0e4f55b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106543"
---
# <a name="referencing-a-property-in-your-provider"></a>Verweisen auf eine Eigenschaft im Anbieter
Suchen Sie die Eigenschaftsgruppe und die Eigenschafts-ID für die gewünschte Eigenschaft. Weitere Informationen finden Sie unter [OLE DB-Eigenschaften](https://msdn.microsoft.com/en-us/library/ms722734.aspx) in der *OLE DB Programmer's Reference*.  
  
 Im folgende Beispiel wird davon ausgegangen, dass Sie eine Eigenschaft aus dem Rowset abrufen möchten. Der Code für die Verwendung der Sitzung oder den Befehl ähnelt, aber eine andere Schnittstelle verwendet.  
  
 Erstellen einer [CDBPropSet](../../data/oledb/cdbpropset-class.md) -Objekt unter Verwendung der Eigenschaftengruppe als Parameter an den Konstruktor übergibt. Zum Beispiel:  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
```  
  
 Rufen Sie [AddProperty](../../data/oledb/cdbpropset-addproperty.md), übergeben sie die Eigenschaften-ID und einen Wert der Eigenschaft zugewiesen werden. Der Typ des Werts ist abhängig von der Eigenschaft, die Sie verwenden.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IRowsetChange, true);  

propset.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);  
```  
  
 Verwenden der `IRowset` Schnittstelle aufrufen **GetProperties**. Übergeben Sie die Eigenschaft als Parameter festgelegt. Hier ist der endgültige Code ein:  
  
```  
CAgentRowset<CMyProviderCommand>* pRowset = (CAgentRowset<CMyProviderCommand>*) pThis;  
  
CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
DBPROPIDSET set;  
set.AddPropertyID(DBPROP_BOOKMARKS);  

DBPROPSET* pPropSet = NULL;  
ULONG ulPropSet = 0;  

HRESULT hr;  
  
if (spRowsetProps)  
   hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  

if (pPropSet)  
{  
   CComVariant var = pPropSet->rgProperties[0].vValue;  
   CoTaskMemFree(pPropSet->rgProperties);  
   CoTaskMemFree(pPropSet);  
  
   if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
   {  
      ...  // Use property here  
   }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)