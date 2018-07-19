---
title: Compilerfehler C3838 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3838
dev_langs:
- C++
helpviewer_keywords:
- C3838
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dea27fde00773ccdaf7acb2dff135cd3cf894da4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267325"
---
# <a name="compiler-error-c3838"></a>Compilerfehler C3838
kann nicht explizit von 'Typ' erben.  
  
 Das angegebene `type` kann nicht als Basisklasse in einer Klasse dienen.  
  
## <a name="example"></a>Beispiel
 Im folgende Beispiel wird C3838 generiert:  
  
```  
// C3838a.cpp  
// compile with: /clr /c  
public ref class B : public System::Enum {};   // C3838  
```  
