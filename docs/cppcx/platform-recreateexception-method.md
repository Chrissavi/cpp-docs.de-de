---
title: 'Platform:: recreateexception-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
dev_langs:
- C++
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0472d74be21048aeaf25ca92dbb5c1e98ca0ca90
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33087828"
---
# <a name="platformrecreateexception-method"></a>Platform::ReCreateException-Methode
Diese Methode ist nur für die interne Verwendung bestimmt und nicht für Benutzercode gedacht. Verwenden Sie stattdessen die Exception:: createexception-Methode.

## <a name="syntax"></a>Syntax

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>Parameter
`hr`

### <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert

Gibt eine neue Platform::Exception^ basierend auf dem angegebenen HRESULT zurück.

