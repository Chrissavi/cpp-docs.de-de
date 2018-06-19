---
title: Schwerwiegender Fehler C1026 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1026
dev_langs:
- C++
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24c034d45b7f8b222471094f4580902ae1b8dc66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198104"
---
# <a name="fatal-error-c1026"></a>Schwerwiegender Fehler C1026
Stapelüberlauf im Parser, Programm zu komplex  
  
 Der Speicherplatz, der zum Analysieren der Anwendung benötigt verursacht einen Stapelüberlauf des Compilers.  
  
 Verringern Sie die Komplexität der Ausdrücke, nach:  
  
-   Verringern die Schachtelung im `for` und `switch` Anweisungen. Fügen Sie mehr tief geschachtelte Anweisungen in separate Funktionen.  
  
-   Aufteilen von langen Ausdrücken, die durch Trennzeichen Operatoren oder Funktionsaufrufe einschließen.