---
title: Eine einfache Schleife parallel ausgeführten a. 1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98b2fbac6ce31d2dbc56a4ef6d9fe87c14d5ee16
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686125"
---
# <a name="a1---executing-a-simple-loop-in-parallel"></a>A.1   Parallele Ausführung einer einfachen Schleife
Im folgende Beispiel wird veranschaulicht, wie eine einfache Schleife mit parallelisiert werden die `parallel for` Richtlinie ([Abschnitt 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) auf Seite "16"). Die Schleifeniterationsvariable ist standardmäßig privat, daher ist es nicht notwendig, explizit in eine private-Klausel angeben.  
  
```  
#pragma omp parallel for  
    for (i=1; i<n; i++)  
        b[i] = (a[i] + a[i-1]) / 2.0;  
```