---
title: Compilerfehler C2433 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2433
dev_langs:
- C++
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8445e35b929dc3fa2d9d6507f0b6469df26130db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197844"
---
# <a name="compiler-error-c2433"></a>Compilerfehler C2433
'Bezeichner': 'Modifizierer' auf Datendeklarationen nicht zulässig.  
  
 Die `friend`, `virtual`, und `inline` Modifizierer können nicht für Datendeklarationen verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2433 generiert.  
  
```  
// C2433.cpp  
class C{};  
  
int main() {  
   inline C c;   // C2433  
}  
```