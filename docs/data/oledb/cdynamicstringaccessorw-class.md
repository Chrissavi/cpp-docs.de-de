---
title: CDynamicStringAccessorW-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorW
helpviewer_keywords:
- CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
ms.openlocfilehash: 20ea4a2d795108e00c4b11c3abea6cf7b9953ca7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025149"
---
# <a name="cdynamicstringaccessorw-class"></a>CDynamicStringAccessorW-Klasse

Können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnisse über das Datenbankschema (zugrunde liegende Struktur) verfügen.

## <a name="syntax"></a>Syntax

```cpp
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;
```

## <a name="remarks"></a>Hinweise

Beide anfordern, dass der Anbieter alle Daten aus dem Datenspeicher Daten, die Zeichenfolge abruft, aber `CDynamicStringAccessor` Anforderungen von Unicode-Zeichenfolgendaten.

`CDynamicStringAccessorW` erbt `GetString` und `SetString` aus `CDynamicStringAccessor`. Bei Verwendung dieser Methoden in einer `CDynamicStringAccessorW` Objekt `BaseType` ist **WCHAR**.

## <a name="requirements"></a>Anforderungen

**Header**: atldbcli.h

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor-Klasse](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessor-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
