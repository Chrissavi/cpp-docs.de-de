---
title: 'NMAKE: Schwerwiegender Fehler U1100 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1100
dev_langs:
- C++
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d4ed57c980813c8539fbffed0e41a35048c0571
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319617"
---
# <a name="nmake-fatal-error-u1100"></a>NMAKE: Schwerwiegender Fehler U1100
das Makro 'Makroname' ist im Kontext des Batchregel "Regel" nicht zulässig  
  
 NMAKE generiert diesen Fehler, wenn der Befehlsblock einer Batchmodus Regel direkt oder indirekt ein Makro spezielle Datei verweist, nicht ist $<.  
  
 $< ist der einzige zulässige Makro für Batch-Modus-Regeln.