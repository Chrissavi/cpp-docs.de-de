---
title: _SCL_SECURE_NO_WARNINGS | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
dev_langs:
- C++
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec02ce5aab3d8a7f95ec9020fe3e2a00c1f5bef7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854352"
---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS

Aufrufen einer potenziell unsicheren Methoden in der C++-Standardbibliothek führt zu [Compilerwarnung (Stufe 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Um diese Warnung zu deaktivieren, definieren Sie das Makro **_SCL_SECURE_NO_WARNINGS** in Ihrem Code:

```cpp
#define _SCL_SECURE_NO_WARNINGS
```

Bei Verwendung von vorkompilierten Headern fügen Sie diese Direktive in der vorkompilierten Headerdatei, bevor Sie alle C-Laufzeitbibliothek oder standard bibliotheksheader einfügen. Wenn Sie fügen Sie ihn in einer einzelnen Quellcodedatei, bevor Sie die vorkompilierte Headerdatei einschließen, wird es vom Compiler ignoriert.

## <a name="remarks"></a>Hinweise

Weitere Methoden zum Deaktivieren der Warnung C4996 sind u.a.:

- Mithilfe der Compileroption [/D (Präprozessordefinitionen)](../build/reference/d-preprocessor-definitions.md):

   > CL /D_SCL_SECURE_NO_WARNINGS [anderen Compileroptionen] myfile.cpp

- Mithilfe der Compileroption [/w](../build/reference/compiler-option-warning-level.md):

   > CL-/wd4996 [anderen Compileroptionen] myfile.cpp

- Mithilfe der Anweisung [#pragma warning](../preprocessor/warning.md):

   ```cpp
   #pragma warning(disable:4996)
   ```

Sie können die Stufe der Warnung C4996 mit der Compileroption **/w\<l >\<n >** auch manuell ändern. Um beispielsweise die Warnung C4996 auf Stufe 4 festzulegen:

> CL-/w44996 [anderen Compileroptionen] myfile.cpp

Weitere Informationen finden Sie unter [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (Warnstufe)](../build/reference/compiler-option-warning-level.md).

## <a name="see-also"></a>Siehe auch

[Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
