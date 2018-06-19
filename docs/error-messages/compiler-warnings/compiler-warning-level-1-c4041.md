---
title: Compilerwarnung (Stufe 1) C4041 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4041
dev_langs:
- C++
helpviewer_keywords:
- C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfd8c933522e523329c41ebe666a5a7e3c198cb0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286096"
---
# <a name="compiler-warning-level-1-c4041"></a>Compilerwarnung (Stufe 1) C4041
Compilerlimit : Browserausgabe wird abgebrochen  
  
 Die Browserinformationen haben das Compilerlimit überschritten.  
  
 Diese Warnung kann durch die Kompilierung mit [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) (Browserinformationen einschließlich lokaler Variablen) verursacht werden.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Kompilieren Sie mit /Fr (Browserinformationen ohne lokale Variablen).  
  
2.  Deaktivieren Sie die Browserausgabe (Kompilieren ohne/fr oder/FR).