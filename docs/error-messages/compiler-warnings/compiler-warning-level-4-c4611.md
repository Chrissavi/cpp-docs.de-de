---
title: Compilerwarnung (Stufe 4) C4611 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4611
dev_langs:
- C++
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5946c10b5e0e0e7e08f1ee37c77120896937adb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293152"
---
# <a name="compiler-warning-level-4-c4611"></a>Compilerwarnung (Stufe 1) C4600
Interaktion zwischen "Function" und die Zerstörung von C++ ist nicht portabel  
  
 Auf manchen Plattformen, Funktionen, die enthalten **catch** unterstützen möglicherweise keine C++-Objekt-Semantik der Zerstörung außerhalb des Bereichs.  
  
 Um unerwartetes Verhalten zu vermeiden, verwenden Sie **catch** in Funktionen, die Konstruktoren und Destruktoren besitzen.  
  
 Diese Warnung wird nur einmal ausgegeben; finden Sie unter [Pragma Warnung](../../preprocessor/warning.md).