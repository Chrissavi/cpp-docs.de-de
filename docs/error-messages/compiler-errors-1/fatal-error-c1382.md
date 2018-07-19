---
title: Schwerwiegender Fehler C1382 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1382
dev_langs:
- C++
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07c6af1209faface96585224cbd08b4e35101478
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229254"
---
# <a name="fatal-error-c1382"></a>Schwerwiegender Fehler C1382
die PCH-Datei 'File' wurde neu erstellt, da "Obj" generiert wurde. Erstellen Sie dieses Objekt neu.  
  
 Bei Verwendung [/LTCG](../../build/reference/ltcg-link-time-code-generation.md), der Compiler hat eine PCH-Datei, die neuer als eine CIL OBJ-Datei ist, die auf diese Seite verweist. Die Informationen in der CIL-OBJ-Datei ist nicht aktuell. Erstellen Sie das Objekt neu.  
  
 C1382 kann auch auftreten, wenn beim Kompilieren mit **"/ Yc"**, jedoch mehreren Quellcodedateien an den Compiler übergeben.  Verwenden Sie zum Beheben nicht **"/ Yc"** bei mehreren Quellcodedateien an den Compiler übergeben.  Weitere Informationen finden Sie unter [/Yc (Datei der vorkompilierten Header erstellen)](../../build/reference/yc-create-precompiled-header-file.md).