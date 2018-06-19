---
title: once_flag-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::once_flag
dev_langs:
- C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8a8d28f19e32988bfa179642a87e880413bb0ff
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852337"
---
# <a name="onceflag-structure"></a>once_flag-Struktur

Stellt eine `struct` dar, die mit der Vorlagenfunktion [call_once](../standard-library/mutex-functions.md#call_once) verwendet wird, damit der Initialisierungscode auch bei mehreren Ausführungsthreads nur einmal aufgerufen wird.

## <a name="syntax"></a>Syntax

Struktur once_flag { constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag& operator=(const once_flag&); };

## <a name="remarks"></a>Hinweise

Die `once_flag` `struct` verfügt über nur einen Standardkonstruktor.

Objekte vom Typ `once_flag` können erstellt, aber nicht kopiert werden.

## <a name="requirements"></a>Anforderungen

**Header:** \<mutex>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
