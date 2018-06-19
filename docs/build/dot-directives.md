---
title: Dot-Richtlinien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dot directives
- dot directives in NMAKE
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29eeedbdc2eaccb753751082a38736fa239837b2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367663"
---
# <a name="dot-directives"></a>Punktanweisungen
Punktdirektiven Sie außerhalb eines Blocks von Beschreibung, am Anfang einer Zeile. Punktdirektiven beginnen mit einem Punkt (. ), gefolgt von einem Doppelpunkt (:). Registerkarten "und" Leerzeichen sind zulässig. Punkt-Direktivennamen sind Groß-/Kleinschreibung beachtet und Großbuchstaben.  
  
|Direktive|Zweck|  
|---------------|-------------|  
|**. IGNORIEREN:**|Ignoriert Exitcodes ungleich NULL zurückgegeben, die von Befehlen, aus dem sie bis zum Ende des Makefiles angegeben ist. Standardmäßig wird NMAKE angehalten, wenn ein Befehl einen Exitcode ungleich NULL zurückgibt. Verwenden Sie zum Wiederherstellen der fehlerüberprüfung **! CMDSWITCHES**. Wenn den Exitcode für einen einzelnen Befehl ignorieren möchten, verwenden Sie den Bindestrich (-)-Modifizierer. Um Exitcodes für eine gesamte Datei ignorieren möchten, verwenden Sie / I.|  
|**. PRECIOUS:** *Ziele*|Behält *Ziele* auf dem Datenträger, wenn die Befehle, deren Aktualisierung angehalten werden; hat keine Auswirkung, wenn ein Befehl einen Interrupt behandelt, durch Löschen der Datei. Trennen Sie die Zielnamen mit Leerzeichen oder Tabstopps. Standardmäßig löscht NMAKE ein Ziel aus, wenn ein Build, indem Sie STRG + C oder STRG + UNTBR unterbrochen wird. Jede Verwendung von **. WERTVOLLE** gilt für das gesamte Makefile; mehrere Spezifikationen sind kumulativ.|  
|**. AUTOMATISCHE:**|Unterdrückt die Anzeige von ausgeführten Befehle, aus dem sie bis zum Ende des Makefiles angegeben ist. Standardmäßig zeigt NMAKE die Befehlen verwenden, die ihn aufruft. Verwenden Sie zum Wiederherstellen der Echo **! CMDSWITCHES**. Verwenden Sie zur Eingabe eines einzelnen Befehls zu unterdrücken, die **@** Modifizierer. Um die Eingabe für eine gesamte Datei zu unterdrücken, verwenden Sie/S.|  
|**. SUFFIXE:** `list`|Führt die Erweiterungen für den Abgleich Rückschlussregel; die folgenden Erweiterungen enthalten vordefinierte: .exe .obj asm .c .cpp .cxx BAS .cbl zurückgegeben .pas Res RC .f .f90|  
  
 So ändern Sie die **. SUFFIXE** -Liste zu ändern oder um eine neue Liste angeben, löschen Sie die Liste, und geben Sie eine neue Einstellung. Um die Liste zu löschen, müssen Geben Sie keine Erweiterungen hinter dem Doppelpunkt stehenden an:  
  
```  
.SUFFIXES :  
```  
  
 Geben Sie zum Hinzufügen von zusätzlichen Suffixe an das Ende der Liste  
  
```  
.SUFFIXES : suffixlist  
```  
  
 wobei *Suffixlist* ist eine Liste der Suffixe durch eine oder mehrere Leerzeichen bzw. Tabstopps getrennt. Um die aktuelle Einstellung der finden Sie unter **. SUFFIXE**, anzuzeigen NMAKE mit  
  
## <a name="see-also"></a>Siehe auch  
 [NMAKE-Referenz](../build/nmake-reference.md)