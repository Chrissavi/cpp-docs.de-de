---
title: Schwerwiegender Fehler C1076 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1076
dev_langs:
- C++
helpviewer_keywords:
- C1076
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c02cc55280202b9ce576dc1e771b3428837209c8
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42541630"
---
# <a name="fatal-error-c1076"></a>Schwerwiegender Fehler C1076
Compilerlimit: Interne Heapgrenze erreicht; Verwenden Sie /Zm, um eine höhere Grenze anzugeben  
  
 Dieser Fehler kann durch zu viele Symbole oder Vorlageninstanziierungen verursacht werden.  
  
 So beheben Sie diesen Fehler:  
  
1.  Verwenden der [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) Arbeitsspeicherlimit des Compilers auf den im angegebenen Wert festlegen die [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) Fehlermeldung angezeigt. Weitere Informationen, die zum Festlegen dieses Werts in Visual Studio enthält, finden Sie im Abschnitt "Hinweise" in [/Zm (Geben Sie vorkompilierte Header Begrenzung der Speicherzuweisung)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).  
  
2.  Verwenden Sie in einem 64-Bit-Betriebssystem anstelle von gehosteten 32-Bit-Compilern gehostete 64-Bit-Compiler. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren ein 64-Bit-Visual C++-Toolsets in der Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).  
  
3.  Löschen Sie überflüssige Includedateien.  
  
4.  Entfernen Sie unnötige globale Variablen, indem Sie beispielsweise Speicher dynamisch belegen, anstatt ein umfangreiches Array zu deklarieren.  
  
5.  Entfernen Sie nicht benötigte Deklarationen.  
  
6.  Teilen Sie umfangreichere Funktionen in kleinere Funktionen auf.  
  
7.  Teilen Sie umfangreichere Klassen in kleinere Klassen auf.  
  
8.  Teilen Sie die aktuelle Datei in kleinere Dateien auf.  
  
 Wenn C1076 tritt auf, unmittelbar nachdem der Build gestartet wurde, der für Wert angegebene **/Zm** ist wahrscheinlich für das Programm zu hoch. Reduzieren der **/Zm** Wert.