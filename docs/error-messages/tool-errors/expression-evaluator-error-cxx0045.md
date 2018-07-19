---
title: Ausdrucksauswertungsfehler CXX0045 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0045
dev_langs:
- C++
helpviewer_keywords:
- CXX0045
- CAN0045
ms.assetid: 32181bc8-e79c-4ad7-a82f-47c62ec06d7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ac52b16c2c8551282b79ef6a7fda40e24acc6bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299733"
---
# <a name="expression-evaluator-error-cxx0045"></a>Ausdrucksauswertungsfehler CXX0045
keine Funktion  
  
 Eine Argumentliste wurde auf ein Symbol in der Anwendung bereitgestellt, die nicht den Namen einer Funktion ist.  
  
## <a name="example"></a>Beispiel  
  
```  
queue( alpha, beta )  
```  
  
 Wenn `queue` ist keine Funktion.  
  
 Dieser Fehler ist mit CAN0045 identisch.