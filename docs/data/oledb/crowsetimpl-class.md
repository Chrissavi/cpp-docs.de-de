---
title: CRowsetImpl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl
- ATL.CRowsetImpl
- ATL::CRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- CRowsetImpl class
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eece641adacd6ce918929366c4fc6dc78105e71a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098718"
---
# <a name="crowsetimpl-class"></a>CRowsetImpl-Klasse
Stellt eine Standardimplementierung der OLE DB-Rowset ohne mehrfache Vererbung von vielen Implementierung Schnittstellen bereit.  
  
## <a name="syntax"></a>Syntax

```cpp
template <  
   class T,  
   class Storage,  
   class CreatorClass,  
   class ArrayType = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class RowsetInterface = IRowsetImpl <T, IRowset>   
>  
class CRowsetImpl :    
   public CComObjectRootEx<CreatorClass::_ThreadModel>,   
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>,   
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Benutzer von abgeleitete Klasse `CRowsetImpl`.  
  
 `Storage`  
 Die Benutzerdatensatz-Klasse.  
  
 `CreatorClass`  
 Die Klasse, die Eigenschaften für das Rowset enthält; in der Regel der Befehl.  
  
 `ArrayType`  
 Die Klasse, die als Speicher für das Rowset Daten fungieren sollen. Dieser Parameter ist standardmäßig `CAtlArray`, aber sie können jede Klasse, die die erforderliche Funktionen unterstützt werden.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[NameFromDBID](../../data/oledb/crowsetimpl-namefromdbid.md)|Extrahiert eine Zeichenfolge aus einem **DBID** und kopiert ihn auf die `bstr` übergeben.|  
|[SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)|Überprüft, und speichert die **DBID**s in den beiden Zeichenfolgen ([M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).|  
  
### <a name="overridable-methods"></a>Überschreibbaren Methoden  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/crowsetimpl-getcolumninfo.md)|Ruft die Spalteninformationen für einen bestimmten Client-Anforderung ab.|  
|[GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md)|Überprüft, wenn eine oder beide Parameter Zeichenfolgenwerte enthält, und wenn dies der Fall ist, kopiert die Zeichenfolgenwerte in der Datenmember [M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
|[ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md)|Überprüfen, ob eine oder beide Ziele überprüft **DBID**s Zeichenfolgenwerte enthalten, und wenn dies der Fall ist, kopiert Sie sie in seinen Datenmembern [M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)|Wird standardmäßig ein `CAtlArray` , die vom Benutzer Datensatz Vorlagenargument zu templatizes `CRowsetImpl`. Ein anderes Array-Klasse von Type verwendet werden kann, durch Ändern der `ArrayType` Vorlagenargument für `CRowsetImpl`.|  
|[m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)|Enthält der erste Befehl das Rowset an.|  
|[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)|Enthält die Rowset-ausgangsindex an.|  
  
## <a name="remarks"></a>Hinweise  
 `CRowsetImpl` enthält die Außerkraftsetzungen in Form von statischen werden. Die Methoden steuern die Art und Weise, in der ein angegebenes Rowset Befehlstext überprüft wird. Eigene erstellen `CRowsetImpl`-Formatklasse, indem Sie die Verfügbarkeit Ihrer Implementierung Schnittstellen mehrere vererbt. Die einzige Methode, die für die Sie bereitstellen müssen, Implementierung **Execute**. Je nach Art des Schemarowsets Sie erstellen, die Ersteller Methoden erwarten, dass andere Signaturen für **Execute**. Angenommen, Sie verwenden eine `CRowsetImpl`-abgeleitete Klasse, um ein Schemarowset implementieren die **Execute** Methode wird die folgende Signatur aufweisen:  
  
 `HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`  
  
 Wenn Sie erstellen eine `CRowsetImpl`-abgeleitete Klasse zum Implementieren eines Befehls oder des Sitzungsstatus-Rowset der **Execute** Methode wird die folgende Signatur aufweisen:  
  
 `HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`  
  
 Zum Implementieren der `CRowsetImpl`-abgeleitete **Execute** Methoden, müssen Sie Ihre internen Datenpuffer Auffüllen ([M_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“