---
title: Compilerwarnung (Stufe 2) C4653 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4653
dev_langs:
- C++
helpviewer_keywords:
- C4653
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c312b7530fa11bb734dc99a872b36e926890f658
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290995"
---
# <a name="compiler-warning-level-2-c4653"></a>Compilerwarnung (Stufe 2) C4653
die Compileroption 'Option' inkonsistent mit der vorkompilierten Headerdatei; aktuelle Befehlszeilenoption wird ignoriert  
  
 Eine Option angegeben wird, mit der vorkompilierte Header (["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md))-Option nicht konsistent mit den Optionen, die beim Erstellen des vorkompilierten Headers angegeben wurde. Dieser Kompilierung verwendet die Option beim Erstellen des vorkompilierten Headers angegeben.  
  
 Diese Warnung kann auftreten, wenn ein anderer Wert für die Option Pack Strukturen ([/Zp](../../build/reference/zp-struct-member-alignment.md)) während der Kompilierung des vorkompilierten Headers angegeben wurde.