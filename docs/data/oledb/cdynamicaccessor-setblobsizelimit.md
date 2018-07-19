---
title: 'CDynamicAccessor:: Setblobsizelimit | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
dev_langs:
- C++
helpviewer_keywords:
- SetBlobSizeLimit method
ms.assetid: fb8cb85d-f841-408e-a344-37895b10993f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8731857507fa096d500a31f31a7c31ef4f94cfc6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096079"
---
# <a name="cdynamicaccessorsetblobsizelimit"></a>CDynamicAccessor::SetBlobSizeLimit
Legt die maximale BLOB-Größe in Bytes fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      void SetBlobSizeLimit(DBLENGTH nBlobSize);  
```  
  
#### <a name="parameters"></a>Parameter  
 `nBlobSize`  
 Gibt das Größenlimit für BLOBs an.  
  
## <a name="remarks"></a>Hinweise  
 Legt die maximale BLOB-Größe in Bytes fest. Spaltendaten, die größer als dieser Wert werden als BLOB behandelt. Einige Anbieter bieten extrem große Größen für Spalten (z. B. 2 GB). Anstatt zu versuchen, Zuweisen von Arbeitsspeicher für eine Spalte dieser Größe, würde in der Regel versucht, diese Spalten als BLOBs zu binden. Auf diese Weise müssen Sie nicht sämtlichen Arbeitsspeicher zuzuweisen, aber Sie können weiterhin alle Daten ohne abgeschnitten zu lesen. Es gibt jedoch einige Fälle, in dem gewünschten erzwungen `CDynamicAccessor` große Spalten in ihren systemeigenen Datentypen zu binden. Zu diesem Zweck rufen `SetBlobSizeLimit` vor dem Aufruf **öffnen**.  
  
 Die Konstruktormethode [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) legt die maximale BLOB-Größe auf einen Standardwert von 8.000 Bytes.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)